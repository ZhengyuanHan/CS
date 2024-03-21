Service是一个后台运行的组件，用于处理与应用程序关联的后台操作，执行长时间运行且不需要用户交互的任务。即使应用被销毁也依然可以工作。服务基本上包含两种状态：
### Started
Android的应用程序组件，如Activity，通过startService()启动了Service，则Service是Started状态。一旦启动，Service可以在后台无限期运行，即使启动它的组件已经被销毁。
### Bound
当Android的应用程序组件通过bindService()绑定了Service，则Service是Bound状态。Bound状态的Service提供了一个客户服务器接口来允许组件与Service进行交互，如发送请求，获取结果，甚至通过IPC来进行跨进程通信。  
![Service生命周期](https://github.com/ZhengyuanHan/CS/blob/main/img/services%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F.png)
| 回调 | 描述 |
| --- | --- |
| onStartCommand() | 其他组件(如Activity)通过调用startService()来请求启动Service时，系统调用该方法。如果你实现该方法，你有责任在工作完成时通过stopSelf()或者stopService()方法来停止Service。 |
| onBind() | 当其他组件想要通过bindService()来绑定Service时，系统调用该方法。如果你实现该方法，你需要返回IBinder对象来提供一个接口，以便Client来与Service通信。你必须实现该方法，如果你不允许绑定，则直接返回null。 |  
| onUnbind() | 当Client中断所有Service发布的特殊接口时，系统调用该方法。 |  
| onRebind() | 当新的客户端与Service连接，且此前它已经通过onUnbind(Intent)通知断开连接时，系统调用该方法。 |  
| onCreate() | 当Service通过onStartCommand()和onBind()被第一次创建的时候，系统调用该方法。该调用要求执行一次性安装。 |  
| onDestroy() | 当Service不再有用或者被销毁时，系统调用该方法。你的Service需要实现该方法来清理任何资源，如线程，已注册的监听器，接收器等。 |  
