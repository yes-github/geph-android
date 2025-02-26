_Geph Android_

#### 编译前准备
- [NDK下载](https://github.com/android/ndk/wiki/Unsupported-Downloads#r19c)
#### 编译步骤
```bash
# 切换到Ubuntu下进行编译
export JAVA_HOME=/home/ye/tmp/jdk-17.0.14+7
export ANDROID_HOME=/home/ye/tmp/android/android-sdk
export HTTP_PROXY=http://192.168.32.66:19910
export HTTPS_PROXY=https://192.168.32.66:19910
./gradlew :app:assembleDebug
```