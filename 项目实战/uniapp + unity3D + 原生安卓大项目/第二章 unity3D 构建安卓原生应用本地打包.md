# uniapp + unity3D + 原生安卓大项目实战

> 本系列通过一个完整的项目来讲解涉及多个技术框架的大型应用如何构建，在这个项目中，我们会涉及到uniapp、unity3D、原生安卓等技术，并通过实践来加深对这些技术的理解，让大家在实际开发中能够更好地运用这些技术，来应对各种需求场景下的挑战

## 大纲目录
### [第一章 uniapp 构建安卓原生应用本地打包](./part1.md)

### [第二章 unity3D 构建安卓原生应用本地打包](./part2.md)

### [第三章 android Studio 构建安卓原生应用本地打包](./part3.md)

### [第四章 uniapp + unity3D + android Studio 构建安卓原生应用本地打包](./part4.md)

### [第五章 uniapp + unity3D + android Studio 混合项目构建命令脚本的编写](./part5.md)

### [第六章 uniapp + unity3D + android Studio 混合项目的消息通信](./part6.md)

### [第七章 uniapp + unity3D + android Studio 混合项目的消息通信实战（微信登陆）](./part7.md)

### [第八章 uniapp + unity3D + android Studio 混合项目的消息通信实战（微信支付）](./part7.md) 

## 第一章 uniapp 构建安卓原生应用本地打包



直接使用 uniapp 提供的 simpleDemo 来开始我们的项目





## 第一章 uniapp 构建安卓原生应用本地打包

不得不说，uniapp 对打包的封装是真的不错，只需要点点就行，主要会对我们造成困扰的，更多的是项目配置，比如：sdk版本不匹配，appId 没有对应好等等造成后续的各种问题

### 打包流程

在 HbuilderX 中依次点击 `发行 - App-Android本地打包 - 生成本地打包App资源 - 点击构建`

### 关于 manifest 配置

最基础的配置，`package` （安卓的包名）和 `appid` （uniapp的应用Id）需要和你在平台上注册的保持一致

```
{
    // ...
    "package" : "com.XXXX.app",
    "appid" : "__UNI__XXXX",
    // ...
}
```

这里的配置很重要，不同的使用场景都会涉及这里的改动，后面也会根据不同的场景告诉大家这里应该如何配置，这里先举个简单的例子抛砖引玉，比如你要上架应用市场，那肯定会要求你写明所使用的权限说明，使用用途，相关SDK列表等等，这些都是需要在 manifest 中进行配置的

```
    // Android平台应用启动时申请读写手机存储权限策略配置
    "permissionExternalStorage" : {
        "request" : "always",
        "prompt" : "应用保存运行状态等信息，需要获取读写手机存储（系统提示为访问设备上的照片、媒体内容和文件）权限，请允许。"
    },
    // Android平台应用启动时申请读取设备信息权限配置
    "permissionPhoneState" : {
        "request" : "always",
        "prompt" : "为保证您正常、安全地使用，需要获取设备识别码（部分手机提示为获取手机号码）使用权限，请允许。"
    }
```

