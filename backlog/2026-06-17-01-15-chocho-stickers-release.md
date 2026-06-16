- **实现功能**：
  - 支持表情包专属图片处理逻辑：新增 `--sticker` 参数，限制最大边为 512px，采用 Lanczos 滤镜缩放以保持锐度。
  - 发布了啾啾的微信表情包文章，内含 16 张表情包贴纸的展示，并提供相关的生成技巧。
  - 在微信表情包平台完成了表情包上架，提供了上架的详情页面链接。

- **主要修改**：
  - 修改 [src/process_images.py](file:///Users/sipan/workspace/_working/jiujiu-miemie-gallery/src/process_images.py)，增加了 `--sticker` 参数及相关的 Lanczos 缩放和限宽逻辑。
  - 修改 [AGENTS.md](file:///Users/sipan/workspace/_working/jiujiu-miemie-gallery/AGENTS.md)，更新了命令及 Blog 协作工作流。
  - 修改 [src/build.py](file:///Users/sipan/workspace/_working/jiujiu-miemie-gallery/src/build.py)，引入 `parse_inline` 辅助函数以提供标准 Markdown 链接 `[text](url)` 的渲染解析支持。
  - 新增文章 [source/2026-06-17-01-10_chocho-stickers.md](file:///Users/sipan/workspace/_working/jiujiu-miemie-gallery/source/2026-06-17-01-10_chocho-stickers.md)。
  - 对 `inbox/` 目录下的 16 张 PNG 表情包原图进行重命名，应用新处理流程生成 16 张 512px 规格的 JPEG 图片输出至 `gallery/`。

- **验证结论**：
  - 处理后的表情包图片分辨率被成功限制在 512px 内且保留了锐度，并已成功嵌入版权 EXIF。
