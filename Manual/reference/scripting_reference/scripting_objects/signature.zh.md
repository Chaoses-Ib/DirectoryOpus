# Signature

**Signature** 对象由 **[FSUtil](fsutil.zh.md).GetSignature** 方法返回，以提供有关用于对可执行文件进行数字签名的签名的信息。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
certissuer</td><td>

*object:CertInfo*</td><td>
有关用于签署文件的证书的颁发者的信息。
</td></tr><tr><td>
certsigner</td><td>

*object:CertInfo*</td><td>
有关用于签署此文件的证书的信息。
</td></tr><tr><td>
certtimestamp</td><td>

*object:CertInfo*</td><td>

有关用于对签名进行时间戳的证书的信息（仅当 `timestamped` 为真时）。
</td></tr><tr><td>
moreinfo</td><td>

*string*</td><td>
更多信息（发布者提供的可选字符串）。
</td></tr><tr><td>
progname</td><td>

*string*</td><td>
返回程序名称。
</td></tr><tr><td>
publink</td><td>

*string*</td><td>
返回发布者的链接。
</td></tr><tr><td>
selfsigned</td><td>

*bool*</td><td>

如果文件是自签名的，则返回 **True**。
</td></tr><tr><td>
timestamp</td><td>

*date*</td><td>

返回签名的时间戳（如果 `timestamped` 为真）。
</td></tr><tr><td>
timestamped</td><td>

*bool*</td><td>

如果签名已加时间戳，则返回 **True**。
</td></tr><tr><td>
valid</td><td>

*bool*</td><td>

如果签名验证成功，则返回 **True**。 请注意，只有在调用 **GetSignature** 方法时将 **verify** 参数设置为 **True** 或其它验证标志之一时，才会验证签名。
</td></tr></tbody>
</table>

### Signature.CertInfo

**Signature.CertInfo** 对象由 `certissuer`、`certsigner` 和 `certtimestamp` 属性返回。

<table>
<thead><tr><th>
属性名称</th><th>
返回值类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
issuer</td><td>

*string*</td><td>
颁发证书的方。
</td></tr><tr><td>
serial</td><td>

*string*</td><td>
签名的序列号（文本形式）。
</td></tr><tr><td>
serialdata</td><td>

*object:**[Blob](blob.zh.md)***</td><td>
签名的序列号（二进制形式）。
</td></tr><tr><td>
subject</td><td>

*string*</td><td>
签名的主体名称。
</td></tr><tr><td>
valid</td><td>

*bool*</td><td>

如果证书有效，则返回 **True**。
</td></tr></tbody>
</table>