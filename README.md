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
