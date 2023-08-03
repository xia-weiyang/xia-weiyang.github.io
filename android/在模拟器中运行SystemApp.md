### 在模拟器中运行System App

https://blog.csdn.net/LyamAL/article/details/104538901

- 新建模拟器时，Images不能包含Google APIs，否则系统签名的apk将安装不上

- 使用如下命令运行模拟器
  D:\Android\Sdk\emulator\emulator.exe -writable-system -avd Pixel_C_API_28_2 -no-snapshot-load -qemu

- 使用adb运行如下命令
  
  ```
  adb root
  adb remount
  adb shell
  su
  // 以下两句可能失败，但最终以能将apk拷贝到/system/app目录下为准
  chmod 777 system
  mount -o rw,remount -t auto /system
  ```

如果还不行重启模拟器

### 系统签名

https://juejin.cn/post/7052229760503513095
