# AXIOS
AXIOS详解


#ajax请求
#区别一般http请求与ajax请求
1. ajax请求是一种特别的http请求
2. http请求对服务器端来说,没有任何区别,区别在浏览器端
3. 浏览器端发请求:只有XHR或fetch发出的才是ajax请求,其它所有的都是非ajax请求
#浏览器端接收到响应
1. 一般请求:浏览器一般会直接显示响应体数据,也就是我们常说的刷新跳转页面
2. ajax请求:浏览器不会对界面进行任何更新操作,只是调用监视的回调函数并传入响应相关数据


#XHRAPI
1. xmlhttprequest(): 创建XHR对象的构造函数
2. status:响应状态码值,比如200,404
3. statusText:响应状态文本
4. readyState:标识请求状态的只读属性
    0:  初始
    1:  open()之后
    2:  send()之后
    3:  请求中
    4:  请求完成
5. onreadystatechange:绑定 readyState 改变的监听
6. responseType:指定响应数据类型,如果是json,得到响应后自动解析响应体数据
7. response:响应体数据,类型取决于responseType的指定
8. timeout:指定请求超时时间,默认为0代表没有限制
9. ontimeout:绑定超时的监听
10. onerror:绑定请求网络错误的监听
11. open():初始化一个请求,参数为:(method, url[asyncl])
12. send(data)发送请求
13. abort():中断请求
14. getResponseHeader(name):获取指定名称的响应头值
15. getAllResponseHeaders():获取所有响应头组成的字符串
16. setRequestHeader(name, value):设置请求头

#axios特点
1.  基本promise的异步ajax请求库
2.  浏览器端/node端都可以使用
3.  支持请求/响应拦截器
4.  支持请求取消
5.  请求/响应数据转换
6.  批量发送多个请求

#AXIOS常用API
1. axios(config):通用/最本质的发任意类型请求的方式
2. axios(url[,config]):可以只指定url发get请求
3. axios.request(config):等同于axios(config)
4. axios.get(url[,config]):发get请求
5. axios.delete(url[,,config]):发delete请求
6. axios.post(url,[,data,config]):发post请求
7. axios.put(url,[,data,config]):发put请求

8. axios.defaults.xxx:请求的默认全局配置
9.  axios.interceptors.request.use():添加请求拦截器
10. axios.interceptors.response.use():添加响应拦截器

11. axios.create([config]):创建一个新的 axios(它没有下面的功能)
12. axios.Cancel():用于创建取消请求的错误对象
13. axios.CancelToken():用于创建取消请求的 token对象
14. axios.isCancel():是否是一个取消请求的错误
15. axios.all(promises):用于批量执行多个异步请求

16. axios.spread():用来指定接收所有成功数据的回调函数的方法 与axios.all结合使用