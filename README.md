# bluenexus
bluesky client
# 🌐 BlueNexus

Client Bluesky local, autonome, sans cloud.
*A local, self-contained Bluesky client — no cloud, no auth, no external dependencies.*

BlueNexus est une plateforme sociale complète qui tourne entièrement sur ta machine :
un script Bash génère un moteur Python (stdlib uniquement), qui sert une interface web
connectée à l'API publique Bluesky, avec une IA locale intégrée.

## ✨ Fonctionnalités

- 🔍 Recherche multi-profils — explore n'importe quel acteur Bluesky
-  Feed complet — posts d'un auteur en temps réel
- 🔥 Tendances & suggestions — découvre quoi et qui suivre
- 📬 Recherche de posts — interroge le réseau par mot-clé
- 🤖 Nexus AI — chat IA local (règles + mémoire de session), zéro appel cloud
- 💾 Cache intelligent — réponses API cachées (md5), stats calls / hits / errors
- 📄 Multi-pages — Accueil · Profil · Recherche · Tendances · À propos
- 🔒 Lecture seule — API publique Bluesky, aucune authentification requise

## 🧱 Architecture
bluenexus.sh (Bash, multi-passes)
   └── génère → server.py (Python 3, stdlib only)
                   ├── Module 1 : BlueskyAPI (client + cache)
                   ├── Module 2 : NexusAI (règles + mémoire)
                   ├── Module 3 : Search
                   ├── Module 4 : Feed
                   ├── Module 5 : Trending
                   ├── Module 6 : UI (rendu HTML)
                   └── Module 7 : Serveur HTTP (ThreadingMixIn)

## 📦 Prérequis

| Outil | Rôle |
|---|---|
| bash | lanceur multi-passes |
| python3 | moteur (stdlib uniquement) |
| curl | appels API (v2) |
| bc, md5sum | formatage & cache (v2) |

Aucune bibliothèque externe. Aucun pip. Aucun npm.

## 🚀 Démarrage
git clone https://github.com/Aissamohammedi88/bluenexus.git
cd bluenexus
chmod +x nexus2v
./nexus2v 8080

Puis ouvre : http://localhost:8080
════════════════════════════════════════════════
 🌐 http://localhost:8080
 📄 Pages : Profil dynamique · Feed · Search
 🔌 APIs : profile · feed · suggestions · search · trending · ai
 🤖 IA : Nexus local
 💾 Cache : /tmp/bluenexus/cache
════════════════════════════════════════════════

## 🔌 Endpoints API

| Endpoint | Description |
|---|---|
| GET /api/profile?actor= | Profil Bluesky |
| GET /api/feed?actor=&limit= | Feed d'un auteur |
| GET /api/search/actors?q= | Recherche d'acteurs |
| GET /api/search/posts?q= | Recherche de posts |
| GET /api/trending | Tendances |
| GET /api/suggestions | Suggestions |
| GET /api/ai?q= | Chat Nexus AI |

## 🗂 Structure du dépôt
bluenexus/
├── app.v1      # BlueNexus v2.0 — première plateforme complète (Bash + curl)
├── nexus2v     # BlueNexus v4.0 — moteur 7 modules, multi-passes, 0 code mort ⭐️ recommandé
├── LICENSE     # MIT
└── README.md

## 🧭 Historique des versions

| Version | Fichier | Apport |
|---|---|---|
| v2.0 | app.v1 | Multi-pages, cache, IA locale, 100 % Bash |
| v4.0 | nexus2v | Moteur Python modulaire (7 modules), vérification d'environnement, 0 code mort |

## 🤖 Nexus AI

IA locale à base de règles avec mémoire de session (100 échanges max).
Aucun appel externe : chaque réponse est générée sur ta machine.

## ⚖️ Licence

MIT — voir [LICENSE](LICENSE).

## 👤 Auteur

Aissa Mohammedi (DSK) — [GitHub](https://github.com/Aissamohammedi88)

---
*BlueNexus : le réseau plaforme client
