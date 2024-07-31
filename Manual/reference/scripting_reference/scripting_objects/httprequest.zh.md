# HTTPRequest

**HTTPRequest** 对象允许您轻松地向远程 Web 服务器发送异步 HTTP 请求并接收和处理响应。

此对象是通过 [Dialog](dialog.zh.md) 对象的 `NewHTTPReq` 方法创建的，因此需要 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md)才能使用。对话框还必须是 [分离的](/Manual/scripting/script_dialogs/the_dialog_message_loop/detached_dialogs.zh.md)。

使用此对象的通用过程如下：

1. 创建 **HTTPRequest** 对象
2. 添加任何必需的标头
3. 根据需要添加 POST 数据或 GET 查询名称/值对
4. 发送请求
5. 在您的消息循环中处理 "http" 事件
6. 当您收到 "data" 事件时，读取任何返回的数据。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
contenttype</td><td>

*string*</td><td>
当收到响应时，返回 Content-Type 响应标头的值。
</td></tr><tr><td>
complete</td><td>

*bool*</td><td>
当请求完成（并且所有数据都已收到）时返回 True。
</td></tr><tr><td>
errorcode</td><td>

*int*</td><td>
返回错误代码（如果有）。
</td></tr><tr><td>
errortext</td><td>

*string*</td><td>
返回错误消息（如果有）。
</td></tr><tr><td>
id</td><td>

*int*</td><td>
返回请求的 ID。此 ID 在创建请求时自动分配。如果您一次使用多个请求，则需要此 ID。
</td></tr><tr><td>
response</td><td>

*string*</td><td>
返回 HTTP 响应消息。
</td></tr><tr><td>
responsecode</td><td>

*int*</td><td>
返回 HTTP 响应代码（例如 200、404）。
</td></tr><tr><td>
status</td><td>

*string*</td><td>

返回请求的当前状态。当您在消息循环中检索 HTTP 消息时，这也会通过 **[Msg](msg.zh.md).value** 属性提供。有效的状态值是：notready、ready、pending、data、complete、error、shutdown。

状态值为 "data" 表示响应已收到，并且数据可供读取。状态值为 "complete" 表示响应已完成（例如 HEAD 请求不会返回任何数据，因此在这种情况下您会查找 "complete"）。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
Abort</td><td>

*none*</td><td>

*none*</td><td>

如果请求尚未返回任何数据，则中止请求，并删除您添加的任何标头和发布数据。

调用此方法会将 `HTTPRequest` 对象重置为其初始状态，这意味着它可以重新用于发送另一个请求。
</td></tr><tr><td>
AddHeader</td><td>

\<string:name\>  
\<string:value\>  
*或*  
\<**Map**:headers\></td><td>

*none*</td><td>

向 HTTP 请求添加一个或多个标头。您可以提供两个字符串（名称和值），也可以提供一个名称 -\> 值对的 [Map](map.zh.md) 来一次添加多个标头。
</td></tr><tr><td>
AddPostData</td><td>

\<string:name\>  
\<value\>  
\[\<string:contenttype\>\]  
\[\<string:filename\>\]  
\[\<string::encoding\>\] *或*  
\<**Map**:data\></td><td>

*none*</td><td>

向请求的 POST 数据添加一个或多个名称/值对。您可以提供两个参数的名称和值，在这种情况下，您还可以选择提供内容类型字符串。或者，您可以提供一个名称 -\> 值对的 [Map](map.zh.md)。发布数据元素的 *value* 可以是字符串，也可以是 [Blob](blob.zh.md) 对象来提供二进制数据。

如果您只添加了一项 POST 数据，您可以将名称留空（传递空字符串）。这可以让您例如以 JSON 格式发布数据 - 将 *name* 设置为空字符串，将 *value* 设置为字符串形式的 JSON 数据，并将 *contenttype* 设置为 `application/json`。

如果添加 **Blob**，您可以提供 *filename* 参数，该参数为接收系统提供一个建议的存储文件的文件名。您还可以指定 *encoding* 类型 - 设置为 "base64" 以将 **Blob** 作为 base64 编码的数据发送（否则默认情况下将作为二进制数据发送）。如果您已对数据进行了编码，您可以指定另一个编码类型，该类型将作为 *Content-Transfer-Encoding* 标头的值传递。

