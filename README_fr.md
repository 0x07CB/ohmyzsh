# Oh My Zsh

<p align="center"><img src="https://ohmyzsh.s3.amazonaws.com/omz-ansi-github.png" alt="Oh My Zsh"></p>

Oh My Zsh est un framework open source, porté par la communauté, destiné à la gestion de votre configuration zsh.

Cela semble ennuyeux. Réessayons.

> **Oh My Zsh ne fera pas de vous un développeur 10x… mais vous pourriez avoir cette impression.**

Une fois installé, votre terminal deviendra la coqueluche du quartier *ou remboursé !* À chaque frappe dans votre invite de commande, vous profiterez de centaines de plugins puissants et de magnifiques thèmes. Des inconnus viendront vous voir dans les cafés pour vous demander :

> « C’est incroyable ! Êtes-vous une sorte de génie ? »

Enfin, vous commencerez à recevoir l’attention que vous avez toujours estimé mériter. …ou peut-être utiliserez-vous le temps gagné pour passer plus régulièrement du fil dentaire. 😬

---

## Table des matières

* Premiers pas

  * Compatibilité des systèmes d’exploitation
  * Prérequis
  * Installation de base

    * Inspection manuelle
* Utilisation d’Oh My Zsh

  * Plugins

    * Activer les plugins
    * Utiliser les plugins
  * Thèmes

    * Choisir un thème
  * FAQ
* Sujets avancés
* Mises à jour
* Désinstallation
* Contribution
* Contributeurs
* Réseaux sociaux
* Produits dérivés
* Licence

---

# Premiers pas

## Compatibilité des systèmes d’exploitation

| Système        | Statut |
| -------------- | :----: |
| Android        |    ✅   |
| FreeBSD        |    ✅   |
| LCARS          |   🛸   |
| Linux          |    ✅   |
| macOS          |    ✅   |
| OS/2 Warp      |    ❌   |
| Windows (WSL2) |    ✅   |

## Prérequis

* **Zsh** doit être installé (version 4.3.9 minimum ; 5.0.8 ou plus recommandée).
* **curl** ou **wget** doit être disponible.
* **git** doit être installé (version 2.4.11 ou supérieure recommandée).

## Installation de base

Oh My Zsh s’installe en exécutant l’une des commandes suivantes :

| Méthode   | Commande                                                                                          |
| --------- | ------------------------------------------------------------------------------------------------- |
| **curl**  | `sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"` |
| **wget**  | `sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`   |
| **fetch** | `sh -c "$(fetch -o - https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"` |

### Miroir alternatif

Si `raw.githubusercontent.com` est bloqué dans votre pays, utilisez :

| Méthode   | Commande                                          |
| --------- | ------------------------------------------------- |
| **curl**  | `sh -c "$(curl -fsSL https://install.ohmyz.sh/)"` |
| **wget**  | `sh -c "$(wget -O- https://install.ohmyz.sh/)"`   |
| **fetch** | `sh -c "$(fetch -o - https://install.ohmyz.sh/)"` |

> **Remarque :** tout fichier `.zshrc` existant sera renommé en `.zshrc.pre-oh-my-zsh`.

### Inspection manuelle

Il est recommandé d’inspecter le script avant de l’exécuter :

```sh
wget https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh
sh install.sh
```

---

# Utilisation d’Oh My Zsh

## Plugins

Oh My Zsh inclut une très grande collection de plugins prêts à l’emploi.

### Activer les plugins

Ouvrez votre fichier de configuration :

```sh
vi ~/.zshrc
```

Puis ajoutez les plugins souhaités :

```sh
plugins=(
  git
  bundler
  dotenv
  macos
  rake
  rbenv
  ruby
)
```

> Les plugins doivent être séparés par des espaces, tabulations ou retours à la ligne. N’utilisez pas de virgules.

### Utiliser les plugins

Chaque plugin est accompagné d’un fichier **README** décrivant :

* les alias disponibles ;
* les fonctionnalités supplémentaires ;
* les options spécifiques au plugin.

---

## Thèmes

