# 基于ESP32制作的多功能LED点阵屏幕
这是一个基于ESP32开发的可以用手机APP控制的多功能LED点阵屏幕，点阵行数为16行，列数支持级联，可根据需要焊接。通过安卓APP控制，支持滚动显示、静态显示、时钟显示、自定义显示和歌词显示。点阵屏幕分三部分组成，ESP32控制板、底板和模块板，需要将模块板插到底板上，然后底板和底板使用排母进行焊接即可级联。

效果演示：【自制】DIY一个能在桌子上显示歌词的点阵屏幕 https://www.bilibili.com/video/BV1dX4y1R7UC/

控制软件APP开源地址：https://github.com/literem/led-matrix-android

ESP32代码开源地址：https://github.com/literem/led-matrix-esp32



### 硬件实物图

级联了8个16x16点阵模块的效果：

![image-20230331143825363.jpg](https://github.com/literem/led-matrix/blob/master/%E5%9B%BE%E7%89%87/image-20230331143825363.jpg?raw=true)



![image-20230331143912285.jpg](https://github.com/literem/led-matrix/blob/master/%E5%9B%BE%E7%89%87/image-20230331143912285.jpg?raw=true)



没有级联的效果：

![image-20230331144303057.jpg](https://github.com/literem/led-matrix/blob/master/%E5%9B%BE%E7%89%87/image-20230331144303057.jpg?raw=true)



![image-20230331144332983.jpg](https://github.com/literem/led-matrix/blob/master/%E5%9B%BE%E7%89%87/image-20230331144332983.jpg?raw=true)



![image-20230331152303041.jpg](https://github.com/literem/led-matrix/blob/master/%E5%9B%BE%E7%89%87/image-20230331152303041.jpg?raw=true)

### 点阵控制板

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



