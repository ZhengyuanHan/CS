Activity 代表了一个具有用户界面的单一屏幕。其作用是描述UI，并且处理用户与机器屏幕的交互。  
![Activity 生命周期](https://github.com/ZhengyuanHan/CS/blob/main/img/activity%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F.png)
| 回调 | 描述 |
| --- | --- |
| onCreate() | 这是第一个回调，在Activity第一次创建时调用 |
| onStart() | 这个回调在Activity为用户可见时被调用 |  
| onResume() | 这个回调在应用程序与用户开始可交互的时候调用 |  
| onPause() | 被暂停的Activity无法接受用户输入，不能执行任何代码。当前Activity将要被暂停，上一个Activity将要被恢复时调用 |  
| onStop() | 当Activity不在可见时调用 |  
| onDestroy() | 当Activity被系统销毁之前调用 |  
| onRestart() | 当Activity被停止以后重新打开时调用 |  
