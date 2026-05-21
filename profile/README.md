# Arborisis

<p align="center">
  <img src="./profile/logo.svg" alt="Arborisis Logo" width="200" />
</p>

<p align="center">
  <em>Plateforme sociale premium de field recording dediee aux sons de la nature.</em>
</p>

<p align="center">
  <a href="https://arborisis.com"><img src="https://img.shields.io/badge/Website-arborisis.com-4CAF50?style=flat-square&logo=safari&logoColor=white" alt="Website" /></a>
  <a href="https://discord.gg/arborisis"><img src="https://img.shields.io/badge/Discord-Rejoindre-5865F2?style=flat-square&logo=discord&logoColor=white" alt="Discord" /></a>
  <a href="https://twitter.com/arborisis"><img src="https://img.shields.io/badge/Twitter-@arborisis-1DA1F2?style=flat-square&logo=twitter&logoColor=white" alt="Twitter" /></a>
</p>

---

## Qu'est-ce qu'Arborisis ?

Arborisis est une **plateforme sociale et educative** dediee au **field recording** et a la preservation des **sons de la nature**. Elle permet aux utilisateurs de :

- **Enregistrer et partager** des sons de la nature en haute qualite
- **Decouvrir** de nouveaux environnements sonores via une carte interactive
- **Contribuer** a la preservation acoustique de la biodiversite
- **Apprendre** grace a l'analyse automatique des enregistrements (BirdNET)
- **Interagir** avec une communaute passionnee par les sons naturels

## Architecture

La plateforme est decoupee en plusieurs services independants :

```
+-------------------------------------------------------+
|                    Arborisis Platform                  |
+-------------------------------------------------------+
|                                                        |
|  +--------+  +-------------+  +------------------+    |
|  |   App  |  | Discord Bot |  | Audio Services   |    |
|  | Laravel|  |   Node.js   |  | FastAPI + Python |    |
|  +--------+  +-------------+  +------------------+    |
|       |            |                  |               |
|  +----v------------v------------------v--------+      |
|  |         Cloudflare Workers              |     |     |
|  |  AI Agent | Audio Orchestrator | R2 Proxy|     |     |
|  +-------------------------------------------+      |
|       |            |                  |               |
|  +----v------------v------------------v--------+      |
|  |              Infrastructure                  |      |
|  |  Docker | Nginx | PostgreSQL | Redis | R2   |      |
|  +-----------------------------------------------+      |
|                                                        |
+-------------------------------------------------------+
```

## Repositories

| Repository | Description | Tech Stack |
|------------|-------------|------------|
| [<img src="https://img.shields.io/badge/-app-blue?style=flat-square&logo=laravel" />](https://github.com/Arborisis/app) | Application Laravel principale | PHP 8.4, Vue 3, PostgreSQL |
| [<img src="https://img.shields.io/badge/-discord--bot-5865F2?style=flat-square&logo=discord" />](https://github.com/Arborisis/discord-bot) | Bot Discord officiel | Node.js 22, Discord.js |
| [<img src="https://img.shields.io/badge/-audio--services-orange?style=flat-square&logo=python" />](https://github.com/Arborisis/audio-services) | Analyse audio et data science | Python, FastAPI, BirdNET |
| [<img src="https://img.shields.io/badge/-workers-F38020?style=flat-square&logo=cloudflare" />](https://github.com/Arborisis/workers) | Workers Cloudflare | TypeScript, Wrangler |
| [<img src="https://img.shields.io/badge/-infrastructure-green?style=flat-square&logo=docker" />](https://github.com/Arborisis/infrastructure) | Infrastructure et deploiement | Docker, Nginx, CI/CD |

## Fonctionnalites principales

### 🎵 Upload et partage audio
- Enregistrements haute qualite avec metadonnees GPS approximees
- Visualisations interactives (waveform, spectrogramme)
- Tags et categories par environnement

### 🗺️ Carte interactive
- Decouverte geographique des lieux d'ecoute
- Filtrage par type d'environnement (foret, ocean, montagne...)
- **Privacy-first** : coordonnees GPS exactes jamais exposees

### 🏆 Gamification
- Points de visite (Arborisis Points)
- Quetes quotidiennes et hebdomadaires
- Achievements et medals
- Systeme anti-cheat avec Redis

### 📻 Radio nature
- Diffusion en continu basee sur les enregistrements
- Generation automatique de contenu radio
- Personnalites DJ avec storytelling

### 🔬 Analyse audio
- Classification des especes via BirdNET
- Features audio : MFCC, centroid spectral, ZCR
- Visualisations : spectrogrammes, heatmaps

### 💰 ECHO
- Systeme de dons entre utilisateurs
- Integration Stripe pour les paiements
- Portefeuille virtuel et historique

## Stack technique globale

### Backend
- **Laravel 12.x** + PHP 8.4
- **PostgreSQL 16** + PostGIS
- **Redis** (cache, sessions, queues)
- **OpenSearch** (recherche)

### Frontend
- **Vue 3** + Composition API
- **Inertia.js** + **Tailwind CSS**
- **Vite** + **Pinia**
- **Leaflet** (carte) + **Wavesurfer.js** (audio)

### Services
- **FastAPI** (analyse audio)
- **Discord.js** (bot)
- **Cloudflare Workers** (edge computing)

### Infrastructure
- **Docker** + Docker Compose
- **Nginx** (reverse proxy)
- **GitHub Actions** + **GitLab CI**
- **Cloudflare R2** (stockage objet)

## Privacy & Securite

- **GPS exact jamais expose** - Coordonnees approximees uniquement
- **Floutage automatique** selon sensibilite ecologique
- **RGPD conforme** - Donnees exportables et supprimables
- **Uploads valides** - MIME, extension, taille, duree verifies
- **Rate limiting** et anti-cheat

## Contribution

Nous accueillons les contributions ! Veuillez consulter le [CONTRIBUTING.md](https://github.com/Arborisis/app/blob/main/CONTRIBUTING.md) de l'application principale.

## Communaute

- **Discord** : [discord.gg/arborisis](https://discord.gg/arborisis)
- **Twitter** : [@arborisis](https://twitter.com/arborisis)
- **Site web** : [arborisis.com](https://arborisis.com)

## License

Tous les repositories sont sous licence [MIT](LICENSE).

---

<p align="center">
  <em>Fait avec amour pour la nature.</em>
</p>
