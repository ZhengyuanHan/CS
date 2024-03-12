## path的作用
path是系统用来指定可执行文件的完整路径，即使不在path中设置JDK的路径也可执行JAVA文件，但必须把完整的路径写出来，如C:\Program Files\Java\jdk1.6.0_10\bin\javac TheClass.java。path是用来搜索所执行的可执行文件路径的，如果执行的可执行文件不在当前目录下，那就会依次搜索path中设置的路径；而java的各种操作命令是在其安装路径中的bin目录下，所以在path中设置了JDK的安装目录后就不用再把java文件的完整路径写出来了，它会自动去path中设置的路径中去找。

## classpath的作用
classpath是指定你在程序中所使用的类（.class）文件所在的位置，就如在引入一个类时：import javax.swing.JTable这句话是告诉编译器要引入javax.swing这个包下的JTable类，而classpath就是告诉编译器该到哪里去找到这个类（前提是你在classpath中设置了这个类的路径）；如果你想要编译在当前目录下找，就加上“.”,如：.;D:\Program Files\Java\jdk\,这样编译器就会到当前目录和D:\Program Files\Java\jdk\去找javax.swing.JTable这个类；还提下：大多数人都是用Eclipse写程序，不设classpath也没关系，因为Eclipse有相关的配置。

## path和classpath区别：
1.	用途上：path是os用，classpath是java用  
2.	路径上：path里面不光有Java的bin，还可以包含许多其他的，tc，masm，只要在path中设了这些环境的路径，你在dos下的任何路径上都可以调用这些路径下的命令。 classpath是java专用的查找类的路径  
3.	包含上：系统变量是环境变量的一种，环境变量一种仅本用户适用，另一种即系统变量整个系统的用户都适用,两者都可以在使用应用程序时提供快捷.一般在编辑java文件或者C#文件时需要修改,设计到多个文件夹之间的切换时也可以根据自己的需要设置. 简单的说就是，如果设置系统变量和用户变量，都叫做设置环境变量，设置系统变量时，该系统的所有帐号的用户都可以使用，但是设置用户变量时，其他的帐号登陆时就不一定可以使用。   
