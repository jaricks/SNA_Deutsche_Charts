**Codebuch**

**Edgelist (Edge-Attribute)**

**from**  
Songs (Sender einer Beziehung:  Entspricht ID in der Nodelist. Keine Sonderzeichen, nur ein Wort)

**to**  
Akteure (Empfänger: Entspricht ID in der Nodelist. Keine Sonderzeichen, etc.)

**year**  
welches Chartjahr (definiert einen Zeitraum, in dem die Beziehung zwischen zwei Knoten stattgefunden hat)

**edge\_role**  
definiert die Art des Akteurs bzw. wie er zum Song beigetragen hat 1=Künstler ("hat den Song performt"), 2=Writer ("hat den Song geschrieben/ komponiert), 3=Produzent ("hat den Song produziert), 4=Label ("hat den Song veröffentlicht)

**Nodelist (Node-Attribute)**

**id**

eindeutige Identifikation jedes einzelnen Knotens (vertex), der erfasst wird; damit wird dann in R gearbeitet

**name**

Name oder Bezeichnung des Knotens, der dann im netzwerk auch angezeigt wird (also vollständig)

**sex**

Geschlecht; bei Label und Songs NA

**type**

Unterscheidung zwischen Songs und Akteuren; Akteure sind Künstler, Writer, Produzenten, Label (alles außer Songs) Song=1, Akteur=2

**chart\_rank**

NUR BEI type=1 (sonst NA); die Chart-Platzierung als Zahl 1-100

**de\_rank**

Platz in unserem Ranking, also welchen Platz von den deutschsprachigen Songs in den deutschen Charts 1-10

