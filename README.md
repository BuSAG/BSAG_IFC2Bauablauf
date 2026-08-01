# BSAG_IFC2Bauzustand

Eigenentwickeltes Tool zur modellbasierten Visualisierung von Bauzuständen in IFC-Modellen. Basierend auf den Merkmalen (Properties) `Bauphase` und `Rueckbauphase` werden Bauphasen regelbasiert dargestellt, um Abläufe zu analysieren, Mengen abzuleiten sowie Bauphasenpläne effizient zu erstellen und zu kommunizieren. Zusätzlich werden je Bauphase phasenabhängige Kollisionsprüfungen (Clash Rules) erzeugt, die ausschliesslich gleichzeitig vorhandene Bauteile vergleichen und dadurch keine Scheinkollisionen melden.

Der dazugehörige Use Case «Modellbasierte Planung Bauablauf» ist Teil des buildingSMART Use Case Management (UCM).

Independently developed tool for model-based visualization of construction states in IFC models. Based on the properties `Bauphase` and `Rueckbauphase`, construction stages are represented using rule-based logic to analyze processes, derive quantities, and efficiently create and communicate construction phase plans. In addition, phase-dependent clash rules are generated per construction phase; they compare only elements that coexist within the same phase and therefore report no false-positive clashes.

The related use case «Modelbased construction sequencing» is part of the buildingSMART Use Case Management (UCM).

🔗 [ucm.buildingsmart.org](https://ucm.buildingsmart.org/de/use-cases/3515/de)

## Beschreibung

«BSAG_IFC2Bauzustand» visualisiert Bau- und Rückbauphasen direkt aus IFC-Modellen auf Basis von openBIM-Standards. Durch die regelbasierte Logik der Merkmale `Bauphase` und `Rueckbauphase` werden Projektfortschritt und Bauteilzustände dargestellt. Das optionale Merkmal `Status` (Baustelleneinrichtung, Bauhilfsmassnahme, Drittprojekt) ermöglicht eine phasenübergreifende, die Phaseneinfärbung überlagernde Darstellung. Die Modelldaten werden dabei nicht verändert – es wird lediglich eine temporäre, merkmalsbasierte Einfärbung erzeugt.

✨ Funktionen  
🏗️ Phasenbasierte Visualisierung von Bauzuständen in einer interaktiven 3D-Vorschau mit Phasen-Zeitstrahl  
⚙️ Liest IFC2x3, IFC4.0 und IFC4.3  
📚 Nutzt Property-Logik, ohne die Modelldaten zu verändern  
💥 Erzeugt je Bauphase Clash Rules (*.bcr) – prüft nur gleichzeitig vorhandene Bauteile, keine Scheinkollisionen  
🎨 Optionale Status-Einfärbung (Baustelleneinrichtung, Bauhilfsmassnahme, Drittprojekt)  
📤 Exportiert SmartViews (*.bcsv), Clash Rules (*.bcr) und BCF (*.bcf) für BIMcollab ZOOM  
🧩 Exportiert Searchsets (*.xml) und eine TimeLiner-Aufgabenliste (*.csv) für Autodesk Navisworks  
🖼️ Erstellt farbcodierte IFC-Modelle je Phase, Einzelbilder (PNG/JPEG), mehrseitige PDF-Bauphasenpläne mit Plankopf und ein animiertes Daumenkino (GIF)  
🌐 Mehrsprachige Oberfläche (DE/EN/FR/IT), Dark Mode  
💾 Lokale Verarbeitung im Browser – keine Datenspeicherung; Projekteinstellungen als JSON/CSV sicher- und wiederverwendbar

🛠 Technologie  
Browserbasierte HTML-Applikation (Single-File) • Vanilla JavaScript • XML-Output

🌍 Open Source  
Ein transparentes, leichtgewichtiges Tool zur modellbasierten Bauphasen-Visualisierung.

## Overview

«BSAG_IFC2Bauzustand» visualizes construction and demolition stages directly from IFC models using openBIM standards. It applies rule-based logic to the properties `Bauphase` and `Rueckbauphase` to display project progress and element status. The optional property `Status` (site installation, temporary works, third-party project) provides a cross-phase representation that overlays the phase-based coloring. Model data is never modified – only a temporary, property-driven coloring is generated.

✨ Features  
🏗️ Phase-based visualization of construction states in an interactive 3D preview with a phase timeline  
⚙️ Reads IFC2x3, IFC4.0, IFC4.3 models  
📚 Uses property-driven logic without altering data  
💥 Generates clash rules (*.bcr) per phase – compares only coexisting elements, no false positives  
🎨 Optional status coloring (site installation, temporary works, third-party project)  
📤 Exports SmartViews (*.bcsv), clash rules (*.bcr) and BCF (*.bcf) for BIMcollab ZOOM  
🧩 Exports search sets (*.xml) and a TimeLiner task list (*.csv) for Autodesk Navisworks  
🖼️ Produces color-coded IFC models per phase, single images (PNG/JPEG), multi-page PDF phase plans with a title block, and an animated flip-book (GIF)  
🌐 Multilingual interface (DE/EN/FR/IT), dark mode  
💾 Local, in-browser processing – no data uploaded; project settings saved and reused as JSON/CSV

🛠 Tech Stack  
Browser-based HTML application (single file) • Vanilla JavaScript • XML output

🌍 Open Source  
Transparent, lightweight, and extendable tool for BIM phase visualization.

## Merkmale / Properties

| Merkmal (Property) | Datentyp | Wertebereich | Pflicht |
|---|---|---|---|
| `CH_Ing_Uebergeordnet.Bauphase` | IfcReal (Dezimalzahl) | ≥ 0 | ja |
| `CH_Ing_Uebergeordnet.Rueckbauphase` | IfcReal (Dezimalzahl) | ≥ 0 | ja |
| `CH_Ing_Uebergeordnet.Status` | IfcLabel (Text) | Baustelleneinrichtung; Bauhilfsmassnahme; Drittprojekt (oder projektspezifisch) | optional |

Wird ein Bauteil nicht rückgebaut, ist für `Rueckbauphase` der Wert `0` zu vergeben. Wird die Werteliste des Merkmals `Status` projektspezifisch erweitert, müssen sowohl das HTML-Tool (Farbzuordnung) als auch die mitgelieferte IDS-Prüfdatei (zulässige Werteliste) entsprechend angepasst werden.

## Disclaimer

Diese Software wurde eigenstaendig von den Partnern des jeweiligen Anwendungsfalles entwickelt und stellt eine unabhaengige Programmierung dar. Sie steht in keinem direkten oder indirekten Zusammenhang mit buildingSMART International oder einem seiner Chapters. Die Nutzung, Weitergabe oder Anpassung der Software erfolgt auf eigene Verantwortung. Fuer Fragen, Feedback oder Fehlermeldungen steht das GitHub-Repository des Projektes als zentrale Anlaufstelle zur Verfuegung.

Die bereitgestellte Software dient zur Umsetzung des Anwendungsfalles «Modellbasierte Planung Bauablauf» und erhebt keinen Anspruch auf Vollstaendigkeit oder offizielle Validierung durch buildingSMART oder andere Institutionen.

This software has been independently developed by the partners of the respective use case and represents a standalone programming effort. It is not directly or indirectly associated with buildingSMART International or any of its chapters. The use, distribution, or modification of the software is at the user's own risk. For questions, feedback, or issue reports, please refer to the project's GitHub repository as the central point of contact.

The provided software has been developed for the implementation of the use case «Modelbased construction sequencing» and does not claim completeness or official validation by buildingSMART or any other institution.
