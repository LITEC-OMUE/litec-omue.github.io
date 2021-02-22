---
title: "Produktionsprozess mit Odoo"
date: 2021-02-02
# thumbnail: "img/placeholder.png"
tags:
  - "Labor"

  
categories:
  - "BET"
  - "WINF"

# menu: main
typora-root-url: ../../static/
---
# ERP System "Odoo"  

## Produktion / Fertigung  

Fertigung ist grundsätzlich nur eine weitere "Route" wie Produkte beschafft werden können.  

MakeToOrder und MakeToStock sind möglich (und alle Unterarten wie AssembleToOrder, etc)  

### Stammdaten

- Alle Stammdaten der anderen Module (Verkauf, Einkauf, Artikel, etc)
- Stücklisten (BoM)
  - Set (Bausatz)
  - Stücklisten für Produktion
- Arbeitsplätze
- Arbeitspläne

#### Vorbedingungen, Vorbereitungen

- alle Komponenten welche in BoM eingehen, müssen als Produkte angelegt sein
- Arbeitsplätze anlegen
  - Alle in den Arbeitsplänen als Ressourcen angelegte Arbeitsplätze, Abteilungen, Maschinen etc. mit Kosten / Arbeitsstunde, Kapazität, Rüstzeiten,  anlegen. 
- Stücklisten anlegen (Bausatz oder Fertigungsstückliste=mit Arbeitsplan)
- Arbeitsplan anlegen (Verbindung einer Tätigkeit/Aufgabe mit einem Arbeitsplatz/Ressource und einer Zeitdauer)
  - Auftragsabhängig (für einen Auftrag)
  - Neutral (für viele verschiedene Produkte, z.B nur Verpacken)
  - Produktbezogen (für ein bestimmtes Produkt)
- Produkt - Arbeitsplan zuordnen (bei "echter" Produktion)
- Kontrolle der Zeiten und Kosten (Stückliste)

## Produktion/Fertigung Prozess

### Struktur

- Fertigungsauftrag besteht aus Arbeitsaufträgen (pro Schritt im Arbeitsplan)
  - Arbeitsaufträge werden automatisch aus Fertigungsauftrag generiert
- Demontageauftrag (Auftragsart ohne Arbeitsplan, für Zerlegen/Rückabwickeln von Fertigungsaufträgen) 

### Fertigen

- Fertigungsauftrag anlegen 
- Bestände prüfen - reservieren
- Auftrag einplanen (Starttermine prüfen bzw. anpassen)
- Arbeitsaufträge (Prozess) starten und abarbeiten
- Arbeitsaufträge Zeiten kontrollieren und ggf. korrigieren
- Fertigungsauftrag abschließen
- Kostenkontrolle des Fertigungsauftrages
- Bestandskontrolle des gefertigten Produktes

<!-- 

# Auszug aus alten Unterlagen

ACHTUNG bei mehrstufigen Fertigungen:
Z.B erst Fertigung Tisch, dann geht tisch in Überprodukt ein - aber selbes Vorgehen

Produkte/Artikel
Neuer Reiter unter "mehr" - Stücklisten, Verwendungsnachweis, etc. - zeigen

Stückliste (BoM = Bill of Material)
Jede BoM wird ein Produkt (siehe Filter "hergestellte Produkte"
Alle Komponenten einer Stückliste müssen als Produkt angelegt sein
Sets (Kit) werden auch als Stückliste abgebildet

Fertigungsauftrag (nur mit Stückliste) anlegen (LOMUE_YDIF mit Schraube und Odoo-Manual)
Hinweis: Schrauben als Verbrauchsartikel angelegt, daher keine Bestandsführung!
Hinweis: Fertigungsauftrag besteht aus einem oder mehreren Arbeitsaufträgen (pro Arbeitsplatz im Arbeitsplan)

 **Aufgaben 45 -47 durchführen lassen und dokumentieren!! (alle Bestellungen WE, RE, Zahlung buchen)**

 Demontageauftrag für ein Produkt machen und kontrollieren, ob Hauptprodukt wieder weniger am Lager und Komponenten wieder mehr am Lager

 **Aufgaben 48 durchführen lassen und dokumentieren!! (alle Bestellungen WE, RE, Zahlung buchen)**

 Arbeitsplatz
Zeigen der angelegten Arbeitsplätze
OEE = overall equipment effectivness oder GAE (Gesamtanlageneffektivität)

Arbeitsplan
Alle Vorgänge für die Fertigung des Produktes mit Arbeitsplätzen verbinden und Zeit abschätzen.
Arbeitsplan mit Bom des zu fertigenden Produktes verbinden

 **Aufgaben 49 -52 durchführen lassen und dokumentieren!! (alle Bestellungen WE, RE, Zahlung buchen)**

Fertigungsauftrag anlegen für Produkt (z.. Lomue Tisch)
Menge erfassen
Verfügbarkeit prüfen - dann wird reserviert – Lagerstand kontrollieren (Reservierungen)
Hinweis: Datum und Uhrzeit wann Auftrag laufen soll notieren
ACHTUNG: Echtzeit zwischen Start und Ende wird genommen
Planung (Auftrag oder Arbeitsplatz) ansehen - Auftrag hat Zeit eingeplant Ganttdiagramm

 

**Aufgaben 53-54 - durchführen lassen und dokumentieren!! (alle Bestellungen WE, RE, Zahlung buchen)**

Fertigungsartikel mit Komponente die beschafft werden muss (bspw. LOMUE_YDIV_AP)
Komponente vorher auf Bestand 0 setzen (Odoo Manual)
Replenish Fertigungsartikel – oder Neuen Fertigungsauftrag erzeugen
Komponente muss Anfrage erstellt werden (automatisch) - Hinweis: es dürfen keine Bestellungen offen sein.
Fertigungsauftrag für Fertigungsartikel muss angelegt werden (automatisch)

 MPS:
Fertigungsartikel auswählen (Bestandsmenge wird angezeigt)
In gewünschter Periode Produktionsmenge eintragen und berechnen
Wenn zu wenig Bestand verfügbar, wird Fertigungsauftrag angelegt und Beschaffung angestoßen (wie oben)
-->