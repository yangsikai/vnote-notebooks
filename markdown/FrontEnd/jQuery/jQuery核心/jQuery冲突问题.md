# jQuery冲突问题

jQuery中的$有可能与其他的框架产生冲突，这个时候我们需要取消$符号的意义

释放 $ 的使用权 `jQuery.noConflic()`

释放的同时自定义jQuery的访问符号 `var xxx = jQuery.noConflict()`

