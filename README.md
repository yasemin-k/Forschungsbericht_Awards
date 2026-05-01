Codebuch

## Forschungsinteresse

Ziel des Projekts ist die Analyse, ob frühere Auszeichnungen bei den Golden Globes und BAFTA Awards die Wahrscheinlichkeit erhöhen, zu einem späteren Zeitpunkt einen Oscar zu gewinnen oder nominiert zu werden.

Im Zentrum steht der Matthäus-Effekt bei Nominierungen und Auszeichnungen in den Kategorien Schauspiel, Regie und Drehbuch bei Oscars, Golden Globes und BAFTA.

## Hypothesen

H1 – Matthäus-Effekt
Personen mit früherer Award-Anerkennung bei den Golden Globes oder BAFTA (Nominierung oder Gewinn) haben eine höhere Wahrscheinlichkeit für spätere Oscar-Nominierungen oder -Gewinne.

H2 – Diversität
Wie divers sind nominierte und ausgezeichnete Personen hinsichtlich Ethnie?

H3 – Alter
Unterscheiden sich nominierte und ausgezeichnete Personen im Durchschnittsalter zwischen Männern und Frauen?

H4 – Geschlecht
Wie verteilt sich das Geschlecht in gemischten Kategorien?

## Datengrundlage

Zeitraum: (eintragen)
Awards:

* oscar
* golden_globe
* bafta

Analyseeinheit: Beziehung zwischen Person und Award-Event
Datentyp: Netzwerkdaten (Edge- und Nodelist)

## Netzwerktyp

gerichtetes Netzwerk (person → award_event)
gewichtetes Netzwerk (nominiert vs. gewonnen)
bipartites Netzwerk (Personen und Award-Events)

## Edge-Liste (edgelist.csv)

Jede Zeile beschreibt eine Beziehung zwischen einer Person und einem Award-Event.

from
Name der Person

to
Award-Event inklusive Jahr (z. B. oscar_2024)

year
Jahr der Preisverleihung

award
Art des Awards (oscar, golden_globe, bafta)

weight
Gewicht der Beziehung
1 = nominiert
2 = gewonnen

category
Kategorie der Auszeichnung (z. B. actor, actress, supporting_actor, supporting_actress, writing, directing)

project
Film/Projekt

## Node-Liste (nodelist.csv)

Metadaten zu allen Knoten im Netzwerk.

id
Name des Knotens

type
Knotentyp (person, award_event)

sex
Geschlecht (male, female, NA für award_event)

ethnicity
Ethnische Zuordnung (white, black, asian, latin, mixed, NA)

year_of_birth
Geburtsjahr (numerisch, NA für award_event)

## Modellierungsentscheidungen

Award-Events werden als jahresspezifische Knoten modelliert (z. B. oscar_2024)
Dadurch werden Mehrfachkanten vermieden
Das Jahr wird zusätzlich als Variable gespeichert, um zeitliche Analysen zu ermöglichen
Die Gewichtung unterscheidet zwischen Nominierung und Gewinn

## Datenbereinigung

Einheitliche Schreibweise in snake_case
Entfernung von Leerzeichen und Tippfehlern
Konsistente Kategorien bei award, category und ethnicity
Fehlende Werte werden als NA codiert

## Nutzung

Der Datensatz dient der explorativen Netzwerkanalyse und ermöglicht keine kausalen Aussagen.
