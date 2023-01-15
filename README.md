# KDE NEON (UBUNTU 22.04 LTS BASE): after install
Things to do after installing KDE Neon Operating System. <br/>
Tested version: KDE Neon 5.26 (based on Ubuntu 22.04.1 LTS) <br/>
https://kubuntu.org/alternative-downloads/

<br/>

## 1 ➜ DOWNLOAD .DEB PACKAGES
**VS Code:** https://code.visualstudio.com/download/ <br/>
**PowerShell:** https://github.com/PowerShell/PowerShell#get-powershell <br/>
**Google Chrome:** https://www.google.com/chrome/browser/desktop/ <br/>
**WPS Office (BR Stable):** https://github.com/aldebaranbm/wpsoffice-linux_pt-br/releases/tag/11.1.0.8865 <br/>
**Spotify:** https://www.spotify.com/br/download/linux/ <br/>
**OpenRGB:** https://openrgb.org/releases.html

<br/>

## 2 ➜ RUN COMMANDS IN TERMINAL

	xdg-user-dirs-update && 

	sudo apt update && 

	# sudo apt install kde-l10n-ptbr -y && 			# ALREADY INCLUDED IN KUBUNTU 22.04
	# sudo apt install software-properties-common -y && 	# ALREADY INCLUDED IN KUBUNTU 22.04
	# sudo apt install libreoffice-l10n-pt-br -y && 
	# sudo apt install libreoffice-style-sifr -y && 

	sudo apt install kubuntu-restricted-extras -y && 
	sudo apt install build-essential dkms git-all bc -y && 
	sudo apt install unace unrar zip unzip p7zip-full p7zip-rar sharutils rar -y && 
	sudo apt install bleachbit -y && 
	sudo apt install krusader -y && 
	sudo apt install kcalc -y && 
	sudo apt install kolourpaint -y && 
	sudo apt install kpat ksudoku quadrapassel lskat -y && 

	sudo apt update && 

	sudo add-apt-repository ppa:numix/ppa -y && 
	sudo add-apt-repository ppa:danielrichter2007/grub-customizer -y && 
	sudo add-apt-repository ppa:qbittorrent-team/qbittorrent-stable -y && 
	sudo add-apt-repository ppa:inkscape.dev/stable -y && 

	sudo apt update && 

	sudo apt install numix-icon-theme numix-icon-theme-circle -y && 
	sudo apt install grub-customizer -y && 
	sudo apt install qbittorrent -y && 
	sudo apt install inkscape -y

> Join lines using Sublime Text or VS Code shortcut `CTRL + J`. Then run all commands at once. <br/>
> Or join lines online:
https://www.browserling.com/tools/join-lines

<br/>

### 2.1 – REALTEK RTL8821CU WI-FI DRIVER
	# INSTALL BELOW IF YOU DON'T HAVE IT YET #
	sudo apt install build-essential dkms git-all bc -y
	
	# OPEN DRIVER FOLDER IN TERMINAL #
	
	sudo su
	make
	sudo make install
	sudo reboot

- Source 1: https://github.com/brektrou/rtl8821CU
- Source 2: https://www.youtube.com/watch?v=tyLMzIAxj-4
- Source 3: https://github.com/jcqSCH/kubuntu-after/blob/main/ZIP_Driver_RTL8821CU_RAW.7z

<br/>

### 2.2 – ~WPS OFFICE TRANSLATION PT-BR~
	# OPEN TRANSLATION FOLDER IN TERMINAL #

	bash install.sh

- ~Source 1: https://github.com/vaamonde/pt_br-wpsoffice~
- ~Source 2: https://www.youtube.com/watch?v=PzIgNdJDdFE~
- ~Source 3: https://github.com/jcqSCH/kubuntu-after/blob/main/ZIP_Translation_WPS_Office_PT-BR.7z~

<br/>

## 3 ➜ SETTINGS

### 3.1 – To do:
- Disable screen edges;
- Disable wallet application;
- Enable 2 clicks to open files;
- Enable Num Lock by default;
- Enable New Session when restarting system;
- Configure Dolphin to always start a new session when reopening the application;

<br/>

### 3.2 – Appearance:
Global Themes:			<br/>
✔ We10XOS-dark			<br/>
● ChromeOS-dark			<br/>
● Willow Desktop (Light)	<br/>
● Layan				<br/>
● Orchis-dark			<br/>
● Itchy				<br/>
● Scratchy			<br/>
● Win11OS-Nord			<br/>


Application Style: <br/>
✔ Breeze <br/>

Application Style: <br/>
✔ ChromeOSLight <br/>

Window Decorations: <br/>
✔ Breeze <br/>

Fonts: <br/>
✔ Inter <br/>
✔ Maax Mono <br/>

Icons: <br/>
✔ Willow Light <br/>

Cursors: <br/>
✔ Capitaine Cursors <br/>

<br/>

### 3.3 – Plank:
Download themes: https://github.com/dabrowski-adam/plank-themes

|  SETTINGS        |             …             |
|       ---        |            ---            |
|  Theme:          |  Shade                    |
|  Icons:          |  68                       |
|  Zoom:           |  125                      |

>**Ordem:** Dolphin, Terminal, Spotify, Firefox, Chrome, VS Code, KCalc, Writer, Impress, KSysGuard, System Settings

<br/>

### 3.4 – Barra Superior:
>**Ordem:** Menu de Aplicativos, Gerenciador de Tarefas com Ícones, Lixeira, Área de Notificação, Bloquear/Encerrar, Relógio, Área de Trabalho

<br/>

### 3.5 – Spotify:
	sudo kate /usr/share/applications/spotify.desktop
>**Substituir:** Exec=spotify %U <br/>
>**Por:** Exec=spotify %U --force-device-scale-factor=1.25

<br/>

## 4 ➜ HINTS

### 4.1 – Open folder as Administrator:
Open Krusader ➜ Tools ➜ Start Root Mode Krusader (**ALT + SHIFT + K**)
- Source: https://askubuntu.com/questions/990611/how-to-run-dolphin-as-root/1048826#1048826

<br/>

### 4.2 – Unmount the Windows partition while logged into Ubuntu (or derivatives):
	mount -o ro /dev/sda2
> Edit `sda2` above if that's not the partition your Windows is installed on.
- Source: https://askubuntu.com/questions/335909/error-mounting-dev-sda2-at-media/335922#335922

<br/>

### 4.3 – Check the video driver installed
	lspci -k | grep -EA3 'VGA|3D|Display'
> The `VGA|3D|Display` stands for `INTEL|NVIDIA|AMD` respectively.

<br/>

### 4.4 – Fix the bug "Can't move files to the trash":
	sudo chown -R “$USER” ~/.local/share/Trash
> Edit the `“$USER”` part above and enter your Ubuntu username (without quotes).
- Source: https://askubuntu.com/questions/288513/cant-move-files-to-the-trash/298335#298335

<br/>

### 4.5 – Recover lost GRUB after a Windows update (dual boot):
	bcdedit /set "{bootmgr}" path \EFI\ubuntu\grubx64.efi
> Logged into Windows, run the command above in PowerShell as Administrator.
- Source: https://askubuntu.com/questions/655011/windows-10-upgrade-kills-grub-and-boot-repair-doesnt-help/655279#655279

<br/>
