# -Luhn-Algorithmus
Der Luhn-Algorithmus, auch bekannt als Modul 10 oder Modul 10-Algorithmus
 **Schritte**, die am Luhn-Algorithmus beteiligt sind
 Lassen Sie uns den Algorithmus an einem **Beispiel** verstehen:
 Betrachten wir das Beispiel einer **Kontonummer** "79927398713".

**Schritt 1 -**  Ausgehend von der äußersten rechten Ziffer verdoppeln Sie den Wert jeder zweiten Ziffer,

![](https://github.com/killuahh/-Luhn-Algorithmus/blob/master/gfgedit-300x60.png)

**Schritt 2 -** Wenn die Verdoppelung einer Zahl eine zweistellige Zahl ergibt, d.h. größer als 9 (z.B. 6 × 2 = 12), dann addieren Sie die Ziffern des Produkts (z.B. 12: 1 + 2 = 3, 15: 1 + 5 = 6), um eine einstellige Zahl zu erhalten.

![](https://github.com/killuahh/-Luhn-Algorithmus/blob/master/gfg3-3-300x81.png)

**Schritt 3 -** Nehmen Sie nun die Summe aller Ziffern.

![](https://github.com/killuahh/-Luhn-Algorithmus/blob/master/SummeZiffern.png)

**Schritt 4 -** Wenn das Gesamtmodulo 10 gleich 0 ist (wenn die Summe auf Null endet), dann ist die Zahl gemäß der Luhn-Formel gültig; andernfalls ist sie nicht gültig.

![](https://github.com/killuahh/-Luhn-Algorithmus/blob/master/gfg2-2-300x101.png)
```cpp
using namespace std; 

// Returns true if given card number is valid
bool 
checkLuhn(const string& cardNo) {
  
  int nDigits = cardNo.length();

  int nSum = 0;

  for (int i = nDigits - 1; i >= 0; i--) {

     int d = cardNo[i] - '0';

     if (i % 2 == 0)
        d = d * 2;

    if (d > 9)
       d = d - 9;

    nSum += d;
  }
  return (nSum % 10 == 0);
}

 int main() 
 { 
    
    string cardNo = "79927398713"; 

     if (checkLuhn(cardNo)) 
         printf("This is a valid card"); 
     else
         printf("This is not a valid card"); 

     return 0; 
}
```



