# G-buffer TexVerse · 完整示例资产

从 [YiboZhang2001/G-buffer-TexVerse](https://huggingface.co/datasets/YiboZhang2001/G-buffer-TexVerse)
取出的**一个完整 asset**，canonical 与 sphere 两个 split 都有，未做任何裁剪。

- **asset id**：`0000ecca9a234cae994be239f6fec552_1024`（README 里用的同名示例资产）
- **来源桶**：`canonical/bsdf/00.zip` → `sphere/bsdf/00.zip`（id 前两位 hex = `00`）
- **下载体积**：canonical 2.01 MB + sphere 13.92 MB（均为单个 asset 的内层 zip）
- **解包后**：409 个文件，19 MB
- **许可**：CC0 1.0

## 目录结构

```
canonical/0000ecca9a234cae994be239f6fec552_1024/0000ecca9a234cae994be239f6fec552_1024/
├── albedo/000..005.webp              6   反照率
├── bump_normal_camera/000..005.webp  6   法向（相机空间）
├── bump_normal_world/000..005.webp   6   法向（世界空间）
├── position/000..005.webp            6   规范空间坐标
├── roughness_metallic/000..005.webp  6   粗糙度/金属度（该资产提供）
├── render_0/000..005.webp            6   HDRI 728 打光
├── render_1/000..005.webp            6   HDRI 130 打光
├── render_2/000..005.webp            6   HDRI 559 打光
├── pose/000..005.npy                 6   相机外参 3×4
├── render_ref_0/000..003.webp + env_id.txt   4   训练参考图（HDRI 728）
├── render_ref_1/000..003.webp + env_id.txt   4   （HDRI 130）
├── render_ref_2/000..003.webp + env_id.txt   4   （HDRI 559）
├── render_ref_0_poses/000..003.npy   4
├── render_ref_1_poses/000..003.npy   4
├── render_ref_2_poses/000..003.npy   4
├── env_indices.txt                   [728, 130, 559]
└── intrinsics.npy                    3×2
                                共 83 个文件

sphere/0000ecca9a234cae994be239f6fec552_1024/0000ecca9a234cae994be239f6fec552_1024/
├── albedo/000..035.webp              36
├── bump_normal_camera/               36
├── bump_normal_world/                36
├── position/                         36
├── roughness_metallic/               36
├── render_0/  render_1/  render_2/   36 × 3
├── pose/000..035.npy                 36
├── env_indices.txt                   [728, 130, 559]
└── intrinsics.npy                    3×2
                                共 326 个文件（无 render_ref）
```

## 实测字段值

| 项 | 值 |
|---|---|
| 图像尺寸 / 格式 | 2048×2048，RGBA（alpha = 可见前景 mask） |
| `env_indices.txt` | `[728, 130, 559]` |
| `render_ref_i/env_id.txt` | 728 / 130 / 559，与 env_indices 逐项一致 |
| `intrinsics.npy` | `[[3200, 3200], [1024, 1024], [2048, 2048]]`，即 `[[fx, fy], [cx, cy], [W, H]]`，水平 FOV ≈ 35.5° |
| `pose/000.npy`（canonical） | 3×4，`[[1,0,0,0],[0,0,-1,-1.55],[0,1,0,0]]` |
| canonical 视角 | 000–003 侧面（方位 0/90/180/270，仰角 0）、004 顶视、005 底视 |
| sphere 视角 | 36 = 12 方位（每 30°）× 3 仰角（−40°/−20°/+30°） |

## 文件说明

| 文件 | 内容 |
|---|---|
| `gallery.html` | 本地浏览器，切换 split / 通道，直接看全部 409 张图（不联网） |
| `preview_canonical.png` | 8 通道 × 6 视角联系表 |
| `preview_canonical_ref.png` | 3 组 × 4 张训练参考图 |
| `preview_sphere.png` | sphere 的 albedo 与 render_0 各 36 视角 6×6 网格 |

## 复用方式

想拿别的 asset，替换 id 即可，外层桶按 id 前两位 hex 定位：

```python
from huggingface_hub import hf_hub_download
import zipfile, io

AID = "0000ecca9a234cae994be239f6fec552_1024"
bucket = AID[:2]

p = hf_hub_download(
    repo_id="YiboZhang2001/G-buffer-TexVerse",
    filename=f"canonical/bsdf/{bucket}.zip",
    repo_type="dataset",
)
z = zipfile.ZipFile(p)                      # 外层桶 16 GB，只解单条会慢
zipfile.ZipFile(io.BytesIO(z.read(AID + ".zip"))).extractall("./out")
```

只取单个 asset 时不必下整个 16 GB 桶——用 HTTP Range 远程读 zip 目录即可：

```python
from remotezip import RemoteZip
z = RemoteZip(f"https://huggingface.co/datasets/YiboZhang2001/G-buffer-TexVerse"
              f"/resolve/main/canonical/bsdf/{bucket}.zip")
zipfile.ZipFile(io.BytesIO(z.read(AID + ".zip"))).extractall("./out")
```

## 注意

发布的 351,847 个 asset 是**筛选后的 BSDF 池**。UltraTex 训练实际只用其中 268,365 个
（再经 albedo 熵筛选 + AI 内容移除 `meshy`/`tripo`/`createdwithai` 两道过滤），
这一步的产物没有单独发布，要复现训练得自己再筛一遍。
