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
```ps1
# Define ou atualiza a variável FLUTTER_HOME no escopo do usuário
[Environment]::SetEnvironmentVariable("FLUTTER_HOME", "$env:USERPROFILE\dev\flutter", "User")

# Recupera o PATH atual do usuário
$oldPath = [Environment]::GetEnvironmentVariable("Path", "User")

# Define o novo caminho do Flutter (diretório bin)
$flutterBin = "$env:USERPROFILE\dev\flutter\bin"

# Remove todas as entradas do PATH que contenham "\dev\flutter\bin" (evitando duplicatas ou caminhos antigos)
$filteredPaths = $oldPath -split ';' | ForEach-Object { $_.Trim() } | Where-Object { $_ -and ($_ -notlike "*\dev\flutter\bin*") }

# Monta o novo PATH, colocando o diretório Flutter no início
$newPath = "$flutterBin;" + ($filteredPaths -join ';')

# Atualiza a variável de ambiente Path no escopo do usuário
[Environment]::SetEnvironmentVariable("Path", $newPath, "User")
```

# Setup

```sh
where flutter dart
```


```sh
# https://developer.android.com/tools/variables?hl=pt-br#set
# https://developer.android.com/studio/intro/update?hl=pt-br#sdk-manager

cd $env:USERPROFILE\AppData\Local\Android\Sdk\cmdline-tools\latest\bin
./sdkmanager --install "cmdline-tools;latest"
```

```sh
flutter doctor --android-licenses
```

```sh
flutter doctor
flutter doctor -v
```
```sh
flutter upgrade
```


## Upgrading packages

### To update to the latest compatible versions of all the dependencies listed in the pubspec.yaml file

```sh
flutter pub upgrade
```

### To update to the latest possible version of all the dependencies listed in the pubspec.yaml file
```sh
flutter pub upgrade --major-versions
```

## Configurando novas plataformas


```sh
flutter config --enable-windows-desktop
flutter config --enable-linux-desktop
flutter config --enable-macos-desktop
flutter config --enable-web
flutter config --enable-android
flutter config --enable-ios
```

```sh
flutter config --no-enable-windows-desktop
flutter config --no-enable-linux-desktop
flutter config --no-enable-macos-desktop
flutter config --no-enable-web
flutter config --no-enable-android
flutter config --no-enable-ios
```

## Executando em outras plataformas

```sh
flutter run -d windows
flutter run -d macos
flutter run -d linux
```

## Criando projetos

```sh
flutter create project_sample_1
```

```sh
flutter create -e project_sample_2
```
