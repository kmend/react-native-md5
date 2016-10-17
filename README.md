# react-native-md5

```
npm install react-native-md5 --save
```

```
import EventEmitter from "react-native-md5";
```


一个栗子
```
....
import md5 from "react-native-md5";
....

componentWillMount() {

        let hex_md5v = md5.hex_md5( Date.now() +"" );
        console.log(">>>>hex_md5:", hex_md5v);

        let b64_md5v = md5.b64_md5( Date.now() +"" );
        console.log(">>>>b64_md5:", b64_md5v);

        let str_md5v = md5.str_md5( Date.now() +"" );
        console.log(">>>>str_md5:", str_md5v);

        let hex_hmac_md5v = md5.hex_hmac_md5("my_key", Date.now() +"" );
        console.log(">>>>hex_hmac_md5:", hex_hmac_md5v);

        let b64_hmac_md5v = md5.b64_hmac_md5("my_key", Date.now() +"" );
        console.log(">>>>b64_hmac_md5:", b64_hmac_md5v);

        let str_hmac_md5v = md5.str_hmac_md5("my_key", Date.now() +"" );
        console.log(">>>>str_hmac_md5:", str_hmac_md5v);

}

....


```

更多姿势参考 [scripts](http://pajhome.org.uk/crypt/md5/scripts.html)。

## License

(The MIT License)

Copyright (c) 2016-2018 NetEase, Inc. and other contributors

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
