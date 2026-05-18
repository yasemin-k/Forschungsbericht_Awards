# Codebuch

## Forschungsinteresse

Ziel des Projekts ist die Analyse, ob frühere Anerkennung bei den Golden Globes oder BAFTA Awards mit einer späteren Oscar-Nominierung beziehungsweise einem späteren Oscar-Gewinn zusammenhängt.

Im Zentrum steht der Matthäus-Effekt bei Nominierungen und Auszeichnungen in den Kategorien Schauspiel, Regie und Drehbuch bei Oscars, Golden Globes und BAFTAs.

## Hypothesen

H1 – Matthäus-Effekt:  
Frühere Award-Anerkennung bei den Golden Globes oder BAFTAs, in Form von Nominierungen oder Gewinnen, steht in Zusammenhang mit späterer Oscar-Anerkennung.

H2 – Ethnische Diversität unter Nominierten und Gewinner*innen:  
PoC sind im untersuchten Award-Netzwerk insgesamt seltener vertreten als weiße Personen.

H3 – Geschlechterverteilung in gemischten Kategorien:  
In den Kategorien Regie und Drehbuch sind Männer unter den Nominierten und Gewinner*innen stärker vertreten als Frauen.

H4 – Altersverteilung nach Geschlecht:  
Das Durchschnittsalter männlicher Nominierter und Gewinner liegt über dem Durchschnittsalter weiblicher Nominierter und Gewinnerinnen.

## Datengrundlage

Zeitraum: 2022 bis 2025

Awards:
- Oscar
- Golden Globe
- BAFTA

Analyseeinheit: Beziehung zwischen Person und Award-Event  
Datentyp: Netzwerkdaten (Edge- und Nodelist)

## Netzwerktyp

Es handelt sich um ein ungerichtetes, gewichtetes Two-Mode-Netzwerk aus Personen und Award-Events.

Die Kanten verbinden Personen mit den Award-Events Oscar, Golden Globe und BAFTA. Die Gewichtung unterscheidet zwischen Nominierung und Gewinn.

## Edge-Liste (edgelist.csv)

Jede Zeile beschreibt eine Beziehung zwischen einer Person und einem Award-Event.

from:  
Name der Person

to:  
Award-Event, z. B. Oscar, BAFTA oder Golden Globe

year:  
Jahr der Preisverleihung

award:  
Art des Awards: Oscar, Golden Globe oder BAFTA

weight:  
Gewichtung der Beziehung  
1 = Nominierung  
2 = Gewinn

category:  
Kategorie der Auszeichnung, z. B. acting, writing oder directing

project:  
Film/Projekt. Diese Variable wurde dokumentiert, aber nicht als eigener Knotentyp in das finale Netzwerk aufgenommen.

## Node-Liste (nodelist.csv)

Metadaten zu allen Knoten im Netzwerk.

id:  
Name des Knotens

type:  
Knotentyp: Person oder AwardEvent

sex:  
Geschlecht: male, female oder leer für Award-Events

ethnicity:  
Ethnische Zugehörigkeit, z. B. White, Black, Asian, Latin, Mixed, Indigenous, Arab oder leer für Award-Events

Die Variable non_white umfasst alle Personen, die im Datensatz nicht als White codiert wurden. Für die Ergebnisdarstellung wird diese Gruppe zusammenfassend als People of Color (PoC) bezeichnet. Dabei ist zu berücksichtigen, dass es sich um eine analytische Gruppierung innerhalb des Datensatzes handelt und nicht um eine individuell erhobene Selbstbezeichnung.

year_of_birth:  
Geburtsjahr, numerisch oder leer für Award-Events

## Modellierungsentscheidungen

Die Award-Events werden als Award-Knoten modelliert: Oscar, Golden Globe und BAFTA. Das Jahr der Preisverleihung wird zusätzlich als Variable in der Edgelist gespeichert, um zeitliche Analysen zu ermöglichen.

Die Gewichtung der Kanten unterscheidet zwischen Nominierung und Gewinn. Filme beziehungsweise Projekte wurden nicht als eigene Knoten in das finale Netzwerk aufgenommen, damit der Fokus auf Personen und Award-Events liegt.

## Datenbereinigung

- Einheitliche Schreibweise der Personen- und Award-Namen
- Entfernung überflüssiger Leerzeichen
- Korrektur von Tippfehlern
- Konsistente Kategorien bei award, category und ethnicity
- Fehlende Werte wurden leer gelassen, damit sie in R als NA eingelesen werden können

## Nutzung

Der Datensatz dient der explorativen Netzwerkanalyse. Er ermöglicht die Untersuchung von Zusammenhängen und strukturellen Mustern, erlaubt jedoch keine kausalen Aussagen.
## Nutzung

Der Datensatz dient der explorativen Netzwerkanalyse und ermöglicht keine kausalen Aussagen.
