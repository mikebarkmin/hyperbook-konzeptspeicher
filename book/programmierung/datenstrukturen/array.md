---
name: Array
lang: de
---

# Array

Oft möchte man viele gleichartige Daten (d.h. Daten mit demselben Datentyp) speichern, z.B. die ersten 1000 Primzahlen. Stell Dir vor, Du müsstest für jede dieser Zahlen einen eigenen Variablennamen vergeben:

```java
int p1 = 2;
int p2 = 3;
int p3 = 5;
...
int p1000 = ?!?
```

Oder stell Dir vor, Du möchtest dann diese 1000 gespeicherten Zahlen kommasepariert ausgeben (2, 3, 5, 7, …): 

```java
System.out.println(p1 + ", " + p2 + ", " + p3 + ", " + p4 + ", " + ... + p1000);
```

Zur Lösung des Problems gibt es die Datenstruktur Array.

## Basics

Ein Array (deutsch: "Feld") ist ein Datentyp, der es gestattet, viele gleichartige Daten (d.h. Daten mit demselben Datentyp) zu speichern und durch Angabe eines Indizes (d.h. ihrer Position innerhalb des Feldes) schnell auf sie zuzugreifen.

**Beispiel:**
Lege ein Feld an, in dem 10 int-Werte gespeichert werden können und nenne dieses Feld test.

```java
int[] test = new int[10]; 
```

Dabei ist int[] der Datentyp "Feld von int-Werten". Der Term new int[10] reserviert einen Speicherbereich, in dem 10 int-Werte Platz haben, füllt ihn mit zehn 0-Werten und liefert eine Referenz darauf zurück. Nach der Zuweisung (=) zeigt die Variable test auf diesen Speicherbereich.

Die zehn Werte nennt man Feldelemente. Sie werden mit den Indizes 0 bis 9 durchnummeriert. Du kannst Dir das Feld so vorstellen:

![](/images/programmierung/array/feld1.png)

**Zugriff auf die Feldelemente:**

* test[3] = 12; weist dem vierten(!) Feldelement den Wert 12 zu. Das Feld sieht danach so aus:

![](/images/programmierung/array/feld2.png)

* int a = test[0]; kopiert den Wert des ersten Feldelements in die Variable a.

## Prüfe dich

Gegebn ist der nachfolgende Quelltext. Was wird ausgegeben werden. Denke zuerst nach, bevor Du das Programm ausführst.

:::onlineide

```java Raetsel.java
int[] zahlen = new int[4];    //Das Feld zahlen hat 4 Werte, mit den Indizes 0, 1, 2, 3

zahlen[1] = 12;
zahlen[2] = 8;
zahlen[0] = zahlen[2] * 3;
zahlen[3] = zahlen[1] + zahlen[0];

for (int i = 0; i < 4; i++) {
   println(i + ": " + zahlen[i]);
}
```

:::

## Lineare Suche

Bei der linearen Suche wird das Array von Vorne nach Hinten durchlaufen. Dabei soll ein bestimmtes Objekt oder ein bestimmter Wert im Array gefunden werden.

Häufig wird zum Beispiel das größte Element in einem Array gesucht.


### Aufgabe

Das nachfolgende Programm soll den größten Wert in einem Array finden. 

1. Führe das Programm aus und erkläre, warum nicht das größte Element gefunden wird.
2. Verändere das Programm so, dass das größte Element ausgegeben wird.

:::onlineide

```java Suche.java
double[] werte = new double[10];

for (int i = 0; i < 10; i++) {
   werte[i] = Math.sin(i);
   println(i + ": " + werte[i]);
}

double maximum = werte[0]; 
for (int i = 1; i < 10; i++) {
   if(werte[i] < maximum) {
      maximum = werte[i];
   }
}

println("Der größte Wert ist: " + maximum, Color.lightseagreen);
```

:::

### Aufgabe

Manchmal soll auch überprüft werden, ob ein spezielles Element in einem Array vorhanden ist.

1. Implementiere die Methode `istVorhanden`, die überprüfen soll, ob ein Element im Array vorhanden ist. Wenn das Element nicht vorhanden ist, soll false zurückgegeben werden, wenn es vorhanden ist true.

:::onlineide

```java Finden.java
// TESTEN
Namensliste meineListe = new Namensliste();
System.out.println(meineListe.istVorhanden("Karl") + " (sollte true sein)");
System.out.println(meineListe.istVorhanden("Karlo") + " (sollte false sein)");
// TESTEN

public class Namensliste {

    private String[] namen;

    public Namensliste() {
        this.namen = new String[6];
        this.namen[0] = "Hans";
        this.namen[1] = "Karl";
        this.namen[2] = "Susi";
        this.namen[3] = "Karla";
        this.namen[4] = "Paul";
        this.namen[5] = "Xenia";
    }

    public boolean istVorhanden(String pName) {
        return false;
    }
}

```

:::




## Sortieren

Wenn ein Array nach einem bestimmten Wert sortiert werden soll, dann brauchen wir dazu einen Sortieralgorithmus.

In der Informatik wurden verschiedene Algorithmen entwicklet um Arrays zu sortieren.

Ein einfacher Algorithmus ist der Bubble Sort-Algorithmus. Das folgende Video erklärt diesen Algorithmus erst anschaulich und überführt in dann in Java Quelltext.

::youtube[Bubble Sort]{#Dv4qLJcxus8}

Der Bubble Sort-Algorithmus kann auch getanzt werden.

::youtube[Bubble Sort Folk Dance]{#lyZQPjUT5B4}
