<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Windows no the Xiaomi Pad 5

## Atualizando Drivers

### Pré requesitos


- [```Imagem do UEFI```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/UEFI/uefi-v3.img)

- [```Imagem do Recovery```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```Drivers```](https://github.com/map220v/MiPad5-Drivers/releases/latest)

### Inicie o recovery usando seu PC com o comando

```cmd
fastboot boot <recovery.img>
```


### Execute o msc
> Se o comando disser pra fazer de novo, faça
```cmd
adb shell msc
```

### Atribua letras aos discos

#### Inicie o gerenciador de discos do Windows

> Quando o seu Xiaomi Pad 5 for detectado como um disco use

```cmd
diskpart
```


### Atribua a letra `X` para o volume Windows

#### Selecione o volume Windows do tablet
> Use `list volume` para encontrá-lo, é o que tem o nome de "WINNABU"

```diskpart
select volume <número>
```

#### Atribua a letra X
```diskpart
assign letter x
```

### Saia do diskpart
```diskpart
exit
```


### Instalar os Drivers

> Você pode fazer o download dos drivers [aqui](https://github.com/map220v/MiPad5-Drivers/releases/latest)

> Se aparecer `"Automatic WINNABU detection failed! Enter Drive Letter manually"` digite **`X`**
```cmd
 abra a pasta dos Drivers e inicie o OfflineUpdater.cmd
```

### Reinicie para o bootloader e faça o flash da imagem UEFI
> Ou se o UEFI já está instalado, apenas reinicie com ```adb reboot```
```cmd
adb reboot bootloader
```

#### Inicie o Windows com a imagem UEFI
> Substitua <uefi.img> com o caminho correto para o arquivo da imagem UEFI
```cmd
fastboot flash boot <uefi.img>
```

## Concluído!









