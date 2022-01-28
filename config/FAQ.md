## 遇到的一些异常的处理

#### 	1、CMake点击configure直接报错，没法修改选项

​	解决办法：清空build目录，

#### 	2、CMake报错：`No CMAKE_C_COMPILER could be found`

​	解决办法： 参考：https://blog.csdn.net/qq_39482438/article/details/81013100

​	3、教程“你好，窗口”一节按照教程的代码不会进入循环，直接退出进程：

原因：

```c++
`if (!gladLoadGLLoader((GLADloadproc)glfwGetProcAddress)) {`
	`std::cout << "failed to initialize GLAD" << std::endl;`
	`return -1;`
`}`
```

这里gladLoadGLLoader会返回0，导致退出程序

解决办法： 

```cc
	glfwMakeContextCurrent(window); //必须先调用这个函数，教程里面没写清楚，源码里有
	
	if (!gladLoadGLLoader((GLADloadproc)glfwGetProcAddress)) {
		std::cout << "failed to initialize GLAD" << std::endl;
		return -1;
	}
```

