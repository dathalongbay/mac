# mac

2. Cài đặt node_modules

```sh
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
  gradlew clean
  ```
- Build bản Release:
  ```sh
  gradlew assembleRelease
  ```
- Bản cài sẽ nằm ở đường dẫn: android/app/build/outputs/apk/release/app_release.apk

## Build bản phát hành
