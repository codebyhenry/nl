omdat er wat vragen waren over waar je het beste een git repo kan plaatsen op je computer hier zijn een paar tips.

er zijn grofweg 4 manieren.

1. onder je HOME (sub)dir
2. in een ROOT (sub)dir
3. externe schijf
4. extern in de cloud (meer handig voor CI/CD)

Alles wat je in de home directory doet is userspace, dat wil zeggen dat toegang beperkt is tot de gebruiker en steeds vaker standaard encypted is. Voordeel is wel dat folders in userpace worden meegenomen in backups.

```
  
  tip: 
maak jezelf bekend met "environment variables" voor jou systeem,
  dit is ook de standaard entry folder voor SSH.

```  

windows: %HOME% (test in terminal met echo %HOME%)
mac/linux: $HOME (test in terminal met echo $HOME)

Zet je het in een root directory, dan is dit systemwide beschikbaar. dat kan handig zijn als je meerdere login accounts hebt op de computer.

```
windows: c:\werkfolder\projectfolder
mac/linux: /werkfolder/projectfolder
```

andere manieren zijn de externe oplossingen. 

In windows krijg een usb drive dus zoiets als 
```
E:\werkfolder\projectfolder
```

sync vs mounten
zet je de werkfolder in de lokale onedrive folder
via de terminal : %OneDrive%\werkfolder\projectfolder
dan staat je data dus op 2 plekken.

Met een NAS of hosting/cloud provider kun je externe opslag ook lokaal mounten, de data staat dan nog steeds elders op 1 plek, maar zodra je verbonden bent werkt het grotendeels als een gewone lokale folder. 

voor externe host/cloud is een SSH (sftp) verbinding de meest veilige methode. 

NOTE: bedenk wel dat herverbinden soms tricky kan zijn, vooral als de verbinding wegvalt via het editten.

er zijn desktop (GUI) tools zoals nsoftware SSHdrive en cyberduck voor windows en mac, linux kan standaard via de filemanager mounten. 

Een professionelere setup valt buiten deze scope, maar wil je remote toegang tot je lokale werkfolder, dan kun het beste met tailscale een eigen netwerk opzetten. Dit is een moderne VPN oplossing, waar je in notime een veilige IP verbinding mee opzet. Voor SSH heb je wel een server nodig.

een NAS heeft deze standaard ingebouwd. Daarop kun je ook je eigen dev en test omgevingen bouwen met behulp van docker. je heb je niet veel nodig, een oudere laptop of low power single board computer met een linux variant erop zoals proxmox of truenas is al goed genoeg. Meest belangrijke is voldoende (minimaal 4) ram en processor cores, gpu is onbelangrijk voor html,js en php zaken.

Bouw je standalone (zoals android/java) applicaties of dingen die veel rekenwerk doen als machinelearing met dall-e of wil je druk bezochte ecommerce sites hosten, dan kun je met betere container technieken zoals kubernetes meer hardware inzetten en zo je eigen homelab opschalen en uitbouwen.







