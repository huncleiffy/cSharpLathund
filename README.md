# 🏙️ C# Lathund - Staden C# 🏙️

## 📋 Innehållsförteckning
- [🏙️ C# Lathund - Staden C# 🏙️](#️-c-lathund---staden-c-️)
  - [📋 Innehållsförteckning](#-innehållsförteckning)
  - [📐 KLASSER = BLUEPRINTS/RITNINGAR](#-klasser--blueprintsritningar)
  - [🚗 OBJEKT = RIKTIGA SAKER SOM BYGGTS FRÅN BLUEPRINTSEN](#-objekt--riktiga-saker-som-byggts-från-blueprintsen)
  - [🔨 KONSTRUKTOR = STARTPAKET NÄR OBJEKTET SKAPAS](#-konstruktor--startpaket-när-objektet-skapas)
    - [Flera konstruktorer](#flera-konstruktorer)
  - [📦 VARIABLER = LÅDOR MED SAKER](#-variabler--lådor-med-saker)
  - [🎬 METODER = FUNKTIONER SOM GÖR SAKER](#-metoder--funktioner-som-gör-saker)
    - [Metoder med parametrar](#metoder-med-parametrar)
    - [Metoder som returnerar värden](#metoder-som-returnerar-värden)
  - [🪟 EGENSKAPER =  Fönster till objektets data](#-egenskaper---fönster-till-objektets-data)
  - [🧬 ARV = BARN SOM ÄRVER FRÅN FÖRÄLDRAR](#-arv--barn-som-ärver-från-föräldrar)
  - [🚪 Main() = STADENS HUVUDENTRÉ](#-main--stadens-huvudentré)
  - [🅿️ LISTOR = PARKERINGAR](#️-listor--parkeringar)
  - [🔁 LOOPAR = ROBOTAR SOM JOBBAR OM OCH OM IGEN](#-loopar--robotar-som-jobbar-om-och-om-igen)
    - [For-loop](#for-loop)
    - [Foreach-loop](#foreach-loop)
    - [While-loop](#while-loop)
  - [🛂 IF-SATSER = VAKTER SOM FATTAR BESLUT](#-if-satser--vakter-som-fattar-beslut)
  - [🎲 RANDOM = TÄRNING](#-random--tärning)
  - [✉️ PARAMETRAR = MEDSKICKADE PAKET](#️-parametrar--medskickade-paket)
  - [📢 CONSOLE = HÖGTALARE + MIKROFON](#-console--högtalare--mikrofon)
  - [🏷️ VIKTIGA NYCKELORD OCH TERMER](#️-viktiga-nyckelord-och-termer)
    - [`public` – Öppet för alla 🔓](#public--öppet-för-alla-)
    - [`private` – Privat och låst 🔒](#private--privat-och-låst-)
    - [`static` – Tillhör blueprinten, inte objektet 🏗️](#static--tillhör-blueprinten-inte-objektet-️)
    - [`namespace` – Stadsdelar 🏘️](#namespace--stadsdelar-️)
    - [`void` – Returnerar ingenting 🚫📦](#void--returnerar-ingenting-)
    - [`new` – Skapa nytt objekt 🆕](#new--skapa-nytt-objekt-)
    - [Sammanfattning av termer](#sammanfattning-av-termer)
  - [🧩 HELHETSBILD](#-helhetsbild)
  - [📚 Exempel: Komplett program](#-exempel-komplett-program)

---

## 📐 KLASSER = BLUEPRINTS/RITNINGAR
En **class** är en ritning, blueprint eller mall för hur något ska byggas.

**Exempel:**
* Bil-blueprint
* Person-blueprint  
* Bankkonto-blueprint
* Hund-blueprint

En blueprint beskriver hur något är uppbyggt - men det är inte själva grejen än.
```csharp
class Bil
{
    public string RegistreringsNummer;
    public string Tillverkare;
}
```

Detta är som blueprinten för hur en bil ska se ut.
Men än så länge finns ingen riktig bil. Bara blueprinten.

---

## 🚗 OBJEKT = RIKTIGA SAKER SOM BYGGTS FRÅN BLUEPRINTSEN
Ett **objekt** är en riktig grej som skapas från blueprint.
```csharp
Bil minBil = new Bil();
Bil dinBil = new Bil();
```

Nu skapades två riktiga bilar 🚗🚗

**Så:**
* **Class** = blueprint 📐
* **Objekt** = verklig sak som byggts från blueprint/ritningen 🚗

Du kan skapa många objekt från samma class.
Som flera bilar från samma fabrik - alla följer samma blueprint men är olika exemplar.

---

## 🔨 KONSTRUKTOR = STARTPAKET NÄR OBJEKTET SKAPAS
En **konstruktor** är en speciell metod som körs automatiskt när ett objekt skapas med `new`.
Den ser till att objektet får rätt startvärden direkt från början.

```csharp
class Bil
{
    public string Tillverkare;
    public string RegistreringsNummer;

    // Konstruktor - körs automatiskt vid "new Bil(...)"
    public Bil(string tillverkare, string regNummer)
    {
        Tillverkare = tillverkare;
        RegistreringsNummer = regNummer;
    }
}
```

Nu kan du skapa en bil och ge den värden direkt:
```csharp
Bil minBil = new Bil("Volvo", "ABC123");
```

Istället för att behöva sätta allt efteråt:
```csharp
// Utan konstruktor (mer kod, lättare att glömma något)
Bil minBil = new Bil();
minBil.Tillverkare = "Volvo";
minBil.RegistreringsNummer = "ABC123";
```

**Tänk så här:**
* Konstruktorn är som ett **startpaket** 🎁 — den ser till att varje ny bil som byggs redan har tillverkare och registreringsnummer från start.
* Utan konstruktor är bilen tom när den skapas och du måste fylla i allt själv efteråt.

### Flera konstruktorer
En klass kan ha flera konstruktorer med olika parametrar:
```csharp
class Bil
{
    public string Tillverkare;
    public string RegistreringsNummer;

    // Konstruktor med alla värden
    public Bil(string tillverkare, string regNummer)
    {
        Tillverkare = tillverkare;
        RegistreringsNummer = regNummer;
    }

    // Konstruktor med bara tillverkare
    public Bil(string tillverkare)
    {
        Tillverkare = tillverkare;
        RegistreringsNummer = "OKÄNT";
    }
}
```

---

## 📦 VARIABLER = LÅDOR MED SAKER
Variabler är lådor som lagrar information 📦
```csharp
int ålder = 25;
string namn = "Oskar";
bool ärBesiktad = true;
```

**Typer av lådor:**
* `int` → heltal 🔢 (123, 42, -5)
* `string` → text 📝 ("Hej", "Volvo")
* `bool` → sant/falskt ✔️❌ (true, false)
* `double` → decimaltal 🔢 (3.14, 99.99)
* `char` → enskild bokstav ('A', 'x')

---

## 🎬 METODER = FUNKTIONER SOM GÖR SAKER
Metoder är funktioner - de beskriver vad ett objekt kan göra.
```csharp
public void Kör()
{
    Console.WriteLine("Bilen kör!");
}

public void Bromsa()
{
    Console.WriteLine("Bilen stannar!");
}
```

**Metoder = beteenden.**

En bil kan:
* köra
* bromsa  
* tuta

En person kan:
* prata
* gå
* äta

### Metoder med parametrar
```csharp
public void Kör(int hastighet)
{
    Console.WriteLine($"Bilen kör i {hastighet} km/h");
}
```

### Metoder som returnerar värden
```csharp
public int BeräknaÅlder(int födelseår)
{
    return 2024 - födelseår;
}
```

## 🪟 EGENSKAPER =  Fönster till objektets data
Egenskaper (properties) är som kontrollerade fönster in till ett objekts privata rum.
Du kan kika in och ta ut saker, men du måste följa vissa regler.

```csharp
public class Bil
{
    private int hastighet; // Privat fält, låst inne i rummet

    public int Hastighet   // Egenskap, ett kontrollerat fönster
    {
        get { return hastighet; }. 
        set { hastighet = value; }
    }
}
```

I detta exempel kan `get` bara läsa värdet, men `set` kan kontrollera vad som får ändras.

Då kan man använda dem så här:
```csharp
Bil minBil = new Bil();
minBil.Märke = "Volvo";
minBil.Årsmodell = 2020;
Console.WriteLine($"Min bil är en {minBil.Märke} från {minBil.Årsmodell}");
```

**Varför egenskaper?**
* Du kan lägga in logik — t.ex. hindra negativa värden
* Du kan göra data skrivskyddat med bara `get` 🔒
* Det är standard i C# — de flesta klasser använder det

**Exempel med kontroll:**
```csharp
public class Bil
{
    private int hastighet;
    
    public int Hastighet
    {
        get { return hastighet; }
        set 
        { 
            if (value >= 0)
                hastighet = value;
            else
                Console.WriteLine("Hastigheten kan inte vara negativ!");
        }
    }
}
```

Nu kan du inte ge bilen en negativ hastighet — egenskapen vaktar vid dörren! 🛂

---

## 🧬 ARV = BARN SOM ÄRVER FRÅN FÖRÄLDRAR
Arv betyder att en klass kan ärva egenskaper och metoder från en annan klass.
```csharp
// Basklassen (föräldern)
class Pasta
{
    public string Form;
}

// Subklassen (barnet som ärver)
class Spaghetti : Pasta
{
    // Spaghetti får automatiskt egenskapen Form från Pasta!
}
```

**Tänk så här:**
* `Pasta` = förälder 👨‍👩‍👧
* `Spaghetti` = barn (en special-variant av Pasta)

När du skapar en Spaghetti får du både Pasta-egenskaper OCH Spaghetti-egenskaper.

**Varför arv?**
* Undvik att upprepa samma kod
* Skapa specialversioner av saker
* Exempel: Fordon → Bil, Motorcykel, Lastbil

**Konstruktorer vid arv:**
```csharp
class Spaghetti : Pasta
{
    public Spaghetti() : base("Spaghetti")
    {
        // base() = anropa förälderns konstruktor först
    }
}
```

`base()` skickar värden till föräldern så den kan byggas klart innan barnet skapas.

---

## 🚪 Main() = STADENS HUVUDENTRÉ
Programmet börjar alltid här.
```csharp
static void Main(string[] args)
{
    // Här startar allt!
    Console.WriteLine("Programmet startar!");
}
```

Detta är stadens huvudentré 🚪 Allt börjar härifrån.
Programmet frågar: "Vad ska jag göra först?"
Och svaret finns i `Main()`.

---

## 🅿️ LISTOR = PARKERINGAR
Listor lagrar många objekt av samma typ.
```csharp
List<Bil> bilar = new List<Bil>();
bilar.Add(minBil);
bilar.Add(dinBil);
```

Detta är en parkering 🅿️ med många bilar.

**Du kan:**
* Lägga till: `bilar.Add(nyBil)`
* Ta bort: `bilar.Remove(minBil)`
* Räkna: `bilar.Count`
* Komma åt: `bilar[0]` (första bilen)
* Kolla om tom: `bilar.Count == 0`

---

## 🔁 LOOPAR = ROBOTAR SOM JOBBAR OM OCH OM IGEN
Loopar gör samma sak flera gånger 🤖

### For-loop
```csharp
for(int i = 0; i < 10; i++)
{
    Console.WriteLine($"Detta är iteration {i}");
}
```

### Foreach-loop
```csharp
foreach(Bil bil in bilar)
{
    Console.WriteLine(bil.Tillverkare);
}
```

### While-loop
```csharp
while(spelet_pågår)
{
    // Fortsätt spela
}
```

---

## 🛂 IF-SATSER = VAKTER SOM FATTAR BESLUT
If är en vakt vid dörren som kontrollerar regler.
```csharp
if (ärBesiktad)
{
    Console.WriteLine("Du får köra!");
}
else if (ålder < 18)
{
    Console.WriteLine("För ung för att köra!");
}
else
{
    Console.WriteLine("Du får inte köra!");
}
```

Vakten kollar villkoret och bestämmer vad som händer 🛂

**Jämförelseoperatorer:**
* `==` → lika med
* `!=` → inte lika med
* `>` → större än
* `<` → mindre än
* `>=` → större än eller lika med
* `<=` → mindre än eller lika med

---

## 🎲 RANDOM = TÄRNING
```csharp
Random random = new Random();
int slumptal = random.Next(1, 7); // tal mellan 1-6
int slumptal100 = random.Next(0, 101); // tal mellan 0-100
```

Detta är en tärning 🎲 som används för slump.
Bra för spel, simuleringar eller när du vill variera något.

---

## ✉️ PARAMETRAR = MEDSKICKADE PAKET
När en metod får input skickas information med.
```csharp
void SlumpaBilar(List<Bil> bilLista, int antal)
{
    // Nu kan metoden jobba med bilListan och antal
    for(int i = 0; i < antal; i++)
    {
        bilLista.Add(new Bil());
    }
}
```

Metoden får paket med information ✉️ och kan använda dem.

---

## 📢 CONSOLE = HÖGTALARE + MIKROFON
Console är programmets sätt att prata med användaren.
```csharp
// Högtalare - programmet pratar
Console.WriteLine("Hej!"); 
Console.Write("Utan ny rad"); 

// Mikrofon - programmet lyssnar
string svar = Console.ReadLine(); 

// Rensa skärmen
Console.Clear();

// Färger
Console.ForegroundColor = ConsoleColor.Green;
Console.WriteLine("Grön text!");
Console.ResetColor();
```

Programmet kan både prata 📢 och lyssna 🎤

---

## 🏷️ VIKTIGA NYCKELORD OCH TERMER
Här är viktiga termer du kommer stöta på i C#. Tänk på dem som regler och skyltar i staden 🏙️

### `public` – Öppet för alla 🔓
Betyder att något är tillgängligt överallt, från vilken klass som helst.
```csharp
public string Namn; // Alla kan läsa och ändra Namn
```

### `private` – Privat och låst 🔒
Betyder att något bara kan användas inuti den egna klassen. Ingen annan klass kommer åt det.
```csharp
private int hemligKod; // Bara denna klass kan använda hemligKod
```

**Tänk så här:** `public` = öppen dörr, `private` = låst rum. Om du inte skriver något alls framför så är det `private` som standard i C#.

### `static` – Tillhör blueprinten, inte objektet 🏗️
Normalt tillhör variabler och metoder ett specifikt objekt. Men `static` betyder att det tillhör **klassen själv** — du behöver inte skapa ett objekt för att använda det.
```csharp
class Räknare
{
    public static int AntalBilar = 0; // Delas av ALLA objekt

    public Räknare()
    {
        AntalBilar++; // Ökar varje gång ett nytt objekt skapas
    }
}
```

Du kommer åt det via klassens namn, inte ett objekt:
```csharp
Console.WriteLine(Räknare.AntalBilar);
```

**Därför skriver vi `static void Main()`** — Main tillhör själva programmet, inte ett objekt.

### `namespace` – Stadsdelar 🏘️
Ett `namespace` grupperar klasser som hör ihop, precis som stadsdelar i en stad.
```csharp
namespace Fordon
{
    class Bil { }
    class Motorcykel { }
}

namespace Djur
{
    class Hund { }
    class Katt { }
}
```

**Tänk så här:** `namespace` håller ordning så att klasser med samma namn inte krockar. Det är som att ha en "Bil" i stadsdelen Fordon och en annan "Bil" i stadsdelen Leksaker — de kan heta samma sak utan att blandas ihop.

### `void` – Returnerar ingenting 🚫📦
En metod med `void` gör något men skickar inte tillbaka något värde.
```csharp
public void SägHej()
{
    Console.WriteLine("Hej!");
    // Inget return-värde
}
```

Jämför med en metod som returnerar:
```csharp
public int Addera(int a, int b)
{
    return a + b; // Skickar tillbaka ett värde
}
```

### `new` – Skapa nytt objekt 🆕
`new` används för att bygga ett objekt från en klass (blueprint).
```csharp
Bil minBil = new Bil(); // Skapar ett nytt Bil-objekt
```

### Sammanfattning av termer

| Nyckelord | Betydelse | Tänk som |
|-----------|-----------|----------|
| `public` | Tillgängligt överallt | 🔓 Öppen dörr |
| `private` | Bara tillgängligt i egen klass | 🔒 Låst rum |
| `static` | Tillhör klassen, inte objektet | 🏗️ Gemensam för alla |
| `namespace` | Grupp av klasser | 🏘️ Stadsdel |
| `void` | Returnerar inget värde | 🚫📦 Tomt paket |
| `new` | Skapar nytt objekt | 🆕 Bygg från blueprint |

---

## 🧩 HELHETSBILD
Så här hänger allt ihop:

1. **Program startar i Main** 🚪
2. **Main använder klasser (blueprintar)** 📐
3. **Klasser skapar objekt (riktiga saker)** 🚗👤🐕
4. **Objekt lagras i listor** 🅿️
5. **Metoder gör jobbet** 🎬
6. **Loopar upprepar** 🔁
7. **If fattar beslut** 🛂
8. **Console pratar med användaren** 📢

Och plötsligt har du ett levande program som fungerar som en hel stad! 🏙️

---



## 📚 Exempel: Komplett program
```csharp
using System;
using System.Collections.Generic;

class Program
{
    static void Main(string[] args)
    {
        // Skapa en lista med bilar
        List<Bil> bilar = new List<Bil>();
        
        // Skapa några bilar
        Bil bil1 = new Bil();
        bil1.Tillverkare = "Volvo";
        bil1.RegistreringsNummer = "ABC123";
        
        Bil bil2 = new Bil();
        bil2.Tillverkare = "Saab";
        bil2.RegistreringsNummer = "XYZ789";
        
        // Lägg till i listan
        bilar.Add(bil1);
        bilar.Add(bil2);
        
        // Skriv ut alla bilar
        foreach(Bil bil in bilar)
        {
            bil.VisaInfo();
        }
    }
}

class Bil
{
    public string RegistreringsNummer;
    public string Tillverkare;
    
    public void VisaInfo()
    {
        Console.WriteLine($"{Tillverkare} - {RegistreringsNummer}");
    }
    
    public void Kör()
    {
        Console.WriteLine("Bilen kör!");
    }
}
```
