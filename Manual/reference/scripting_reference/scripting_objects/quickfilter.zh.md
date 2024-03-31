# 快速过滤器

**快速过滤器** 对象提供对标签页中快速过滤器状态信息的访问权限。由 **[标签页](tab.zh.md)。快速过滤器属性** 返回。

表格: |

**属性名称**|**返回类型**|**说明**
|--|--|--|
|*\<默认值\>* |*string* |返回当前的过滤器字符串（如果存在）。
| autoclear |*bool* |如果已在配置中设置自动清除模式，则返回 **True**。
| autostar |*bool* |如果已在配置中设置自动星标模式，则返回 **True**。
| disable |*bool* |如果已禁用过滤器，则返回 **True**。
| easymode |*bool* |如果已选择简易模式，则返回 **True**。
| filter |*string* |返回当前的过滤器字符串。
| flatview |*bool* |如果在平面视图中已开启文件夹过滤，则返回 **True**。
| hidealldirs |*bool* |如果已隐藏所有文件夹，则返回 **True**。
| hideallfiles |*bool* |如果已隐藏所有文件，则返回 **True**。
| overrideflatview |*bool* |（旧标志。）如果已重写平面视图中的文件夹过滤，则返回 **True**。使用 **flatview** 标志找出其实际状态（处于开启或关闭）。
| partial |*bool* |如果已启用部分匹配，则返回 **True**。
| realtime |*bool* |如果已启用实时过滤，则返回 **True**。
| regex |*bool* |如果已启用正则表达式模式，则返回 **True**。
| showalldirs |*bool* |如果已显示所有文件夹，则返回 **True**。
| showallfiles |*bool* |如果已显示所有文件，则返回 **True**。
| showeverything |*bool* |如果 [显示全部](/Manual/basic_concepts/searching_and_filtering/show_everything.zh.md) 模式处于开启状态，则返回 **True**，它将覆盖（几乎）所有过滤。