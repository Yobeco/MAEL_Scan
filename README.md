![MAEL](https://github.com/Yobeco/MAEL_Phono_fouille/blob/main/readme_assets/Logo-MAEL-120.png "Logo du projet MAEL")

# MAEL Scan

*Une application appartenant au [__projet MAEL__](https://github.com/Yobeco/MAEL_Project)*   
Copyright (c) 2025 Yonnel Bécognée

[![License: Libre Non Commerciale](https://img.shields.io/badge/license-GNU%20GENERAL%20PUBLIC%20LICENSE%20V3-white.svg)](./LICENSE)

[![Kotlin](https://img.shields.io/badge/Kotlin-V2.2.20%2B-9933FF?logo=kotlin&logoColor=FF66FF)](https://kotlinlang.org/)

[![SQLite](https://img.shields.io/badge/SQLite-V3.50.4%2B-003366?logo=sqlite&logoColor=99CCFF)](https://sqlite.org/)

[![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-009900.svg)](#contributing) [![Beginner friendly](https://img.shields.io/badge/Beginner%20friendly-FF8000)]()

[![Status: Active](https://img.shields.io/badge/status-active-009900.svg)]()

## :fr: [Français](https://github.com/Yobeco/MAEL_Scan) | :gb: English

---

![](https://github.com/Yobeco/MAEL_Project/blob/main/readme_assets/MAEL-Scan2-seul-350px.png)


## A- Description :eye:

**MAEL Scan** est une application pour téléphone portable :iphone: (bientôt, une version Raspberry  Pi <img src="https://cdn.simpleicons.org/raspberrypi/FFFF" width="24" height="24" style="vertical-align: middle;" />) qui permet à l'élève de flasher les code QR créés par son professeur avec **MAEL Gen** et d'écouter leur contenu.
Son interface est conçue pour être utilisée par un enfant, dés 4 ans.
Elle ne comporte que 3 gros boutons par défaut.

**MAEL Scan** permet aux élèves ne possédant auncun "parlant" chez lui d'écouter la langue étudiée dans un contexte pédagogique élaboré par son professeur.

---

## B- Fonctionnalités :clipboard:

- **Scanner** : Lance le scan du code QR puis oralise son contenu.
- **Écouter à nouveau** : Permet de ré-écouter sans re-scanner.
- **Écouter plus lentement** : Permet de ré-écouter sans re-scanner, mais de manière plus lente (ne fonctionne pas avec les mp3).
- **Lecture "MP3"** : Lors du scan, si le lien point vers un fichier mp3, l'élève entendra ce fichier.

---

## C- Comment utiliser MAEL Scan ? :blush:

:warning: Assurez-vous que vous avez [**installé la voix de synthèse**](./readme_assets/MAEL_Scan_tuto.pdf) correspondant la langue utilisée sur votre téléphone.   
Pour ces exemples, installez la voix française :fr:.

---

***⟶ L'élève ne sait pas ce que contient le code QR, il n'a qu'à le flasher.***

1. **Lancez MAEL Scan**
1. **Flasher un code QR généré par MAEL Gen depuis une texte.**

Appuyez sur ce bouton :

![Scan](./readme_assets/Scanner.png)

---

### 1- Si le code QR contient du texte :spiral_notepad:

 |  | Exemple |  | Exemple |  | Exemple |
 |:--------:|--------------------|:--------:|--------------------|:--------:|--------------------|
 | Mode Lecture | ![Code QR de test](./readme_assets/test_text_lec.png) | Mode Dicter | ![Code QR de test](./readme_assets/test_text_dic.png) | Mode Épeler | ![Code QR de test](./readme_assets/test_text_epe.png) |




1. **:speaker: Écouter le contenu du code QR.**

1. **Ré-écouter**

![Ré-écouter](./readme_assets/Reecouter.png)

1. **Ré-écouter plus lentement**

![Ré-écouter](./readme_assets/Lent.png)

*⟶ L'élève entendra une voix de synthèse :speaking_head:*

---

### 2- Si le code QR contient un lien vers un fichier MP3 :microphone:

 :magic_wand: **[Comment mettre un .mp3 sur Google Drive](https://github.com/Yobeco/MAEL_Gen/blob/main/README.md#2--fichier-mp3) <img src="https://cdn.simpleicons.org/googledrive/FFFF" width="24" height="24" style="vertical-align: middle;" /> **

<!-- Lien vers une page et un titre en particulier. Ne fonctionne pas si le titre contient un icône. Ne fonctionne pas dans tous les éditeurs-->

![Code QR de test](./readme_assets/test_mp3.png)

1. **:speaker: Écouter le fichier mp3.**
1. **Ré-écouter**

![Ré-écouter](./readme_assets/Reecouter.png)

1. **Gérer la lecture du fichier**

![Play](./readme_assets/Play.png) ![Stop](./readme_assets/Stop.png) ![Pause](./readme_assets/Pause.png)

*⟶ L'élève entendra une voix de synthèse :speaking_head:*

---

## D- Principe de fonctionnement :gear:

*(Pour aider à la compréhension du code)*

---

text

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

3- **Mode "épeler"**

*Explication péralable :*

Pour épeler un texte, **MAEL Scan** contient une structure de données contenant les correspondances entre les lettres et ce qu'il doit dire.

*Exemples :*

 | Lettre | Ce qui sera prononcé |
 |:--------:|--------------------|
 | A | a majuscule |
 | a | a |
 | é | e accent aigü |
 | ç | c cédille |

Cette base de données est très spécifique à chaque langue.
Dans la version *MIT App Inventor* de **MAEL Scan**, ces informations sont stoquées dans une variable de type `dictionnaire` qui prend la forme d'un **immense immeuble :office: de petits blocs** difficile à afficher (et donc à gérer).  
Il parait très compliqué de créer 55 dictionnaires de ce type :face_with_spiral_eyes:, c'est un des facteurs limitant de *MIT App Inventor* et donc une des raisons du passage à Kotlin MP <img src="https://cdn.simpleicons.org/kotlin/FFFF" width="24" height="24" style="vertical-align: middle;" />.

1- **Implémentation d'une base de données SQLite <img src="https://cdn.simpleicons.org/sqlite/FFFF" width="24" height="24" style="vertical-align: middle;" />**

Il faudrait donc utiliser une base de données **SQLite** dont chaque table contiendrait les correspondances `Lettre | Ce qui sera prononcé`.

2- **Gestion des écritures idéogrammiques** :ideograph_advantage:

Comment gérer l'épélation des langages comme le chinois :cn:, le japonais :jp: ou le koréen :kr: ?

Si un(e) spécialiste d'une de ces langues est inétressé(e), il (elle) sera le (la) bienvenu(e) ! :open_hands:

### :+1: Proposez votre aider pour developper une de ces fonctions


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

Seule la version Android <img src="https://cdn.simpleicons.org/android/FFFF" width="24" height="24" style="vertical-align: middle;" /> *MIT App Inventor* est disponible pour le moment.   
:inbox_tray: Pour essayer **MAEL Scan** [Télécharger le fichier MAEL_Scan_V5_0.apk](https://raw.githubusercontent.com/Yobeco/MAEL_Scan/main/binary_exec/MAEL_Scan_V5_0.apk)


