# NumWorks App Template 

Ce dossier contient le **code de base nécessaire pour créer sa propre application sur calculatrice NumWorks** en **C++ avec EADK**.

C’est un **template simple** pour démarrer rapidement un projet (jeu, outil, menu, animation, etc.).

----

##  Technologies

- **C++**
- **EADK**

Header principal :

```cpp
#include "eadkpp.h"
```

---

## 📁 Structure

```text
NumWorks-App-Template/
│
├── main.cpp
└── README.md
```

---

##  Base du code

```cpp
#include "eadkpp.h"

using namespace EADK;

extern const char eadk_app_name[]
__attribute__((section(".rodata.eadk_app_name"))) = "MyApp";

extern const uint32_t eadk_api_level
__attribute__((section(".rodata.eadk_api_level"))) = 0;

int main() {
    while (1) {
        Keyboard::State touches = Keyboard::scan();

        // logique de l'application

        Timing::msleep(1);
    }
}
```

----

##  Affichage

Afficher du texte :

```cpp
Display::drawString(
    "Hello NumWorks",
    Point(10, 10),
    true,
    Color(0xFFFFFF),
    Color(0x000000)
);
```

Effacer l’écran :

```cpp
Display::pushRectUniform(
    Screen::Rect,
    Color(0x000000)
);
```

---

##  Clavier

Exemple de détection de touche :

```cpp
if (touches.keyDown(Keyboard::Key::OK)) {
    // action
}
```

---

##  Boucle principale

Toute la logique de l’application se fait ici :

```cpp
while (1) {
    Keyboard::State touches = Keyboard::scan();

    // logique
    // affichage

    Timing::msleep(1);
}
```

---

##  Utilisation

- copier ce dossier
- renommer le projet
- modifier `eadk_app_name`
- ajouter votre code dans la boucle principale

---

## 💡 Idées de projets

- jeux
- outils
- menus
- animations
- mini applications
