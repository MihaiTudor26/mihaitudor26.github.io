---
title: "Rețele neuronale - Un prim contact"
date: 2025-08-19
tags:
  - matematică
  - retele-neuronale
  - inteligenta-artificială
  - python
---
<script>
window.MathJax = {
  tex: {
    inlineMath: [['$', '$'], ['\\(', '\\)']],
    displayMath: [['$$', '$$'], ['\\[', '\\]']],
    processEscapes: true,
    tags: 'ams'
  },
  options: {
    processHtmlClass: 'arithmatex'
  }
};
</script>
<script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/prism/1.24.1/components/prism-core.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/prism/1.24.1/components/prism-python.min.js"></script>
<link href="https://cdnjs.cloudflare.com/ajax/libs/prism/1.24.1/themes/prism.min.css" rel="stylesheet" />

<style>
/* Styling pentru formulele matematice - mai discret și profesionist */
mjx-container[display="true"] {
    background: linear-gradient(135deg, #fafbfc 0%, #f8f9fa 100%) !important;
    border: 1px solid #e1e5e9 !important;
    border-left: 3px solid #4a90e2 !important;
    border-radius: 4px !important;
    padding: 1.5rem !important;
    margin: 1.5rem 0 !important;
    box-shadow: 0 1px 3px rgba(0,0,0,0.05) !important;
    position: relative !important;
}

mjx-container[display="true"]:hover {
    box-shadow: 0 2px 8px rgba(74, 144, 226, 0.08) !important;
    border-left: 3px solid #2c5aa0 !important;
}

mjx-container:not([display="true"]) {
    background: #f8f9fa !important;
    border: 1px solid #dee2e6 !important;
    border-radius: 3px !important;
    padding: 0.2rem 0.4rem !important;
    margin: 0 0.1rem !important;
}

/* Îmbunătățiri pentru blocquote - pentru întrebările importante */
blockquote {
    background: linear-gradient(135deg, #fff7e6 0%, #ffeaa7 100%) !important;
    border-left: 4px solid #fdcb6e !important;
    border-radius: 0 6px 6px 0 !important;
    padding: 1rem 1.5rem !important;
    margin: 1.5rem 0 !important;
    box-shadow: 0 2px 6px rgba(253, 203, 110, 0.2) !important;
}

/* Styling pentru codul Python - fundal alb cu syntax highlighting */
pre {
    background: #ffffff !important;
    border: 1px solid #e1e5e9 !important;
    border-left: 3px solid #28a745 !important;
    border-radius: 4px !important;
    box-shadow: 0 1px 3px rgba(0,0,0,0.05) !important;
    padding: 1.5rem !important;
    margin: 1.5rem 0 !important;
    overflow-x: auto !important;
}

pre:hover {
    box-shadow: 0 2px 8px rgba(40, 167, 69, 0.08) !important;
    border-left: 3px solid #218838 !important;
}

/* Syntax highlighting pentru Python */
.token.keyword {
    color: #d73a49 !important;
    font-weight: 600 !important;
}

.token.function {
    color: #6f42c1 !important;
}

.token.string {
    color: #032f62 !important;
}

.token.number {
    color: #005cc5 !important;
}

.token.comment {
    color: #6a737d !important;
    font-style: italic !important;
}

.token.operator {
    color: #d73a49 !important;
}

.token.punctuation {
    color: #24292e !important;
}

code {
    color: #24292e !important;
    font-family: 'SFMono-Regular', Consolas, 'Liberation Mono', Menlo, monospace !important;
    font-size: 14px !important;
    line-height: 1.45 !important;
}

/* Output-uri - fundal verzui pentru rezultate */
pre:has(+ p:contains("Student")) + p,
p:contains("Student 1:") {
    background: #f8fff9 !important;
    border: 1px solid #d4edda !important;
    border-left: 3px solid #28a745 !important;
    border-radius: 4px !important;
    padding: 1rem !important;
    font-family: 'SFMono-Regular', Consolas, 'Liberation Mono', Menlo, monospace !important;
    white-space: pre-line !important;
    color: #155724 !important;
    font-size: 14px !important;
    line-height: 1.45 !important;
}

/* Pentru listele cu punct - spacing mai bun */
ul li {
    margin-bottom: 0.5rem;
}

/* Strong text - culoare subtil diferită */
strong {
    color: #2c3e50;
    font-weight: 600;
}

/* Headers - culori subtile */
h2 {
    color: #34495e;
    border-bottom: 2px solid #3498db;
    padding-bottom: 0.3rem;
}

h3 {
    color: #2c3e50;
}
</style>

În ansamblu, putem afirma faptul că rețelele neuronale încearcă să găsească modele (patterns) în date pentru a face predicții. O rețea neuronală "învață" prin încercări repetate de a prezice output-ul corect, ajustându-și parametrii interni (ponderile) când greșește. În continuare, ne propunem să analizăm acest mecanism implementând o serie de rețele neuronale simple în care urmărim procesul ce se derulează în spatele cortinei, încercând să transpunem informațiile deduse în contextul literaturii de specialitate. Consider că o abordare academică riguroasă, dezvoltată încă de la primii pași, poate uneori să mascheze tocmai ideile fundamentale care, în esență, pot fi desprinse doar prin încercări repetate și erori de gândire care, în cele din urmă, dacă sunt însoțite de concluzii concrete și riguros construite, converg la înțelegerea unor concepte fundamentale.

Raportându-mă la partea tehnică, personal prefer să lucrez în Jupyter Notebook, deoarece îmi oferă o libertate mai mare în a compila codul scris în Python din spatele rețelelor neuronale și de a-l putea organiza eficient. Pentru început, NumPy rămâne librăria de bază prin intermediul căreia fac apel la instrumentele matematice (calculul matriceal și vectorial, în special) necesare implementării.

## De la simplu la complex...

Componentele de bază ale oricărei rețele neuronale determină următoarea triadă:

$$\text{input} \longrightarrow \text{weight} \longrightarrow \text{prediction}$$

Simplist, le putem caracteriza pe acestea astfel:
- **input**: valoarea pe care o primește rețeaua
- **weight (ponderea)**: parametrul care controlează transformarea  
- **prediction (predicția)**: rezultatul furnizat de rețea

Cu alte cuvinte, cea mai simplă transformare liniară $\text{prediction} = \text{input} \times \text{weight}$ devine fundamentul tuturor operațiilor mai complexe din rețelele neuronale.

## Prima rețea neuronală

Ne dorim să construim cea mai simplă rețea neuronală posibilă și să înțelegem fiecare componentă înainte să adăugăm complexitate.

### Configurarea problemei

Vă propun să pornim de la următorul context concret: Cerem o predicție a notei finale a studenților pe baza orelor de studiu săptămânale. Datele folosite vor fi reținute în următoarele două liste:

```python
study_hours_weekly = [15, 25, 35, 20]  # ore de studiu pe săptămână (input)
final_grade_percentage = [0.65, 0.78, 0.89, 0.72]  # nota finală (0-1) (predicția dorită)
```

Înainte să oferim o implementare a rețelei în Python și să discutăm aspectele tehnice, facem precizarea că lista "final_grade_percentage" reține nota finală reală obținută de fiecare student în urma numărului de ore de studiu efectuate. Astfel, un student care studiază 15 ore obține 0,65, pe când un student care studiază 35 de ore obține 0,89. Obiectivul rețelei este să prezică aceste note cu o acuratețe cât mai bună, tehnic vorbind aceasta reprezentând faza de antrenare a rețelei neuronale (training phase).

### Implementare

```python
weight = 0.02  # pondere inițială (ghicitură)

def neural_network(study_hours, weight):
    grade_prediction = study_hours * weight
    return grade_prediction

# Testarea modelului
for i in range(len(study_hours_weekly)):
    predicted_grade = neural_network(study_hours_weekly[i], weight)
    goal_pred = final_grade_percentage[i]
    error = (predicted_grade - goal_pred) ** 2
    
    print(f"Student {i+1}:")
    print(f"  Ore studiu/săptămână: {study_hours_weekly[i]}")
    print(f"  Nota reală: {goal_pred:.2f}")
    print(f"  Nota prezisă: {predicted_grade:.3f}")
    print(f"  Eroare pătratică: {error:.6f}")
    print()
```

În urma rulării programului obținem următoarele rezultate:

```
Student 1:
  Ore studiu/săptămână: 15
  Nota reală: 0.65
  Nota prezisă: 0.375
  Eroare pătratică: 0.075625

Student 2:
  Ore studiu/săptămână: 25
  Nota reală: 0.78
  Nota prezisă: 0.625
  Eroare pătratică: 0.024025

Student 3:
  Ore studiu/săptămână: 35
  Nota reală: 0.89
  Nota prezisă: 0.875
  Eroare pătratică: 0.000225

Student 4:
  Ore studiu/săptămână: 20
  Nota reală: 0.72
  Nota prezisă: 0.500
  Eroare pătratică: 0.048400
```

Analizând rezultatele furnizate de rețea, observăm că singurul caz în care rețeaua reușește să se apropie destul de mult de rezultatul real este în cazul "Student 3", unde eroarea este mică (0.000225). În celelalte cazuri aceasta are tendința de a subevalua.

În acest moment avem cadrul necesar pentru a discuta câteva aspecte de ordin tehnic care se desprind:

**1.** Surprinzător sau nu, codul propus definește scheletul celei mai simple rețele neuronale având cele trei concepte care stau la baza arhitecturii acesteia: 

$$\text{input} \longrightarrow \text{weight} \longrightarrow \text{prediction}$$. 

Mai exact, până în acest punct, codul mimează o regresie liniară simplificată. Vorbim în acest caz de Supervised Learning - rețeaua învață să mapeze input-urile la output-urile dorite.

**2.** Pentru a putea interpreta erorile, am folosit Eroarea pătratică (Mean Squared Error - MSE), aceasta având câteva avantaje clare comparativ cu eroarea absolută:
   - rețeaua "se concentrează" mai mult pe corectarea erorilor mari decât pe cele mici
   
   **Eroare absolută vs Eroare pătratică:**
   - |error| = 0.1 → error² = 0.01 (eroare mică → penalizare mai mică)
   - |error| = 1.0 → error² = 1.0 (eroare medie → penalizare similară)  
   - |error| = 2.0 → error² = 4.0 (eroare mare → penalizare mult mai mare!)

   Totuși, trebuie punctat în acest caz faptul că devine sensibilă la outliers (valorile extreme). Poate "supra-penaliza" erorile mari care, într-un set mare de date de antrenament, acestea sunt legitime și pot apărea. O analiză complexă a acestei sensibilități o vom aborda cu atenție într-o postare viitoare.

   - Eroarea pătratică oferă proprietăți matematice valoroase în contextul optimizării rețelei propuse:
     - este o funcție diferențiabilă pe tot domeniul de definiție (eroarea absolută nu este diferențiabilă în punctul 0), ceea ce ne permite calculul gradientului pentru optimizare (aspect pe care îl vom analiza în cadrul postării)
     - în cazul transformării liniare (cazul particular abordat de rețeaua propusă), MSE este convexă:
     
     $$\text{prediction} = \text{weight} \times \text{input}$$
     
     $$\text{MSE}(\text{weight}) = \frac{1}{n} \sum(\text{weight} \times x_i - y_i)^2$$
     
     $$\frac{\partial^2 \text{MSE}}{\partial w^2} = \frac{2}{n} \sum x_i^2 \geq 0 \text{ (întotdeauna pozitivă!)}$$
     
     Acest aspect conduce la determinarea unui minim global, viteza de convergență fiind bună. În cazul rețelelor neuronale complexe în care intervin funcții de activare neliniare, convexitatea se pierde (altfel spus pot apărea mai multe minime locale posibile).

**3.** În cazul rețelei noastre întâlnim o limitare fundamentală - ponderea fixă:
   - nu avem nicio justificare pentru această valoare
   - pentru diferite probleme, am avea nevoie de ponderi diferite
   - performanța depinde complet de "ghicirea ponderii"

Aspectele dezbătute la punctul 3 deschid drumul spre următoarea întrebare: 

> **"Dacă știu că performanța depinde de pondere/ponderi, cum aleg ponderea/ponderile optimă/optime?"**

## Optimizarea ponderilor

Pentru a răspunde la întrebarea noastră, reducem pentru început problema propusă la un singur input:

```python
weight = 0.02
input = 15
goal_prediction = 0.65

prediction = input * weight  # 0.375
error = (prediction - goal_prediction) ** 2  # (0.375 - 0.65)² = 0.075625
```

Conceptul cheie care ne ghidează spre un prim pas important este următorul: **"Eroarea ne spune cât de departe suntem de soluția dorită."**

Având în vedere acest lucru, ne dorim ca rețeaua să își ajusteze singură ponderile pentru a face predicții cât mai bune, deci eroarea să fie cât mai aproape de 0.

Un prim pas pe care îl facem în acest demers este să introducem pentru început ideea de derivată la nivel intuitiv, analizând următoarea formulă:

$$\text{derivata} = \text{eroarea} \times \text{input} \quad (1)$$

Aceasta ne dă pe de o parte "direcția" în care să schimbăm ponderea, iar pe de alta magnitudinea schimbării.

Funcțiile pe care noi trebuie să le avem în vedere sunt următoarele:
- $\text{prediction}(w) = \text{input} \times w$ (funcția de predicție)
- $\text{error}(w) = \text{prediction}(w) - \text{goal} = \text{input} \times w - \text{goal}$ (eroarea liniară)
- $\text{loss}(w) = \text{error}(w)^2 = (\text{input} \times w - \text{goal})^2$ (funcția de cost/pierdere)

Pentru funcția de cost, formula (1) devine:

$$\text{derivata} = \frac{d}{dw}[(\text{input} \times w - \text{goal})^2]$$

$$= 2 \times (\text{input} \times w - \text{goal}) \times \frac{d}{dw}[\text{input} \times w - \text{goal}]$$

$$= 2 \times (\text{input} \times w - \text{goal}) \times \text{input}$$

$$= 2 \times \text{error} \times \text{input}$$

Un alt amănunt important pe care trebuie să-l avem în vedere este să controlăm cu atenție cât de mare trebuie să fie actualizarea ponderii la fiecare iterație. Astfel apare nevoia introducerii unui nou parametru în procesul de învățare numit **learning rate**. Tehnic vorbind, acesta este un hiperparametru (se setează manual, iar valoarea sa rămâne constantă pe parcursul procesului de antrenament al modelului), alegerea valorii optime a acestuia influențând convergența algoritmului.

Astfel, algoritmul de optimizare care minimizează funcția de eroare prin ajustarea parametrilor în direcția opusă gradientului ne conduce la următoarea formulă generală:

$$\text{ParameterNou} = \text{ParameterVechi} - (\text{LearningRate} \times \text{Derivată})$$

## Implementarea algoritmului de optimizare

Plecând de la aceste aspecte teoretice, oferim o implementare a algoritmului de optimizare în situația în care avem o singură pondere și un singur input:

```python
def visualize_learning():
    weights = []
    errors = []
    predictions = []

    weight = 0.02
    input = 15 
    goal = 0.65
    alpha = 0.001

    for i in range(30):
        pred = input * weight
        error = (pred - goal) ** 2

        weights.append(round(weight, 3))
        errors.append(round(error, 8))
        predictions.append(round(pred, 3))

        # Afișare la fiecare 5 iterații
        if (i + 1) % 5 == 0:
            print(f"Iterația {i + 1}:")
            print(f"Weight: {round(weight, 3)}")
            print(f"Error: {round(error, 8)}")
            print(f"Prediction: {round(pred, 3)}")
            print()

        # Update
        derivative = (pred - goal) * input
        weight = weight - (alpha * derivative)

visualize_learning()
```

În urma rulării programului obținem următoarele rezultate:

```
Iterația 5:
Weight: 0.035
Error: 0.01594225
Prediction: 0.524

Iterația 10:
Weight: 0.041
Error: 0.00124614
Prediction: 0.615

Iterația 15:
Weight: 0.043
Error: 9.741e-05
Prediction: 0.64

Iterația 20:
Weight: 0.043
Error: 7.61e-06
Prediction: 0.647

Iterația 25:
Weight: 0.043
Error: 6e-07
Prediction: 0.649

Iterația 30:
Weight: 0.043
Error: 5e-08
Prediction: 0.65
```

## Limitări și perspective

Abordarea noastră are câteva limitări clare:

- algoritmul actualizează o singură pondere și are în vedere un singur input în procesul de antrenare. În practică, problemele reale au sute/mii de parametri și milioane de date de antrenament
- predicția cerută de noi este simplă, în realitate problemele au o complexitate exponențial mai mare

În următoarea postare, raportându-ne la același exemplu, încercăm să răspundem la următoarele întrebări:

> **"Cum actualizăm optim multiple ponderi simultan?"**
> 
> **"Cum procesăm multiple input-uri în faza de antrenament?"**
