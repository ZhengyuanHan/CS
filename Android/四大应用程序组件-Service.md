Service是一个后台运行的组件，执行长时间运行且不需要用户交互的任务。即使应用被销毁也依然可以工作。服务基本上包含两种状态：
### Started
Android的应用程序组件，如Activity，通过startService()启动了Service，则Service是Started状态。一旦启动，Service可以在后台无限期运行，即使启动它的组件已经被销毁。
### Bound
当Android的应用程序组件通过bindService()绑定了Service，则Service是Bound状态。Bound状态的Service提供了一个客户服务器接口来允许组件与Service进行交互，如发送请求，获取结果，甚至通过IPC来进行跨进程通信。  
![Service生命周期](https://github.com/ZhengyuanHan/CS/blob/main/img/services%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F.png)
