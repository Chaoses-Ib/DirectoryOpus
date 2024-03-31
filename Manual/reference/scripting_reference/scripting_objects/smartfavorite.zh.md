# SmartFavorite

**SmartFavorite** 对象表示 [智能收藏夹](/Manual/basic_concepts/the_lister/navigation/smartfavorites.zh.md) 表中的文件夹条目的条目。 通过枚举或编制索引**[智能收藏夹](smartfavorites.zh.md)** 对象检索它。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
path</td><td>

*对象:***[Path](path.zh.md)**</td><td>

将此条目表示的路径作为 **[Path](path.zh.md)** 对象返回。
</td></tr><tr><td>
points</td><td>

*int*</td><td>
返回此条目作为源文件夹的点数。 作品集使用分数来确定要显示哪些文件夹。
</td></tr><tr><td>
destpoints</td><td>

*int*</td><td>
返回此条目作为目标文件夹的点数。
</td></tr></tbody>
</table>