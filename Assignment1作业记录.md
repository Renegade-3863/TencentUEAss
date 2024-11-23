### Assignment1 作业记录
#### 作业要求：
- 从源码编译 UE 引擎，并创建一个空白 C++ 项目 + 做一些场景调整
- 打包 UE 项目成安卓应用 .apk 文件，尝试运行

#### 完成情况：
- 源码编译和空白项目创建已完成，具体流程参考了 csdn 博主：闪耀的橙子 https://blog.csdn.net/Wavecut_Platform/article/details/143919760 的经验，在此声明以表感谢
- 打包过程参考了 csdn 博主：晴窗v https://blog.csdn.net/qq_35587645/article/details/139207695 的博客，在此声明以表感谢
> 目前的不足之处，尝试了多种 PC 端的 Android 模拟设备，由于硬件驱动和 OpenGL 版本等原因，只有 mac 端的 Mumu 模拟器可以正常运行打包出来的 .apk 文件
- 手头没有安卓手机，所以实际调试难度可能较大
- 新學習了向 Github 提交超過 100 MiB 大文件的方法：使用 lfs
``` bash
git lfs track "file_name"  
git add "file_name" 
git commit -m "commit_message"  # 提交文件
git push  # 推送文件
# 感谢 csdn 博主 wyw0000 的博客：https://blog.csdn.net/wyw0000/article/details/132719319
# 细节问题：为什么 lfs 需要生成一个 .gitattributes 文件？
# 解答：
# 观察 .gitattributes 文件中记录的这些信息，不难看出，这就是一个保存了需要 lfs 模块管理的大文件的类似索引的记录文件
# Assignment1-arm64.apk filter=lfs diff=lfs merge=lfs -text
# 结合 lfs 管理文件的特性：远程服务器存储，而不是 github 仓库本地存储
# 不难理解是在仓库本地存储一个 lfs 模块可以理解的远端存储的访问链接
# 在需要下载的时候解析索引提供下载链接来完成对大文件的访问操作
```

#### 问题更新：
1. Windows 端 BlueStack 模拟器可以以 OpenGL 兼容模式跑起来打包的文件，但是渲染会有问题，屏幕下半是蓝色的，目前原因不明
![image](https://github.com/user-attachments/assets/20124be4-800b-4b2d-a1c2-0aa3a5ab2656)
1_Sol. 问题已解决，在BlueStack 设置中把界面渲染器从 OpenGL/DirectX 切换为 "软件" 即可
<img width="1440" alt="image" src="https://github.com/user-attachments/assets/b5b7f5c5-d84b-4975-bf43-823939b68832">

![image](https://github.com/user-attachments/assets/6484a291-3d11-4bff-bcb8-3a9f0295d7c8)


