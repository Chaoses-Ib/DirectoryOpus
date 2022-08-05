# Favorites
## 显示、设置、删除文件夹别名
显示别名列表：
```cmd
Favorites ALIAS=list NOOPENINTABS SHOWICONS
```

设置和删除别名：
```cmd
Favorites ALIAS=set NAME=别名 PATH "C:\Windows"
Favorites ALIAS=delete NAME=别名
```
需要注意的是，以上命令在某些版本的 DOpus 下会导致相应按钮变为收藏夹动态列表，因此最好使用脚本包装要执行的命令（或直接使用脚本接口进行操作），例如：
```js
function OnClick(clickData)
{
	// Avoid showing dynamic lists
	clickData.func.command.RunCommand('Favorites ALIAS=set NAME=别名 PATH "C:\\Windows"');
}
```