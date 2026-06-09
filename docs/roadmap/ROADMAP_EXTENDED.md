# Roadmap-Erweiterung — 11 neue Sprints + 4 Meilensteine

> Stand: 2026-06-09 | Erweiterung der bestehenden 26 Sprints
> Grundlage: Vollstaendigkeits-Audit (ROADMAP_COMPLETENESS_AUDIT.md)

---

## Neue Sprints (Phase 2 — Erweiterung)

### Sprint 2.9 — Frontier EVM-Pallet Integration (Sep 2026)

**Ziel:** KAI-OS kann Solidity-Contracts ausfuehren. MetaMask verbindet sich.

**Aufgaben:**
- [ ] Frontier-Pallet in Substrate-Runtime einbauen (pallet-evm, pallet-ethereum, pallet-base-fee)
- [ ] Chain-ID 9000 konfigurieren
- [ ] EVM-RPC aktivieren (Port 9933 fuer HTTP, 9944 fuer WebSocket)
- [ ] MetaMask-Verbindung testen (wallet_addEthereumChain)
- [ ] Basis-ERC-20 deployen und testen
- [ ] Blockscout-Explorer lokal aufsetzen
- [ ] KAI_EVM_CHAIN_ID.md Dokumentation schreiben

**Meilenstein:** MetaMask verbindet sich mit KAI-OS Devnet — erste ETH-TX on-chain

---

### Sprint 2.10 — IPFS-Mounting in ATCFS (Okt 2026)

**Ziel:** Dezentrale Dateien sind als lokales Filesystem mountbar.

**Aufgaben:**
- [ ] IPFS-Node in shivaos/fs/atcfs.py integrieren
- [ ] FUSE-Mount: IPFS-CID als Dateipfad mounten
- [ ] Verschluesselung at-rest: AES-256-GCM pro Datei
- [ ] Content-Adressierung: CID als Datei-Identifier
- [ ] Versionierung: Jede Aenderung = neuer CID (unveraenderlich)
- [ ] atcfs_spec_v2.md schreiben

---

## Neue Sprints (Phase 3 — Erweiterung)

### Sprint 3.9 — Solana Anchor-Programme (Feb 2027)

**Ziel:** ATC-SPL Token und erste Shivamon NFTs auf Solana Devnet.

**Aufgaben:**
- [ ] Anchor-Entwicklungsumgebung einrichten
- [ ] atc-spl-token Program implementieren (mint_from_bridge, burn_to_bridge)
- [ ] Solana Devnet Deployment
- [ ] Tests: Token-Transfer, Bridge-Mint, Bridge-Burn
- [ ] Phantom-Wallet Integration im Frontend
- [ ] docs/blockchain/SOLANA_INTEGRATION.md finalisieren

---

### Sprint 3.10 — Wormhole Bridge Substrate <-> Solana (Mär 2027)

**Ziel:** ATC fliesst zwischen Substrate und Solana.

**Aufgaben:**
- [ ] kai-bridge Anchor-Program (Wormhole-Integration)
- [ ] Bridge-Relayer-Service implementieren (Python/Rust)
- [ ] 3-of-5 Multi-Sig fuer Bridge-Operations
- [ ] Devnet End-to-End Test: ATC Substrate -> ATC-SPL Solana -> Rueck-Bridge
- [ ] Emergency-Pause-Mechanismus
- [ ] Bridge-Monitoring Dashboard
- [ ] Security-Review: Bridge-Logik

---

### Sprint 3.11 — Solidity Contract Suite + Hardhat (Apr 2027)

**Ziel:** Vollstaendige EVM-Contract-Suite auf KAI-OS Testnet.

**Aufgaben:**
- [ ] ATCToken.sol (ERC-20) mit Bridge-Roles
- [ ] ShivamonNFT.sol (ERC-721 + ERC-2981 Royalties)
- [ ] KAIGovernance.sol (Governor Bravo kompatibel)
- [ ] KAIMarketplace.sol (ERC-721 Marketplace)
- [ ] KAIBridge.sol (Lock/Unlock fuer ETH-Bridge)
- [ ] Hardhat-Tests: >90% Coverage
- [ ] Deployment auf KAI-OS Testnet (Chain-ID 9000)
- [ ] Etherscan-Verifikation (Blockscout)

---

### Sprint 3.12 — LLM-Router & RAG-System (Mai 2027)

**Ziel:** Agenten nutzen automatisch das beste Modell. Lokale Wissensbasis.

**Aufgaben:**
- [ ] KAILLMRouter implementieren (core/llm_router.py)
- [ ] pallet-ai-registry: ModelMetadata-Storage hinzufuegen
- [ ] IPFS-Modell-Download + BLAKE2b-Verifikation
- [ ] RAG-System: Qdrant lokal + On-Chain-State als Kontext
- [ ] Agent-Memory-Persistenz (IPFS + lokale Vektordatenbank)
- [ ] 5 Modelle in lokaler Registry (phi-3-mini bis llama3-8b)
- [ ] Tests: Router-Selektion, Modell-Verifikation

