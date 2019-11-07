<img src='http://oleeed73x.bkt.clouddn.com/1522417405_153693.png' />

### React Native App 版本升级封装库，兼容Android 4 - 9 版本

### 一、功能
#### Android
```xml
（1）版本检测
（2）下载更新
（3）进度提示
（4）自动安装
```

#### iOS
```xml
（1）版本检测
（2）自动跳转App Store
```

### 二、使用

```xml
  yarn add react-native-app-upgrade
```

iOS
打开Xcode, 将 ios_upgrade 导入到项目目录。


```javascript
  import { 
    upgrade,
    versionName,
    versionCode,
    openAPPStore,
    checkIOSUpdate,
    addDownLoadListener,
  } from 'react-native-app-upgrade';
  
  //可通过RN.versionName获取apk版本号和远程版本号进行比较
  if(Android) {
    if(res.versionCode > versionCode) {
      upgrade(res.apkUrl);
    }
  } else {
    const IOSUpdateInfo = await checkIOSUpdate(appid, 1.0.0);
    console.log(
      IOSUpdateInfo.code,
      IOSUpdateInfo.msg,
      IOSUpdateInfo.version,
    )
  }
```

如果需要接收下载进度，可通过如下方式：
```javascript
   addDownLoadListener((progress) => {});
```
