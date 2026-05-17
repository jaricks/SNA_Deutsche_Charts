# SNA Deutsche Charts 🎵

Kollaborationsnetzwerk der erfolgreichsten deutschsprachigen Songs der Jahre 2015–2025.  
Semesterprojekt im Kurs **Netzwerkanalyse** (226305) an der **Hochschule der Medien Stuttgart**, Studiengang **Crossmedia-Redaktion/Public Relations (CR/PR)**.

**Autor:innen:** Jannes Rickerts, Emma Idestroem, Lilli Zenth, Alisa Wilhelm, Anna Stauß

---

## Inhalt des Repositories

| Datei | Beschreibung |
|---|---|
| `Nodelist` | Alle Knoten des Netzwerks (Songs, Akteure, Labels) |
| `Edgelist` | Alle Kanten des Netzwerks (Verbindungen mit Rollen) |
| `CODEBUCH.md` | Vollständige Dokumentation aller Variablen der Node- und Edgelist |
| `Wer_macht_den_Hit.Rmd` | Vollständiger R-Analyse-Code mit Kommentaren |

---

## Datengrundlage

Die Daten basieren auf den **Offiziellen Deutschen Charts** (GfK / offiziellecharts.de).  
Erfasst wurden die **zehn erfolgreichsten deutschsprachigen Songs pro Jahr** für den Zeitraum 2015–2025 (97 Songs nach Bereinigung von Mehrfachnennungen).

Zu jedem Song wurden folgende Beteiligte manuell recherchiert und kodiert:

- Künstler:innen (Performer)
- Songwriter:innen
- Produzent:innen
- Label (inkl. Zuordnung zu den Mutterkonzernen Warner, Sony, Universal)

---

## Codebuch

Die vollständige Dokumentation aller Variablen, ID-Konventionen und Kodierregeln für Node- und Edgelist ist in der Datei **[CODEBUCH.md](CODEBUCH.md)** im Repository hinterlegt.

---

## Netzwerk in R laden

```r
library(igraph)
library(tidygraph)

el <- read.csv("https://raw.githubusercontent.com/jaricks/SNA_Deutsche_Charts/refs/heads/main/Edgelist",
               header = TRUE, as.is = TRUE, sep = ",")

nl <- read.csv("https://raw.githubusercontent.com/jaricks/SNA_Deutsche_Charts/refs/heads/main/Nodelist",
               header = TRUE, as.is = TRUE, sep = ",")

s <- tbl_graph(nodes = nl, edges = el, directed = FALSE, node_key = "id")
```

---

*Dieses Projekt ist ein Semesterprojekt und nicht zur kommerziellen Weiterverwendung bestimmt.*
