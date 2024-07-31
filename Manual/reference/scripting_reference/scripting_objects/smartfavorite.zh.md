# SmartFavorite

一个 **SmartFavorite** 对象代表 [智能收藏夹](/Manual/basic_concepts/the_lister/navigation/smartfavorites.zh.md) 表中一个文件夹的条目。它可以通过枚举或索引 **[SmartFavorites](smartfavorites.zh.md)** 对象来获取。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
path</td><td>

*对象:***[Path](path.zh.md)**</td><td>

返回此条目所代表的路径，作为一个 **[Path](path.zh.md)** 对象。
</td></tr><tr><td>
points</td><td>

*int*</td><td>
返回此条目作为源文件夹拥有的点数。点数评分用于 Opus 确定要显示哪些文件夹。
</td></tr><tr><td>
destpoints</td><td>

*int*</td><td>
返回此条目作为目标文件夹拥有的点数。
</td></tr></tbody>
</table>