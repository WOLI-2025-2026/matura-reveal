
# **Systemy liczbowe**

--

## **Dlaczego różne systemy liczbowe?**

* System dziesiętny (base-10) jest **naturalny dla człowieka** – używamy 10 cyfr (0–9).
* Komputery operują na **systemie binarnym (base-2)**, bo rozróżniają tylko dwa stany:
  **0 (brak napięcia)** i **1 (napięcie obecne)**.
* W informatyce używa się także **systemów pochodnych**:

  * ósemkowego (base-8)
  * szesnastkowego (base-16)


--

# **System binarny (dwójkowy)**

--

## **Porównanie systemu dziesiętnego i binarnego**

| System dziesiętny | System binarny |
| ----------------- | -------------- |
| 0                 | 0              |
| 1                 | 1              |
| 2                 | 10             |
| 3                 | 11             |
| 4                 | 100            |
| 5                 | 101            |
| 6                 | 110            |
| 7                 | 111            |
| 8                 | 1000           |

**Zasada:**
Każda kolejna pozycja to potęga podstawy (2⁰, 2¹, 2², …)

--

## **Przykład konwersji dziesiętnej → binarnej**

Przekształć 45₁₀ do systemu binarnego:

45 ÷ 2 = 22 r1

22 ÷ 2 = 11 r0

11 ÷ 2 = 5 r1

5 ÷ 2 = 2 r1

2 ÷ 2 = 1 r0

1 ÷ 2 = 0 r1

Odczytując od końca:
👉 **45₁₀ = 101101₂**

--

## **Dodawanie w systemie binarnym**

Dodawanie pisemnie:

```
   1011
+  0110
--------
  10001
```

👉 11₁₀ + 6₁₀ = 17₁₀ (czyli 10001₂)


--

# **System ósemkowy (ósemkowy = base-8)**

--

## **Podstawowe cyfry**

Cyfry: 0, 1, 2, 3, 4, 5, 6, 7

Każda pozycja to potęga 8:
8⁰, 8¹, 8², …

Przykład:
**472₈ = 4·8² + 7·8¹ + 2·8⁰ = 256 + 56 + 2 = 314₁₀**

--

## **Konwersja binarny → ósemkowy**

Grupujemy bity po **trzy od prawej**:

```
101011110₂ = 101 011 110 = 5 3 6
```

👉 **101011110₂ = 536₈**

--

## **Dodawanie w systemie ósemkowym**

Przykład:

```
   725₈
+  153₈
--------
  1100₈
```

Bo:
725₈ = 469₁₀
153₈ = 107₁₀
Suma = 576₁₀ = 1100₈ ✅

--

# **System szesnastkowy (hexadecimal)**

--

## **Cyfry w systemie 16**

| Cyfra | Wartość           |
| ----- | ----------------- |
| 0–9   | jak w dziesiętnym |
| A     | 10                |
| B     | 11                |
| C     | 12                |
| D     | 13                |
| E     | 14                |
| F     | 15                |

--

## **Konwersja binarny → szesnastkowy**

Grupujemy bity po **cztery od prawej**:

```
101110110011₂ = 1011 1011 0011 = B B 3
```

👉 **101110110011₂ = BB3₁₆**

--

## **Dodawanie w systemie szesnastkowym**

```
   2A₁₆
+  3F₁₆
--------
   69₁₆
```

Bo:
2A₁₆ = 42₁₀
3F₁₆ = 63₁₀
Suma = 105₁₀ = 69₁₆ ✅

--

```
   1A89
+   611
--------
   209A
```

👉 6793₁₀ + 1553₁₀ = 8346₁₀ (czyli 209A₁₆)

--

# **System trójkowy (base-3)**

--

## **Cyfry i wartości**

Cyfry: 0, 1, 2
Pozycje to potęgi 3: 3⁰, 3¹, 3², …

Przykład:
**210₃ = 2·9 + 1·3 + 0·1 = 21₁₀**

--

## **Dodawanie w systemie trójkowym**

Dodawanie pisemne:

```
  121₂₍₃₎
+ 210₍₃₎
---------
 1111₍₃₎
```

(→ 13₁₀ + 21₁₀ = 34₁₀, czyli 1111₍₃₎)

--

# **System siódemkowy (base-7)**

--

## **Cyfry i wartości**

Cyfry: 0, 1, 2, 3, 4, 5, 6
Pozycje: 7⁰, 7¹, 7², …

Przykład:
**254₇ = 2·49 + 5·7 + 4·1 = 98 + 35 + 4 = 137₁₀**

--

## **Dodawanie w systemie siódemkowym**

```
   452₇
+  263₇
--------
  1025₇
```

Bo:
452₇ = 233₁₀
263₇ = 137₁₀
Suma = 370₁₀ = 1025₇ ✅

--

# **Podsumowanie porównawcze**

| System       | Podstawa | Cyfry    | Przykład liczby |
| ------------ | -------- | -------- | --------------- |
| Binarny      | 2        | 0–1      | 101101₂         |
| Trójkowy     | 3        | 0–2      | 210₃            |
| Siódemkowy   | 7        | 0–6      | 254₇            |
| Ósemkowy     | 8        | 0–7      | 472₈            |
| Dziesiętny   | 10       | 0–9      | 314₁₀           |
| Szesnastkowy | 16       | 0–9, A–F | 2A₁₆            |

--

## **Dlaczego to ważne w informatyce?**

* System **binarny** – podstawa działania procesorów.
* System **ósemkowy i szesnastkowy** – skrócony zapis binarny (łatwiejszy odczyt bitów).
* Pozostałe systemy (np. trójkowy, siódemkowy) – użyteczne w badaniach nad logiką, teorią informacji i kryptografią.
