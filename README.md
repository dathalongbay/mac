# mac

1. lấy code mới nhất từ git
```
git fetch --all
git checkout dev
git pull
```

3. Cài đặt node_modules

```sh
rm -rf node_modules
yarn install
```

3. Cài đặt Pod cho IOS

```sh
cd ios
pod install
```

## Khởi chạy dự án trên máy ảo

- IOS:

```sh
npm run ios
```

- Android:

```sh
npm run android
```

## Khởi chạy dự án trên thiết bị thật

### IOS

Build ứng dụng thông qua Xcode và đẩy lên Testflight.

### Android

- Cd tới thư mục android và clean các dữ liệu cũ:
  ```sh
  cd android
  ./gradlew clean
  ```
- Build bản Release:
  ```sh
  ./gradlew assembleRelease
  ```
- Bản cài sẽ nằm ở đường dẫn: android/app/build/outputs/apk/release/app_release.apk

## Build bản phát hành

### Android

- Build bản bundleRelease và tải lên play console
  ```sh
  ./gradlew bundleRelease
  ```
- Bản cài sẽ nằm ở đường dẫn: android/app/build/outputs/apk/bundle/app-release.aab
## Lỗi khi chạy pod install
- Khắc phục: 
Chạy lệnh pod deintegrate để clean sau đó chạy pod install lại: ./gradlew clean
Chạy pod repo update để cập nhật lại phiên bản cho các pod
```
## Thay config để build android để có file name theo version và versionCode đúng
```defaultConfig {
        applicationId "com.tp.loigiaihay"
        minSdkVersion rootProject.ext.minSdkVersion
        targetSdkVersion rootProject.ext.targetSdkVersion
        versionCode 236
        versionName "2.4.8"
        vectorDrawables.useSupportLibrary = true
        setProperty("archivesBaseName", applicationId + "-v" + versionCode + "(" + versionName + ")")
    }```

## Lỗi thư viện trên ios
```
dòng 44 sửa thành thế này khi build gặp lỗi
static YGSize RNDateTimePickerShadowViewMeasure(YGNodeRef node, float width, YGMeasureMode widthMode, float height, YGMeasureMode heightMode)
{
```
## với ios làm theo chỉ dẫn sau để cài đặt lại thư viện pod
```cd ios
pod deintegrate
pod install```
