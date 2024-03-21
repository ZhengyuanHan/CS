Broadcast Receivers用于处理Android操作系统和应用程序之间的通信，响应来自其他应用程序或者系统的广播消息。这些消息有时被称为事件或者意图。例如，应用程序可以初始化广播来让其他的应用程序知道一些数据已经被下载到设备，并可以为他们所用。这样Broadcast Receivers可以定义适当的动作来拦截这些通信。  
  
有以下两个重要的步骤来使系统的广播意图配合广播接收器工作：
- 创建广播接收器
- 注册广播接收器
  
还有一个附加的步骤，要实现自定义的意图，你必须创建并广播这些意图。
### 创建Broadcast Receivers
广播接收器需要实现为BroadcastReceiver类的子类，并重写onReceive()方法来接收以Intent对象为参数的消息。
```
public class MyReceiver extends BroadcastReceiver {
   @Override
   public void onReceive(Context context, Intent intent) {
      Toast.makeText(context, "Intent Detected.", Toast.LENGTH_LONG).show();
   }
}
```
### 注册Broadcast Receivers
应用程序通过在AndroidManifest.xml中注册广播接收器来监听制定的广播意图。假设我们将要注册MyReceiver来监听系统产生的ACTION_BOOT_COMPLETED事件。该事件由Android系统的启动进程完成时发出。
![broadcast](https://github.com/ZhengyuanHan/CS/blob/main/img/broadcast.png)
```
<application
   android:icon="@drawable/ic_launcher"
   android:label="@string/app_name"
   android:theme="@style/AppTheme" >
   <receiver android:name="MyReceiver">

      <intent-filter>
         <action android:name="android.intent.action.BOOT_COMPLETED">
         </action>
      </intent-filter>

   </receiver>
</application>
```
