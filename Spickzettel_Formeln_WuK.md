# 🎯 SPICKZETTEL: Formeln & Lösungsansätze WuK

## **1. KOMBINATORIK - BUCHSTABEN/ZIFFERN-ANORDNUNGEN**

### **a) Anzahl unterscheidbare Anordnungen**
**Formel:** $\frac{n!}{n_1! \cdot n_2! \cdot ... \cdot n_k!}$
- **Variablen:** n = Gesamtanzahl Buchstaben/Ziffern, n₁,n₂,... = Anzahl gleicher Elemente
- **Beispiel:** A,T,T,T,E,E → n=6, n₁=1(A), n₂=3(T), n₃=2(E) → $\frac{6!}{1! \cdot 3! \cdot 2!} = 60$
- **Vorgehen:** Zähle gleiche Elemente, dividiere durch deren Fakultäten

### **b) Anordnungen mit spezifischen Anfangs-/Endbuchstaben**
**Formel:** $\frac{(n-2)!}{n_1! \cdot n_2! \cdot ...}$ (ohne Anfangs-/Endbuchstabe)
- **Beispiel:** Beginnt mit E, endet mit T → $\frac{4!}{2! \cdot 2!} = 6$
- **⚠️ Gemeinheit:** Prüfe ob Anfangs-/Endbuchstabe mehrfach vorhanden!

### **c) Zusammenstehende gleiche Elemente**
**Vorgehen:** Behandle zusammenstehende Elemente als EINE Einheit
- **Beispiel:** TTT zusammen → (TTT),A,E,E → $\frac{4!}{1! \cdot 1! \cdot 2!} = 12$

### **d) Weitere Bedingungen**
**Prinzip:** Reduziere auf einfachere Teilprobleme
**Konkrete Beispiele aus Klausuren:**
- **BANANEN - beginnt UND endet mit A:** n=7, aber nur 2 A verfügbar → $\frac{5!}{3! \cdot 2!} = 10$
- **Fünfstellige Zahlen aus 1,1,2,2,2,3:** n=6, aber nur 5 Stellen → Fallunterscheidung welche Ziffer wegfällt
- **⚠️ Gemeinheit:** Bei "beginnt/endet mit X" prüfen ob genug X-Buchstaben vorhanden!

---

## **2. AUSWAHL-KOMBINATORIK**

### **a) Ohne Einschränkungen**
**Formel:** $\binom{n}{k} = \frac{n!}{k!(n-k)!}$
- **Variablen:** n = Gesamtanzahl Objekte, k = Anzahl zu wählender Objekte
- **Beispiel:** 7 aus 10 → n=10, k=7 → $\binom{10}{7} = \binom{10}{3} = 120$

### **b) Mit Pflichtauswahl (erste beiden)**
**Formel:** $\binom{n-p}{k-p}$ (p = Pflichtanzahl)
- **Variablen:** n = Gesamtanzahl, k = zu wählen, p = Pflicht-Objekte
- **Beispiel:** Erste 2 Pflicht, 7 aus 10 → n=10, k=7, p=2 → $\binom{8}{5} = 56$

### **c) Mit Mindest-/Höchstanzahl aus Teilmenge**
**Formel:** $\sum_{i=m}^{\min(r,k)} \binom{r}{i} \cdot \binom{n-r}{k-i}$
- **Variablen:** n = Gesamt, k = zu wählen, r = Teilmenge, m = Mindestanzahl aus Teilmenge
- **Beispiel:** Genau 3 aus ersten 5 → n=13, k=10, r=5, m=3 → $\binom{5}{3} \cdot \binom{8}{7} = 10 \cdot 8 = 80$

### **d) Weitere Bedingungen**
**Prinzip:** Aufteilen in Teilmengen, dann kombinieren
**Konkrete Beispiele aus Klausuren:**
- **Rosen-Aufgabe:** 6 Rosen, 4 Farben, "jede Farbe mindestens 1" → Inklusion-Exklusion
- **Schachbrett:** n ununterscheidbare Türme auf n×n Brett → Permutationsmatrix → n!
- **ODER-Bedingung:** "erste ODER zweite Aufgabe" → $\binom{9}{6}$ + $\binom{9}{6}$ (nicht beide gleichzeitig)
- **⚠️ Gemeinheit:** "mindestens" vs "genau" vs "höchstens" gut unterscheiden!

---