---

### Sprint 3.13 — Multi-Modal AI (Jun 2027)

**Ziel:** Agenten sehen Bilder, hoeren Audio, fuehren Code aus.

**Aufgaben:**
- [ ] Vision-Modul: LLaVA-1.6 Integration
- [ ] Audio-Modul: Whisper v3 (Speech-to-Text)
- [ ] Audio-Output: Bark (Text-to-Speech)
- [ ] Code-Execution-Sandbox: sicheres Python-Ausfuehren (seccomp + namespace)
- [ ] Tool-Use Framework: Agenten koennen curl, git, kai-cli aufrufen
- [ ] Multi-Modal API: POST /v1/agents/{id}/invoke mit file_attachments

---

## Neue Sprints (Phase 4 — Erweiterung)

### Sprint 4.5 — Solana Mainnet Deployment (Sep 2027)

**Aufgaben:**
- [ ] ATC-SPL Token auf Solana Mainnet deployen
- [ ] Shivamon NFT Collection auf Metaplex Mainnet
- [ ] KAI Marketplace auf Solana Mainnet
- [ ] Phantom/Solflare Wallet-Integration im Dashboard
- [ ] Solana-Explorer-Integration
- [ ] Announcement: Shivamon jetzt auf Solana!

---

### Sprint 4.6 — Ethereum Bridge Mainnet (Okt 2027)

**Aufgaben:**
- [ ] ATCToken.sol auf Ethereum Mainnet deployen
- [ ] Wormhole Bridge: Substrate <-> Ethereum live
- [ ] Etherscan-Verifikation
- [ ] Bridge-Bug-Bounty: $50k fuer kritische Schwachstellen
- [ ] Bridge-Versicherungsfonds: 5% aller Bridge-Fees

---

### Sprint 4.7 — Post-Quantum Kryptographie Migration (Nov 2027)

**Aufgaben:**
- [ ] CRYSTALS-Kyber (Key Encapsulation) evaluieren
- [ ] CRYSTALS-Dilithium (Digitale Signaturen) evaluieren
- [ ] Hybrides Schema: Ed25519 + Dilithium parallel
- [ ] Migration-Plan: Bestehende Keys ohne Downtime migrieren
- [ ] Substrate-Pallet fuer PQ-Signaturen
- [ ] Crypto-Agility: Algorithmus-Wechsel ohne Hard-Fork

---

### Sprint 4.8 — AI Safety Audit + Alignment Certification (Dez 2027)

**Aufgaben:**
- [ ] ConstitutionalChecker v2: KI-gestuetzte Echtzeit-Analyse
- [ ] Alignment-Score-System on-chain aktivieren
- [ ] Kill-Switch: DAO-Vote + Emergency-Multi-Sig
- [ ] Externer AI-Safety-Audit beauftragen (Trail of Bits / OpenMined / Redwood Research)
- [ ] Alignment-Score > 0.95 fuer alle System-Agenten
- [ ] Oeffentliches Transparency-Report veroeffentlichen

---

## Neue Meilensteine

### MK5 — Multi-Chain Live (Okt 2027)
**Bedingung:** Substrate + Ethereum + Solana verbunden. ATC fliesst ueber alle drei Chains.
**Beweis:** 100 successful Bridge-TXs ohne Fehler in 48h

### MK6 — AI Safety Certified (Dez 2027)
**Bedingung:** Externer Audit abgeschlossen. Alle System-Agenten Alignment-Score > 90.
**Beweis:** Oeffentlicher Audit-Report + On-Chain Certification-NFT

### MK7 — 100 Agenten Live (Sep 2027)
**Bedingung:** Dezentrale Agenten-Registry > 100 aktive, verifizierte Agenten.
**Beweis:** pallet-agent-registry: query active_agents() > 100

### MK8 — DeFi TVL $1M (Q1 2028)
**Bedingung:** Total Value Locked in L11 DeFi-Protokollen > $1.000.000.
**Beweis:** On-chain TVL-Oracle-Messung ueber 7 Tage

---

## Aktualisierte Meilenstein-Uebersicht (vollstaendig)

| Meilenstein | Bedingung | Sprint | Geplant |
|-------------|-----------|--------|---------|
| MK1 | Substrate-Node produziert Bloecke | 2.1 | Jul 2026 |
| MK2 | KI-Inferenz on-node, Agent deployed | 2.3 | Aug 2026 |
| MK3 | Multi-Node Testnet live (5 Nodes) | 2.8 | Dez 2026 |
| MK4 | Alpha-Release, externer Security-Audit | 3.6 | Apr 2027 |
| MK5 | Multi-Chain Live (Substrate+ETH+SOL) | 4.6 | Okt 2027 |
| MK6 | AI Safety Certified | 4.8 | Dez 2027 |
| MK7 | 100 aktive Agenten in Registry | 4.5 | Sep 2027 |
| MK8 | DeFi TVL $1M | 4.8+ | Q1 2028 |

---

*KAI-OS Wiki — Roadmap-Erweiterung | v1.0.0 | 2026-06-09*
