# st7789

## 1、介绍


st7789是一颗常用的 TFT LCD 显示驱动 IC ,网络上也有很多 st7789 的驱动程序，如果仔细去看的话，就会发现基本都是差不多的。我这里是照搬了潘多拉开发板 SDK 里面的 LCD 驱动，我只是整理做成了 RT-Thread 的软件包，在使用 RT-Thread 的时候，通过 ENV 工具更加方便的把驱动加入到工程中，这里我们要感谢驱动的作者：flybreak；balanceTWK；ZYLX

（PS：目前暂未联系到以上原作者，如有侵权和疑问，请及时和我联系）

### 1.1 目录结构


| 名称 | 说明 |
| ---- | ---- |
| docs  | 文档目录 |
| examples | 例子目录，并有相应的一些说明 |
| inc  | 头文件目录 |
| src  | 源代码目录 |


### 1.2 许可证


st7789 package 遵循 Apache license v2.0 许可，详见 `LICENSE` 文件。

### 1.3 依赖


- RT-Thread 3.0+


## 2、如何打开 st7789


使用 st7789 package 需要在 RT-Thread 的包管理器中选择它，具体路径如下：

```
RT-Thread online packages
    miscellaneous packages --->
        [*]  st7789 package
```

然后让 RT-Thread 的包管理器自动更新，或者使用 `pkgs --update` 命令更新包到 BSP 中。

## 3、使用 st7789

在打开 st7789 package 后，当进行 bsp 编译时，它会被加入到 bsp 工程中进行编译，由于st7789 采用 SPI 控制，使用st7789 驱动前，请先使能 SPI 总线，并根据使能的 SPI ,将 st7789 注册和挂载到相应的 SPI 总线上。


## 4、注意事项

本驱动采用 4 线 SPI 接口，具体的驱动和 MCU 的接线方式如下

| st7789 | MCU | 说明 |
| ---- | ---- |---- |
| CLK  | SPI_SCLK |SPI时钟线 |
| SDA | SPI_MOSI |SPI数据线 |
| DC/WR  | GPIOXX |数据命令控制线 |
| CS  | GPIOXX |SPI片选线 |
| RES  | GPIOXX |复位线 |
| BLK/PWR  | GPIOXX |背光控制线 |

## 5、联系方式 & 感谢

* 维护：jiangxiangyu
* 主页：https://github.com/RT-Thread-packages/st7789
