# ✅ KAI-OS / A-TownChain OS — Master To-Do Liste

> Letzte Aktualisierung: 2026-06-09 | Quelle: GitHub Issues (A-TownChain-Okosystems/a-townchain-os)  
> Generiert von: Superagent (KAI-OS Agent)

---

## 🔴 Priority HIGH — Kritischer Pfad

### #22 🚀 KAI-OS v1.3.2-beta — Substrate-Integration + DevOps
**Branch:** `feature/kai-os-integration` → `main` | **Sprint:** 2.1 (Substrate Chain Setup) · Milestone M1

- [ ] Substrate-Chain Setup (Substrate Node Template)
- [ ] `pallet-poh` integrieren (Proof of History)
- [ ] `pallet-ai-registry` integrieren
- [ ] `pallet-agent-registry` integrieren
- [ ] GitHub Actions CI/CD Pipeline aufsetzen
- [ ] Wiki Auto-Sync Workflow (wiki-sync.yml)
- [ ] Docusaurus Deployment (docusaurus.yml)
- [ ] PR `feature/kai-os-integration` → `main` mergen

---

### #20 🧪 API-Gateway-Tests — Unit & Integrationstests Port 4000
**Datei:** `gateway/main.py`, `gateway/router.py`, `gateway/middleware/`

- [ ] `tests/test_gateway.py` — Unit-Tests für `create_app()`
- [ ] `tests/test_gateway.py` — Integrationstests für alle Routen
- [ ] Test: Auth-Middleware (gültige/ungültige API-Keys)
- [ ] Test: Rate-Limiter (Burst-Schutz)
- [ ] Test: Service-Routing zu Core/Chain/Wallet/AI/Game
- [ ] Test: Request-Logger Ausgabe
- [ ] CI: Tests in GitHub Actions einbinden
- [ ] Coverage-Report generieren (Ziel: >80%)

---

### #17 ⛓ [Testnet] Longest-Chain-Rule — Fork-Auflösung
**Datei:** `shivaos/consensus/shiva_consensus.py`