Oh My Zsh fournit plus de **150 thèmes**.

### Choisir un thème

Le thème par défaut est :

```sh
ZSH_THEME="robbyrussell"
```

Pour utiliser un autre thème :

```sh
ZSH_THEME="agnoster"
```

### Important

De nombreux thèmes nécessitent l’installation d’une :

* **Powerline Font**
* ou **Nerd Font**

Sans ces polices, certains symboles de l’invite de commande risquent de s’afficher incorrectement.

> Les thèmes ne modifient que l’apparence de l’invite de commande. Ils ne changent ni la police ni les couleurs de votre terminal.

### Thème aléatoire

Pour choisir un thème aléatoire à chaque ouverture du terminal :

```sh
ZSH_THEME="random"
```

Limiter le choix à certains thèmes :

```sh
ZSH_THEME_RANDOM_CANDIDATES=(
  "robbyrussell"
  "agnoster"
)
```

Exclure certains thèmes :

```sh
ZSH_THEME_RANDOM_IGNORED=(pygmalion tjkirch_mod)
```

---

# Installation avancée

## Répertoire personnalisé

Par défaut :

```sh
~/.oh-my-zsh
```

Pour utiliser un autre emplacement :

```sh
ZSH="$HOME/.dotfiles/oh-my-zsh" sh install.sh
```

## Installation sans interaction

```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)" "" --unattended
```

Cette option :

* ne change pas le shell par défaut ;
* ne lance pas automatiquement `zsh` après l’installation.

---

## Installation manuelle

### 1. Cloner le dépôt

```sh
git clone https://github.com/ohmyzsh/ohmyzsh.git ~/.oh-my-zsh
```

### 2. Sauvegarder le fichier `.zshrc`

```sh
cp ~/.zshrc ~/.zshrc.orig
```

### 3. Créer une nouvelle configuration

```sh
cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
```

### 4. Changer le shell par défaut

```sh
chsh -s $(which zsh)
```

### 5. Ouvrir un nouveau terminal

La configuration Oh My Zsh sera alors chargée automatiquement.

---

# Mises à jour

Par défaut, Oh My Zsh vérifie les mises à jour toutes les deux semaines.

## Mise à jour automatique

```sh
zstyle ':omz:update' mode auto
```

## Rappel uniquement

```sh
zstyle ':omz:update' mode reminder
```

## Désactiver les mises à jour automatiques

```sh
zstyle ':omz:update' mode disabled
```

## Fréquence

```sh
zstyle ':omz:update' frequency 7
```

Vérification tous les 7 jours.

---

## Mise à jour manuelle

```sh
omz update
```

🎉 Magie !

---

# Désinstallation

Pour supprimer Oh My Zsh :

```sh
uninstall_oh_my_zsh
```

Cette commande :

* supprime Oh My Zsh ;
* restaure votre configuration Bash ou Zsh précédente.

---

# Comment contribuer ?

Avant toute contribution, lisez le code de conduite du projet.

Vous pouvez notamment :

* proposer des améliorations ;
* corriger des bogues ;
* tester des pull requests ;
* participer aux discussions sur les issues ouvertes.

## Ne nous envoyez pas de thèmes

L’équipe considère disposer d’un nombre suffisant de thèmes. Les nouveaux thèmes doivent être publiés dans la page du wiki dédiée aux thèmes externes.

---

# Contributeurs

Oh My Zsh bénéficie d’une communauté active de contributeurs et d’utilisateurs passionnés.

**Merci à toutes celles et ceux qui participent au projet !**

---

# Suivez-nous

* X (anciennement Twitter) : **@ohmyzsh**
* Facebook
* Instagram
* Discord

---

# Produits dérivés

Des autocollants, t-shirts et mugs sont disponibles pour afficher votre passion pour Oh My Zsh.

---

# Licence

Oh My Zsh est distribué sous licence **MIT**.

---

# À propos de Planet Argon

Oh My Zsh a été créé par l’équipe de **Planet Argon**, une agence spécialisée dans le développement Ruby on Rails.

Découvrez également leurs autres projets open source.
