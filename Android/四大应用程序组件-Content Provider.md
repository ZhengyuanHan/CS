Content Provider组件负责处理数据和数据库管理方面的问题。其通过请求从一个应用程序向其他的应用程序提供数据。这些请求由类 ContentResolver 的方法来处理。Content Provider可以使用不同的方式来存储数据。数据可以被存放在数据库，文件，甚至是网络。
![Content Provider](https://github.com/ZhengyuanHan/CS/blob/main/img/content%20provider.png)

有时候需要在应用程序之间共享数据。这时Content Provider变得非常有用。
  
Content Provider可以让内容集中，必要时可以有多个不同的应用程序来访问。Content Provider的行为和数据库很像。你可以查询，编辑它的内容，使用 insert()， update()， delete() 和 query() 来添加或者删除内容。多数情况下数据被存储在 SQLite 数据库。
  
Content Provider被实现为类 ContentProvider 类的子类。需要实现一系列标准的 API，以便其他的应用程序来执行事务。
