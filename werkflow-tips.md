omdat er wat vragen waren over waar je het beste een git repo kan plaatsen op je computer hier zijn een paar tips.

er zijn grofweg 4 manieren.

1. onder je HOME (sub)dir
2. in een ROOT (sub)dir
3. externe schijf
4. extern in de cloud (meer handig voor CI/CD)

Alles wat je in de home directory doet is userspace, dat wil zeggen dat toegang beperkt is tot de gebruiker en steeds vaker standaard encypted is. Voordeel is wel dat folders in userpace worden meegenomen in backups.

`TIP: maak jezelf bekend met [environment variables] voor jou systeem, dit is ook de standaard entry folder voor SSH.`
	
```  
	windows: %HOME% (test in terminal met echo %HOME%)
	mac/linux: $HOME (test in terminal met echo $HOME)
```
	
zoals je ziet is de HOME in hoofdletters, in de terminal commands zijn vaak hoofdletter gevoelig, een Home of home zijn dus  andere folders of commando's dan HOME. Zet je het in een root directory, dan is dit systemwide beschikbaar. dat kan handig zijn als je meerdere login accounts hebt op de computer.

```
windows: c:\werkfolder\projectfolder
mac/linux: /werkfolder/projectfolder
```

andere manieren zijn de externe oplossingen. 

In windows krijg een usb drive dus zoiets als:

```
E:\werkfolder\projectfolder
```

## sync vs mounten
zet je de werkfolder in de lokale onedrive folder dan kan je via de terminal de OneDrive ENV gebruiken, met sync staat je data dus op 2 plekken.

`%OneDrive%\werkfolder\projectfolder` 

Met een NAS of hosting/cloud provider kun je externe opslag lokaal mounten, anders dan bij de sync manier, staat je data elders op 1 plek, zodra je verbonden bent werkt de mount folder grotendeels als een gewone lokale folder. 

Voor extern hosting/cloud is een SSH (sftp) verbinding de meest gebruikte methode. ook voor een "poor mans VPN" via een ssh tunnel, data wordt dan veilig versleuteld verzonden tussen je pc en de cloud, de verbinding is vaak wat stabieler. 

NOTE: bedenk wel dat herverbinden soms tricky kan zijn, vooral als de verbinding wegvalt via het editten. dat kan bijvoorbeeld gebeuren door een slechte wifi verbinding of een instelling dat auto disconnect. 

Er zijn desktop (GUI) tools zoals [nsoftware SSHdrive](https://www.nsoftware.com/sftp/drive/) en [cyberduck](https://cyberduck.io), linux kan standaard via de filemanager mounten. hiervoor moet dan wel de sshd_config worden bewerkt en de firewall moet de ssh poort toegang geven.

## Webstacks
Een professionelere setup valt buiten deze scope, maar wil je veilig remote toegang tot je lokale werkfolder zonder poort forwarden, dan kun het beste met [tailscale](https://tailscale.com),[wireguard](https://wireguard.com) of [teleport](https://goteleport.com) je eigen ZeroTier netwerk opzetten. Dit zijn een moderne verbindingen. 

note: [bekijk deze korte deepdive](https://www.youtube.com/watch?v=Sxxw3qtb3_g&t=1s) over webstacks.


Een linux NAS heeft dergelijke functies vaak standaard ingebouwd of is makkelijk toe te voegen. Daarop kun je ook je eigen dev en test omgevingen bouwen met behulp van docker. Veel is daarvoor niet nodig, een oudere laptop of low power single board computer met een linux variant erop zoals proxmox of truenas is al goed genoeg. Meest belangrijke is voldoende (minimaal 4) ram en processor cores, gpu is onbelangrijk voor html,js en php zaken.

Bouw je standalone (zoals android/java) applicaties en apps die veel rekenwerk vragen zoals compilen van sourcecode of ga je met dall-e (Machine Learing) aan de slag of wil je druk bezochte ecommerce sites hosten, dan kun je met betere container-technieken zoals kubernetes meer hardware clusteren en zo je eigen homelab en netwerk opschalen en uitbouwen.

### Github Repo, codespaces, gists
Github is de microsoft cloud oplossing voor git, net als bij google docs of MS 365 staan je documenten in de cloud. Github heeft 2 mogelijkheden. je kan kleine stukjes code in een gist posten, als een soort note zoals je met google keep kleine snippets kan bewaren. voor projecten kun je mappen aanmaken onder repositories. 

`git clone github.com/<USERNAME>/<REPO>` 

je kan een spatie en dot gebruiken om de clone in de huidige map te plaatsen of foldernaam of $HOME/folder

bijvoorbeeld:

```
git clone https://github.com/codebyhenry/nl $HOME/test
```








