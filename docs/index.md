# C#-Nachschlagewerk

# Theorie
## Arrays in C#

Arrays sind Sammlungen von Elementen eines bestimmten Typs, die über einen Index abgerufen werden können.

[Übungsaufgabe](#Array-Basics)

### Allgemein

**Arrays** sind grundlegende Datenstrukturen in C# und dienen zur Speicherung von Sammlungen von Elementen. Hier sind einige ausführliche Stichpunkte, die das Konzept von Arrays in C# und ihre Funktionsweise erklären:

1. **Definition**: Ein Array in C# ist eine Sammlung von Elementen, die denselben **Datentyp** haben und über einen **Index** zugänglich sind.

2. **Deklaration**: In C# wird ein Array mit der Syntax `Datentyp[] ArrayName` deklariert, z.B. `int[] myArray;`.

3. **Initialisierung**: Arrays in C# können bei der Erstellung initialisiert werden, indem man ihnen eine Liste von Werten zuweist oder die Größe angibt. Beispiele: `int[] myArray = new int[5];` oder `int[] myArray = {1, 2, 3, 4, 5};`.

4. **Index**: Jedes Element im Array hat einen eindeutigen Index, der seine Position innerhalb des Arrays angibt. Indices sind typischerweise ganze Zahlen, die bei 0 beginnen.

5. **Speicherung**: Arrays in C# speichern ihre Elemente in aufeinanderfolgenden **Speicheradressen**, was sie effizient für den Zugriff auf Elemente anhand ihres Indexes macht. Also um bei einem int-Array der Länge 5 `int[] test = new int[4]` auf  den Index `3` zuzugreifen wird die Speicheradresse des ersten Elements `0` plus den Index mal der Länge des Datentyps (bei int `4 bytes`) gerechnet. Nehmen wir an Index 0 liegt an der "Speicheradresse" `8` dann liegt Index 3 bei `8+(3*4)` also `20`.

6. **Feste Größe**: Die Größe eines Arrays in C# ist festgelegt und kann nach der Erstellung nicht geändert werden. Um die Größe eines Arrays zu ändern, muss man normalerweise ein neues Array erstellen und die Elemente kopieren.

7. **Zugriff**: Elemente eines Arrays in C# können über ihren Index abgerufen oder geändert werden.

8. **Schleifen**: Arrays in C# können mit Schleifen durchlaufen werden, um auf ihre Elemente zuzugreifen oder sie zu bearbeiten. Häufig verwendete Schleifen sind `for`, `foreach` und `while`-Schleifen.

9. **Mehrdimensionale Arrays**: Arrays in C# können mehrere Dimensionen haben, wie z.B. 2D- oder 3D-Arrays. Mehrdimensionale Arrays sind im Grunde genommen Arrays von Arrays. Beispiele: `int[,] my2DArray = new int[3, 4];` oder `int[,,] my3DArray = new int[3, 4, 5];`.

10. **Jagged Arrays**: C# unterstützt auch unregelmäßige Arrays (jagged arrays), die Arrays von Arrays sind, wobei jedes innere Array eine unterschiedliche Länge haben kann. Beispiel: `int[][] myJaggedArray = new int[3][];`.

11. **Anwendungsbereiche**: Arrays in C# sind in vielen Bereichen der Programmierung und Informatik nützlich, z.B. bei der Speicherung von Daten, der Durchführung von Berechnungen und der Implementierung von Algorithmen.

12. **Alternative Datenstrukturen**: Arrays sind in C# nicht immer die beste Wahl für bestimmte Aufgaben. Andere Datenstrukturen wie `List<T>`, `HashSet<T>` oder `Dictionary<TKey, TValue>` können in bestimmten Situationen besser geeignet sein.




### Erstellen eines Arrays

Ein Array wird erstellt, indem man den Typ der Elemente, gefolgt von eckigen Klammern `[]` und dann den Array-Namen angibt. Du musst auch die Größe des Arrays bei der Erstellung festlegen.

Beispiel:

```csharp
int[] zahlen = new int[5];
```

#### Aufgabe: Erstellen eines String-Arrays

Erstelle ein String-Array mit dem Namen `namen` und einer Größe von 3.

<details>
<summary>Lösung</summary>

```csharp
string[] namen = new string[3];
```

</details>

### Füllen eines Arrays

Du kannst einem Array Werte zuweisen, indem du den Index verwendest.

Beispiel:

```csharp
zahlen[0] = 1;
zahlen[1] = 2;
zahlen[2] = 3;
zahlen[3] = 4;
zahlen[4] = 5;
```

#### Aufgabe: Füllen eines String-Arrays

Fülle das `namen`-Array mit den Werten "Max", "Mia" und "Tom".

<details>
<summary>Lösung</summary>

```csharp
namen[0] = "Max";
namen[1] = "Mia";
namen[2] = "Tom";
```

</details>

### Zugreifen auf Elemente eines Arrays

Um auf die Werte eines Arrays zuzugreifen, verwende den Index.

Beispiel:

```csharp
int zweiteZahl = zahlen[1];
```

#### Aufgabe: Zugreifen auf ein Element eines String-Arrays

Greife auf das zweite Element des `namen`-Arrays zu und speichere es in einer Variablen namens `zweiterName`.

<details>
<summary>Lösung</summary>

```csharp
string zweiterName = namen[1];
```

</details>

### Die `.Length`-Eigenschaft

Die `.Length`-Eigenschaft gibt die Anzahl der Elemente in einem Array zurück. Beachte, dass der höchste Index immer um eins kleiner ist als die `.Length`, da die Indizierung bei 0 beginnt.

Beispiel:

```csharp
int[] zahlen = new int[6];
int arrayLength = zahlen.Length; // arrayLength ist 6
int hoechsterIndex = arrayLength - 1; // hoechsterIndex ist 5
```

#### Frage: Was ist der höchste Index eines Arrays mit der Länge 10?

<details>
<summary>Antwort</summary>

Der höchste Index eines Arrays mit der Länge 10 ist 9, da die Indizierung bei 0 beginnt.

</details>


### Iterieren über ein Array

Um über die Elemente eines Arrays zu iterieren, verwende eine `for`-Schleife oder eine `foreach`-Schleife.

Beispiel:

```csharp
for (int i = 0; i < zahlen.Length; i++) {
  Console.WriteLine(zahlen[i]);
}

foreach (int zahl in zahlen) {
  Console.WriteLine(zahl);
}
```

#### Aufgabe: Iterieren über ein String-Array
Iteriere über das `namen`-Array und gib jeden Namen aus.

<details>
<summary>Lösung</summary>

```csharp
for (int i = 0; i < namen.Length; i++) {
  Console.WriteLine(namen[i]);
}

foreach (string name in namen) {
  Console.WriteLine(name);
}
```

</details>
    

### Negativer Index

In C# ist es nicht erlaubt, auf einen negativen Index zuzugreifen. Wenn du dies versuchst, wird eine `IndexOutOfRangeException` ausgelöst.

#### Frage: Was passiert, wenn du auf einen negativen Index zugreifst, z.B. `array[-1]`?

<details>
<summary>Antwort</summary>

Wenn du auf einen negativen Index zugreifst, wird eine `IndexOutOfRangeException` ausgelöst, da negative Indizes in C# nicht erlaubt sind.

</details>

    
# Aufgaben
    
## Array-Basics
    
**Pfad im Google Drive: `C#/Aufgaben/Array/Basics`**
**Direktlink zum Drive Ordner:** [Link](https://drive.google.com/drive/folders/16DGIMG3r0Jz6_PBtJpYvcHCVQmT29TyS?usp=share_link)
    
<details>
<summary>Aufgabe</summary>
    
```csharp
using System;

class ArrayBasics
{
    static void Main()
    {
        // Aufgabe 1: Deklariere ein leeres eindimensionales Array mit einer Größe von 3.
        // Hinweis: Verwende die Schreibweise "int[]" und "new int[3]".

        // Aufgabe 2: Fülle das Array aus Aufgabe 1 mit den Zahlen 1, 2 und 3.
        // Hinweis: Setze die Werte an den entsprechenden Positionen des Arrays.

        // Aufgabe 3: Deklariere und initialisiere ein neues eindimensionales Array mit den Zahlen 4, 5 und 6.
        // Hinweis: Verwende die Schreibweise "new int[] {...}".

        // Aufgabe 4: Gib das zweite Element des ersten Arrays aus.
        // Hinweis: Denke daran, dass Arrays bei 0 anfangen zu zählen.

        // Aufgabe 5: Ändere das dritte Element des zweiten Arrays auf 7.
        // Hinweis: Setze den Wert an der entsprechenden Position des Arrays.

        // Aufgabe 6: Gib alle Elemente des ersten Arrays in umgekehrter Reihenfolge aus.
        // Hinweis: Verwende eine for-Schleife und starte am Ende des Arrays.

        // Aufgabe 7: Schreibe eine Methode, die die Summe der Elemente eines eindimensionalen Arrays berechnet und zurückgibt.
        // Hinweis: Verwende eine for-Schleife und eine Variable zum Speichern der Summe.
    }

    // Implementiere die Methode für Aufgabe 7 hier.
}

```
    
</details>

<details>
<summary>Lösung</summary>
    
```csharp
using System;

class ArrayBasics
{
    static void Main()
    {
        // Aufgabe 1: Deklariere ein leeres eindimensionales Array mit einer Größe von 3.
        int[] array1 = new int[3];
        Console.Write("Aufgabe 1: Leeres Array: ");
        PrintArray(array1);
        Console.WriteLine();

        // Aufgabe 2: Fülle das Array mit den Zahlen 1, 2 und 3.
        array1[0] = 1;
        array1[1] = 2;
        array1[2] = 3;
        Console.Write("Aufgabe 2: Array mit Zahlen 1, 2 und 3: ");
        PrintArray(array1);
        Console.WriteLine();

        // Aufgabe 3: Deklariere und initialisiere ein eindimensionales Array mit den Zahlen 4, 5 und 6.
        int[] array2 = new int[] { 4, 5, 6 };
        Console.Write("Aufgabe 3: Array mit Zahlen 4, 5 und 6: ");
        PrintArray(array2);
        Console.WriteLine();

        // Aufgabe 4: Gib das zweite Element des ersten Arrays aus.
        Console.WriteLine("Aufgabe 4: Zweites Element des ersten Arrays: " + array1[1]);

        // Aufgabe 5: Ändere das dritte Element des zweiten Arrays auf 7.
        array2[2] = 7;
        Console.Write("Aufgabe 5: Zweites Array nach Änderung des dritten Elements: ");
        PrintArray(array2);
        Console.WriteLine();

        // Aufgabe 6: Gib alle Elemente des ersten Arrays in umgekehrter Reihenfolge aus.
        Console.Write("Aufgabe 6: Elemente des ersten Arrays in umgekehrter Reihenfolge: ");
        for (int i = array1.Length - 1; i >= 0; i--)
        {
            Console.Write(array1[i] + " ");
        }
        Console.WriteLine();

        // Aufgabe 7: Berechne die Summe der Elemente des zweiten Arrays.
        int sum = CalculateSum(array2);
        Console.WriteLine("Aufgabe 7: Summe der Elemente des zweiten Arrays: " + sum);
    }

    // Hilfsmethode zum Ausgeben eines Arrays.
    static void PrintArray(int[] array)
    {
        for (int i = 0; i < array.Length; i++)
        {
            Console.Write(array[i] + " ");
        }
    }

    // Methode zur Berechnung der Summe eines Arrays.
    static int CalculateSum(int[] array)
    {
        int sum = 0;
        for (int i = 0; i < array.Length; i++)
        {
            sum += array[i];
        }
        return sum;
    }
}

    
```

</details>
