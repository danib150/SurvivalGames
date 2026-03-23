# 🎮 SurvivalGames Plugin - Documentazione

## 📌 Descrizione

Questo plugin implementa una modalità **Survival Games (Hunger Games)** per server Minecraft Bukkit/Spigot.

🔧 **Nota:**
Questo plugin è una **fork del progetto originale** disponibile qui:
https://github.com/WildAdventure/SurvivalGames

---

## 📦 Dipendenze

Questo plugin richiede le seguenti dipendenze:

* WildCommons → https://github.com/danib150/WildCommons
* Boosters → https://github.com/danib150/Boosters

⚠️ **Importante:**
Queste librerie **NON sono pubblicate su Maven Central**, quindi devono essere:

* installate manualmente
* oppure buildate automaticamente tramite GitHub Actions

---

## ⚙️ Build del progetto

### ✔️ Metodo consigliato (GitHub Actions)

Per compilare automaticamente il plugin, è necessario buildare prima le dipendenze.

```yaml id="0h3l9d"
name: Build

on:
  push:
  pull_request:

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout plugin
        uses: actions/checkout@v4

      - name: Setup Java
        uses: actions/setup-java@v4
        with:
          distribution: temurin
          java-version: 8

      - name: Clone WildCommons
        run: git clone https://github.com/danib150/WildCommons.git

      - name: Build WildCommons
        run: |
          cd WildCommons
          mvn -B install

      - name: Clone Boosters
        run: git clone https://github.com/danib150/Boosters.git

      - name: Build Boosters
        run: |
          cd Boosters
          mvn -B install

      - name: Build SurvivalGames
        run: mvn -B package
```

---

## 📁 Struttura delle cartelle

```text id="r0t2wo"
plugins/
└── SurvivalGames/
    ├── config.yml
    ├── chests.yml
    ├── maps/
    │   ├── maps.yml
    │   └── nomeMappa/
    │       ├── level.dat
    │       ├── region/
    │       ├── data/
    │       └── ...
```

---

## 🗺️ Mappe

### 📌 Dove vanno messe

```text id="v7s0zq"
/plugins/SurvivalGames/maps/
```

---

### 📄 maps.yml

```yaml id="v0s9u2"
breeze2:
  name: "Breeze 2"
  radius: 400
  time: DAY
  rain: false
  thunder: false
```

---

## 📍 Setup della mappa

### ✔️ Spawn

```id="qj6v1k"
/setworldspawn
```

### ✔️ Piattaforme

```id="c0c4bg"
SPONGE
BEACON
```

### ✔️ Chest

Vicino allo spawn (~50 blocchi)

---

## ⚠️ Errori comuni

* Cartella mappa non trovata
* Nessuna piattaforma trovata
* Mappa non caricata

---

## 👨‍💻 Crediti

* Plugin originale: https://github.com/WildAdventure/SurvivalGames
* Fork: danib150
* Dipendenze:

  * https://github.com/danib150/WildCommons
  * https://github.com/danib150/Boosters

---