- [ ] `HybridConsensus.resolve_fork(chain_a, chain_b)` implementieren
- [ ] Fork-Erkennung: zwei Blöcke mit gleichem `prev_hash` identifizieren
- [ ] Längste gültige Chain gewinnt (kumulative Arbeit / Höhe)
- [ ] Orphan-Block Pool: verworfene Blöcke zwischenspeichern
- [ ] Reorganisation (Reorg): Chain-Swap bei längerer Konkurrenz-Chain
- [ ] Unit-Tests: `test_fork_resolution.py` (min. 5 Szenarien)
- [ ] Integration mit Block-Propagation (#15)

---

### #16 🔄 [Testnet] Initial Sync — Neue Nodes synchronisieren
**Datei:** `shivaos/net/atcnet.py`, `blockchain/nodes/node.py`

- [ ] `sync_from_peer(peer_address)` — Chain-Download in 50-Block-Batches
- [ ] Sync-Fortschritt im Dashboard anzeigen (Prozent)
- [ ] Checkpoint-System: vertrauenswürdige Block-Hashes hardcoden
- [ ] Parallelisierung: von mehreren Peers gleichzeitig syncen
- [ ] Sync-Abbruch & Resume bei Verbindungsabbruch
- [ ] Validierung jedes heruntergeladenen Blocks
- [ ] Unit-Tests: `test_initial_sync.py`

---

### #15 📡 [Testnet] Block Propagation — P2P Block Broadcasting
**Datei:** `blockchain/nodes/p2p.py` (neu erstellen)

- [ ] `blockchain/nodes/p2p.py` — TCP-Verbindungs-Manager
- [ ] `broadcast_block(block)` — Block an alle Peers senden
- [ ] `broadcast_tx(tx)` — Transaktion an alle Peers senden
- [ ] Deduplication: bereits gesehene Blöcke ignorieren (Bloom Filter)
- [ ] Retry-Logik bei fehlgeschlagener Übertragung
- [ ] Integration mit Bootstrap Node (#14)
- [ ] Unit-Tests: `test_propagation.py`

---

### #14 🌐 [Testnet] Bootstrap Node — P2P Discovery Service
**Datei:** `blockchain/nodes/discovery.py` (neu erstellen)

- [ ] `blockchain/nodes/discovery.py` — UDP-basierter Node-Announcer
- [ ] Bootstrap-Node Config in `config/settings.json` eintragen
- [ ] `NodeRegistry` — Liste aktiver Peers verwalten
- [ ] Heartbeat: inaktive Nodes nach 60s entfernen
- [ ] REST-Endpoint: `GET /peers` — aktive Node-Liste zurückgeben
- [ ] Persistenz: bekannte Peers in `data/peers.json` speichern
- [ ] Docker-ready: Bootstrap-Node als separater Service

---

### #8 🌐 Multi-Node Testnet — P2P Netzwerk live schalten
**Abhängig von:** #14, #15, #16, #17

- [ ] Phase 1: Node-Discovery via UDP Broadcast (`blockchain/nodes/discovery.py`)
- [ ] Phase 2: Peer-Verbindungen aufbauen (TCP, max. 25 Peers)
- [ ] Phase 3: Block-Sync zwischen Nodes
- [ ] Phase 4: Konsens dezentral erreichen (PoI+PoS)
- [ ] Mindestens 3 Nodes im lokalen Testnet synchronisiert
- [ ] End-to-End-Test: TX auf Node A senden, auf Node C bestätigen

---

### #3 ⚔️ Shivamon Battle UI — Animierte Kämpfe im Browser
**Datei:** `frontend/index.html`, `frontend/assets/js/battle.js` (neu)

- [ ] Battle-Seite in `frontend/index.html` (Sidebar-Eintrag `⚔️ Battle`)
- [ ] Shivamon-Auswahl: eigene Collection vs. Gegner-Token-ID
- [ ] Animierter Kampfablauf — Runde für Runde mit HP-Bars
- [ ] Angriffs-Animationen per CSS/Canvas
- [ ] Battle-Log: Aktionen als Text-Stream
- [ ] Sieg/Niederlage-Screen mit XP-Gewinn
- [ ] Backend: `POST /api/game/battle` Endpoint
- [ ] On-Chain: Battle-Ergebnis als Event loggen

---

## 🟡 Priority MEDIUM

### #19 📊 [Testnet] Node-Monitoring Dashboard
**Datei:** `frontend/index.html` (Sidebar: `🌐 Nodes`)

- [ ] Node-Monitor Seite in ShivaOS Dashboard
- [ ] Node-Karten: ID · Typ · Online/Offline · Peers · Chain-Height · Mempool
- [ ] Live-Refresh alle 5 Sekunden (WebSocket oder Polling)
- [ ] Sync-Fortschrittsbalken pro Node
- [ ] Verbindungs-Graph: welche Nodes sind verbunden
- [ ] Alert bei Node-Ausfall (rot markieren)
- [ ] Backend: `GET /api/nodes/status` Endpoint

---

### #18 🐳 [Testnet] Docker Compose — 5-Node lokales Netzwerk
**Datei:** `docker-compose.testnet.yml` (neu), `Dockerfile`

- [ ] `Dockerfile` für A-TownChain OS Backend
- [ ] `docker-compose.testnet.yml` — 5 Service-Definitionen
  - 1x Bootstrap Node
  - 1x Validator Node
  - 1x Miner Node
  - 2x Full Nodes
- [ ] Umgebungsvariablen pro Node-Typ
- [ ] Internes Docker-Netzwerk `atc-testnet`
- [ ] Volume für Chain-Daten (persistenz)
- [ ] Health-Checks für alle Services
- [ ] `make testnet-up` / `make testnet-down` Shortcut

---

### #13 🛒 ATC Marketplace — Shivamon kaufen & verkaufen
**Datei:** `blockchain/contracts/marketplace/marketplace_contract.py` (neu)

- [ ] `list_for_sale(token_id, seller, price_atc)` — NFT listen
- [ ] `buy(token_id, buyer)` — NFT kaufen + ATC transferieren
- [ ] `cancel_listing(token_id, seller)` — Listing entfernen
- [ ] `get_listings()` — alle aktiven Listings abrufen
- [ ] Frontend: Marketplace-Seite im Dashboard (Sidebar: `🛒 Market`)
- [ ] Preis-Filter + Sortierung
- [ ] Transaktion-Bestätigungs-Dialog
- [ ] Backend: `GET/POST /api/game/marketplace` Endpoints

---

### #12 ⛓ Solidity Smart Contracts — On-Chain ATC Token
**Datei:** `blockchain/contracts/solidity/` (neu)

- [ ] `ATCToken.sol` — ERC20 (ATC-8300 Standard)
- [ ] `Shivamon.sol` — ERC721 NFT (ATC-9000 Standard)
- [ ] `ATCGovernance.sol` — DAO Voting (ATC-9900)
- [ ] `GenesisToken.sol` — ATC-001 Genesis Block Token
- [ ] Hardhat-Konfiguration (`hardhat.config.js`)
- [ ] Unit-Tests für alle Contracts (`test/*.js`)
- [ ] Deployment-Script für Testnet (Sepolia/Polygon Mumbai)
- [ ] ABI-Export für Frontend-Integration

---

### #11 🥚 Shivamon Breeding — Gen 2 NFT Züchtung
**Datei:** `blockchain/contracts/shivamon/shivamon_contract.py`

- [ ] `breed(parent1_id, parent2_id, owner)` implementieren
- [ ] DNA-Mixing: Stats aus beiden Eltern kombinieren (50/50 + Mutation)
- [ ] Breed-Cooldown: 24h zwischen Züchtungen
- [ ] Breeding-Fee in ATC-Token
- [ ] Rarity-System: Common/Rare/Epic/Legendary (gewichtet zufällig)
- [ ] Gen-2 NFT minten mit neuer Token-ID
- [ ] Frontend: Breeding-UI im Dashboard

---

### #9 🏛 Governance Contract (ATC-9900) — DAO Voting
**Datei:** `blockchain/contracts/governance/governance_contract.py`

- [ ] `Proposal` Datenstruktur (ID, Titel, Beschreibung, Optionen, Deadline)
- [ ] `create_proposal(title, description, options, voting_period)` 
- [ ] `vote(proposal_id, voter, option)` — gewichtetes Voting (ATC-Balance)
- [ ] `execute_proposal(proposal_id)` — nach Ablauf ausführen
- [ ] Quorum-Prüfung: min. 10% der ATC-Supply muss abstimmen
- [ ] Frontend: Governance-Seite im Dashboard (Sidebar: `🏛 DAO`)
- [ ] On-Chain: Voting-Ergebnis unveränderlich speichern

---

### #7 📦 Build System — EXE / AppImage Installer
**Datei:** `build/build.py`, `build/build.spec`

- [ ] `build/build.py` — PyInstaller-Config ausbauen
- [ ] Single-File EXE: Gateway + Backend + Frontend gebündelt
- [ ] Auto-Start: Gateway bootet beim EXE-Start
- [ ] Embedded Browser (CEF / PyWebView) für Dashboard
- [ ] Windows: `.exe` + Installer (NSIS oder Inno Setup)
- [ ] Linux: `.AppImage` Build
- [ ] macOS: `.dmg` (optional, Phase 3)
- [ ] GitHub Actions: automatischer Build bei Release-Tag

---

### #5 🌐 ATC Blockchain Explorer — Block & TX Browser
**Datei:** `frontend/index.html` (Sidebar: `🔍 Explorer`)

- [ ] Explorer-Seite im Dashboard
- [ ] Block-Liste: Height, Hash, Timestamp, TX-Anzahl
- [ ] TX-Detail-Ansicht: von/an/Betrag/Status
- [ ] Adress-Suche: Balance + TX-History
- [ ] Live-Update: neuer Block → Explorer aktualisiert sich
- [ ] Backend: `GET /api/blockchain/explorer/blocks` Endpoint
- [ ] Pagination für lange Block-Listen

---

### #2 🤖 Gemini AI Integration — Live AI-Chat *(Label: done — Issue schließen!)*
**Status:** ✅ Implementiert am 2026-06-08

- [x] `backend/api/routes/ai.py` — Gemini API Endpoint
- [x] API-Key Management via `.env` (`GEMINI_API_KEY`)
- [x] Gemini AI Orchestrator v2.1.0
- [x] ATCPromptContext + Cache
- [x] REST Routes: `/api/ai/ask`, `/analyze`, `/contract`, `/debug-tx`, `/health`
- [ ] ⚠️ Issue #2 auf GitHub **schließen** (ist noch open)

---

## 🟢 Priority LOW

### #10 🌉 Cross-Chain Bridge — ATC ↔ EVM Interoperabilität
**Datei:** `blockchain/bridge/bridge_contract.py` (neu)

- [ ] `bridge_contract.py` — Lock/Mint Mechanismus
- [ ] Lock-Contract auf A-TownChain: ATC einfrieren
- [ ] Mint-Contract auf EVM-Seite: Wrapped-ATC ausgeben
- [ ] Bridge-Relayer-Service: Events beobachten und weiterleiten
- [ ] Unterstützte Chains: Ethereum Sepolia, Polygon Mumbai, BSC Testnet
- [ ] Security: Multi-Sig für Bridge-Operationen
- [ ] Frontend: Bridge-UI im Dashboard (Sidebar: `🌉 Bridge`)

---

## ✅ Bereits abgeschlossen (Closed Issues)

| # | Titel | Abgeschlossen |
|---|-------|--------------|
| #21 | build(deps): flask-cors 4.0.1 → 6.0.0 (Dependabot) | 2026-06-08 |
| #6  | 🔐 ECDSA Signatur — Sichere TX-Autorisierung | 2026-05-20 |
| #4  | 💾 NFT Persistenz — SQLite statt In-Memory Storage | 2026-05-20 |
| #1  | 🔗 Smart Contract Implementation — ATC Token Standards | 2026-05-22 |

---

## 📊 Fortschritts-Übersicht

| Kategorie | Offen | Erledigt | Gesamt |
|-----------|-------|----------|--------|
| 🔴 P2P / Networking | 5 | 0 | 5 |
| ⛓ Blockchain / Contracts | 4 | 2 | 6 |
| 🎮 Gaming / NFT | 3 | 1 | 4 |
| 🖥 Frontend / UI | 3 | 0 | 3 |
| 🛠 DevOps / Build | 2 | 1 | 3 |
| 🤖 AI / KI | 0 | 1 | 1 |
| **Gesamt** | **17** | **5** | **22** |

---

## 🗺 Kritischer Pfad zum Testnet

```
#14 Bootstrap Node
    ↓
#15 Block Propagation
    ↓
#16 Initial Sync
    ↓
#17 Fork-Auflösung
    ↓
#18 Docker Compose 5-Node
    ↓
#8  Multi-Node Testnet LIVE ✅
```

*Alle 5 P2P-Issues müssen sequenziell abgearbeitet werden.*

---

*Auto-generiert von Superagent (KAI-OS Agent) — 2026-06-09*
