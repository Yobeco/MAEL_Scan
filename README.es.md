
![MAEL](https://github.com/Yobeco/MAEL_Phono_fouille/blob/main/readme_assets/Logo-MAEL-120.png "Logo del proyecto MAEL")

# MAEL Scan

*Una aplicación perteneciente al [__proyecto MAEL__](https://github.com/Yobeco/MAEL_Project)*   
Copyright (c) 2022 Yonnel Bécognée

[![Licencia: Libre No Comercial](https://img.shields.io/badge/license-GNU%20GENERAL%20PUBLIC%20LICENSE%20V3-white.svg)](./LICENSE)

[![Kotlin](https://img.shields.io/badge/Kotlin-V2.2.20%2B-9933FF?logo=kotlin&logoColor=FF66FF)](https://kotlinlang.org/)

[![SQLite](https://img.shields.io/badge/SQLite-V3.50.4%2B-003366?logo=sqlite&logoColor=99CCFF)](https://sqlite.org/)

[![Contribuciones bienvenidas](https://img.shields.io/badge/contributions-welcome-009900.svg)](#contributing) [![Apto para principiantes](https://img.shields.io/badge/Beginner%20friendly-FF8000)]()

[![Estado: Activo](https://img.shields.io/badge/status-active-009900.svg)]()

## :fr: [Français](https://github.com/Yobeco/MAEL_Scan/blob/main/README.fr.md) | :es: Español | :gb: [English](https://github.com/Yobeco/MAEL_Scan/blob/main/README.md)

---

![](https://github.com/Yobeco/MAEL_Project/blob/main/readme_assets/MAEL-Scan2-seul-350px.png)

## A- Descripción :eye:

**MAEL Scan** es una aplicación para teléfono móvil :iphone: (próximamente, una versión para Raspberry Pi <img src="https://cdn.simpleicons.org/raspberrypi/FFFF" width="24" height="24" style="vertical-align: middle;" />) que permite al alumno escanear los códigos QR creados por su profesor con **MAEL Gen** y escuchar su contenido :speaker:.   
Su interfaz está diseñada para ser utilizada por un niño, a partir de los 4 años :baby:.   
Solo incluye 3 botones grandes por defecto.

**MAEL Scan** permite a los alumnos que no poseen ningún “dispositivo parlante” en casa escuchar la lengua estudiada dentro de un contexto pedagógico elaborado por su profesor :100:. Por lo tanto, permite al profesor **potenciar su enseñanza de una lengua** :chart_with_upwards_trend:.

**¡Potencialmente, se pueden implementar 55 lenguas!** :astonished:

:fr: :gb: :es: :portugal: :brazil: :it: :de: :ru: :jp: :cn: :kr: ...

---

## B- Funcionalidades :clipboard:

- **Escanear** :speaker: : Inicia el escaneo del código QR y luego oraliza su contenido.
- **Escuchar de nuevo** :curly_loop: : Permite volver a escuchar sin volver a escanear.
- **Escuchar más lento** :snail: : Permite volver a escuchar sin volver a escanear, pero de forma más lenta (no funciona con archivos mp3).
- **Reproducción “MP3”** :musical_note: : Durante el escaneo, si el enlace apunta a un archivo mp3, el alumno escuchará dicho archivo.
- **Modos especiales** : Son bibliotecas de sílabas en formato mp3 (integradas en MAEL Scan) ya que la lectura de una sílaba única a veces es de mala calidad con la voz sintética :unamused:. Hay:
    - las sílabas del abecedario bilingüe Consigny (en francés y en español)
    - las sílabas del método “Borel-Maisonny” (sílabas muy utilizadas, asociadas a gestos destinados a ayudar a niños con disortografía)

---

## C- ¿Cómo usar MAEL Scan? :blush:

:warning: Asegúrese de haber [**instalado la voz de síntesis**](./readme_assets/MAEL_Scan_tuto.pdf) correspondiente al idioma utilizado en su teléfono.   
Para estos ejemplos, instale la voz francesa :fr:.

---

⟶ El alumno no sabe qué contiene el código QR: es el profesor quien decide el contenido (texto, idioma, modo, enlace mp3, etc.) en el momento de su creación. ***El alumno solo tiene que escanearlo.***

1. **Inicie MAEL Scan**
1. **Escanee un código QR generado por MAEL Gen a partir de un texto.**

Pulse este botón:

![Scan](./readme_assets/Scanner.png)

---

### 1- Si el código QR contiene texto :spiral_notepad:

 |  | Ejemplo |  | Ejemplo |  | Ejemplo |
 |:--------:|--------------------|:--------:|--------------------|:--------:|--------------------|
 | Modo lectura | ![Código QR de prueba](./readme_assets/test_text_lec.png) | Modo dictado | ![Código QR de prueba](./readme_assets/test_text_dic.png) | Modo deletrear | ![Código QR de prueba](./readme_assets/test_text_epe.png) |

1. **:speaker: Escuchar el contenido del código QR.**

2. **Escuchar de nuevo**

![Escuchar de nuevo](./readme_assets/Reecouter.png)

3. **Escuchar de nuevo más lentamente**

![Escuchar de nuevo](./readme_assets/Lent.png)

*⟶ El alumno escuchará una voz sintética :speaking_head:*

---

### 2- Si el código QR contiene un enlace a un archivo MP3 :microphone:

:sparkles: **[Cómo subir un archivo .mp3 a Google Drive](https://github.com/Yobeco/MAEL_Gen/blob/main/README.md#2--utiliser-un-fichier-mp3) <img src="https://cdn.simpleicons.org/googledrive/FFFF" width="24" height="24" style="vertical-align: middle;" />**

![Código QR de prueba](./readme_assets/test_mp3.png)

1. **:speaker: Escuchar el archivo mp3.**
2. **Escuchar de nuevo**

![Escuchar de nuevo](./readme_assets/Reecouter.png)

3. **Gestionar la reproducción del archivo**

![Play](./readme_assets/Play.png) ![Pause](./readme_assets/Pause.png) ![Stop](./readme_assets/Stop.png)

*⟶ El alumno escuchará el archivo .mp3. :musical_note:*

---

## D- Principio de funcionamiento :gear:

*(Para ayudar a comprender el código)*

---

1. **MAEL Scan** escanea un código QR
1. **Descifra** el contenido del código QR (algoritmo ya escrito en Kotlin :+1:).
1. Extrae el **prefijo** y el **sufijo** utilizando [**regex**](https://en.wikipedia.org/wiki/Regular_expression).
1. Deduce el **idioma**, el **país** y el **modo** (o si se trata de un **mp3**).
1. Configura :gear: el módulo de **síntesis de voz** del teléfono según el idioma y el país (o selecciona el módulo de reproducción mp3)
1. Configura :gear: el modo (Lectura / Ocultar / Dictar / Deletrear) y oraliza :speaking_head: el texto según lo solicitado. 
1. Si se trata de un modo especial, recupera el audio correspondiente (integrado en la aplicación) :outbox_tray:.

[Documento complementario](./readme_assets/MAEL_Scan-Pseudo_code_Kotlin.pdf) :spiral_notepad:

>*Anécdota* : la versión *MIT App Inventor* no dispone de las funciones necesarias para descifrar el contenido del código QR. Tuve que escribir el algoritmo en JavaScript para integrarlo en una página web utilizada por el módulo **Web** de *MIT App Inventor*.  
¡Qué rodeo! :grimacing:   
⟶ Otra razón más para migrar a Kotlin <img src="https://cdn.simpleicons.org/kotlin/FFFF" width="24" height="24" style="vertical-align: middle;" />.

---

## E- Funcionalidades a desarrollar :rocket:

1- **Modo “Dictado”**

- El _modo de dictado_ actual (vocalizar el texto pero no mostrarlo) cambiará de nombre y se llamará **“Modo ocultar”**. :arrows_counterclockwise:

- El nuevo _modo de dictado_ incluirá:

    - la lectura del texto, pero sin mostrarlo,
    - la vocalización de la puntuación, y
    - la visualización del menú de reproducción–pausa (con barra de progreso). :play_or_pause_button:

2- **Modo “MP3”**

- Creación de un **MAEL Cloud** :cloud: con menos limitaciones que Google Drive. (alojado en la plataforma **MAEL Phrase**).
- Adición de una opción (sufijo) que indicará a **MAEL Scan** que debe conservar el archivo :inbox_tray: para no tener que volver a descargarlo si se escanea de nuevo.

3- **Modo “Deletrear”**

*Explicación preliminar:*   
Para deletrear un texto, **MAEL Scan** contiene una estructura de datos que almacena las correspondencias entre las letras y lo que debe pronunciarse.

*Ejemplos:*

 | Letra | Lo que será pronunciado |
 |:--------:|--------------------|
 | A | a mayúscula |
 | a | a |
 | é | e acento agudo |
 | ç | c cedilla |

Esta base de datos es muy específica para cada idioma.
En la versión *MIT App Inventor* de **MAEL Scan**, esta información se almacena en una variable de tipo `diccionario`, que adopta la forma de un **enorme edificio :office: compuesto por pequeños bloques**, difícil de mostrar (y por lo tanto de gestionar).  
Parece muy complicado crear 55 diccionarios de este tipo :face_with_spiral_eyes:, lo cual es uno de los factores limitantes de *MIT App Inventor* y, por tanto, una de las razones del paso a Kotlin MP <img src="https://cdn.simpleicons.org/kotlin/FFFF" width="24" height="24" style="vertical-align: middle;" />.

1- **Implementación de una base de datos SQLite <img src="https://cdn.simpleicons.org/sqlite/FFFF" width="24" height="24" style="vertical-align: middle;" />**

Por lo tanto, sería necesario utilizar una base de datos **SQLite** en la que cada tabla contenga las correspondencias `Letra | Lo que será pronunciado`.

2- **Gestión de los sistemas de escritura ideográficos** :ideograph_advantage:

¿Cómo debería gestionarse el deletreo de idiomas como el chino :cn:, el japonés :jp: o el coreano :kr:?

Si un(a) especialista en uno de estos idiomas está interesado(a), ¡será bienvenido(a)! :open_hands:

### :+1: Ofrezca su ayuda para desarrollar una de estas funciones

---

## F- Participe en el proyecto MAEL :open_hands:

:ring_buoy: Para **obtener ayuda** sobre el uso de MAEL o para **participar en el desarrollo** :computer:, escríbame aquí:

### :mailbox_with_mail: ***[mael@lvh.edu.ni](mailto:mael@lvh.edu.ni)***

### :star2: Colaboradores

¡Un gran agradecimiento a todas las personas que contribuirán a este proyecto!

| Avatar | Nombre             | GitHub                          | Rol                      |
|--------|--------------------|---------------------------------|--------------------------|
| [<img src="https://github.com/YoBeco.png" width="50" style="border-radius: 50%;">](https://github.com/YoBeco) | Bécognée Yonnel | [@Yobeco](https://github.com/Yobeco)   | Mantenedor                 |
| [<img src="https://github.com/Nail-yk.png" width="50" style="border-radius: 50%;">](https://github.com/Nail-yk) | Padawan         | [@Nail-yk](https://github.com/Nail-yk) | Traducción de la documentación |
| ... | ... | ... | Desarrollador |
| ... | ... | ... | Desarrolladora |

---

## G- Instalación :arrow_heading_down:

Solo la versión Android <img src="https://cdn.simpleicons.org/android/FFFF" width="24" height="24" style="vertical-align: middle;" /> que utiliza *MIT App Inventor* es funcional por el momento.   
:inbox_tray: Para probar **MAEL Scan**, [Descargar el archivo MAEL_Scan_V5_0.apk](https://raw.githubusercontent.com/Yobeco/MAEL_Scan/main/binary_exec/MAEL_Scan_V5_0.apk)