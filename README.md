## 背景
  vipper是一个配置加载库(详细看原版链接[https://github.com/spf13/viper](https://github.com/spf13/viper), vipper对象并不是一个线程安全的对象, 在项目上最常用的地方是需要定时读取remote的配置信息，更新到本地的vipper对象。因为vipper对象非线程安全，读取配置和写入配置需要上锁。且动态配置改动非常变动，根据这个特效修改vipper代码用COW来保证vipper对象读取远端配置时的线程安全。
## 使用

 项目根据vipper的1.5版本改造，使用可以直接replace替换原来的vipper库。

 ```shell
 go mod edit --replace=github.com/spf13/viper@v1.5.0=github.com/Socketsj/viper@latest
 ```

## diff
[https://github.com/Socketsj/viper/commit/01d8b7ed87b7f87de342a0c89fc6c04d79c9a320](https://github.com/Socketsj/viper/commit/01d8b7ed87b7f87de342a0c89fc6c04d79c9a320)

