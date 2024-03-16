# Icon Sizes

As already mentioned, each icon set can contain one or two distinct groups of icons. For simplicity, these are referred to as the \<ib:inline-code\>`small`\</ib:inline-code\> size and the \<ib:inline-code\>`large`\</ib:inline-code\> size. However, you are not limited to only two sizes of icon-only two groups of icons. It is possible to have different icons of multiple sizes within the one group. For example,

    <set size="small" width="20" height="20" filename="MyIconsSmall.png">
        <icon name="copy" row="1" col="1" />
    </set>
    <set size="small" width="24" height="24" filename="MyIconsMedium.png">
        <icon name="move" row="1" col="1" />
    </set>

 

Note that both \<ib:inline-code\>`set`\</ib:inline-code\> nodes above have the \<ib:inline-code\>`size`\</ib:inline-code\> attribute set to \<ib:inline-code\>`small`\</ib:inline-code\> This example would add two icons to the \<ib:inline-code\>`small`\</ib:inline-code\> group – one, called “copy” that is 20x20 in size, and one called “move” that is 24x24 in size. Even though they are different physical sizes, they would both appear together in the \<ib:inline-code\>`small`\</ib:inline-code\> group for this icon set. The icons you provide in the \<ib:inline-code\>`small`\</ib:inline-code\> and \<ib:inline-code\>`large`\</ib:inline-code\> groups do not have to correspond – you do not **need** to provide both small and large forms of every icon (although it is obviously better for the user if you do.)
