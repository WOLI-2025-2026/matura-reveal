# ZADANIA 2 — ZBIÓR: treść, implementacje C++, odpowiedzi

--

## Zadanie 2.1 — treść
![Zadanie 2.1](media/2025-zad-2-1.png)

--

## Zadanie 2.1 — implementacja (C++)
```cpp
bool czyPalindrom2_1(string tekst) {
    int size = tekst.size() - 1;
    for (int i = 0; i < size; i++) {
        if (tekst[i] != tekst[size - i - 1]) return false;
    }
    return true;
}

void Zadanie2_1() {
    ifstream plik(z2_symbole_txt_path);
    ofstream wynik("../wynik2_1.txt");
    string linia;
    while (getline(plik, linia)) {
        if (czyPalindrom2_1(linia)) {
            cout << linia << endl;
            wynik << linia << endl;
        }
    }
}
```

--

## Zadanie 2.1 — odpowiedź
```
++o+o++o+o++
+*+**++**+*+
*+o++**++o+*
*oo*o**o*oo*
+*++*oo*++*+
+o++oooo++o+
```

--

## Zadanie 2.2 — treść
![Zadanie 2.2](media/2025-zad-2-2.png)

--

## Zadanie 2.2 — implementacja (C++)
```cpp
bool czyKwadrat2_2(string linia[3], int start) {
    char znak = linia[0][start];
    for (int i = 0; i < 3; i++)
        for (int j = 0; j < 3; j++)
            if (linia[i][start + j] != znak) return false;
    return true;
}

struct wspolrzedne { int x; int y; };

void Zadanie2_2() {
    ifstream plik(z2_symbole_txt_path);
    ofstream wynik("../wynik2_2.txt");
    string linia[3]; getline(plik, linia[0]); getline(plik, linia[1]);
    int row = 1, num = 0; wspolrzedne w[2000];
    while (getline(plik, linia[2])) {
        for (int i = 0; i < (int)linia->size()-2; i++) {
            if (czyKwadrat2_2(linia, i)) { w[num++] = {row+1, i+2}; }
        }
        row++; linia[0]=linia[1]; linia[1]=linia[2];
    }
    wynik << num << " "; for (int i=0;i<num;i++) wynik<<w[i].x<<" "<<w[i].y<<" ";
}
```

--

## Zadanie 2.2 — odpowiedź
```
3 399 5 546 2 630 11
```

--

## Zadanie 2.3 — treść
![Zadanie 2.3](media/2025-zad-2-3.png)

--

## Zadanie 2.3 — implementacja (C++)
```cpp
int konwertuj_znak(char z){ return z=='o'?0 : (z=='+'?1:2); }

int konwertuj_ciag(string s){
    int len = s.length()-1, suma = 0;
    for (int i=1, idx=len-1; idx>=0; i*=3, idx--) suma += konwertuj_znak(s[idx])*i;
    return suma;
}

void Zadanie2_3() {
    ifstream plik(z2_symbole_txt_path);
    ofstream wynik("../wynik2_3.txt");
    string linia; getline(plik, linia);
    int mx = konwertuj_ciag(linia); string mxs = linia;
    while (getline(plik, linia)) {
        int now = konwertuj_ciag(linia);
        if (now > mx) { mx = now; mxs = linia; }
    }
    wynik << mx << " " << mxs;
}
```

--

## Zadanie 2.3 — odpowiedź
```
531246 *******o+*+o
```

--

## Zadanie 2.4 — treść
![Zadanie 2.4](media/2025-zad-2-4.png)

--

## Zadanie 2.4 — implementacja (C++)
```cpp
char konwertuj_cyfre(int c){ return c==0?'o' : (c==1?'+':'*'); }

string konwertuj_liczbe(int L){
    if (L==0) return string(1, konwertuj_cyfre(0));
    string res=""; int p=1; while (p*3<=L) p*=3;
    for (int i=p; i>0; i/=3){
        for (int k=2; k>=0; k--) if (k*i<=L){ L-=k*i; res+=konwertuj_cyfre(k); break; }
    }
    return res;
}

void Zadanie2_4() {
    ifstream plik(z2_symbole_txt_path);
    ofstream wynik("../wynik2_4.txt");
    string linia; int suma=0;
    while (getline(plik, linia)) suma += konwertuj_ciag(linia);
    wynik << suma << " " << konwertuj_liczbe(suma);
}
```

--

## Zadanie 2.4 — odpowiedź
```
527865439 ++oo*+oo*++ooo*o*++
```

--

## Zbiorcze wyniki
| Zadanie | Wynik |
|----------|--------|
| 2.1 | palindromy (zob. slajd 2.1) |
| 2.2 | 3 399 5 546 2 630 11 |
| 2.3 | 531246 *******o+*+o |
| 2.4 | 527865439 ++oo*+oo*++ooo*o*++ |
