<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Installare Windows su Xiaomi Mi Pad 5

## Installazione

### Prerequisiti

- [```Immagine Recovery```](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)

- ``` Bootloader sbloccato```

- ```Cervello```

### Note: 

> [!NOTE]\
>  Non sai da dove cominciare? 
- Estrai la cartella [```Android platform tools```](https://developer.android.com/studio/releases/platform-tools)
- Apri il ```prompt dei comandi``` o `powershell` con privilegi di amministratore ed esegui i seguenti comandi sostituendo `"percorso\a\platform-tools"` con il percorso effettivo alla cartella di `platform-tools`:

```cmd
cd "percorso\a\platform-tools"
```
> Ricorda di usare questo terminale per tutta la durata dell'operazione e non chiuderlo.


> [!WARNING]\
> Se elimini una qualsiasi partizione tramite diskpart in qualsiasi momento, Windows invierá un comando UFS che verrá interpretato erroneamente, il quale cancellerá il tuo UFS!
> 
> Tutti i tuoi dati verranno eliminati! Salvali ora se ne hai bisogno.
> 
> NON RIAVVIARE IL TUO DISPOSITIVO! se pensi di aver commesso un errore, chiedi aiuto nella [chat Telegram](https://t.me/nabuwoa)
> 
> PLEASE DON'T USE OUTDATED VIDEO GUIDES ON YOUTUBE OR ANY OTHER PLATFORM! THESE VIDEOS ARE OUTDATED AND YOU CAN BRICK YOUR DEVICE USING THEM! IF YOU NEED A VIDEO GUIDE, USE THIS NEW VIDEO GUIDE FROM ArtoSeVeN

NON UTILIZZARE GUIDE SU YOUTUBE O ALTRE PIATTAFORME! QUESTI VIDEO SONO OBSOLETI E POSSONO BRICKARE IL TUO DISPOSITIVO SE UTILIZZATI! SE HAI BISOGNO DI UNA VIDEO GUIDA, USA QUESTA [NUOVA GUIDA](https://youtu.be/BbgTbTGbXYg) CREATA DA [ArtoSeVeN](https://www.youtube.com/channel/UCYjwfxlYlJ7Nnzv01oszQvA)


#### Avvia la recovery tramite PC con il seguente comando:
```cmd
fastboot boot <recovery.img>
```
 ### Esegui lo script di partizionamento

> Se ti viene chiesto di eseguirlo due volte, allora procedi.
>
> Questa parte è **facoltativa** ma puoi personalizzare la dimensione della partizione utilizzando questo script.
>
> Per personalizzare la dimensione esegui: ```adb shell partition[DIMENSIONE DI WINDOWS IN GB]```



> Ricorda di non aggiungere `GB` alla fine, inserisci solo il numero


```cmd
adb shell partition
```

### Effettua un backup dell'immagine di boot esistente 
```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/normal_boot.img" && adb pull /tmp/normal_boot.img
```


#### Controlla se Android si avvia ancora 
> Riavvia per verificare se Android funziona ancora. Se non si avvia, cancella tutti i dati tramite recovery e riprova. 

```cmd
adb reboot
```


### [Prossimo passaggio: Ottieni permessi di root](/guide/Italian/2-rootguide-it.md)
