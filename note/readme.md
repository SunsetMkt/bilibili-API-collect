# 视频笔记

2020-11-16 B站推出了测试版的功能——"视频笔记"，与视频稿件关联，为富文本模式，可供记录观看视频时的感悟以及视频中的重要内容，目前只可在web端操作

---

继续查看：

- 笔记列表
- 笔记详细信息
- [笔记操作](action.md)√

---

## 附表-笔记正文序列格式

根数组：

| 项   | 类型 | 内容          | 备注 |
| ---- | ---- | ------------- | ---- |
| 0    | obj  | 第1个元素     |      |
| n    | obj  | 第(n+1)个元素 |      |
| ……   | obj  | ……            | ……   |

根数组中的对象：

| 字段       | 类型 | 内容         | 备注                |
| ---------- | ---- | ------------ | ------------------- |
| attributes | obj  | 元素属性     | 无属性无此项        |
| insert     | str  | 元素内容     | 为跳转/图片时无此项 |
| insert     | obj  | 元素跳转信息 | 非跳转/图片时无此项 |

对象中的`attributes`对象：

| 字段       | 类型 | 内容       | 备注                           |
| ---------- | ---- | ---------- | ------------------------------ |
| bold       | bool | 是否加粗   |                                |
| strike     | bool | 是否删除线 |                                |
| underline  | bool | 是否下划线 |                                |
| background | str  | 背景颜色   |                                |
| color      | str  | 文字颜色   |                                |
| list       | str  | 列表属性   | ordered有序列表/bullet无序列表 |
| size       | str  | 文字字号   |                                |

对象中的`insert`对象：

| 字段        | 类型 | 内容     | 备注   |
| ----------- | ---- | -------- | ------ |
| tag         | obj  | 跳转标签 | 二选一 |
| imageUpload | obj  | 笔记图片 | 二选一 |

`insert`中的`tag`对象：

| 字段     | 类型 | 内容              | 备注         |
| -------- | ---- | ----------------- | ------------ |
| cid      | num  | 视频cid           |              |
| status   | num  | 0                 | 作用尚不明确 |
| index    | num  | 在稿件中的分P索引 |              |
| seconds  | num  | 视频进度          |              |
| cidCount | num  | 稿件总分P数       |              |
| key      | str  | 标签创建时间戳    |              |
| title    | str  | output            | 作用尚不明确 |

`insert`中的`imageUpload`对象：

| 字段   | 类型 | 内容       | 备注         |
| ------ | ---- | ---------- | ------------ |
| url    | str  | 图片链接   |              |
| status | str  | done       | 作用尚不明确 |
| width  | num  | 图片宽度-2 |              |
