一、阿里语音原生提供接口：

目前类名为RNGwNls，不合适可再改；

1： 初始化阿里语音开始录音
 * @method startRecognizerwithRecorderWithToken
 * @param  {token，appkey} 

 2: 停止录音
 * @method stopRecognizerwithRecorder

二、RN中：

引入原生模块
const RNGwNls = NativeModules.RNGwNls;

创建事件实例
const emitter = new EventEmitter();

监听原生中提供的事件名称
识别回调，本次请求失败
DeviceEventEmitter.addListener('OnTaskFailed', resp => {
Alert.alert('OnTaskFailed'+resp);
});

识别回调，服务端连接关闭
DeviceEventEmitter.addListener('OnChannelClosed', resp => {
Alert.alert('OnChannelClosed'+resp);
});

识别回调，识别结果结束
DeviceEventEmitter.addListener('OnRecognizedCompleted', resp => {
Alert.alert('OnRecognizedCompleted'+resp.payload.result);
});
