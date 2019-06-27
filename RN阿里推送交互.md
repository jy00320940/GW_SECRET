一、阿里移动推送接口：

1、目前类名为RNGwApns，不合适可再改；

2、导出统一配置文件到iOS、Android项目中：AliyunEmasServices-Info.plist，无需配置AppKey及AppSecret；

3、接收到阿里移动推送回调分为两种方式：
1：推送通知
* @name ApnsData_Notification
* @body  {date：string，title：string，subtitle：string，body：string，extras：string，badge：number} 
2： 推送消息
 * @ name ApnsData_Message
 * @body  {title：string，body：string} 

二、RN中：

创建事件实例
const emitter = new EventEmitter();

监听原生中提供的事件名称
DeviceEventEmitter.addListener('ApnsData_Message', resp => {
Alert.alert('ApnsData_Message'+resp.body);
});

DeviceEventEmitter.addListener('ApnsData_Notification', resp => {
Alert.alert('ApnsData_Notification'+resp.body);
});
