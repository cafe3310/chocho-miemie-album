- **实现功能**：
  - 新写了咩咩 2018 与 2019 年的照片集文章《咩咩，2018与2019的日常》，展示了咩咩年轻时的 12 张珍贵日常照片。
  - 在文章末尾增加了维基链接，分别链接到《咩咩，2018》（初次介绍）以及《用于练习图片生成的猫咪角色设定》（OC 设定）。
  - 处理并导入了 12 张新图像资产，对其重命名、进行了缩放转码、并自动写入了 `cafe3310` 版权 EXIF 敏感信息注入。

- **主要修改**：
  - 新增了文章文件 [source/2026-06-15-21-12-miemie-at-2018-2019.md](file:///Users/sipan/workspace/_working/jiujiu-miemie-gallery/source/2026-06-15-21-12-miemie-at-2018-2019.md)，并添加了指向 `miemie-at-2018` 和 `cat-oc-design` 的维基链接。
  - 对 12 张原图资产按 EXIF 拍摄时间升序进行重命名处理，以 `2026-06-15-21-12-miemie-at-2018-2019-miemie-1.jpg` 至 `12.jpg` 的规范命名格式输出至 `gallery/`。
  - 运行 `python3 src/build.py` 编译了全站静态文件至 `docs/` 目录。

- **验证结论**：全站静态构建顺利，`docs/posts/miemie-at-2018-2019.html` 正常生成，全站 Sitemap 及文章 JSON-LD 正确更新。

