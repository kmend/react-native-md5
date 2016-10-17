# react-native-eventemitter

[EventEmitter2](https://github.com/hij1nx/EventEmitter2) 在 React-Native 封装使用。 

```
npm install react-native-eventemitter --save
```

```
import EventEmitter from "react-native-eventemitter";
```


一个栗子
```
....
import EventEmitter from "react-native-eventemitter";
....

componentWillMount() {


		let callback = (v)=>{
            console.log("Main:", v);
        };
		//监听1
        EventEmitter.on("foo", (value)=>{
            console.log("foo", value);
        });
		//监听2
        EventEmitter.on("foo", callback);

		//监听匹配
		EventEmitter.on("foo.*", (value)=>{
            console.log("ALL", value);
        });
		//条件监听 事件执行2次后销毁
        EventEmitter.many('foo.*', 2, function(value) {
            console.log('foo', value);
        });
		//移除所有监听
		//EventEmitter.removeAllListeners("foo");
		//移除监听2
		//EventEmitter.removeListener("foo", callback);
		
		//触发事件1
		EventEmitter.emit("foo", "value");
		//触发事件2
		EventEmitter.emit("foo.a", "value");
}

....


注：

EventEmitter 为全局变量所以在其他组件中同样可以使用以上方式增加监听，或移除

建议在组件componentWillUnmount 时移除当前监听

栗子：
.....
componentWillMount() {
	EventEmitter.on("foo", this.callback);
}

componentWillUnmount() {
     EventEmitter.removeListener("foo", this.callback);
}

callback(value) {
 	console.log("foo", value);
}
.....

```

更多姿势参考 [EventEmitter2](https://github.com/hij1nx/EventEmitter2)。 


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
