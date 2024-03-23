# Windows

1° Ativar Virtualização - Habilitar o Hyper-V


## PowerShell
```
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V -All
 ```


## Cmd
```
DISM /Online /Enable-Feature /All /FeatureName:Microsoft-Hyper-V
```


2º Baixar o WSL


```
wsl --install
```

### Verificar a versão do WSL

```
wsl -l -v
```


### Atualizar a versão do WSL 1 para o WSL 2




## _Comandos Compose_
    docker-compose -f docker-compose-online.yml up
    docker-compose -f docker-compose-online.yml down
    docker-compose build

    docker cp
    docker compose watch
    docker compose watch ./docker-compose.yml
