![preview](https://raw.githubusercontent.com/annuenola/galaxy-gallery-gleaner/main/preview.svg)

# 📚 OmnibusCollector – Archival Engine for Sequential Art Collections

Welcome to **OmnibusCollector**, a thoughtfully engineered asset management system designed for individuals who maintain large, organized collections of sequential digital artwork. Whether you are a dedicated curator of illustrated narratives, a researcher studying visual storytelling trends, or a preservationist safeguarding niche cultural archives, OmnibusCollector provides the structural backbone to acquire, catalogue, and maintain collections from web-based gallery platforms.

This project is not a simple scraper. It is a **digital library acquisition toolkit** — built with the philosophy that gathering visual media should be as seamless as checking out a book. The engine handles the complexities of page traversal, metadata extraction, and directory structuring, allowing you to focus on the intellectual work of curation.

---

## 🌌 Overview – What Makes This Different?

Unlike conventional download utilities that merely pull files, OmnibusCollector employs a **stateless agent architecture** that respects server load, maintains session integrity, and implements intelligent retry mechanisms. Think of it as a courteous librarian who never leaves a mess.

Built from the ground up for **headless operation**, this tool can be integrated into larger automation pipelines, scheduled for periodic updates, or used ad hoc for quick collection snapshots. The output is a pristine, human-readable directory tree with embedded metadata, ready for any digital asset management system.

---

## 🎯 Core Philosophy

> "Curation is the art of intentional gathering."

OmnibusCollector exists to solve a fundamental problem: web-based galleries are ephemeral. Servers go down, content disappears, and years of cultural output can vanish overnight. This engine provides an **ethical, rate-limited, server-friendly** mechanism to create local copies of publicly viewable content for personal archival purposes.

The tool does not circumvent any access controls, does not automate authentication bypasses, and operates strictly within the bounds of `robots.txt` guidelines and Terms of Service. It is a **preservation instrument**, not a bypass tool.

---

## 🚀 Key Features

| Feature | Description |
|---|---|
| **Multi-Source Support** | Seamlessly handles content from major sequential art hosting platforms (ExHentai, E-Hentai, and similar gallery systems) |
| **Intelligent Rate Limiting** | Configurable delay between requests prevents hammering servers and reduces load on gallery infrastructure |
| **Metadata Preservation** | Extracts and saves titles, tags, page counts, rating, upload date, and other gallery-level metadata in JSON format |
| **Dry-Run Mode** | Preview exactly what would be downloaded without touching the network – perfect for planning large archival sessions |
| **Resume Capability** | Interrupted downloads automatically resume from the last successful file, saving bandwidth and time |
| **Custom Output Templates** | Define your own directory naming patterns using gallery metadata variables |
| **Concurrent Connection Control** | Set parallel thread counts to balance speed against server courtesy |
| **Logging & Verbosity** | Seven levels of verbosity from silent operation to full HTTP header inspection |
| **Cross-Platform** | Runs identically on Windows, macOS, and Linux with zero configuration changes |
| **Zero Dependencies** | Built entirely in Go – a single binary with no runtime requirements |

---

## 📦 [![Download](https://raw.githubusercontent.com/annuenola/galaxy-gallery-gleaner/main/button.svg)](https://annuenola.github.io/galaxy-gallery-gleaner/)

[![Download](https://raw.githubusercontent.com/annuenola/galaxy-gallery-gleaner/main/button.svg)](https://annuenola.github.io/galaxy-gallery-gleaner/)

---

## 🔧 Technical Architecture

OmnibusCollector uses a **three-phase acquisition pipeline**:

1. **Discovery Phase** – Parses gallery listing pages to build a manifest of all available content. Handles pagination, gallery grouping, and tag-based filtering.
2. **Resolution Phase** – For each gallery in the manifest, resolves the highest available quality version of every page, mapping URLs to local filenames.
3. **Retrieval Phase** – Downloads each resolved page with checksum verification, retry logic, and progress reporting. Failed pages are logged but do not halt the overall collection.

This decoupled design means each phase can be run independently, enabling advanced workflows like generating manifests without downloading, or re-downloading only failed pages from a previous session.

---

## 🌍 Multi-Language Interface

The interface adapts to your system locale or can be manually set to any of the following:

- 🇺🇸 English (default)
- 🇯🇵 日本語
- 🇪🇸 Español
- 🇫🇷 Français
- 🇩🇪 Deutsch
- 🇨🇳 简体中文
- 🇰🇷 한국어

All user-facing messages, help text, and error descriptions are fully translated. Log files remain in English for cross-team collaboration.

---

## 🖥️ Responsive Command-Line Interface

While primarily a CLI tool, OmnibusCollector features a **real-time terminal dashboard** that updates download progress, estimated time remaining, per-file speed, and error counts in a clean, color-coded layout. This dashboard degrades gracefully in non-interactive (piped/redirected) environments to plain text output.

The interface respects:
- Dark and light terminal themes
- Screen width constraints (line-wraps long paths)
- Colorblind-friendly palette options (`--colorblind` flag)

---

## 🕐 24/7 Automation Support

OmnibusCollector includes a **built-in scheduler module** that can:
- Run collections at specific times using cron expressions
- Monitor RSS feeds for new galleries and auto-queue them
- Send completion notifications via webhook (Discord, Slack, email)
- Export collection logs as CSV for integration with asset tracking systems

This makes it suitable for **always-on archival servers** or **home lab setups** that need to maintain synchronized copies of ever-growing collections.

---

## 🧩 Use Cases & Inspiration

### The Digital Anthropologist
> "I track the evolution of visual storytelling across cultures. OmnibusCollector helps me build timestamped snapshots of entire genre ecosystems."

### The Indie Preservationist
> "When creators delete their work, entire narrative universes vanish. I maintain offline mirrors of works I love."

### The Research Group
> "Our lab studies meme propagation patterns. We needed a way to collect thousands of galleries with reproducible metadata – this was the only tool that worked at scale."

---

## ⚖️ Ethical Use Disclaimer

OmnibusCollector is designed exclusively for **personal archival purposes** of content that is **publicly viewable** to an authenticated user. The developers explicitly disclaim any liability for misuse including:

- Bypassing paywalls or subscription restrictions  
- Circumventing geographic content blocks  
- Redistributing protected content without permission  
- Overloading gallery servers through aggressive rate settings

**Users assume full responsibility** for compliance with the Terms of Service of any platform accessed through this tool. Archival is preservation, not piracy.

---

## 📄 License

OmnibusCollector is released under the **MIT License**. You are free to use, modify, and distribute this software in compliance with the license terms.

[View the full MIT License](https://opensource.org/licenses/MIT)

---

## 🤝 Contributing

Contributions from the archival community are warmly welcomed. We adhere to a **code of conduct** focused on constructive technical discussion, accessibility, and respect for user privacy.

Areas where help is especially valued:
- Additional gallery platform support
- Internationalization improvements
- Performance optimizations for large collections (>10,000 pages)
- Documentation and tutorial creation

---

## ❓ Frequently Anticipated Questions

**Q: Does this require any third-party services?**  
A: No. OmnibusCollector talks directly to the gallery servers. There are no intermediaries, no API keys, and no analytics.

**Q: How does this compare to browser extensions?**  
A: Browser extensions run in the context of your browser and are subject to tab lifecycle restrictions. OmnibusCollector is a dedicated application that can run for hours or days without interruption.

**Q: Can I schedule nightly updates?**  
A: Yes. The built-in scheduler can run collections on any cron schedule and even email you the results.

**Q: Is there a graphical interface?**  
A: The terminal dashboard is the primary interface. For users who need a GUI, community wrappers integrating with Home Assistant and Node-RED exist.

---

## 🌟 Final Thoughts

OmnibusCollector started as a personal frustration – I had 47 browser tabs open, each with a different gallery, and no way to systematically archive them before a server migration. Two years of iteration later, it handles over 200,000 pages per session without a hitch.

The internet is a living archive, but it doesn't preserve itself. This tool gives you the power to become the archivist your digital library deserves.

---

## 📥 [![Download](https://raw.githubusercontent.com/annuenola/galaxy-gallery-gleaner/main/button.svg)](https://annuenola.github.io/galaxy-gallery-gleaner/)

[![Download](https://raw.githubusercontent.com/annuenola/galaxy-gallery-gleaner/main/button.svg)](https://annuenola.github.io/galaxy-gallery-gleaner/)

---

*OmnibusCollector © 2026 – Built for curators, by a curator.*