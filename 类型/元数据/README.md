# 元数据
元数据是指描述文件自身的数据，每项数据称之为属性。

## 扩展属性
DOpus 有四项扩展属性：
- 标记（label）
- 描述（description）/备注（comment）
- 标签（tag）
- 评分（rating）

描述、标签和评分可以在设置元数据对话框（`工具栏/操作/属性/编辑元数据`，<kbd><kbd>Ctrl</kbd>+<kbd>M</kbd></kbd>）中编辑：

![](images/README/设置.png)

这四项扩展属性的储存位置如下：

元数据 | NTFS ADS | DOpus | 其它
--- | --- | --- | ---
标记 | `OpusMetaInformation` | `标记分配` (`foldercolors.oxc`)
描述 | `SummaryInformation` | ❌ | `descript.ion`
标签 | `OpusMetaInformation` | ❌
评分 | `OpusMetaInformation` | ❌

- 标签和评分只能储存在 NTFS ADS 中，因此只能用于 NTFS 中的文件。
- 标记除了储存到 NTFS ADS 外，还可储存到 DOpus 配置中，但在这种情况下重命名文件**不会**更新对应标记配置。
- 描述除了储存到 NTFS ADS 外，还可储存到相应文件夹下的 `descript.ion` 中，与 Total Commander 兼容。

### 标记
![](images/README/标记.png)

**标记**可以让文件以自定义的颜色显示，同时也支持设置文件图标和状态图标，设置加粗、斜体和下划线字体样式，以及将文件置顶。标记可以手动设置，也可以用标记过滤器自动分配。

### 描述
在 NTFS 下，DOpus 默认会将描述储存到 NTFS ADS 中。如果想要将描述储存到相应文件夹下的 `descript.ion` 文件中，需要勾选以下选项：

![](images/README/descript.ion.png)

注意，在不勾选该选项时，即使文件夹中存在 `descript.ion`，DOpus 也不会读取。

在 DOpus 中，实际上有三种描述字段，它们间的区别如下[^user-description]：
- 描述（Description）：用户说明 + 其它信息（例如图像尺寸和格式）
- 用户说明（User Description）：NTFS ADS / `descript.ion`
- 注释（Comment）：文件类型元数据 / 用户说明

  如果一个文件类型支持注释元数据，那么即使该类型文件的元数据为空，DOpus 也不会显示用户说明。

可以将描述[加入到信息提示中](../../浏览/查看/信息提示.md#提示内容)。

### 批量编辑
你可以通过 [Tagger](https://resource.dopus.com/t/tagger3-for-dopus12/24248) 对标签、描述和评分进行批量编辑：

![](https://resource.dopus.com/uploads/default/original/2X/a/a584253eb7df77aee5584217fc1b0e563bd1734c.jpg)

此外，Tagger 也支持搜索标签、描述和评分（<kbd><kbd>Alt</kbd>+<kbd>F</kbd></kbd>）。

### 搜索
见 [文件搜索](../../搜索/README.md#元数据)。

### 命令
#### 设置标记
```cmd
Properties SETLABEL=标记名
```
- 可通过 `ADDLABEL` 来表示增加标记，例如 `SETLABEL=标记名 ADDLABEL`。
- 可通过 `SETLABELTOGGLE` 来表示切换标记，例如 `SETLABEL=标记名 SETLABELTOGGLE`。

例子：

设为蓝色标记：
```cmd
Properties SETLABEL=蓝色
```

#### 设置描述
```cmd
SetAttr DESCRIPTION "描述"
```
或
```cmd
SetAttr META "comment:描述"
```

#### 设置标签
```cmd
SetAttr META tags:风景;夕阳
```
可通过 `+` `-` 来表示增减标签，例如 `tags:+风景;-夕阳` 表示增加 `风景` 标签，移除 `夕阳` 标签。

#### 设置评分
```cmd
SetAttr META rating:5
```


[^user-description]: [Comments, Description and User Description - why the same? - Help & Support - Directory Opus Resource Centre](https://resource.dopus.com/t/comments-description-and-user-description-why-the-same/20342?u=chaoses-ib)