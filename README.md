# 🎮 SurvivalGames Plugin - Documentazione

## 📌 Descrizione

Questo plugin implementa una modalità **Survival Games** per server Minecraft Bukkit/Spigot.

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
