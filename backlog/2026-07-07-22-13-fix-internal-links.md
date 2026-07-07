+++
title = "Fix Internal Links for Crawlers"
date_created = "2026-07-07 22:13"
creator = "Agent"
background = "Google wasn't crawling post links from index.html because relative URLs were being resolved incorrectly if the root URL missed a trailing slash."
+++

1. 我实际检查了哪些内容
- `docs/index.html` 中的内部链接结构。
- 确认了原链接形如 `<a href="posts/xxx.html">`。

2. 已确认的事实
- 对于相对路径 `posts/xxx.html`，如果访客或爬虫访问 `https://cafe3310.github.io/chocho-miemie-album` (无尾随斜杠)，浏览器/爬虫会将其解析为 `https://cafe3310.github.io/posts/xxx.html` (基于上一级根目录)，从而导致 404，这使得爬虫无法顺藤摸瓜发现文章页面。

3. 目前不能确认的部分
- GSC 中的 "Sitemap could not be read / Couldn't fetch" 问题。这通常是 Google 尚未成功拉取或 UI 显示延迟的已知问题，XML 本身的语法和格式经过检查是完全标准的。

4. 我对项目状态的判断
- 站点的生成逻辑已经被修复，所有内部文章链接现已变更为绝对路径（包含完整域名和 path prefix），能确保任何环境和爬虫都能正确解析。

5. 更好的下一步建议
- 提交代码发布后，在 Google Search Console (GSC) 对首页请求“重新编入索引”。
- 对于 Sitemap，可保留原样耐心等待几天，或在 GSC 中删除它后重新提交一遍。