## **3. FAHRSTUHL-AUFGABEN**

### **a) Fahrstuhl hält nur einmal**
**Formel:** $\frac{k \cdot \binom{n}{n}}{k^n} = \frac{k}{k^n}$
- **Variablen:** n = Anzahl Personen, k = Anzahl Stockwerke
- **Beispiel:** 3 Personen, 4 Stockwerke → n=3, k=4 → $\frac{4}{4^3} = \frac{4}{64} = \frac{1}{16}$

### **b) Fahrstuhl hält mehrfach**
**Formel:** Gesamtmöglichkeiten $k^n$, dann spezifische Fälle berechnen
- **Variablen:** n = Anzahl Personen, k = Anzahl Stockwerke
- **Beispiel:** Hält 3-mal → n=3, k=4 → $\frac{4 \cdot 3 \cdot 2}{4^3} = \frac{24}{64} = \frac{3}{8}$

### **c) Gemeinsames Aussteigen**
**Formel:** $\frac{k \cdot \binom{n}{m}}{k^n}$ (m Personen zusammen)
- **Variablen:** n = Anzahl Personen gesamt, k = Stockwerke, m = Personen die zusammen aussteigen
- **Beispiel:** A,B zusammen → n=3, k=4, m=2 → $\frac{4 \cdot 4}{4^3} = \frac{16}{64} = \frac{1}{4}$

### **d) Alleine aussteigen**
**Formel:** $\frac{k \cdot (k-1)^{n-1}}{k^n}$
- **⚠️ Gemeinheit:** Andere dürfen nicht im gleichen Stockwerk!

---

## **4. SCHÜTZEN/TREFFER-AUFGABEN**

### **Binomialverteilung (genau k Treffer)**
**Formel:** $P(X = k) = \binom{n}{k} \cdot p^k \cdot (1-p)^{n-k}$
- **Variablen:** n = Anzahl Versuche, k = Anzahl Treffer, p = Trefferwahrscheinlichkeit
- **Beispiel:** 3 Schüsse, p=0.5, genau 2 Treffer → n=3, k=2, p=0.5 → $\binom{3}{2} \cdot 0.5^2 \cdot 0.5^1 = 0.375$

### **Mindestens/höchstens Treffer**
**Mindestens k:** $P(X \geq k) = 1 - P(X < k) = 1 - \sum_{i=0}^{k-1} \binom{n}{i} p^i (1-p)^{n-i}$
**Höchstens k:** $P(X \leq k) = \sum_{i=0}^{k} \binom{n}{i} p^i (1-p)^{n-i}$

### **Kombinierte Wahrscheinlichkeiten**
**Formel:** Multiplikation bei Unabhängigkeit, Addition bei Ausschluss
- **⚠️ Gemeinheit:** Prüfe ob Ereignisse unabhängig oder abhängig!
**Konkrete Beispiele aus Klausuren:**
- **3 Schützen gleichzeitig:** P(mindestens 1 trifft) = 1 - P(alle verfehlen) = 1 - 0.5×0.7×0.8
- **Tennis-Match:** Anne gewinnt 2 von 4 Sätzen → $\binom{4}{2} \cdot (2/3)^2 \cdot (1/3)^2$
- **Schützenkönig:** Wie oft schießen für 90% Chance? → $1 - (2/3)^n \geq 0.9$
- **⚠️ Gemeinheit:** Bei "alle/mindestens/höchstens" Komplement-Regel nutzen!

---

## **5. BAYES'SCHE AUFGABEN**

### **Grundformel (IMMER!):**
$$P(A|B) = \frac{P(B|A) \cdot P(A)}{P(B|A) \cdot P(A) + P(B|A^c) \cdot P(A^c)}$$

### **Standard-Schema:**
1. **Gegeben:** P(Krankheit), P(Test+|Krank), P(Test+|Gesund)
2. **Gesucht:** P(Krank|Test+)
3. **Rechnung:** $\frac{Sensitivität \cdot P(Krank)}{Sensitivität \cdot P(Krank) + Falsch-Positiv \cdot P(Gesund)}$

### **Beispielrechnung:**
- P(Krank) = 0.03, Sensitivität = 0.9, Falsch-Positiv = 0.02
- P(Krank|Test+) = $\frac{0.9 \cdot 0.03}{0.9 \cdot 0.03 + 0.02 \cdot 0.97} = \frac{0.027}{0.027 + 0.0194} = 0.582$

