./HelloEposCmd -n 1 -p "USB0" -i "USB"
-n can node id 
-p port name "USB0" "USB1"
-i interface name "USB"

bulid command

make clean && make 

测试代码在demo里面
DemoProfileVelocityMode 速度模式
DemoProfilePositionMode 位置模式
DemoProfileCurrentMode  电流模式

子设备操作
OpenSubDevice
```cpp
//get sub handle
g_pKeyHandle_sub = VCS_OpenSubDevice(g_pKeyHandle,pDeviceName,"CANopen",p_pErrorCode);
if(g_pKeyHandle_sub!=0){
	std::cout<<"init subdevice success"<<" g_pKeyHandle_sub:"<<g_pKeyHandle_sub<<" g_pKeyHandle:"<<g_pKeyHandle<<std::endl;
}
else{
	std::cout<<"init subdevice failed"<<std::endl;
	lResult = MMC_FAILED ;	
}
```
我在demo里想控制子设备，把g_pKeyHandle换成子设备的g_pKeyHandle_sub，
g_usNodeId换成子设备的node_id，这样控制会返回0x34000007的错误
DemoProfileVelocityMode(g_pKeyHandle, g_usNodeId, lErrorCode);

