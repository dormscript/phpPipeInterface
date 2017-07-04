# phpPipeInterface
PHP调取其它语言编译生成的可执行程序

## 使用场景
在使用一些特定的组件时，组件最初往往只提供c/c++/java类的API，并不会及时的提供PHP的API。
那么，php就要尝试与C/Java类的程序进行交互。[参考链接](http://www.jianshu.com/p/9f8651834d9b)
当PHP需要与多个可执行程序交互时，就可以使用本类库

## 使用方法
* 引入类库
```php
    include "PipeInterface.php";
    using ExecutableProgram\PipeInterface;
```

* 指定名称及可执行文件的路径
```php  
    PipeInterface::addPragram('summary', '/data/nlpir/demo/summary');
    PipeInterface::addPragram('key', '/data/nlpir/demo/key');
```  
* 与程序交互 
```php
    $str = "可执行程序（executable program，EXE File）是指一种可在操作系统存储空间中浮动定位的可执行程序。在MS-DOS和MS-WINDOWS下，此类文件扩展名为·exe。";
    $rs = PipeInterface::getInstance('summary')->get($str);
```

** 以上例子中的summary组件是NLPIR中的摘要提取组件，目前只有c/c++/java的动态库 **