**⚠️ Gemeinheit:** P(Gesund) = 1 - P(Krank)!

---

## **6. URNEN-AUFGABEN**

### **a) Ohne Zurücklegen (Hypergeometrische Verteilung)**
**Grundformel:** $P(X = k) = \frac{\binom{r}{k} \cdot \binom{n-r}{m-k}}{\binom{n}{m}}$
- **Variablen:** n = Gesamtkugeln, r = gewünschte Farbe, m = gezogene Kugeln, k = gewünschte aus r
- **Beispiel:** Genau 2 rote aus 3, 2 Bälle gesamt → n=10, r=3, m=2, k=2 → $\frac{\binom{3}{2} \cdot \binom{7}{0}}{\binom{10}{2}} = \frac{3}{45}$

### **b) Mit Zurücklegen (Binomialverteilung)**
**Grundformel:** $P(X = k) = \binom{m}{k} \cdot \left(\frac{r}{n}\right)^k \cdot \left(\frac{n-r}{n}\right)^{m-k}$
- **Variablen:** n = Gesamtkugeln, r = gewünschte Farbe, m = Ziehungen, k = gewünschte Treffer
- **Beispiel:** Genau 2 rote aus 3, 2 Ziehungen → n=10, r=3, m=2, k=2 → $\binom{2}{2} \cdot (0.3)^2 = 0.09$

### **c) Mindestens k Kugeln einer Farbe**
**Strategie:** IMMER Gegenereignis verwenden!
**Formel:** $P(X \geq k) = 1 - P(X < k) = 1 - \sum_{i=0}^{k-1} P(X = i)$
- **Variablen:** n = Gesamtkugeln, r = gewünschte Farbe, m = gezogene Kugeln, k = Mindestanzahl
- **Ohne Zurücklegen:** $P(X \geq k) = 1 - \sum_{i=0}^{k-1} \frac{\binom{r}{i} \cdot \binom{n-r}{m-i}}{\binom{n}{m}}$
- **Mit Zurücklegen:** $P(X \geq k) = 1 - \sum_{i=0}^{k-1} \binom{m}{i} \cdot \left(\frac{r}{n}\right)^i \cdot \left(\frac{n-r}{n}\right)^{m-i}$

### **d) Höchstens k Kugeln einer Farbe**
**Formel:** $P(X \leq k) = \sum_{i=0}^{k} P(X = i)$
- **Variablen:** n = Gesamtkugeln, r = gewünschte Farbe, m = gezogene Kugeln, k = Höchstanzahl
- **Ohne Zurücklegen:** $P(X \leq k) = \sum_{i=0}^{k} \frac{\binom{r}{i} \cdot \binom{n-r}{m-i}}{\binom{n}{m}}$
- **Mit Zurücklegen:** $P(X \leq k) = \sum_{i=0}^{k} \binom{m}{i} \cdot \left(\frac{r}{n}\right)^i \cdot \left(\frac{n-r}{n}\right)^{m-i}$

### **e) Alle verschiedenfarbig**
**Formel:** $\frac{\text{Anzahl Farben auswählen} \times \text{Bälle pro Farbe}}{\text{Gesamtmöglichkeiten}}$
- **Variablen:** n = Gesamtkugeln, m = gezogene Kugeln, F = Anzahl Farben, b = Bälle pro Farbe
- **Beispiel:** 3 aus 4 Farben, je 2 Bälle → n=8, m=3, F=4, b=2 → $\frac{\binom{4}{3} \times 2^3}{\binom{8}{3}} = \frac{4 \times 8}{56} = \frac{32}{56} = \frac{4}{7}$

### **f) Genau k gleichfarbige + Rest andersfarbig**
**Formel:** $\frac{\text{Farben für k-Block} \times \binom{\text{Bälle der Farbe}}{k} \times \text{andere Farben} \times \text{andere Bälle}}{\binom{n}{m}}$
- **Variablen:** n = Gesamtkugeln, m = gezogene Kugeln, k = Anzahl gleichfarbige, F = Anzahl Farben, b = Bälle pro Farbe
- **Beispiel:** 2 rote + 1 andere → n=8, m=3, k=2, F=4, b=2 → $\frac{1 \times \binom{2}{2} \times 3 \times 2}{\binom{8}{3}} = \frac{1 \times 1 \times 6}{56} = \frac{6}{56}$

