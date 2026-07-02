<h1 align="center">Micla&nbsp;DevTeam</h1>

<p align="center">
  <em>The software engineering team of <strong>Micla Design&nbsp;&amp;&nbsp;Engineering</strong></em>
</p>

<p align="center">
  <img alt="Platform" src="https://img.shields.io/badge/platform-Android%20%7C%20Web%20%7C%20Cloud-3DDC84">
  <img alt="Stack" src="https://img.shields.io/badge/stack-Kotlin%20%C2%B7%20Bun%20%C2%B7%20Docker-blue">
  <img alt="Focus" src="https://img.shields.io/badge/focus-offline--first%20%C2%B7%20real--time-4F46E5">
</p>

---

We design and build **offline-first, real-time systems for the field** — web/mobile apps,
backends, geospatial services, and the self-hosted infrastructure that runs them.

Our flagship work is the **Road Accident Platform (Ra)**: an end-to-end system for
digital accident reporting and emergency-services communication, built to run reliably
with intermittent connectivity and to satisfy public-sector deployment constraints.

## The Road Accident Platform

A complete suite spanning the tablet in the field, the cloud backend, the geospatial
services, the deployment gateway, and fleet device management.

| Repository | What it is | Built with |
| --- | --- | --- |
| **[RaApp](https://github.com/Micla-DevTeam/NewRaApp)** | Android app for field accident reporting & emergency VoIP/messaging. Offline-first, encrypted local storage. | Kotlin · Jetpack Compose · Clean Architecture · LiveKit · Socket.IO · PowerSync · SQLCipher · MapLibre |
| **[RaBackend](https://github.com/Micla-DevTeam/NewRaBackend)** | The cloud backend — REST API, media storage (MinIO), and the core domain services. | Bun · Fastify · TypeBox · PostgreSQL |
| **[RaLiveKit](https://github.com/Micla-DevTeam/RaLiveKit)** | Self-hosted real-time voice/video (WebRTC) service powering in-app calls and emergency coordination. | LiveKit · WebRTC · Docker |
| **[RaPowerSync](https://github.com/Micla-DevTeam/RaPowerSync)** | The offline-first sync service that keeps field tablets and the backend database in sync. | PowerSync · PostgreSQL · Docker |
| **[RaGateway](https://github.com/Micla-DevTeam/RaGateway)** | The platform front door — nginx web tier + WebSphere Liberty application-server hop, host-based routing to every service. | nginx · WebSphere Liberty · Docker Compose |
| **[RaMaps](https://github.com/Micla-DevTeam/RaMaps)** | Shared geospatial stack: vector tiles, routing, and geocoding for Tunisia, Morocco & Italy. | Martin · Valhalla · Photon |
| **[RaDocs](https://github.com/Micla-DevTeam/RaDocs)** | The multilingual (EN · FR · AR · IT) technical documentation portal for the platform. | Zensical (Material for MkDocs successor) |
| **[RaMDM](https://github.com/Micla-DevTeam/RaMDM)** | Self-hosted Mobile Device Management to provision and remotely manage the fleet of field tablets. | Headwind MDM · Tomcat · PostgreSQL · Docker |

### How the pieces fit together

```
                        ┌─ api.*     → WebSphere Liberty gateway (RaGateway) → Bun backend (RaBackend)
  Field tablet          ├─ s3.*      → MinIO (media)
                        ├─ sync.*    → Powersync (RaPowersync)
  (RaApp)  ──▶ nginx    ┼─ rtc.*     → LiveKit (voice/video) (RaLivekit)
   managed by           ├─ tiles.*   → Martin  ┐
   RaMDM                ├─ routing.* → Valhalla├─ RaMaps
                        └─ geocode.* → Photon  ┘
```

## What we care about

- **Offline-first** — the field has no guarantee of connectivity, so the app works fully offline and syncs when it can.
- **Real-time** — live voice, video, and messaging for emergency coordination.
- **Self-hosted & sovereign** — the whole stack runs on infrastructure we control, with encryption end to end.
- **Deployable under real constraints** — including public-sector requirements such as running on IBM WebSphere Application Server.

## Tech we work with

![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?logo=kotlin&logoColor=white)
![Jetpack Compose](https://img.shields.io/badge/Jetpack%20Compose-4285F4?logo=jetpackcompose&logoColor=white)
![Bun](https://img.shields.io/badge/Bun-000000?logo=bun&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)
![nginx](https://img.shields.io/badge/nginx-009639?logo=nginx&logoColor=white)
![LiveKit](https://img.shields.io/badge/LiveKit-00B3A4)
![MapLibre](https://img.shields.io/badge/MapLibre-295DAA?logo=maplibre&logoColor=white)

---

<p align="center">
  <sub>Micla&nbsp;DevTeam · part of <strong>Micla Design&nbsp;&amp;&nbsp;Engineering</strong></sub>
</p>
