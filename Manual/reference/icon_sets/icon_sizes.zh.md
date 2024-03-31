# 图标大小

如前所述，每个图标集可以包含一到两组不同的图标。为了简单起见，它们被称为“小”尺寸和“大”尺寸。然而，你不局限于只有两种尺寸的图标，只局限于两组图标。有可能在同一组里面有不同尺寸的不同图标。例如，

    <set size="small" width="20" height="20" filename="MyIconsSmall.png">
        <icon name="copy" row="1" col="1" />
    </set>
    <set size="small" width="24" height="24" filename="MyIconsMedium.png">
        <icon name="move" row="1" col="1" />
    </set>

 

注意，上面的两个 `set` 节点都将 `size` 属性设置为 `small`。此示例将两个图标添加到 `small` 组——一个称为“copy”，大小为 20x20，另一个称为“move”，大小为 24x24。即使它们的物理尺寸不同，它们也会一起出现在该图标集的 `small` 组中。你在 `small` 和 `large` 组中提供的图标不必对应——你不 **需要** 提供每种图标的大小和大小形式（尽管如果你这样做，显然对用户来说更好）。