**Konkrete Beispiele aus Klausuren:**
- **SS14 Aufgabe 3c:** "Mindestens 1 roter Ball" → P = 1 - P(kein roter) = 1 - $\frac{\binom{6}{3}}{\binom{8}{3}}$ = 1 - $\frac{20}{56}$ = $\frac{36}{56} = \frac{9}{14}$
- **WS0607 Aufgabe 3:** "2 gleichfarbige ohne Zurücklegen" → P = $\frac{6}{90} + \frac{2}{90} + \frac{20}{90} = \frac{28}{90} = \frac{14}{45}$
- **⚠️ Gemeinheit:** Bei "mindestens" IMMER Gegenereignis berechnen - spart Zeit!

---

## **7. WÜRFEL-AUFGABEN**
**Vorgehen:** Alle möglichen Werte systematisch auflisten, Wahrscheinlichkeiten berechnen

### **a) Häufigste Augensumme bei 2 Würfeln**
**Methode:** Systematische Aufzählung aller 36 Kombinationen
- **Summe 2:** (1,1) → 1 Weg → P = 1/36
- **Summe 3:** (1,2), (2,1) → 2 Wege → P = 2/36
- **Summe 4:** (1,3), (2,2), (3,1) → 3 Wege → P = 3/36
- **Summe 5:** (1,4), (2,3), (3,2), (4,1) → 4 Wege → P = 4/36
- **Summe 6:** (1,5), (2,4), (3,3), (4,2), (5,1) → 5 Wege → P = 5/36
- **Summe 7:** (1,6), (2,5), (3,4), (4,3), (5,2), (6,1) → 6 Wege → P = 6/36 ⭐
- **Summe 8:** (2,6), (3,5), (4,4), (5,3), (6,2) → 5 Wege → P = 5/36
- **Summe 9:** (3,6), (4,5), (5,4), (6,3) → 4 Wege → P = 4/36
- **Summe 10:** (4,6), (5,5), (6,4) → 3 Wege → P = 3/36
- **Summe 11:** (5,6), (6,5) → 2 Wege → P = 2/36
- **Summe 12:** (6,6) → 1 Weg → P = 1/36
**Antwort:** Summe 7 ist am häufigsten mit P = 6/36 = 1/6

### **b) Unterscheidbare vs ununterscheidbare Würfel**
**Unterscheidbare Würfel:** 6ⁿ Möglichkeiten (n = Anzahl Würfel)
**Ununterscheidbare Würfel:** Multinomialkoeffizient verwenden
- **Formel:** $\frac{n!}{n_1! \cdot n_2! \cdot ... \cdot n_6!}$ wobei n₁...n₆ = Anzahl der jeweiligen Augenzahlen
- **Beispiel:** 3 ununterscheidbare Würfel → alle Kombinationen wie (1,1,1), (1,1,2), (1,2,3), etc. einzeln zählen

### **c) Min/Max bei mehreren Würfeln**
**Methode:** Systematische Aufzählung nach Werten
- **Min(X,Y) bei 2 Würfeln:** P(Min=1) = 11/36, P(Min=2) = 9/36, P(Min=3) = 7/36, etc.
- **Max(X,Y) bei 2 Würfeln:** P(Max=6) = 11/36, P(Max=5) = 9/36, P(Max=4) = 7/36, etc.
- **⚠️ Gemeinheit:** Keine Formel - immer alle Fälle einzeln durchgehen!

### **Wahrscheinlichkeitsfunktion**
**Konkrete Beispiele aus Klausuren:**
- **Min(X,Y) bei 2 Würfeln:** P(Min=1) = 11/36, P(Min=2) = 9/36, P(Min=3) = 7/36, etc.
- **Summe bei 2 Würfeln:** P(Summe=7) = 6/36 (höchste Wahrscheinlichkeit), P(Summe=2) = 1/36
- **Drei Würfel unterscheidbar vs ununterscheidbar:** Unterscheidbar = 6³ = 216, ununterscheidbar = andere Formel
- **⚠️ Gemeinheit:** Unterscheidbare vs ununterscheidbare Würfel komplett andere Rechnung!

### **Erwartungswert**
**Formel:** $E[X] = \sum_{i} x_i \cdot P(X = x_i)$
- **Beispiel:** E[Min] = 1·(11/36) + 2·(9/36) + 3·(7/36) + 4·(5/36) + 5·(3/36) + 6·(1/36) = 91/36

