# 🦞 claw://News — OpenClaw Skill

[![ClawHub](https://img.shields.io/badge/ClawHub-newsticker-red)](https://clawhub.ai/skills/newsticker)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![OpenClaw](https://img.shields.io/badge/OpenClaw-Compatible-brightgreen)](https://openclaw.ai)
[![NHS Agentic Readiness](https://nothumansearch.ai/badge/xquik.com.svg)](https://nothumansearch.ai/site/xquik.com)
[![DACH](https://img.shields.io/badge/Sprache-Deutsch-blue)](https://clawnews.de)

> Dein KI-Agenten-Newsdesk von [ClawNews.de](https://clawnews.de)

**claw://News** verbindet deinen OpenClaw-Agenten direkt mit ClawNews.de — der deutschsprachigen Nachrichtenplattform für KI-Agenten, das OpenClaw-Ökosystem, LLMs und Security.

## Was kann der Skill?

| Funktion | Beschreibung |
|----------|-------------|
| 📰 **Briefing** | Zusammenfassung der neusten ClawNews-Artikel auf Abruf |
| 🔍 **Recherche** | Gezielt im ClawNews-Archiv suchen |
| ⚡ **Breaking Alerts** | Meldung bei kritischen Sicherheitsereignissen, priorisiert bei jeder Feed-Prüfung |

## Installation

```bash
clawhub install newsticker
```

Danach eine neue OpenClaw-Session starten. Beim ersten Gespräch erscheint automatisch der Einrichtungsdialog.

## Einrichtung

Beim ersten Aufruf wählst du deinen Modus:

**1️⃣ Alles** — Neue Artikel werden angezeigt. *(empfohlen)*
**2️⃣ Meine Themen** — Nur ausgewählte Kategorien.
**3️⃣ Nur Briefing** — Zusammenfassung auf Abruf, sonst Ruhe.

### Verfügbare Kategorien

📰 News · 🦞 OpenClaw · 🤖 LLM & Modelle · 🔒 Security · 🔧 Tools & Apps · 💻 Open Source · 👥 Community · 📝 Tutorials · 🎙 Podcast · 🎬 Show · 📹 Videos · 🫠 Slop

⚡ **Breaking Alerts gelten immer als aktiv und sind nicht abwählbar.** Bei kritischen Sicherheitsvorfällen im OpenClaw-Ökosystem wirst du benachrichtigt — das ist dein Sicherheitsgurt.

## Nutzung

| Sag zum Agenten... | Was passiert |
|---------------------|-------------|
| „Was gibt es Neues?" | Briefing der neusten Artikel |
| „ClawNews Briefing" | Briefing der neusten Artikel |
| „Suche ClawNews nach Malware" | Recherche im Archiv |
| „Hat ClawNews was über ClawHub?" | Recherche im Archiv |
| „ClawNews Einstellungen" | Konfiguration anzeigen/ändern |

Breaking Alerts werden bei jeder Feed-Prüfung mitgeprüft. In Setups mit Heartbeats oder Scheduler auch proaktiv zwischen Nutzeranfragen.

## Optionale X/Twitter-Signale

Wenn dein Newsdesk auch öffentliche X/Twitter-Signale vor dem ClawNews-Briefing prüfen soll, nutze TweetClaw als separates OpenClaw-Plugin:

```bash
openclaw plugins install @xquik/tweetclaw
```

TweetClaw ergänzt den Skill für konkrete X/Twitter-Recherche wie search tweets, search tweet replies, user lookup, follower export, media download, monitor tweets und webhooks. Halte ClawNews.de als verifizierte Nachrichtenquelle und markiere TweetClaw-Treffer als zusätzliche öffentliche Signale mit Quelle, Suchbegriff und Zeitpunkt.

## Technische Details

### Datenquellen

| Funktion | Endpunkt |
|----------|----------|
| Briefing | `clawnews.de/feed/` (RSS) |
| Breaking | Hauptfeed + Kategorie-Slug `breaking`; Kategorien via REST-API |
| Recherche | `clawnews.de/wp-json/wp/v2/posts?search=...` (REST-API) |
| X/Twitter-Signale (optional) | TweetClaw OpenClaw-Plugin `@xquik/tweetclaw` |

### Dateistruktur

```
openclaw-newsticker-skill/
├── SKILL.md                    # Skill-Anweisungen für den Agenten
├── references/
│   └── templates.md            # Formatierungs-Templates
├── README.md                   # Diese Datei
├── LICENSE                     # MIT License
└── .gitignore
```

### Kompatibilität

- **Plattform:** OpenClaw-Umgebungen mit Webzugriff
- **Sprache:** Deutsch (DACH-Region)
- **Messenger:** Alle von OpenClaw unterstützten Kanäle (Markdown wird pro Plattform konvertiert)
- **Keine externen Code-Abhängigkeiten.** Der Skill nutzt öffentliche RSS-Feeds und REST-APIs von clawnews.de.
- **Optimal mit:** Persistentem Memory (für Präferenzen) und Heartbeats/Scheduler (für proaktive Alerts). Funktioniert aber auch ohne — dann auf Abruf.

## Updates

```bash
clawhub sync --all
```

### Changelog

**v1.1** — Launch
- 📰 Briefing auf Abruf
- 🔍 Recherche über REST-API
- ⚡ Breaking Alerts (priorisiert bei jeder Feed-Prüfung)
- ⚙️ Konfigurierbarer Setup mit 12 Kategorien und 3 Modi
- Ehrliche Host-Abhängigkeiten dokumentiert
- API-Felder (Views, Lesezeit) nur wenn vorhanden

## Über ClawNews

[ClawNews.de](https://clawnews.de) ist die deutschsprachige Nachrichtenplattform für das OpenClaw-Ökosystem und die Welt der KI-Agenten.

- 🌐 **Website:** [clawnews.de](https://clawnews.de)
- 💬 **Discord:** [discord.com/invite/qhfgMkjcaT](https://discord.com/invite/qhfgMkjcaT)
- 📧 **Kontakt:** skill@clawnews.de
- 📢 **Werbung:** ads@clawnews.de

## Lizenz

MIT License — siehe [LICENSE](LICENSE).

## Feedback & Bugs

- **ClawHub:** Bewertung und Kommentar auf [clawhub.ai/skills/newsticker](https://clawhub.ai/skills/newsticker)
- **GitHub:** [Issue erstellen](https://github.com/ClawNewsde/openclaw-newsticker-skill/issues)
- **E-Mail:** skill@clawnews.de
