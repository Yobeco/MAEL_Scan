![MAEL](https://github.com/Yobeco/MAEL_Phono_fouille/blob/main/readme_assets/Logo-MAEL-120.png "Logo du projet MAEL")

# MAEL Scan

*Une application appartenant au [__projet MAEL__](https://github.com/Yobeco/MAEL_Project)*   
Copyright (c) 2025 Yonnel Bécognée

[![License: Libre Non Commerciale](https://img.shields.io/badge/license-GNU%20GENERAL%20PUBLIC%20LICENSE%20V3-white.svg)](./LICENSE)

![Kotlin](https://img.shields.io/badge/Kotlin-V2.2.20%2B-9933FF?logo=kotlin&logoColor=FF66FF)

[![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-009900.svg)](#contributing) [![Beginner friendly](https://img.shields.io/badge/Beginner%20friendly-FF8000)]()

[![Status: Active](https://img.shields.io/badge/status-active-009900.svg)]()

## :fr: [Français](https://github.com/Yobeco/MAEL_Gen) | :gb: English

---

![](https://github.com/Yobeco/MAEL_Project/blob/main/readme_assets/MAEL-Scan2-seul-350px.png)


## A- Description :eye:

text

---

## B- Fonctionnalités :clipboard:

- **Scanner** : text
- **Écouter à nouveau** : text
- **Écouter plus lentement** : text
- **Lecture "MP3"** : text
---

## C- Comment utiliser MAEL Scan

### 1- Voix de synthèse :speaking_head:

1. Lancez MAEL Gen
1. Introduisez le texte que vous souhaitez faire entendre dans le champ de texte (écrivez-le, ou faites `Ctrl + v` ou encore un simple `clic droit`)
1. Choisissez la langue (Menu `Langue`) dans laquelle est le texte que vous avez introduit.
1. Choisissez le mode (Menu `Paramètre`) selon votre objectif.
1. Ajustez la taille du code QR (champ `Taille` ou glissière)
1. Collez dans votre document : éditeur de texte, LibreOffice Draw <img src="https://cdn.simpleicons.org/libreofficeimpress/FFFF" width="24" height="24" style="vertical-align: middle;" />...

*⟶ L'élève n'aura plus qu'à scanner ce code avec __MAEL Scan__ pour écouter le contenu :headphones:...*

### 2- Fichier MP3 :microphone:

1. Déposez un fichier .mp3 sur votre compte Google Drive <img src="https://cdn.simpleicons.org/googledrive/FFFF" width="24" height="24" style="vertical-align: middle;" />

1. **Partagez** le dossier où se trouve le fichier .mp3 **avec toutes les personnes possédant le lien**.
1. Récupérer le lien de partage.
1. Coller ce lien dans MAEL Gen.
1. Ajustez la taille (champ `Taille`ou glissière).
1. Collez dans votre document (éditeur de texte ou LibreOffice Draw <img src="https://cdn.simpleicons.org/libreofficewriter/FFFF" width="24" height="24" style="vertical-align: middle;" />...).

*⟶ L'élève n'aura plus qu'à scanner ce code avec __MAEL Scan__ pour écouter le fichier mp3 :headphones: : une poésie, un dialogue...*

---

## D- Principe de fonctionnement :gear:

*(Pour aider à la compréhension du code)*

---

**:one: Au premier démarrage**

Quand on écrit un texte dans l'entrée de texte, la langue par défault est "français" :fr: et le mode par défaut est "Lecture" :

1- Le texte subit d'abord un "encryptage" léger.

2- Un code QR contenant ce texte (utf-8) est généré.

*⟶ MAEL Scan comprendra qu'il est en mode lecture et utilisera la voix de synthèse française :fr:.*

---

**:two: Si vous changez _la langue_ du contenu, par exemple _italien_ :**

1- Le texte reçoit un préfixe du type `<it>`

2- Le texte subit d'abord un "encryptage" léger.

3- Un code QR contenant ce texte (utf-8) est généré.

*⟶ __MAEL Scan__ comprendra qu'il est en __mode lecture__ mais il utilisera cette fois la voix de synthèse de voix __italienne__ :it:.*

---

**:three: Si vous choisissez le *mode dicter* :**

1- Le texte reçoit un préfixe du type `<it>`

2- Le texte reçoit un suffixe du type `#d`

2- Le texte subit d'abord un "encryptage" léger.

3- Un code QR contenant ce texte (utf-8) est généré.

*⟶ __MAEL Scan__ comprendra cette fois qu'il est en __mode dictée__ et utilisera la voix de synthèse de voix __italienne__ :it:.*

---

:speaking_head: Les voix de synthèse sont celles générées par le téléphone.

:warning: Certaines langues (avec gtts) ont plusieurs voix possibles. Le préfixe sera alors plus long. Par exemples :

| Voix | Préfixe |
| ----------- | ----------- |
| Portugais du portugal | `<ptPRT>` |
| Portugais du Bésil | `<ptBRA>` |

:bookmark_tabs: [Voir la liste des langues de GTTS (Probablement à actualiser...)](./readme_assets/Langues_GTTS.pdf)

---

**:four: À chaque modification :**

Le fichier `.png` généré est automatiquement envoyé dans le presse-papier. :clipboard:

(Un petit icône indique si dans le presse-papier, il y a un code QR ou du texte)

*⟶ Le professeur n'a plus qu'à faire `Coller` dans son éditeur personnel.*

---

## E- Fonctionnalités à développer :rocket:

1- **Mode "dicter"**

- Le _mode dictée_ actuel (oraliser le texte mais ne pas l'afficher) va changer de nom et s'appeler **"Mode caché"**.

- Le nouveau _mode dicter_ aura :

    - la lecture du texte, mais pas son affichage,
    - l'oralisation de la ponctuation et
    - l'affichage du menu lecture-pause (avec barre de défilement).

2- **Mode "MP3"**

- Création d'un MAEL Cloud avec moins de limitations que Google Drive. (hébergé avec la plateforme MAEL Phrase).
- Ajout d'une option (suffixe) qui indiquera à **MAEL Scan** qu'il doit conserver le fichier pour ne pas à avoir à le re-télécharger s'il est scanné à nouveau.

3- **Interface**

- Remplacement de TKinter par **TTKBootstrap**
- **Déplacer les boutons d'accès au changement de mode** du menu « Paramètres » vers l'emplacement du curseur (qui sera supprimé).
- Gestion des langues s'écrivant de droite à gauche :arrow_left:.

4- **LibreOffice** <img src="https://cdn.simpleicons.org/LibreOffice/FFFF" width="24" height="24" style="vertical-align: middle;" />

Quand on crée un document contenant beaucoup de codes QR, il devient plus facile de se tromper. (Mettre deux fois le même code QR par exemple... :sweat_smile: )

*(Pour que le professeur puisse voir d'un seul coup d'oeil le mode du code QR, j'avais ajouté un petit carré de couleur en bas à droite.)*

De la même manière, pour pouvoir vérifier facilement le contenu du code QR, j'aurais voulu ajouter son texte dans les méta-données du fichier .png pour que, sous LibreOffice, les métadonnées de l'image apparaissent dans une info-bulle :left_speech_bubble: ou bien quelles soient visibles dans l'inspecteur (colonne de droite).

Je n'ai pas encore trouvé comment faire quelque-chose de similaire. :disappointed_relieved:

### :+1: Proposez votre aider pour developper ces fonctions


---

## F- Participez au projet MAEL :open_hands:

:sos: Pour **obtenir de l'aide** concernant l'utilisation de MAEL ou pour **paticiper au développement** :computer:, écrivez moi ici :

### :mailbox_with_mail: ***[mael@lvh.edu.ni](mailto:mael@lvh.edu.ni)***

### :star2: Contributeurs

Un grand merci à toutes les personnes qui vont contribuer à ce projet !

 | Avatar | Nom                | GitHub                          | Rôle                     |
 |--------|--------------------|---------------------------------|--------------------------|
 | ![Bécognée Yonnel](https://github.com/Yobeco.png?size=50) | Bécognée Yonnel | [@Yobeco](https://github.com/Yobeco) | Mainteneur |
 | ... | ... | ... | Développeur |
 | ... | ... | ... | Développeuse |
 | ... | ... | ... | Traductrice |

---

## G- Installation :arrow_heading_down:

Pour essayer **MAEL Gen**, exécutez le script :

    git clone https://github.com/Yobeco/MAEL_Gen.git
    cd MAEL_Gen
    python3 -m venv mael_venv
    source mael_venv/bin/activate
    pip install -r requirements.txt
    python3 MAEL_V5.0.py