如果您传递 **Blob** 对象，或者 **Map** 包含多个名称/值对，则数据将作为 `multipart/form-data` 发送。
</td></tr><tr><td>
AddQueryData</td><td>

\<string:name\>  
\<string:value\>  
*或*  
\<**Map**:data\></td><td>

*none*</td><td>

向请求的 QUERY 数据添加一个或多个名称/值对。您可以提供两个参数的名称和值，也可以提供一个名称 -\> 值对的 [Map](map.zh.md)。查询数据将自动进行 URL 编码，并在发送请求时附加到请求字符串。
</td></tr><tr><td>
GetResponseHeaders</td><td>

*none*</td><td>

**Map**</td><td>

在收到响应数据后，返回一个包含名称 -\> 值对的 [Map](map.zh.md)，其中包含响应标头。
</td></tr><tr><td>
ReadResponse</td><td>

*none*</td><td>

*string* 或  
**Image** 或  
**Blob**</td><td>

在收到响应后（即您的消息循环收到一个值为 "data" 的 "http" 消息），您可以调用此函数来读取返回的数据。请注意，此函数将阻塞，直到所有数据都收到。

该函数尝试根据响应中的 Content-Type 标头自动解释返回的数据。如果可能，文本数据将转换为字符串。如果它是 Opus 识别的格式，图像数据将作为 [Image](image.zh.md) 对象返回。否则，将返回包含响应数据的 [Blob](blob.zh.md)。
</td></tr><tr><td>
ReadResponseData</td><td>

\[\<int:size\>\]</td><td>

**Blob**</td><td>

使用此函数而不是 `ReadResponse` 来读取响应中的原始数据，而无需尝试解释它。数据将作为 [Blob](blob.zh.md) 对象返回。

您可以指定要读取的最大数据量（以字节为单位）。如果请求的大小可用，则将返回该大小；否则，该函数将立即返回尽可能多的数据。如果您将 *size* 指定为 0，或者没有指定大小，则该函数将阻塞，直到整个响应都收到。如果您将 *size* 指定为 -1，则该函数将返回尽可能多的数据，但不会阻塞。
</td></tr><tr><td>
SendRequest</td><td>

\<string:url\>  
\[\<string:action\>\]</td><td>

*none*</td><td>

将 HTTP 请求发送到指定的 Web 服务器。*url* 参数应该是要检索的完整 URL（例如 `https://www.gpsoft.com.au`）。如果您使用 `AddQueryData` 方法添加了任何查询参数，这些参数将自动附加。

默认情况下，HTTP 操作将根据对象的 state 自动选择 - 如果使用了 `AddPostData` 则为 `POST`，否则为 `GET`。如果您愿意，您可以使用可选的 *action* 参数覆盖此操作 - 例如，指定 `HEAD` 只检索标头，不返回任何响应数据。
</td></tr><tr><td>
SetTimeout</td><td>

\<int:seconds\></td><td>

*none*</td><td>

指定超时时间（以秒为单位）（默认值为 30 秒）。如果在指定时间内未收到完整的响应，则阻塞的函数（如 `ReadResponse`）将超时。设置为 0 表示不超时。
</td></tr><tr><td>
SetUserAgent</td><td>

\<string:agent\></td><td>

*none*</td><td>
指定请求的 User-Agent 字符串（如果需要）。
</td></tr><tr><td>
Shutdown</td><td>

*none*</td><td>

*none*</td><td>

调用此方法关闭请求并释放任何关联的资源。如果请求仍然未完成，则会中止该请求。调用此函数后，您将无法查询请求以获取任何其它数据，除了 `complete` 属性。

您无需调用此函数，但如果您使用大量请求，您可能希望在请求完成后调用它以释放内存。

在调用 `Shutdown` 后，请求对象将无法再使用。请注意，即使在调用 `Shutdown` 后，来自请求的消息可能仍然存在于您的对话框的消息队列中 - 最佳做法是在使用任何其它方法或属性之前检查 `complete` 属性。
</td></tr></tbody>
</table>