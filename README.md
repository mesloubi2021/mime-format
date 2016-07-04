# mime-format

Simple module to lookup the base format of HTTP response bodies from the `content-type` header. This module helps disambiguate the nature of the content, especially between `text/*` and `application/*`. The basic seven content type bases as defined [RFC1341](https://www.w3.org/Protocols/rfc1341/4_Content-Type.html) are:

- text
- multipart
- message
- image
- audio
- video
- application

However, from the content-type base, it is not easy to determine which formats are exactly "textual" in nature. For example, "text/json" as well as "application/json" are textual. This module disambiguates the same by maintaining a database of textual contents served over "application/*" content types.

## Usage

```terminal
npm install mime-format --save-dev;
```

```javascript
var mimeFormat = require('mime-format');

console.log(mimeFormat.lookup('application/xml'));
// outputs
// {
//   "type": "text",
//   "format": "xml"
// }
```