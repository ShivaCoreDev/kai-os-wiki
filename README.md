# KAI-OS Wiki — v1.3.3-beta

> Dezentrales KI-gesteuertes Betriebssystem auf Blockchain-Basis
> Stand: 2026-06-09 | Lizenz: Apache 2.0 | Auto-Sync aktiv

---

## Status & Berichte

| Datei | Inhalt |
|-------|--------|
| [STATUS.md](./STATUS.md) | Live-Projektstatus, Traffic, Issue-Uebersicht |
| [PERFORMANCE_REPORT.md](./PERFORMANCE_REPORT.md) | Architektur & Performance-Analyse |
| [FIXES.md](./FIXES.md) | Bug-Fixes Status & Anwendung |
| [TODO.md](./TODO.md) | Master-Aufgabenliste |

---

## Architektur & Dokumentation

| Datei | Inhalt |
|-------|--------|
| [docs/kai-os-wiki.md](./docs/kai-os-wiki.md) | **Hauptwiki** — 8.429 Zeilen, 31 Kapitel |
| [docs/KAI_INTEGRATION.md](./docs/KAI_INTEGRATION.md) | KAI-OS Integration Guide |
| [docs/MIGRATION_MAP.md](./docs/MIGRATION_MAP.md) | Python -> Substrate Migration |
| [docs/ROADMAP_COMPLETENESS_AUDIT.md](./docs/ROADMAP_COMPLETENESS_AUDIT.md) | **Vollstaendigkeits-Audit** — Luecken, Fehler, Erweiterungen |

### Architektur

| Datei | Inhalt |
|-------|--------|
| [docs/architecture/CONSENSUS.md](./docs/architecture/CONSENSUS.md) | Konsens-Architektur (PoH + PoS + PoI) |
| [docs/architecture/GATEWAY.md](./docs/architecture/GATEWAY.md) | API-Gateway (Port 4000) |
| [docs/architecture/TESTNET.md](./docs/architecture/TESTNET.md) | Testnet Setup & Betrieb |
| [docs/architecture/WALLET_KEYGEN.md](./docs/architecture/WALLET_KEYGEN.md) | Wallet & Key-Generation |

---

## Blockchain-Integration (NEU)

| Datei | Inhalt |
|-------|--------|
| [docs/blockchain/SOLANA_INTEGRATION.md](./docs/blockchain/SOLANA_INTEGRATION.md) | **Kap. 32** — Anchor, SPL-Token, Shivamon NFT, Wormhole Bridge |
| [docs/blockchain/ETHEREUM_INTEGRATION.md](./docs/blockchain/ETHEREUM_INTEGRATION.md) | **Kap. 33** — Frontier-Pallet, Solidity Suite (ATCToken.sol, ShivamonNFT.sol), Hardhat, MetaMask |

---

## KI-Dokumentation (NEU)

| Datei | Inhalt |
|-------|--------|
| [docs/ai/LLM_ROUTER.md](./docs/ai/LLM_ROUTER.md) | **Kap. 35** — LLM-Router, Model-Registry on-chain, IPFS-Download |
| [docs/ai/AI_SAFETY.md](./docs/ai/AI_SAFETY.md) | **Kap. 38** — Constitutional AI, Kill-Switch, Alignment-Score, Audit-Trail |

---

## Roadmap

| Datei | Inhalt |
|-------|--------|
| [docs/roadmap/ROADMAP_EXTENDED.md](./docs/roadmap/ROADMAP_EXTENDED.md) | **Erweitert** — Sprint 2.9-4.8, Meilensteine MK5-MK8 (Solana, ETH, AI Safety) |

---

## Standards

