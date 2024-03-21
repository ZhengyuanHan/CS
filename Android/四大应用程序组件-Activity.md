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
## Fragment
碎片是Activity的一部分，使得Activity更加的模块化设计。我们可以认为Fragment是一种子Activity。
  
下面是关于Fragment的重要知识点：
- Fragment拥有自己的布局，自己的行为及自己的生命周期回调。
- 当Activity在运行的时候，你可以在Activity中添加或者移除Fragment。
- 你可以合并多个Fragment在一个单一的Activity中来构建多栏的UI。
- Fragment可以被用在多个Activity中。
- Fragment的生命周期和它的宿主Activity紧密关联。这意味着Activity被暂停，所有Activity中的Fragment被停止。
- Fragment可以实现行为而没有用户界面组件。

Android 的碎片拥有自己的生命周期，与 Android 的活动很相似。下面简单介绍它生命周期的不同阶段。
![fragment生命周期](https://github.com/ZhengyuanHan/CS/blob/main/img/fragment%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F.png)
| 方法 | 描述 |
| --- | --- |
| onAttach() | Fragment实例被关联到Activity实例。Fragment和Activity还没有完全初始化。通常，你在该方法中获取到Activity的引用，在Fragment将来的初始化工作中被使用。 |
| onCreate() | 当创建Fragment时，系统调用该方法。你需要初始化一些Fragment的必要组件。这些组件是当Fragment被暂停、停止时需要保留的，以便被恢复。 |  
| onCreateView() | 当Fragment将要第一次绘制它的用户界面时系统调用该方法。为了绘制Fragment的UI，你需要从该方法中返回一个代表Fragment根布局的View组件。如果该Fragment不提供用户界面，直接返回null。 |  
| onActivityCreated() | 当宿主Activity被创建，在onCreateView()方法之后调用该方法。Activity和Fragment实例与Activity的视图层级被创建。这时，视图可以通过findViewById()方法来访问。在这个方法中，你可以实例化需要Context对象的对象。 |  
| onStart() | Fragment可见时调用该方法。 |  
| onResume() | Fragment可交互时调用该方法。 |  
| onPause() | 当首次表明用户将要离开Fragment时系统调用该方法。通常，这里你需要提交任何的会超出用户会话的持久化的变化。 |  
| onStop() | Fragment将要被停止时调用。 |  
| onDestroyView() | 调用该方法后，Fragment将要被销毁。 |  
| onDestroy() | 该方法被用来清理Fragment的状态。但在Android平台并不保证一定被调用。 |  
