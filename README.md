# 🎮 SurvivalGames Plugin - Documentazione

## 📌 Descrizione

Questo plugin implementa una modalità **Survival Games (Hunger Games)** per server Minecraft Bukkit/Spigot.

🔧 **Nota:**
Questo plugin è una **fork del progetto originale** disponibile qui:
https://github.com/WildAdventure/SurvivalGames

Il sistema gestisce:

* Caricamento mappe casuali
* Spawn dei giocatori su piattaforme
* Loot nelle casse
* Timer di gioco (pregame, invincibilità, final battle)
* Sistema punti e database MySQL
* Sponsor e GUI

---

## 📁 Struttura delle cartelle

```text
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

Le mappe devono essere dentro:

```
/plugins/SurvivalGames/maps/
```

Ogni mappa è una **cartella mondo completa** (NON zip).

---

### 📄 maps.yml

Esempio:

```yaml
breeze2:
  name: "Breeze 2"
  radius: 400
  time: DAY
  rain: false
  thunder: false
```

### 🔹 Campi

* `name` → nome visualizzato (opzionale)
* `radius` → raggio world border (OBBLIGATORIO)
* `time` → DAY, NIGHT, SUNSET (opzionale)
* `rain` → true/false
* `thunder` → true/false

---

## ⚙️ Funzionamento mappe

### 🔄 Caricamento

All'avvio:

1. Il plugin legge `maps.yml`
2. Sceglie una mappa casuale
3. Copia la cartella in `/world`
4. Avvia la partita

---

## 📍 Setup della mappa

### 1. Spawn del mondo (FONDAMENTALE)

Devi impostarlo al centro arena:

```
/setworldspawn
```

---

### 2. Piattaforme giocatori

Ogni player spawna su una piattaforma definita da:

```
SPONGE
BEACON
```

* Beacon sotto
* Sponge sopra

👉 Il plugin:

* rimuove i blocchi
* salva la posizione
* orienta il player verso il centro

---

### 3. Chest dello spawn

Le casse vicino allo spawn:

* vengono rilevate automaticamente
* vengono riempite dal plugin

📌 Devono essere entro ~50 blocchi dallo spawn

---

### 4. Raggio di rilevamento

Il plugin legge:

* 7x7 chunk attorno allo spawn (~48 blocchi)

👉 Se qualcosa è troppo lontano → NON viene visto

---

## 🌦️ Impostazioni mondo

Il plugin imposta automaticamente:

* PvP attivo
* Meteo configurabile
* Ciclo giorno disattivato
* Mob spawning attivo
* Fire tick attivo

---

## 🎁 Sistema casse

Definito in:

```
chests.yml
```

* Tier1 → loot base
* Tier2 → loot avanzato

---

## 🛒 Sponsor

Configurato in:

```
sponsor.yml
```

Permette:

* acquistare oggetti durante la partita
* GUI con icone
* sistema punti

---

## 🗄️ Database MySQL

Il plugin usa MySQL per salvare:

* kills
* deaths
* wins
* points

---

## ⏱️ Timer di gioco

Il sistema include:

* Pregame
* Immobilità iniziale
* Invincibilità
* Game timer
* Final battle
* World border shrinking
* Fine partita

---

## 🧠 Sistema vittoria

Il plugin controlla:

* se resta 1 solo giocatore → vittoria
* assegna punti
* salva nel database
* riavvia server

---

## ⚠️ Errori comuni

### ❌ "Cartella mappa non trovata"

→ nome sbagliato tra config e cartella

### ❌ "Nessuna piattaforma trovata"

→ mancano beacon + sponge

### ❌ Mappa non caricata

→ manca `level.dat`

### ❌ Nessuna mappa valida

→ `radius` ≤ 0 oppure config sbagliato

---

## 🧹 Pulizia mappe (IMPORTANTE)

Puoi eliminare:

```
players/
playerdata/
stats/
advancements/
```

✔ Evita bug
✔ Riduce problemi compatibilità

---

## ✅ Checklist finale

* [ ] mappa dentro `/maps`
* [ ] `maps.yml` configurato
* [ ] spawn centrale corretto
* [ ] beacon + sponge per ogni player
* [ ] chest vicino allo spawn
* [ ] radius > 0

---

## 🚀 Note finali

* Il plugin seleziona una mappa casuale ad ogni avvio
* Tutto ruota attorno allo spawn del mondo
* Le piattaforme definiscono il numero massimo di giocatori

---

## 👨‍💻 Crediti

* Plugin originale: WildAdventure

---