### **Varianz/Standardabweichung**
**Formel:** $Var(X) = E[X^2] - (E[X])^2$
**Standardabweichung:** $\sigma = \sqrt{Var(X)}$

---

## **8. MÜNZWURF-AUFGABEN**

### **Nur Kopf/Zahl**
**Formel:** $p^n$ oder $(1-p)^n$
- **Variablen:** n = Anzahl Würfe, p = Wahrscheinlichkeit für Kopf (meist 0.5)
- **Beispiel:** 8 mal Kopf → n=8, p=0.5 → $0.5^8 = \frac{1}{256}$

### **Genau k mal Kopf**
**Formel:** $\binom{n}{k} \cdot p^k \cdot (1-p)^{n-k}$
- **Variablen:** n = Anzahl Würfe, k = Anzahl Kopf, p = Wahrscheinlichkeit Kopf
- **Beispiel:** Genau 4 mal Kopf → n=8, k=4, p=0.5 → $\binom{8}{4} \cdot 0.5^8 = 70 \cdot \frac{1}{256}$

### **Mindestens/höchstens**
**Konkrete Beispiele aus Klausuren:**
- **Münze mindestens 2 mal Zahl:** $1 - P(\text{0 Zahl}) - P(\text{1 Zahl})$ 
- **Würfel höchstens 1 Sechs:** $P(\text{0 Sechsen}) + P(\text{1 Sechs})$
- **Produkt nicht durch 2 und 3 teilbar:** Nur ungerade UND nicht durch 3 → $(1/2)^3 \cdot (2/3)^3$
- **⚠️ Gemeinheit:** "mindestens" = Komplement verwenden, spart Rechenzeit!

---

## **9. STETIGE ZUFALLSVARIABLEN**

### **Normierungskonstante C bestimmen**
**Formel:** $\int_{-\infty}^{\infty} f(x) dx = 1$
- **Beispiel:** $f(x) = C(1-x^2)$ für $x \in [-1,1]$ → $\int_{-1}^{1} C(1-x^2) dx = C \cdot \frac{4}{3} = 1$ → $C = \frac{3}{4}$

### **Erwartungswert**
**Konkrete Beispiele aus Klausuren:**
- **Stetige Funktion:** $E[X] = \int_{-1}^{1} x \cdot \frac{3}{4}(1-x^2) dx = 0$ (symmetrisch!)
- **Dreiecksfunktion:** $f(x) = cx$ für $0 \leq x \leq a$ → $E[X] = \frac{2a}{3}$
- **⚠️ Gemeinheit:** Bei symmetrischen Funktionen um 0 ist E[X] = 0!

### **Standardabweichung**
**Formel:** $Var(X) = \int_{-\infty}^{\infty} x^2 \cdot f(x) dx - (E[X])^2$
**Standardabweichung:** $\sigma = \sqrt{Var(X)}$

### **Wahrscheinlichkeiten berechnen**
**Formel:** $P(a \leq X \leq b) = \int_{a}^{b} f(x) dx$

---

## **10. MODULARE ARITHMETIK**

### **Euler'sches Theorem**
**Formel:** $a^{\varphi(n)} \equiv 1 \pmod{n}$ (falls $\gcd(a,n) = 1$)
- **Beispiel:** $8^{243} \bmod 25$ → $\varphi(25) = 20$ → $8^{243} = 8^{20 \cdot 12 + 3} = (8^{20})^{12} \cdot 8^3 \equiv 1^{12} \cdot 8^3 = 512 \equiv 12 \pmod{25}$

### **Erweiterte Euklidische Algorithmus**
**Vorgehen:** 
1. $\gcd(a,b)$ mit Euklidischem Algorithmus
2. Rückwärts einsetzen für $ax + by = \gcd(a,b)$
- **Beispiel:** $582x + 123y = 6$ → $\gcd(582, 123) = 3$ → Nicht lösbar für 6!

### **Teilbarkeitsbeweis**
**Konkrete Beispiele aus Klausuren:**
- **$a^5 - a$ durch 5 teilbar:** Fallunterscheidung: a ≡ 0,1,2,3,4 (mod 5), dann Fermat anwenden
- **Letzte Dezimalstelle von $7^{222}$:** $7^{222} \bmod 10$ → $\varphi(10) = 4$ → $7^{222} = 7^{4 \cdot 55 + 2} \equiv 7^2 = 49 \equiv 9 \pmod{10}$
- **⚠️ Gemeinheit:** Bei Teilbarkeitsbeweisen Fermat'sches Theorem (nicht Euler) oft einfacher!

