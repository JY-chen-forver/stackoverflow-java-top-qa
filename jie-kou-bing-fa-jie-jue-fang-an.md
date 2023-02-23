# 接口并发解决方案

接口并发解决方案

假设冰墩墩在当天晚上上热搜之后，迅速有十几万人去淘宝下单购买，如果没有做好对该商品的缓存预热以及准备，如何操作？

在电商高并发系统中，对接口的保护一般采用：**缓存、限流、降级** 来操作。

假设该接口已经接受过风控的处理，过滤掉一半的机器人脚本请求，剩下都是人为的下单请求。

限流 主要的目的是通过对并发访问/请求进行限速，或者对一个时间窗口内的请求进行限速，一旦达到限制速率则可以拒绝服务、排队或等待、降级等处理。

Sentinel的实现、TCP滑窗

滑窗算法 是将一个时间周期分为N个小周期，分别记录每个小周期内访问次数，并且根据时间滑动删除过期的小周期。???????