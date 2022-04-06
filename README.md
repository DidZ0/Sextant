# TP Sextant

## Installation de git
### Windows
* Installer 'Git for Windows' pour avoir git et un shell (git bash)
    * https://gitforwindows.org/
### Ubuntu
* `sudo apt install git`
### MACOS

Il faut installer le gestionnaire de paquet [https://brew.sh/](https://brew.sh/) pour pouvoir récupérer les dépendences logicielles.

#### Installation de brew

Ouvrez un terminal (`CMD` + `Espace` puis entrez `terminal`):
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

vérifier que l'installation a fonctionné en entrant la commande `brew` dans le terminal:
```bash
➜  TP1 git:(master) ✗ brew -v
Homebrew 2.2.10
Homebrew/homebrew-core (git revision 373b0; last commit 2020-03-25)
Homebrew/homebrew-cask (git revision 9949e; last commit 2020-03-25)
```

#### Installation des dépendences logicielles

Dans un terminal entrez la commande suivante pour install QEMU:
```shell
brew install qemu
```

Puis installer les outils de compilation elf avec les commandes suivantes:
```shell
brew tap nativeos/i386-elf-toolchain
brew install i386-elf-binutils i386-elf-gcc
```

## Démarrage avec Visual Studio Code
* Installer l'éditeur de code Visual Studio Code (VS Code)
    * https://code.visualstudio.com/download
* Ouvrir VSCode
* Ouvrir l'exécuteur de commande: `View > Command Palette` ou `Ctrl + Shift + P`
* Entrer 'clone' et exécuter la commande `Git: clone`
* Entrer l'URL `git@github.com:sextant-tpx/TPX.git`
* Installer l'extension 'C/C++'(ms-vscode.cpptools)
    * Ouvrir le panneau extension : `View > Extensions` ou `Ctrl + Shift + X`
    * Entrer 'C/C++' ou 'ms-vscode.cpptools' dans la barre de recherche
    * Cliquer sur `Install`

## Exécution des tâches
* Les tâches sont définies dans `.vscode/tasks.json`
* Exécuter d'une tâche
    * Ouvrir l'exécuteur de commande: `View > Command Palette` ou `Ctrl + Shift + P`
    * Choisir `Run Task`
    * Sélectionner la tâche à exécuter


# Adapt

# Build sextant
$ make
# Run sextant 
$ cd build/boot; qemu-system-x86_64 -net nic,model=ne2k_isa -net user,tftp=./ -cdrom grub.iso
# Debug sextant 
$ cd build/boot; qemu-system-i386 -S -s -net nic,model=ne2k_isa -net user,tftp=./ -cdrom grub.iso 
# Run sextant no graphic 
$ cd build/boot; qemu-system-x86_64 -curses -net nic,model=ne2k_isa -net user,tftp=./ -cdrom grub.iso



pour lancer qemu en ligne de commande
il faut taper une des trois commandes
qemu-system-x86_64 -net nic,model=ne2k_isa -net user,tftp=./ -cdrom grub.iso
démarre qemu avec une carte réseau :  -net nic,model=ne2k_isa
démarre un "faux" serveur tftp qui pointe en local : tftp=./
et démarre une image disque de cdrom : -cdrom grub.iso
Avant de démarrer qemu, il faut bien sur avoir compilé le noyau avec la commande make
# Sextant
# Sextant