| Datei | Inhalt |
|-------|--------|
| [docs/standards/ATC_ECOSYSTEM_STANDARDS.md](./docs/standards/ATC_ECOSYSTEM_STANDARDS.md) | Vollstaendige Oekosystem-Standards (ATC-001/8300/9000/9900 + ATS-001-008) |
| [docs/standards/ATC_STANDARDS.md](./docs/standards/ATC_STANDARDS.md) | ATC Token Standards |
| [docs/standards/ATS_STANDARDS.md](./docs/standards/ATS_STANDARDS.md) | ATS Technische Standards |

---

## Smart Contracts

| Datei | Inhalt |
|-------|--------|
| [docs/contracts/SHIVAMON_NFT_CONTRACT.md](./docs/contracts/SHIVAMON_NFT_CONTRACT.md) | Shivamon NFT Contract (Ink!) |
| [docs/contracts/ATC_TOKEN_STANDARD.md](./docs/contracts/ATC_TOKEN_STANDARD.md) | ATC Token Contract |

---

## Issues & To-Dos

| Datei | Inhalt |
|-------|--------|
| [docs/issues/OPEN_ISSUES_MASTER.md](./docs/issues/OPEN_ISSUES_MASTER.md) | Alle offenen Issues + Sub-Tasks |
| [docs/issues/](./docs/issues/) | Issue-Dokumentation nach Nummer (ISSUE_01-ISSUE_20) |

---

## Source-Code Spiegel (A-TownChain OS)

| Verzeichnis | Inhalt |
|-------------|--------|
| [code/shivaos/](./code/shivaos/) | ShivaOS Kernel, Consensus, P2P (atcnet), Filesystem (atcfs) |
| [code/blockchain/](./code/blockchain/) | Consensus (PoH/PoS/PoW/Hybrid), Nodes, Wallet, Contracts |
| [code/gateway/](./code/gateway/) | API-Gateway + 4 Middleware-Dateien |
| [code/core/](./code/core/) | Kernel, Event Bus, AI Kernel, KAI CLI |
| [code/backend/](./code/backend/) | API-Server, alle Routes, DB, Wallet |
| [code/atclang/](./code/atclang/) | ATCLang Lexer, Parser, VM, Compiler, REPL |
| [code/tests/](./code/tests/) | 7 Test-Dateien |
| [code/config/](./code/config/) | settings.json, kai_config.toml |
| [code/.github/workflows/](./code/.github/workflows/) | 4 CI/CD Workflows |

---

## Architektur (L0-L12 NFT-Stack)

| Layer | Komponente | Status | Kapitel |
|-------|-----------|--------|---------|
| L0 | Security (S1-S6) | Implementiert | 25 |
| L1 | Hardware | Geplant | 24 |
| L2 | Micro-Kernel (Rust) | In Migration | 24 |
| L3 | KI-Modul (pallet-ai-registry) | Implementiert | 24.3 |
| L4 | Blockchain (pallet-poh + GRANDPA) | Implementiert | 4 |
| L5 | P2P-Netzwerk (libp2p) | In Migration | 2.4 |
| L6 | Storage (IPFS + ATCFS) | In Migration | 2.5 |
| L7 | API & CLI | Implementiert | 8 |
| L8 | Governance (DAO) | Implementiert | 19 |
| L9 | Agent-Registry (pallet-agent-registry) | Implementiert | 10 |
| L10 | dApp-Oekosystem | Geplant | 5 |
| L11 | DeFi (AMM, Lending, Oracle) | Geplant | 26 |
| L12 | Gamification (Shivamon, Battle) | Teilweise | 27 |

---

## Links

- [A-TownChain OS Repo](https://github.com/A-TownChain-Okosystems/a-townchain-os)
- [Notion Roadmap](https://app.notion.com/p/373b826db85c8125ba83f04995191bf0)
- [Google Sheet Dashboard](https://docs.google.com/spreadsheets/d/1s8fl7u6Rr5bM0Rc49BJy5_kJp4NrUIffo4Mb3UGfPtY/edit)

---

*Letzte Aktualisierung: 2026-06-09 | Auto-Sync: Superagent (KAI-OS Agent)*
