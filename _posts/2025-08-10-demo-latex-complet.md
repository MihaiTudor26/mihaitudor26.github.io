---
layout: post
title: "Demonstrație completă LaTeX - Matematică avansată"
date: 2025-08-10
categories: [matematică, latex, demonstrație]
---

# Ghid complet LaTeX pentru GitHub Pages

Această postare demonstrează toate tipurile de formule matematice pe care le poți folosi cu LaTeX pe GitHub Pages.

## 1. Ecuații și Formule de bază

### Formule inline
Ecuația lui Einstein: \\(E = mc^2\\) este una dintre cele mai faimoase formule din fizică.

Teorema lui Pitagora: \\(a^2 + b^2 = c^2\\) descrie relația în triunghiurile dreptunghice.

Formula pentru aria unui cerc: \\(A = \pi r^2\\) unde \\(r\\) este raza.

### Ecuații pe blocuri

Ecuația cuadratică și soluțiile sale:
$$ax^2 + bx + c = 0$$

$$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$

Formula binomului lui Newton:
$$(a + b)^n = \sum_{k=0}^{n} \binom{n}{k} a^{n-k} b^k$$

## 2. Limite și Derivate

Definiția limitei:
$$\lim_{x \to a} f(x) = L$$

Definirea derivatei:
$$f'(x) = \lim_{h \to 0} \frac{f(x+h) - f(x)}{h}$$

Limite speciale:
$$\lim_{x \to 0} \frac{\sin x}{x} = 1$$

$$\lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^n = e$$

## 3. Integrale

### Integrale nedefinite
$$\int x^n dx = \frac{x^{n+1}}{n+1} + C \quad (n \neq -1)$$

$$\int \frac{1}{x} dx = \ln|x| + C$$

$$\int e^x dx = e^x + C$$

$$\int \sin x \, dx = -\cos x + C$$

### Integrale definite
$$\int_0^1 x^2 dx = \frac{1}{3}$$

$$\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}$$

### Integrale multiple
$$\iint_D f(x,y) \, dx \, dy = \int_a^b \int_{g_1(x)}^{g_2(x)} f(x,y) \, dy \, dx$$

## 4. Matrici și Determinanți

### Matrice 2x2
$$A = \begin{pmatrix} 
a & b \\ 
c & d 
\end{pmatrix}$$

### Matrice 3x3
$$B = \begin{bmatrix} 
1 & 2 & 3 \\ 
4 & 5 & 6 \\ 
7 & 8 & 9 
\end{bmatrix}$$

### Determinant
$$\det(A) = \begin{vmatrix} 
a & b \\ 
c & d 
\end{vmatrix} = ad - bc$$

### Matrice identitate
$$I_3 = \begin{pmatrix} 
1 & 0 & 0 \\ 
0 & 1 & 0 \\ 
0 & 0 & 1 
\end{pmatrix}$$

### Sistem de ecuații liniare
$$\begin{cases}
x + y + z = 6 \\
2x - y + z = 3 \\
x + 2y - z = 1
\end{cases}$$

## 5. Serii și Șiruri

### Progresii
Progresie aritmetică: \\(a_n = a_1 + (n-1)d\\)

Suma unei progresii aritmetice:
$$S_n = \frac{n}{2}(2a_1 + (n-1)d) = \frac{n}{2}(a_1 + a_n)$$

Progresie geometrică: \\(a_n = a_1 \cdot q^{n-1}\\)

Suma unei progresii geometrice:
$$S_n = a_1 \frac{1-q^n}{1-q} \quad (q \neq 1)$$

### Serii celebre
Seria lui Taylor pentru \\(e^x\\):
$$e^x = \sum_{n=0}^{\infty} \frac{x^n}{n!} = 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \cdots$$

Seria lui Taylor pentru \\(\sin x\\):
$$\sin x = \sum_{n=0}^{\infty} \frac{(-1)^n x^{2n+1}}{(2n+1)!} = x - \frac{x^3}{3!} + \frac{x^5}{5!} - \cdots$$

## 6. Funcții speciale și Operatori

