<div align="center">

# ⬡ OSIRIS: SIGINT Enhanced Edition

### Open Source Intelligence & Reconnaissance Integrated System — SIGINT Fork

[![Next.js](https://img.shields.io/badge/Next.js-16-black?style=for-the-badge&logo=next.js)](https://nextjs.org)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=for-the-badge&logo=typescript&logoColor=white)](https://typescriptlang.org)
[![License](https://img.shields.io/badge/License-MIT-D4AF37?style=for-the-badge)](LICENSE)

**A production-grade OSINT platform extended with real-time SIGINT telemetry ingestion, historical data persistence, and relational intelligence mapping.**

</div>

---

## 🚀 SIGINT Enhanced Extensions

Esta versión de OSIRIS extiende la arquitectura base para entornos de inteligencia operativa y análisis de campo avanzado.

### Nuevas Capacidades
* **Motor de Ingesta (SIGINT):** Integración de hardware (`esp32`, `rf_system`) a través de un `scanner-server.js` dedicado para captura de telemetría en tiempo real.
* **Persistencia Relacional:** Gestión de historial de objetivos y base de datos local para análisis de datos históricos (`torres_totales.json`), permitiendo análisis fuera de línea.
* **Análisis de Comportamiento:** Lógica de triangulación integrada para el cálculo de posición basado en torres y mapeo relacional.
* **Visualización de Inteligencia:** Paneles extendidos para el monitoreo de señales y persistencia de alertas.

![Interfaz OSIRIS Mejorado](assets/Captura%20de%20pantalla_2026-07-07_22-31-33.png)

---

## Architecture (SIGINT Extended)

┌────────────────────────────────────────────────────────────┐
│                       OSIRIS CLIENT                        │
│ ┌──────────┐   ┌──────────┐   ┌───────────────┐ ┌────────┐ │
│ │ MapLibre │   │ SIGINT   │   │ RELATIONAL INT│ │ PERSIST│ │
│ │ GL (GPU) │   │ Panels   │   │ PERSISTENCE   │ │ ENGINE │ │
└────────────┴──────────────┴───────────────────┴──────────┘ │
├────────────────────────────────────────────────────────────┤
│                    NEXT.JS API ROUTES                      │
│ (Original +) /api/sdk/ingest | /api/intel/triangulation    │
├────────────────────────────────────────────────────────────┤
│                  INTEL LAYER / BACKEND (C2)                │
│ scanner-server.js (RF/SIGINT Ingestion) -> torres_totales  │
└────────────────────────────────────────────────────────────┘


---

## Overview

Osiris is a production-grade OSINT platform that provides situational awareness across multiple intelligence domains.

### Key Capabilities

| Domain | Data Points | Sources |
|--------|------------|---------|
| **Aviation** | Commercial, Private, Military, Jets | OpenSky Network |
| **Maritime** | 39 Global Ports, 10 Chokepoints | Static Naval Intel |
| **CCTV** | 2,000+ Cameras | TfL, WSDOT, Caltrans, NYC DOT, VicRoads |
| **Seismic** | Real-time M2.5+ | USGS Earthquake API |
| **Fires** | Active Hotspots | NASA FIRMS |
| **News** | 24/7 Live Streams | 25+ Global Broadcasters |
| **Cyber** | CVE Threats | NVD |

---

## Quick Start

```bash
git clone [https://github.com/kukitotelo/osiris-sigint-enhanced.git](https://github.com/kukitotelo/osiris-sigint-enhanced.git)
cd osiris-sigint-enhanced
npm install
npm run dev

