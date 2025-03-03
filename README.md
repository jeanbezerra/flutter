# flutter

## Dowload

```ps1
wget https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_3.29.0-stable.zip
```

## Install

```ps1
Expand-Archive `
      –Path $env:USERPROFILE\Downloads\flutter_windows_3.29.0-stable.zip `
      -Destination $env:USERPROFILE\dev\
```

# Setup

```sh
where flutter dart
```

```sh
flutter doctor
```

```sh
flutter doctor --android-licenses
```
