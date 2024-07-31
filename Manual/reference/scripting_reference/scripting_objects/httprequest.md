# HTTPRequest

The **HTTPRequest** object lets you easily send an asynchronous HTTP request to a remote webserver and receive and process the response.

This object is created via the [Dialog](dialog.md) object's `NewHTTPReq` method, and so requires a [Script Dialog](/Manual/scripting/script_dialogs/README.md) in order to use. The dialog also must be [detached](/Manual/scripting/script_dialogs/the_dialog_message_loop/detached_dialogs.md).

The general process to use this object is as follows:

1.  Create the HTTPRequest object
2.  Add any required headers
3.  Add POST data or GET query name/value pairs as required
4.  Send the request
5.  Process "http" events in your message loop
6.  Read any returned data when you get a "data" event.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
contenttype</td><td>

*string*</td><td>
When a response has been received, returns the value of the Content-Type response header.
</td></tr><tr><td>
complete</td><td>

*bool*</td><td>
Returns True when a request is complete (and all data has been received).
</td></tr><tr><td>
errorcode</td><td>

*int*</td><td>
Returns the numerical error code, if any.
</td></tr><tr><td>
errortext</td><td>

*string*</td><td>
Returns the error message, if any.
</td></tr><tr><td>
id</td><td>

*int*</td><td>
Returns the ID of the request. This is assigned automatically when the request is created. You'll need this if you use more than one request at once.
</td></tr><tr><td>
response</td><td>

*string*</td><td>
Returns the HTTP response message.
</td></tr><tr><td>
responsecode</td><td>

*int*</td><td>
Returns the HTTP response code (e.g. 200, 404).
</td></tr><tr><td>
status</td><td>

*string*</td><td>

Returns the current status of the request. This is also provided via the **[Msg](msg.md).value** property when you retrieve an HTTP message in your message loop. Valid status values are: notready, ready, pending, data, complete, error, shutdown.

A status value of "data" means the response has been received and data is available to read. A status of "complete" means the response is complete (e.g. a HEAD request won't return any data, so you'd look for "complete" in that case).
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
Method Name</th><th>

**Arguments**</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
Abort</td><td>

*none*</td><td>

*none*</td><td>

Aborts the request if it hasn't yet returned any data, and removes any headers and post data that you've added.

Calling this method resets the `HTTPRequest` object to its initial state, meaning it can be reused to send another request.
</td></tr><tr><td>
AddHeader</td><td>

\<string:name\>  
\<string:value\>  
*or*  
\<**Map**:headers\></td><td>

*none*</td><td>

Adds one or more headers to the HTTP request. You can either provide two strings (a name and a value), or a [Map](map.md) of name -\> value pairs to add more than one header at once.
</td></tr><tr><td>
AddPostData</td><td>

\<string:name\>  
\<value\>  
\[\<string:contenttype\>\]  
\[\<string:filename\>\]  
\[\<string::encoding\>\] *or*  
\<**Map**:data\></td><td>

*none*</td><td>

Adds one or more name/value pairs to the request's POST data. You can either provide the name and value as two arguments, in which case you can also optionally provide a content type string. Alternatively, you can provide a [Map](map.md) of name -\> value pairs. The *value* of a posted data element can either be a string, or a [Blob](blob.md) object to provide binary data.

If you only add a single item of POST data you can leave the name empty (pass an empty string). This lets you, for example, POST data formatted as JSON - set the *name* to an empty string, the *value* to the JSON data in string form, and *contenttype* to `application/json`.

If adding a **Blob** you can provide the *filename* argument which gives the receiving system a suggested filename to store the file under. You can also specify the *encoding* type - set to "base64" to have the **Blob** sent as base64-encoded data (otherwise by default it will be sent as binary). If you've encoded the data yourself you can specify another encoding type which will be passed as the value of the *Content-Transfer-Encoding* header.

The data will be sent as `multipart/form-data` if you either pass a **Blob** object, or the **Map** contains more than one name/value pair.
</td></tr><tr><td>
AddQueryData</td><td>

\<string:name\>  
\<string:value\>  
*or*  
\<**Map**:data\></td><td>

*none*</td><td>

Adds one or more name/value pairs to the request's QUERY data. You can either provide the name and value as two arguments, or you can provide a [Map](map.md) of name -\> value pairs. The query data will be automatically url-encoded and appended to the request string when the request is sent.
</td></tr><tr><td>
GetResponseHeaders</td><td>

*none*</td><td>

**Map**</td><td>

Returns a [Map](map.md) of name -\> value pairs containing the response headers once the response data has been received.
</td></tr><tr><td>
ReadResponse</td><td>

*none*</td><td>

*string* or  
**Image** or  
**Blob**</td><td>

Once a response has been received (i.e. your message loop gets an "http" message with the value type set to "data"), you can call this function to read the returned data. Note that this function will block until all data is received.

The function tries to interpret the returned data automatically based on the Content-Type header in the response. Text data wil be converted to a string if possible. Image data will be returned as [Image](image.md) object if it's a format that Opus recognises. Otherwise, a [Blob](blob.md) containing the response data will be returned.
</td></tr><tr><td>
ReadResponseData</td><td>

\[\<int:size\>\]</td><td>

**Blob**</td><td>

Use this function instead of `ReadResponse` to read the raw data from the response without trying to interpret it. The data is returned as a [Blob](blob.md) object.

You can specify the maximum about of data to read in bytes. If the requested size is available it will be returned; otherwise the function will return immediately with as much data as possible. If you specify *size* as 0, or don't specify a size, then the function will block until the entire response has been received. If you specify *size* as -1 then the function will return as much data as possible, but won't block.
</td></tr><tr><td>
SendRequest</td><td>

\<string:url\>  
\[\<string:action\>\]</td><td>

*none*</td><td>

Sends the HTTP request to the specified webserver. The *url* parameter should be the full URL to retrieve (e.g. `https://www.gpsoft.com.au`). If you've added any query parameters via the `AddQueryData` method these will be appended automatically.

By default HTTP action will be chosen automatically based on the state of the object - `POST` if `AddPostData` has been used, otherwise `GET`. You can override this with the optional *action* parameter if you like - e.g. specify `HEAD` to just retrieve the headers without any response data.
</td></tr><tr><td>
SetTimeout</td><td>

\<int:seconds\></td><td>

*none*</td><td>

Specifies a timeout in seconds (default is 30). Functions which block like `ReadResponse` will timeout if a complete response is not received in time. Set to 0 for no timeout.
</td></tr><tr><td>
SetUserAgent</td><td>

\<string:agent\></td><td>

*none*</td><td>
Specifies the User-Agent string of the request, if requires.
</td></tr><tr><td>
Shutdown</td><td>

*none*</td><td>

*none*</td><td>

Call this to close down the request and free any associated resources. This aborts the request if it's still outstanding. Once you've called this function you can't query the request for any other data except the `complete` property.

You don't need to call this function but if you use a lot of requests you may want to once they're completed in order to free up memory.

Once `Shutdown` has been called the request object can no longer be used. Note that messages from the request may still be in your dialog's message queue even after calling `Shutdown` - best practice is to check the `complete` property before using any other methods or properties.
</td></tr></tbody>
</table>

