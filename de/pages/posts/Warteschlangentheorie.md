---
title: "Warteschlangentheorie"
date: 2021-02-18

tags:
  - "Theorie"
  - "Grundlagen"

categories:
  - "BET"

# menu: main
#typora-root-url:
---

# Warteschlangentheorie

## Einführung


<img src="./assets/Warteschlangentheorie.assets/Warteschlange.png" style="zoom: 20%;" />



Die Warteschlangentheorie kann zur Analyse unterschiedlicher Systeme genutzt werden. Dazu gehören beispielsweise:

- Fertigungsstraßen in Betrieben
- Logistiksysteme
- Telekommunikationssysteme und Computer
- Verkehrs- und Infrastruktursysteme

Das Ziel der Warteschlangentheorie ist die Ermittlung von Wartezeiten innerhalb des Systems zur Optimierung der gesamten Abläufe. In der Regel sollen damit die Gesamtkosten des Systems minimiert werden, um das Unternehmen effektiver zu machen. 

Es werden unter anderem Vorgänge betrachtet, bei denen bestimmte Einheiten oder Transaktionen in unregelmäßigen oder unkontrollierbaren Abständen auf Engpässe treffen. Hier werden die ankommenden Einheiten abgefertigt, wobei es zu Wartezeiten kommen kann. 

<img src="./assets/Warteschlangentheorie.assets/Warteschlange_1.png" alt="Warteschlange_1" style="zoom: 80%;" />  

## Ein Beispiel als Einführung


Die Verpackungs- und Versandabteilung einer Firma ist 12 Stunden am Tag besetzt, wobei pro Tag 300 Schreibsets die Abteilung erreichen. Die Verpackung und der Versand eines Schreibsets dauert durchschnittlich 2 Minuten.   

## Fragen
1. Wie hoch ist die Auslastung der Verpackungs- und Versandabteilung? 
2. Wie lange dauert es durchschnittlich, bis ein Schreibset die Abteilung durchlaufen hat? 
3. Wie lange wird ein Set nicht bearbeitet, sondern wartet auf eine Bearbeitung? 
4. Wie viele Sets warten auf eine Bearbeitung? 
5. Wie viele Sets sind insgesamt in der Abteilung im Umlauf? 



## Abkürzungen

- λ=Ankunftsrate 

- μ=Servicerate / Outputrate / Durchsatz
  
- Bearbeitungsdauer
  
$$
\frac{1}{\mu}
$$

- ρ=Auslastung
$$
\rho=\frac{\lambda}{\mu}
$$

  


## Antworten auf die Fragen

### ad 1  Ankunftsrate, Outputrate, Auslastung

ad 1 **Ankunftsrate**

 λ = 300/12 = 25 /* 25 Sets pro Stunde kommen in der Verpackung an

ad 1 **Outputrate**

μ = 60/2 = 30 /* 30 Sets pro Stunde können die Verpackung verlassen 

ad 1 **Auslastung**

$$\rho=\lambda/\mu=25/30=83,3% Auslastung$$




### ad 2 Durchlaufzeit (Wartezeit + Bearbeitungszeit)

$$Ws=\frac{1}{\mu-\lambda}=1/(30-25) = 0,2 Stunden = 12 Minuten$$



### ad 3 Wartezeit Wq

$$Wq=Ws-1/\mu=12-2 Minuten = 10 Minuten$$

$$Wq=\frac{\rho}{(\mu-\lambda)}= \frac{\lambda}{\mu(\mu-\lambda)}=25/(30(30-25))=0,1666 Stunden = 10 Minuten$$



### ad 4 Anzahl Sets in der Warteschlange

$$Lq=(\rho*\lambda)/(\mu-\lambda)=\frac{ \lambda^{2} }{ \mu-(\mu-\lambda }=\frac{0,8333*25}{30-25}=4,167 Sets warten im Schnitt$$



### ad 5 Anzahl Sets in der Abteilung

$$Ls=\lambda/(\mu-\lambda)=25/(30-15)=5 Sets sind im System (wartend oder bearbeitend)$$



## **Formelsammlung Warteschlangentheorie**

λ=Ankunftsrate (Durchschnitt)
μ=Servicerate (Durchschnitt)−Outputrate
1/μ=Bearbeitungsdauer

ρ=Auslastung
$$\rho=\frac{\lambda}{\mu}$$

Durchlaufzeit, DLZ, Ws, Verweildauer (Durchschnitt) 
$$Ws=\frac{1}{(μ−λ)}$$

DLZ Warten, Wq, Verweildauer in Warteschlange (Durchschnitt) 
$$Wq=\frac{ρ}{(μ−λ)}=\frac{λ}{(μ(μ−λ))}$$

Anzahl Kunden im System, Ls
$$Ls=\frac{λ}{μ−λ}$$

Anzahl Kunden in Warteschlange,   

$$Lq=\frac{\rho*\lambda}{\mu-\lambda}=\frac{ \lambda^{2} }{ \mu-(\mu-\lambda }$$



