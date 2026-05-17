# Codebuch

## Nodelist

| Variable | Beschreibung | Ausprägungen |
|---|---|---|
| `id` | Eindeutige Knoten-ID | Vergabe nach Knotentyp (siehe ID-Vergabe unten) |
| `name` | Anzeigename im Netzwerk | Freitext, z. B. `LEA`, `Whiteheart Records`, `Till Lindemann (Rammstein)` |
| `type` | Knotentyp | `1` = Song (Musikstück in den Charts), `2` = Akteur (Künstler:in, Songwriter:in oder Produzent:in), `3` = Label (Sub- oder Dachkonzern) |
| `year` | Erstes Chartjahr des Songs | Vierstellige Jahreszahl, z. B. `2024`. Nur bei `type = 1`, sonst `NA` |
| `sex` | Geschlecht der Person | `m` = männlich, `f` = weiblich. Nur bei `type = 2`, sonst `NA` |

## Edgelist

| Variable | Beschreibung | Ausprägungen |
|---|---|---|
| `from` | ID des Ausgangsknotens | ID eines Songs (bei `edge_role` 1–3) oder eines Dachkonzerns (bei `edge_role = 4`), z. B. `Wunder_24_25`, `B_Label_Sony` |
| `to` | ID des Zielknotens | ID eines Akteurs oder Labels, z. B. `Ayliva`, `Label_Whiteheart` |
| `year` | Chartjahr der Beziehung | Vierstellige Jahreszahl, z. B. `2024` |
| `edge_role` | Rolle des Akteurs beim Song | `1` = Künstler:in (tritt auf dem Song auf), `2` = Writer (hat den Song geschrieben), `3` = Produzent:in (hat den Song produziert), `4` = Label (Sublabel ist dem Dachkonzern zugeordnet) |

## ID-Vergabe

| Knotentyp | Muster | Beispiel-ID | Besonderheit |
|---|---|---|---|
| Song | `Songname_JJ` | `Zeit_24` | – |
| Song | `Songname_JJ_JJ` | `Wunder_24_25` | Song in mehreren Chartjahren erfasst |
| Song | `Wort_Wort_..._JJ` | `Was_du_Liebe_nennst_17_18` | Mehrteiliger Titel: Wörter durch Unterstriche verbunden |
| Akteur | `VornameNachname` | `HerbertGrönemeyer` | Sonderzeichen und Bindestriche werden entfernt, z. B. `DagAlexisKopplin` für Dag-Alexis Kopplin |
| Akteur | `VornameNachname` | `TillLindemann` | Bandmitglieder erhalten individuelle IDs; Gruppenzugehörigkeit steht im `name`-Feld in Klammern: `Till Lindemann (Rammstein)` |
| Label | `Label_Kurzname` | `Label_FourMusic` | Alle Sublabels tragen das Präfix `Label_` |
| Label | `B_Label_Konzern` | `B_Label_Sony` | Dachkonzerne tragen das Präfix `B_Label_`; Sublabels werden ihnen über `edge_role = 4` zugeordnet |
