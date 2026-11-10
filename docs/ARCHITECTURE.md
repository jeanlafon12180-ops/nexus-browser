# NEXUS BROWSER — Architecture

## 1. Product architecture

NEXUS BROWSER will be developed as a Firefox-based desktop distribution.

```text
NEXUS branding and product configuration
                 |
                 v
       Firefox desktop application
                 |
       +---------+----------+
       |                    |
       v                    v
   Gecko engine        Browser services
       |              tabs, history, bookmarks,
       v              downloads, permissions
  Web content
       |
       v
  SpiderMonkey
```

This is a conceptual diagram. The Firefox application already contains the browser chrome, Gecko integration and browser services. NEXUS should customize these layers through documented configuration and small, reviewable patches.

## 2. Why not embed Gecko in Electron?

Gecko is not distributed as a simple, supported desktop widget comparable to Chromium Embedded Framework. Firefox's browser UI and engine are integrated in a large codebase. An Electron shell would use Chromium's rendering engine and would not meet the Gecko requirement.

## 3. Upstream strategy

- Track a deliberate Mozilla Firefox release or ESR baseline.
- Keep NEXUS changes in a small patch series.
- Record the upstream revision used for every build.
- Rebase and test patches when updating upstream.
- Preserve Mozilla and third-party license notices.
- Do not imply Mozilla endorses NEXUS.

## 4. Initial feature boundaries

### Milestone 0.1.0-alpha
- Project structure and build documentation.
- NEXUS name, icon and theme specification.
- Identify a reproducible Firefox build baseline.

### Milestone 0.2.0
- NEXUS-branded browser build.
- Basic browsing, tabs and address bar using Firefox desktop foundations.
- Verify builds on supported desktop platforms.

### Later milestones
- Bookmarks, history and downloads customization.
- Privacy controls and tracker protection configuration.
- Optional NEXUS IA integration, disabled by default until configured.

## 5. Privacy and security principles

- No browsing history or page contents sent to NEXUS services by default.
- AI features must be opt-in and clearly explain what data is transmitted.
- Never store passwords or session tokens in project telemetry.
- Keep permissions visible and user-controlled.
- Prefer upstream security fixes over long-lived local forks.

## 6. Platform strategy

Target platforms:
- Windows x64 initially; evaluate ARM64 separately.
- macOS supported architectures according to the selected Mozilla build baseline.
- Linux x86_64 initially; document distribution dependencies.

A single source tree does not guarantee identical packaging or support across operating systems. Each platform needs its own build and release validation.
