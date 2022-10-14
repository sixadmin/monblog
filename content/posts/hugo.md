---
title: "Hugo: Installation et configuration"
date: 2022-10-14T01:00:00+02:00
draft: false
---
 Installation d'un site sous Hugo

## Installation de brew

Un pré requis à l'installation de homebrew est la présence d'un compilateur.

```bash
sudo apt install build-essential
```

Nous téléchargeons ensuite l'installateur

```bash
curl -fsSL -o install.sh https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh
```

Et nous l'executons

```bash
/bin/bash install.sh
```

Enfin, on indique à notre système le chemin vers le binaire

```bash
echo '# Set PATH, MANPATH, etc., for Homebrew.' >> /home/richard/.profile
```

```bash
echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"' >> /home/richard/.profile
```

```bash
eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
```

## Installation de Hugo

```bash
brew install hugo
```

```bash
hugo new site monblog -f yml
Congratulations! Your new Hugo site is created in /home/richard/Documents/dev/hugo/monblog.

Just a few more steps and you're ready to go:

1. Download a theme into the same-named folder.
   Choose a theme from https://themes.gohugo.io/ or
   create your own with the "hugo new theme <THEMENAME>" command.
2. Perhaps you want to add some content. You can add single files
   with "hugo new <SECTIONNAME>/<FILENAME>.<FORMAT>".
3. Start the built-in live server via "hugo server".

Visit https://gohugo.io/ for quickstart guide and full documentation.
```

## Installation du thème Papermod

On se refère à la documentation:

https://github.com/adityatelange/hugo-PaperMod/wiki/Installation

```bash
git clone https://github.com/adityatelange/hugo-PaperMod themes/PaperMod --depth=1
```

Nous allons ensuite éditer le fichier config.yml à la racine de notre site pour lui indiquer le thème utilsé (entre autres)

```yaml
baseURL: ""
languageCode: fr-fr
title: Blog 6adm.in
theme: PaperMod
```

On peut dès lors lancer notre site avec la commande suivante:

```bash
hugo server
```

On accède à notre site via l'url suivante: http://localhost:1313/

## Ajouter du contenu à notre site

Le site fonctionne mais il n'a aucun contenu à afficher.

Le dossier content est destiné à contenir nos pages. Nous allons donc lancer la commande suivante

```bash
hugo new posts/docker.md
```

Cette commande va créer un dossier posts qui contient le fichier markdown docker.md

Si on l'édite, on voit le contenu suivant:

```markdown
---
title: "Docker"
date: 2022-10-09T21:24:42+02:00
draft: true
---
```

Il est indiqué le titre de notre document, la date de création et il est actuellement en mode brouillon.

Si on souhaite que la page apparaisse, on modifie la ligne draft: true en draft: false