---

## **11. AFFINE CHIFFRE**

### **Grundformel**
**Verschlüsselung:** $f(x) = (ax + b) \bmod 26$

### **Lösungsweg:**
1. **Zwei Paare gegeben:** $(x_1, y_1)$ und $(x_2, y_2)$
2. **Gleichungssystem:** $ax_1 + b \equiv y_1 \pmod{26}$, $ax_2 + b \equiv y_2 \pmod{26}$
3. **Subtrahieren:** $a(x_1 - x_2) \equiv y_1 - y_2 \pmod{26}$
4. **a bestimmen:** $a \equiv (y_1 - y_2) \cdot (x_1 - x_2)^{-1} \pmod{26}$
5. **b bestimmen:** $b \equiv y_1 - ax_1 \pmod{26}$

### **Beispielrechnung:**
- E→K, K→E: $(4, 10)$ und $(10, 4)$
- $a \cdot (4-10) \equiv 10-4 \pmod{26}$ → $a \cdot (-6) \equiv 6 \pmod{26}$ → $a \equiv 25 \pmod{26}$
- $b \equiv 10 - 25 \cdot 4 \equiv 10 - 100 \equiv 10 - 22 \equiv 14 \pmod{26}$

**⚠️ Gemeinheit:** $\gcd(a, 26) = 1$ muss gelten!

---

## **12. RSA-ENTSCHLÜSSELUNG**

### **Schritt-für-Schritt:**

#### **a) Öffentlichen Exponenten bestimmen**
**Vorgehen:** Teste alle gegebenen e-Werte mit $\gcd(e, \varphi(n)) = 1$
- **Variablen:** e = öffentlicher Exponent, n = Modul, φ(n) = Euler-Funktion

#### **b) Privaten Schlüssel berechnen**
1. **Faktorisierung:** $n = p \cdot q$ (oder $n = p^2$)
2. **φ(n) berechnen:** 
   - $\varphi(pq) = (p-1)(q-1)$ 
   - $\varphi(p^2) = p(p-1)$ ⚠️
3. **d finden:** $ed \equiv 1 \pmod{\varphi(n)}$ mit erweiterte Euklidische
- **Variablen:** p,q = Primfaktoren, d = privater Schlüssel, e = öffentlicher Exponent

#### **c) Nachricht entschlüsseln**
**Formel:** $m = c^d \bmod n$
- **Variablen:** m = Klarnachricht, c = Kryptogramm, d = privater Schlüssel, n = Modul

### **Beispielrechnung (m=35, e=5, c=10):**
1. **Faktorisierung:** $35 = 5 \cdot 7$
2. **φ(35):** $\varphi(35) = 4 \cdot 6 = 24$
3. **gcd(5,24):** $\gcd(5,24) = 1$ ✓
4. **d finden:** $5d \equiv 1 \pmod{24}$ → $d = 5$ (da $5 \cdot 5 = 25 \equiv 1 \pmod{24}$)
5. **Entschlüsseln:** $m = 10^5 \bmod 35 = 100000 \bmod 35 = 15$

### **⚠️ KRITISCHE SPEZIALFÄLLE:**
- $n = 25 = 5^2$ → $\varphi(25) = 5 \cdot 4 = 20$ (NICHT 16!)
- $n = 35 = 5 \cdot 7$ → $\varphi(35) = 4 \cdot 6 = 24$
- $n = 77 = 7 \cdot 11$ → $\varphi(77) = 6 \cdot 10 = 60$

---

## **🎯 ALLGEMEINE TIPPS:**

1. **Immer Formeln hinschreiben** - auch bei falscher Rechnung gibt's Teilpunkte!
2. **Sonderfälle prüfen** - besonders bei RSA und Affine Chiffre
3. **Zwischenschritte zeigen** - vollständige Darstellung nötig
4. **Kontrolle** - Ergebnisse auf Plausibilität prüfen
5. **Zeitmanagement** - nicht zu lange an einer Teilaufgabe hängen

**🚀 Mit diesem Spickzettel hast du alle wichtigen Formeln griffbereit!**