### Funcții trigonometrice inverse
$$\arcsin x + \arccos x = \frac{\pi}{2}$$

### Logaritmi
$$\log_a(xy) = \log_a x + \log_a y$$

$$\log_a(x^n) = n \log_a x$$

### Operatori nabla
Gradientul: \\(\nabla f = \left(\frac{\partial f}{\partial x}, \frac{\partial f}{\partial y}, \frac{\partial f}{\partial z}\right)\\)

Divergența: \\(\nabla \cdot \vec{F} = \frac{\partial F_x}{\partial x} + \frac{\partial F_y}{\partial y} + \frac{\partial F_z}{\partial z}\\)

Rotorul: \\(\nabla \times \vec{F}\\)

## 7. Probabilitate și Statistică

### Distribuția normală
$$f(x) = \frac{1}{\sigma\sqrt{2\pi}} e^{-\frac{1}{2}\left(\frac{x-\mu}{\sigma}\right)^2}$$

### Combinatorii
Combinări: \\(\binom{n}{k} = \frac{n!}{k!(n-k)!}\\)

Aranjamente: \\(A_n^k = \frac{n!}{(n-k)!}\\)

Permutări: \\(P_n = n!\\)

### Teorema lui Bayes
$$P(A|B) = \frac{P(B|A) \cdot P(A)}{P(B)}$$

## 8. Geometrie și Trigonometrie

### Identități trigonometrice fundamentale
$$\sin^2 x + \cos^2 x = 1$$

$$\tan x = \frac{\sin x}{\cos x}$$

$$\sin(a + b) = \sin a \cos b + \cos a \sin b$$

### Formula lui Euler
$$e^{ix} = \cos x + i \sin x$$

### Distanța între două puncte
$$d = \sqrt{(x_2-x_1)^2 + (y_2-y_1)^2}$$

## 9. Ecuații diferențiale

### Ecuații cu variabile separabile
$$\frac{dy}{dx} = f(x)g(y)$$

### Ecuația diferențială de ordinul al doilea
$$y'' + py' + qy = 0$$

Soluția generală pentru ecuația caracteristică \\(r^2 + pr + q = 0\\):

Pentru \\(\Delta > 0\\): \\(y = C_1 e^{r_1 x} + C_2 e^{r_2 x}\\)

Pentru \\(\Delta = 0\\): \\(y = (C_1 + C_2 x) e^{rx}\\)

Pentru \\(\Delta < 0\\): \\(y = e^{\alpha x}(C_1 \cos \beta x + C_2 \sin \beta x)\\)

## 10. Exemple complexe

### Transformata Fourier
$$F(\omega) = \int_{-\infty}^{\infty} f(t) e^{-i\omega t} dt$$

### Ecuațiile lui Maxwell
$$\nabla \cdot \vec{E} = \frac{\rho}{\varepsilon_0}$$

$$\nabla \cdot \vec{B} = 0$$

$$\nabla \times \vec{E} = -\frac{\partial \vec{B}}{\partial t}$$

$$\nabla \times \vec{B} = \mu_0 \vec{J} + \mu_0 \varepsilon_0 \frac{\partial \vec{E}}{\partial t}$$

### Formula integrală a lui Cauchy
$$f(z_0) = \frac{1}{2\pi i} \oint_C \frac{f(z)}{z-z_0} dz$$

---

## Concluzie

Această demonstrație arată că poți folosi aproape orice structură LaTeX pe GitHub Pages! Sintaxa de reținut:

- **Formule inline**: `\\(formula\\)`
- **Formule pe bloc**: `$$formula$$`
- **Matrici**: `\begin{pmatrix}...\end{pmatrix}` sau `\begin{bmatrix}...\end{bmatrix}`
- **Sisteme**: `\begin{cases}...\end{cases}`
- **Fracții**: `\frac{numărător}{numitor}`
- **Exponenți**: `x^2` pentru \\(x^2\\)
- **Indici**: `x_1` pentru \\(x_1\\)

Acum poți scrie orice formulă matematică în postările tale! 🚀
