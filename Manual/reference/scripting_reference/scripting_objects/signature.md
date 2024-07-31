# Signature

The **Signature** object is returned by the **[FSUtil](fsutil.md).GetSignature** method to provide information about the signature used to digitally sign an executable file.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
certissuer</td><td>

*object:CertInfo*</td><td>
Information about the issuer of the certificate used to sign the file.
</td></tr><tr><td>
certsigner</td><td>

*object:CertInfo*</td><td>
Information about the certificate used to sign this file.
</td></tr><tr><td>
certtimestamp</td><td>

*object:CertInfo*</td><td>

Information about the certificate used to timestamp the signature (only if `timestamped` is true).
</td></tr><tr><td>
moreinfo</td><td>

*string*</td><td>
More information (optional string provided by the publisher).
</td></tr><tr><td>
progname</td><td>

*string*</td><td>
Returns the name of the program.
</td></tr><tr><td>
publink</td><td>

*string*</td><td>
Returns the publisher's link.
</td></tr><tr><td>
selfsigned</td><td>

*bool*</td><td>

Returns **True** if the file is self-signed.
</td></tr><tr><td>
timestamp</td><td>

*date*</td><td>

Returns the signature's timestamp (if `timestamped` is true).
</td></tr><tr><td>
timestamped</td><td>

*bool*</td><td>

Returns **True** if the signature was timestamped.
</td></tr><tr><td>
valid</td><td>

*bool*</td><td>

Returns **True** if the signature validation was successful. Note that the signature is only validated if the **verify** parameter is set to **True** or one of the other validation flags when the **GetSignature** method is called.
</td></tr></tbody>
</table>

### Signature.CertInfo

The **Signature.CertInfo** object is returned by the `certissuer`, `certsigner` and `certtimestamp` properties.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
issuer</td><td>

*string*</td><td>
The party that issued the certificate.
</td></tr><tr><td>
serial</td><td>

*string*</td><td>
The signature's serial number (in text form).
</td></tr><tr><td>
serialdata</td><td>

*object:**[Blob](blob.md)***</td><td>
The signature's serial number in binary form.
</td></tr><tr><td>
subject</td><td>

*string*</td><td>
The signature's subject name.
</td></tr><tr><td>
valid</td><td>

*bool*</td><td>

Returns **True** if the certificate is valid.
</td></tr></tbody>
</table>

