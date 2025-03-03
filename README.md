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

# Obtém o valor atual da variável Path do usuário
$oldPath = [Environment]::GetEnvironmentVariable("Path", "User")

# Cria o novo path do Flutter (diretório bin)
$newPathEntry = "$env:FLUTTER_HOME\bin"

# Se o diretório não estiver presente, adiciona-o no início do Path
if ($oldPath -notlike "*$newPathEntry*") {
    [Environment]::SetEnvironmentVariable("Path", "$newPathEntry;$oldPath", "User")
}
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
