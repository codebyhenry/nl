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

```
windows: %HOME% (test in terminal met echo %HOME%)
mac/linux: $HOME (test in terminal met echo $HOME)

```
zoals je ziet is de HOME in hoofdletters, in de terminal commands zijn vaak hoofdletter gevoelig, een Home of home zijn dus  andere folders of commando's dan HOME

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

### sync vs mounten
zet je de werkfolder in de lokale onedrive folder dan kan je via de terminal de OneDrive ENV gebruiken, met sync staat je data dus op 2 plekken.

` %OneDrive%\werkfolder\projectfolder ` 

Met een NAS of hosting/cloud provider kun je externe opslag ook lokaal mounten, anders dan bij de sync manier, staat je data elders op 1 plek, zodra je verbonden bent werkt de mount folder grotendeels als een gewone lokale folder. 

voor extern hosting/cloud is een SSH (sftp) verbinding de meest gebruikte methode. Je kan ook een "poor mans VPN" opzetten via een ssh tunnel, je data wordt dat veilig versleuteld verzonden tussen je pc en de cloud, de verbinding is vaak wat stabieler. 

NOTE: bedenk wel dat herverbinden soms tricky kan zijn, vooral als de verbinding wegvalt via het editten. dat kan bijvoorbeeld gebeuren door een slechte wifi verbinding of een instelling dat auto disconnect. 

er zijn desktop (GUI) tools zoals [nsoftware SSHdrive](https://www.nsoftware.com/sftp/drive/) en [cyberduck voor windows en mac](https://cyberduck.io), linux kan standaard via de filemanager mounten. 

Een professionelere setup valt buiten deze scope, maar wil je remote toegang tot je lokale werkfolder, dan kun het beste met tailscale een eigen netwerk opzetten. Dit is een moderne VPN oplossing, waar je in notime een veilige IP verbinding mee opzet. Voor SSH heb je wel een server nodig.

een NAS heeft deze standaard ingebouwd. Daarop kun je ook je eigen dev en test omgevingen bouwen met behulp van docker. je heb je niet veel nodig, een oudere laptop of low power single board computer met een linux variant erop zoals proxmox of truenas is al goed genoeg. Meest belangrijke is voldoende (minimaal 4) ram en processor cores, gpu is onbelangrijk voor html,js en php zaken.

Bouw je standalone (zoals android/java) applicaties of dingen die veel rekenwerk doen als machinelearing met dall-e of wil je druk bezochte ecommerce sites hosten, dan kun je met betere container technieken zoals kubernetes meer hardware inzetten en zo je eigen homelab opschalen en uitbouwen.

## Github Repo, codespaces, gists

Github is de microsoft cloud oplossing voor git, net als bij google docs of MS 365 staan je documenten in de cloud. Github heeft 2 mogelijkheden. je kan kleine stukjes code in een gist posten, als een soort note zoals je met google keep kleine snippets kan bewaren. voor projecten kun je mappen aanmaken onder repositories. 

`git clone github.com/<USERNAME>/<REPO> ` spatie aanvullend een dot om het in de huidige map te klonen of foldername,  clone je lokaal de repo in je repo naam. 

note: de dot heeft dus net als bij code . eenzelfde functie, je zegt tegen de terminal open een programma (in dit voorbeeld dus VScode) met de huidige werkfolder. dat is handig als je vanuit de terminal werkt, je kan ook de folder slepen naar VScode.






