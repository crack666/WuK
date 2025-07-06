# 📚 WuK - Wahrscheinlichkeitsrechnung und Kryptographie

Materialsammlung für das Studium der Wahrscheinlichkeitsrechnung und Kryptographie mit Fokus auf effiziente Klausurvorbereitung.

## 📂 Repository-Struktur

### 📊 **Analysedateien**
- **`Klausuranalyse_WuK.ipynb`** - Jupyter Notebook mit systematischer Analyse der Aufgabentypen und optimaler Klausurstrategie
- **`Spickzettel_Formeln_WuK.md`** - Kompakter Spickzettel mit allen wichtigen Formeln und Lösungsansätzen

### 📁 **Probeklausuren**
- **`Probeklausuren/`** - Sammlung von 5 analysierten Klausuren:
  - 21SoSe-Klausur_WuK.pdf
  - SoSe20-Klausur_WuK.pdf
  - Klausur_Wahrsch_Krypto_WS0607.pdf
  - Klausur_Wahrsch-Krypto_SS14.pdf
  - Klausur_Wahrsch-Krypto_WS0809.pdf

### 📈 **Semesterordner**
- **`SS19/`** bis **`SS24/`** - Archivierte Materialien verschiedener Semester

## 🎯 **Klausurstrategie: "Top-5 mit Puffer"**

### **Optimale Aufgaben-Reihenfolge (52 Punkte = Bestanden):**
1. **Kombinatorik (1)** - 10/12 Punkte ⭐
2. **Auswahl-Kombinatorik (2)** - 10/12 Punkte ⭐⭐
3. **Bayes (5)** - 8/10 Punkte ⭐⭐ *(Schema-Aufgabe!)*
4. **Fahrstuhl (3)** - 12/16 Punkte ⭐⭐⭐
5. **Würfel/Schützen (4)** - 12/16 Punkte ⭐⭐⭐⭐

**Erfolgsquote:** 90-95% bei 100 Minuten Bearbeitungszeit

## 🧮 **Wichtige Formeln**

### **Kombinatorik**
```
Permutationen mit Wiederholung: n!/(n₁!·n₂!·...·nₖ!)
Kombinationen: C(n,k) = n!/(k!(n-k)!)
```

### **RSA Spezialfälle** ⚠️
```
φ(25) = 5·4 = 20 (NICHT 16!)
φ(35) = 2·4 = 8
φ(77) = 6·10 = 60
```

### **Bayes-Schema**
```
P(Krank|Test+) = (Sensitivität × P(Krank)) / 
                 (Sensitivität × P(Krank) + Falsch-Positiv × P(Gesund))
```

## 🚀 **Verwendung**

1. **Klausuranalyse studieren** - `Klausuranalyse_WuK.ipynb` für Strategieplanung
2. **Spickzettel verwenden** - `Spickzettel_Formeln_WuK.md` beim Üben griffbereit haben
3. **Probeklausuren durchrechnen** - Mit der optimierten Strategie üben

## 📈 **Erfolgstipps**

- **Fokus auf Top-5 Aufgaben** statt Vollabdeckung
- **Bayes-Schema perfektionieren** - sehr schematisch, hohe Punktausbeute
- **RSA-Spezialfälle kennen** - φ(p²) = p(p-1), nicht (p-1)²
- **Teilpunkte mitnehmen** - Formeln immer hinschreiben

---

**Erstellt:** Juli 2025  
**Basierend auf:** 5 Probeklausuren-Analyse  
**Ziel:** Effiziente Klausurvorbereitung mit 90%+ Erfolgsquote
