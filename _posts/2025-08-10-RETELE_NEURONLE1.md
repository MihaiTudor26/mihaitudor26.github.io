---
title: "Rețele neuronale - o privire de ansamblu"
date: 2025-08-12
tags:
  - matematică
  - retele-neuronale
  - inteligenta-artificială
---

<script>
window.MathJax = {
  tex: {
    inlineMath: [['\\(', '\\)']],
    displayMath: [['$$', '$$']]
  }
};
</script>
<script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>


Începând cu această postare căutăm să înțelegem mai bine mecanismele care stau în spatele Rețelelor Neuronale, făcând apel la aparatul matematic pentru a avea o viziune mai amplă asupra proceselor care se derulează în spatele cortinei. Consider că simplitatea abordării este cheia de a deschide ușa către un tărâm atât de complex ce acoperă începutul unui transit tehnologic extrem de fertil.

Având la baza proiectării lor modele matematice complexe care se derulează la nivelul procesării informației în creierul uman, Rețelele Neuronale se caracterizează prin 3 elemente de bază:

- **neuronul** (neuron/unit/cell/node) - unitatea de procesare a informației
- **ponderile** (weights) - echivalenta „forței" conexiunilor sinaptice  
- **funcția de activare** (activation function) - determină dacă și în ce măsură un neuron „se activează" și transmite semnalul mai departe

Modul de legare al neuronilor în rețea (neuronal architecture), metoda de determinare a ponderilor (training) și funcția de activare (activation function) joacă, de asemenea, un rol esențial în activitatea de procesare a informației la nivelul rețelei.

## O triadă de întrebări justificate

- „Ce fac diferit rețelele neuronale comparativ cu alte metode de procesare a informației?"
- „Cum folosim rețele neuronale în soluționarea unor probleme concrete?"
- „Când putem folosi rețele neuronale?"

Aceste întrebări vor ghida analiza noastră în următoarele postări, unde vom încerca să înțelegem mecanismele din spatele rețelelor neuronale.

## O abordare vizuală a rețelelor neuronale

La fel ca și neuronii biologici, cei artificiali funcționează pe baza unei stări interne (state) numită (activation/activity level) care, odată calculată, generează un singur semnal de ieșire difuzat simultan către multiple ținte post-sinaptice, diferențierea informațională realizându-se prin ponderile specifice ale fiecărei conexiuni individuale.

Pentru a putea avea o imagine mai intuitivă asupra aspectelor teoretice ne raportăm la următorul exemplu. Vom considera un neuron Y care primește semnale de intrare (inputs) de la trei neuroni \\(X_{1}\\), \\(X_{2}\\) și \\(X_{3}\\). Nivelul de activitate al acestor neuroni (activity level) este dat de \\(x_{1}\\), \\(x_{2}\\), respectiv \\(x_{3}\\) (în acest exemplu, cu rol de fixare la nivelul percepției asupra conceptelor, \\(x_{1}\\), \\(x_{2}\\) și \\(x_{3}\\) pot fi privite ca fiind valori numerice concrete). „Forța conexiunilor sinaptice" dintre neuronii  \\(X_{1}\\), \\(X_{2}\\) și \\(X_{3}\\) și neuronul \\(Y\\) se realizează prin ponderile  \\(w_{1}\\), \\(w_{2}\\) și \\(w_{3}\\). În aceste condiții semnalul primit de neuronul \\(Y\\) (net input), este o sumă ponderată de forma:

\\[
y_{net_input} = w_{1}x_{1} + w_{2}x_{2} + w_{3}x_{3}
\\]

Activarea neuronului \\(Y\\) (activity level) se realizează prin aplicarea funcției de activare (activation function) asupra semnalului primit \\(y_{net_input}\\) astfel încât \\(y = f(y_{net_input})\\), unde \\(y\\) devine nivelul de activitate corespunzător neuronului \\(Y\\), iar \\(f\\), funcția de activare.

<img src="/images/incercare.png" alt="Rețea Neurală" style="width: 300px; height: auto; display: block; margin: 0 auto;">

O abordare riguroasă din punct de vedere matematic asupra acestor concepte împreună cu o analiză asupra diferitelor arhitecturi de rețea vor reprezenta obiectul de studiu pentru următoarele postări.
