# iosapp
一款外部设备对苹果的位置进行的更改软件
原理如下
主要是利用了苹果的通用外设协议，通过MFi（Made For iOS）认证厂商，可以获得MFI Accessory Interface Specification文档，其中提供了很多隐藏功能，包含时间通讯、音乐数据通讯、定位功能等等。其中定位功能的使用只需要照着文档，按照协议格式发送对应位置数据，即可。
硬件从EA通道接收到GPS信息之后，根据iAP2中的Location Information协议把GPS信息进行编码，发送给iOS系统。 iOS系统接收到硬件通过Location Information协议过来的GPS信息之后，就会把整个系统底层的定位信息更新，这样包括微信在内的所有应用的定位都修改成了刚刚选择的模拟定位点了。
![IMG_3106](https://github.com/user-attachments/assets/5bb9ef3d-b30c-4a7e-9202-8cd00e3136f1)
模拟定位的App 使用 EA协议跟外设连接。这个App集成了地图SDK，主要用途就是方便用户进行搜索或者地图点选来获取想要虚拟定位的GPS信息，然后通过EA通道使用自定义的数据协议把用户选好的GPS信息发送给硬件。
如图所示
![IMG_3105(20250507-155646)](https://github.com/user-attachments/assets/b5a2aab7-84a4-432c-b1e1-fbe5077324cd)
硬件如图所示
![IMG_3103](https://github.com/user-attachments/assets/a87a6092-87a7-4e20-a8a3-781359441e97)

目前MFI Accessory Interface Specification地址见：https://usermanual.wiki/Document/MFiAccessoryInterfaceSpecificationR18NoRestriction.1631705096.pdf

文档中搜索Locaiton即可看到定位相关信息，如下：

![image](https://github.com/user-attachments/assets/9dd19be6-749d-48ca-9fb9-8a3cb7edbcec)
