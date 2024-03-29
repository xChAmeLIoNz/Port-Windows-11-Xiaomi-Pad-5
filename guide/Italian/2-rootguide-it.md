<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Installare Windows su Xiaomi Mi Pad 5

## Ottieni permessi di root
> [!NOTE]
> **Se hai i permessi di root, salta questo passaggio e vai alla pagina successiva**

### Prerequisiti
- ```Cervello```
  
- [```Backup immagine boot di Android```](/guide/Italian/1-partition-it.md#Effettua-un-backup-della-partizione-di-boot) (della quale hai eseguito il backup nella prima pagina della guida)


## Patch immagine boot

- Copia il ```normal_boot.img``` file dalla cartella ```platform tools``` sul tablet


- Scarica e installa [Magisk Manager](https://github.com/topjohnwu/Magisk/releases/latest) sulla dispositivo
  
-  Apri Magisk e fai clic sul pulsante ```Install```. Seleziona l'opzione ```Select and Patch a File``` e trova il file ```normal_boot.img``` che hai copiato in precedenza sul tablet. Clicca il pulsante ```Let's Go``` e attendi il completamento del processo di patch.
  
- Copia il file```magisk_patched....img``` dalla cartella ```Downloads``` sul tablet, alla cartella ```platform tools``` sul tuo computer.

- Riavvia il dispositivo in modalità fastboot
  
- Apri il prompt dei comandi nella cartella dei `platform-tools` 

 ## Esegui il flash dell'immagine appena modificata
 > Sostituisci `<magisk_patched.img>` con l'effettivo percorso di ```magisk_patched.img```.
```cmd
fastboot flash boot <magisk_patched.img>
```

### [Passaggio successivo: installazione di Windows](/guide/Italian/3-install-it.md)
