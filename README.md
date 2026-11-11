# 优质设计库

线上：https://crayon-ai.github.io/design-library/

- 收藏：明确存进去的截图
- 心动设计：点名喜欢的颜色 / 形状 / 字体手法（带缩略图）/ 方向
- Behance 收藏：https://crayon-ai.github.io/design-library/#behance

## Behance 收藏

作品单独放在 `behance.json`，封面放在 `behance/`。页面打开「Behance 收藏」时读取这份 JSON 渲染；`#behance` 会直接打开该 Tab。已有的「收藏」和「心动设计」不从这里读取。

新增一条只做两件事：

1. 封面存成 `behance/<项目编号>.jpg`，文件名用 Behance 项目编号，例如 `behance/253589547.jpg`。
2. 在 `behance.json` 数组里加一项（页面按数组顺序展示，想排在最前就插到开头）：

```json
{
  "id": "253589547",
  "title": "PORTFOLIO | Graphic Designer",
  "url": "https://www.behance.net/gallery/253589547/PORTFOLIO-Graphic-Designer",
  "cover": "behance/253589547.jpg",
  "date": "2026-11-11"
}
```

`id` 是项目编号，`cover` 是相对站点根目录的图片路径，`url` 是 Behance 项目页。卡片只显示封面（保持原比例）和标题，整张卡在新标签打开 `url`。
