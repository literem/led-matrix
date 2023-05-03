# 基于ESP32制作的多功能LED点阵屏幕
这是一个基于ESP32开发的可以用手机APP控制的多功能LED点阵屏幕，点阵行数为16行，列数支持级联，可根据需要焊接。通过安卓APP控制，支持滚动显示、静态显示、时钟显示、自定义显示和歌词显示。点阵屏幕分三部分组成，ESP32控制板、底板和模块板，需要将模块板插到底板上，然后底板和底板使用排母进行焊接即可级联。

bilibili视频效果演示：【自制】DIY一个能在桌子上显示歌词的点阵屏幕 https://www.bilibili.com/video/BV1dX4y1R7UC/

控制软件APP开源地址：https://github.com/literem/led-matrix-android

ESP32代码开源地址：https://github.com/literem/led-matrix-esp32

立创开源硬件平台：https://oshwhub.com/cyaroge/dz_16-n_control#P6



**注意：主控需要使用ESP32-WROOM-32E，8M内存的版本；存储芯片要用AT24C32；焊接点阵模块的时候，点阵模块上的“788BS”字样要向着模块板上的“列”的丝印；焊接排母时可以先将排母插到点阵模块板的排针上，然后拿出点阵底板放在桌面对准，再焊接外面的触点，焊接完成拔下点阵模块焊接里面的触点；拼接模块时也是将模块放到桌面上然后放排针焊接，尽可能保证平整。为了节省打板的成本我选择用模块拼接的方式，如果想要一整块板可以选择自己画板。**



### 更新说明

**2023.5.4**

新增BOM表

**2023.4.16**

原来的点阵底板R8电阻封装出错，导致电源短路，已修改该问题。如果发现短路，可以用小刀刮掉R8电阻旁边的覆铜层再上电

**2023.4.3**

支持Android12设备

### 硬件实物图

级联了8个16x16点阵模块的效果：

![image-20230331143825363.jpg](https://github.com/literem/led-matrix/blob/master/%E5%9B%BE%E7%89%87/image-20230331143825363.jpg?raw=true)

![image-20230331143912285.jpg](https://github.com/literem/led-matrix/blob/master/%E5%9B%BE%E7%89%87/image-20230331143912285.jpg?raw=true)

没有级联的效果：

![image-20230331144303057.jpg](https://github.com/literem/led-matrix/blob/master/%E5%9B%BE%E7%89%87/image-20230331144303057.jpg?raw=true)

![image-20230331144332983.jpg](https://github.com/literem/led-matrix/blob/master/%E5%9B%BE%E7%89%87/image-20230331144332983.jpg?raw=true)



### 点阵控制板

采用ESP32-WROOM-32E单片机，点阵屏用的GBK字库放在里面了，省了外挂字库芯片的麻烦。支持电池供电和外接TypeC或DC接口输入，还有一个DC接口是给电池充电用的。之所以外接供电和充电接口要分开，是因为避免外接供电的时候一直给电池充电，当然这个也可以加mos开关控制是否充电，但是这需要电池电压采集和mos控制电路，还有代码的逻辑判断，比较麻烦，索性分开了。ESP32右边的芯片是AT24C32，是一颗E2PROM，存储点阵屏信息的芯片。还有一个时钟芯片RX8025，某宝一块多很容易就买到。TypeC口旁边的是CH340C芯片，给ESP32下载代码的。顶部有四个按键，左边那个是复位的，还有三个按键没有做功能开发，目前只是个摆设。

![image-20230331152303041.jpg](https://github.com/literem/led-matrix/blob/master/%E5%9B%BE%E7%89%87/image-20230331152303041.jpg?raw=true)

![image-20230331152305017.jpg](https://github.com/literem/led-matrix/blob/master/%E5%9B%BE%E7%89%87/image-20230331152305017.jpg?raw=true)



### 点阵底板

![image-20230331144616896.jpg](https://github.com/literem/led-matrix/blob/master/%E5%9B%BE%E7%89%87/image-20230331144616896.jpg?raw=true)



### 点阵模块板

![image-20230331145701296.jpg](https://github.com/literem/led-matrix/blob/master/%E5%9B%BE%E7%89%87/image-20230331145701296.jpg?raw=true)



### 软件界面

连接设备界面

<img src="https://github.com/literem/led-matrix/blob/master/%E5%9B%BE%E7%89%87/image-20230331151815400.png?raw=true" alt="image-20230331151815400.png" style="zoom:50%;" />

功能界面

<img src="https://github.com/literem/led-matrix/blob/master/%E5%9B%BE%E7%89%87/image-20230331151836870.png?raw=true" alt="image-20230331151836870.png" style="zoom:50%;" />

