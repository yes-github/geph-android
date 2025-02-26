_Geph Android_

#### 代码修改点说明
- 改动点标记`// HACK：`
- 主要改动点：
    - 默认打开`排除中国大陆流量`
    - 黑名单改为白名单：添加允许访问VPN连接的应用程序

#### 编译步骤
```bash
# 下载子模块
git submodule update --init --recursive

# 安装最新版nodejs
curl -sL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt-get install -y nodejs

# 编译子模块gephgui
cd gephgui/
npm install
npm run build

# 修改gephgui代码后需要重新编译
npm run build

# 切换到Ubuntu下进行编译
export JAVA_HOME=/home/ye/tmp/jdk-17.0.14+7
export ANDROID_HOME=/home/ye/tmp/android/android-sdk
export HTTP_PROXY=http://192.168.32.66:19910
export HTTPS_PROXY=https://192.168.32.66:19910

# debug -> app/build/outputs/apk/debug/app-debug.apk
./gradlew :app:assembleDebug --no-build-cache

# release
./gradlew :app:assembleRelease
```