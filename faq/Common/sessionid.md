# API基本上都需要SessionID,请问这个SessionID是从哪里可以得到？有什么用？

 有API和Notify两个接口类，API是提供给上层App的调用接口，Notify相当于Spi，由上层App实现。

每一次调用认为是一个Session,有唯一的一个SessionID。

App调用API请求类接口时，传入SessionID指针，API会返回一个值。
当服务器应答数据回来时，API通过Notify接口把对应的SessionID和应答数据一同返回。