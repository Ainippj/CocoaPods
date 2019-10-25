###制作自己的cocoaPod私有库

 >第一步 创建仓库

![](/Users/lijun_xue/Desktop/20191024141430.jpg)

 >第二步 将创建的仓库添加到cocoapods仓库中

######终端执行命令 其中xxxx为私有库名称
`pod repo add xxxx https://github.com/username/xxxx.git`

>第三步 创建开发模板

`pod repo add xxxx https://github.com/username/xxxx.git`

 执行命令后根据提示输入
![](/Users/lijun_xue/Desktop/20191024144418.jpg)

到这里会自动打开Xcode 模板就创建成功了 

打开工程将ReplaceMe.m替换成自己的文件
![](/Users/lijun_xue/Desktop/20191024145837.jpg)
替换成功后，修改podspec文件，然后执行 `pod install`
![](/Users/lijun_xue/Desktop/20191024150834.jpg)

>第四步 验证podspec文件合法性
 `pod lib lint xxxx.podspec --allow-warning`
>第五步 将制作好的组件上传至github


1.  `git remote add origin https://github.com/xxxx/xxxx.git`
2. `git push -u origin master`
上传组件也可使用第三方工具

编写项目源码，编译成功 提交到github 执行以下命令，打上tag
`git tag -a 版本号 -m 'tag release 版本号' `
`git push --tags`  
`git push origin master`
到这里就制作完成了，需要使用组件的工程中就可以使用pod加载到工程中  
`pod 'xxxx'`


