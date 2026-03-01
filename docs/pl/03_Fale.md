# Sekcja 3: Fale

## 1. Własności fal

Fala dźwiękowa w powietrzu ma częstotliwość 440 Hz. Jeśli prędkość dźwięku w powietrzu wynosi 343 m/s, jaka jest jej długość fali? Jaka jest jej długość fali w wodzie, gdzie prędkość dźwięku wynosi 1482 m/s?

## 2. Harmoniczne na strunie

Struna gitary ma długość 64 cm i częstotliwość podstawową (jedna strzałka) równą 330 Hz. Jaka jest prędkość fali na tej strunie?

## 3. Zasada superpozycji

Dwie fale opisane są równaniami $y_1(x, t) = A \sin(kx - \omega t)$ oraz $y_2(x, t) = A \sin(kx + \omega t)$. Jakie jest równanie powstałej fali stojącej? Wyznacz położenia węzłów.

## 4. Różnica faz

Jaka jest różnica faz (w radianach) między dwoma punktami fali oddalonymi o $\lambda/3$? 

## 5. Pomiar odległości metodą echa

Osoba krzyczy w kierunku klifu i słyszy echo po 1 sekundzie. Jak daleko znajduje się klif? (Prędkość dźwięku w powietrzu wynosi 343 m/s).

## 6. Równanie fali

Fala opisana jest równaniem $y(x,t) = 0.05 \sin(2\pi x - 50\pi t)$, gdzie $x$ i $y$ są wyrażone w metrach, a $t$ w sekundach. Wyznacz:

a) Amplitudę $A$.

b) Długość fali $\lambda$.

c) Częstotliwość $f$.

d) Prędkość rozchodzenia się fali $v$.

## 7. Mody fali stojącej

Na strunie o długości $L = 80$ cm wytworzono falę stojącą z czterema strzałkami. Jaka jest długość fali?

## 8. Fale

Które z poniższych funkcji mogą opisywać falę biegnącą? Wskazówka: sprawdź, czy spełniają równanie falowe

$$\frac{\partial^2 y}{\partial x^2} = \frac{1}{v^2} \frac{\partial^2 y}{\partial t^2}$$

a) $y(x,t) = A \cos(kx^2 - \omega t)$

b) $y(x,t) = A(x-vt)^2$

c) $y(x,t) = A \log(x+vt)$

## 9. Oscylator tłumiony

Dla równania opisującego tłumiony oscylator harmoniczny:

$$
m \frac{d^2 x}{dt^2} + b \frac{dx}{dt} + k x = 0
$$

stwórz interaktywną animację HTML z suwakiem parametru $b$, aby pokazać zachowanie układu w przypadkach: niedotłumionym, krytycznie tłumionym oraz przetłumionym. Dołącz wykresy $x(t)$ oraz portret fazowy dla każdego przypadku.

1. Zapisz rozwiązanie ogólne.
2. Przedstaw klasyfikację przypadków: niedotłumiony, krytycznie tłumiony, przetłumiony.
3. Rozwiąż równanie numerycznie (RK4).
4. Zbadaj wpływ parametru $b$.
5. Wygeneruj wykres $x(t)$.
6. Wygeneruj portret fazowy.

## 10. Animacja: Źródła fal

Napisz animację HTML, w której można rozmieszczać punkty pełniące rolę źródeł fal opisanych równaniem:

$$
u(\vec{r},t) = \frac{A}{|\vec{r}-\vec{r_0}|^\alpha} \sin(k |\vec{r} - \vec{r_0}| - \omega t)
$$

gdzie $\vec{r_0}$ jest położeniem punktu, a $\alpha$ jest parametrem, który można ustawiać w zakresie $[0, 2]$. Animacja powinna pokazywać superpozycję fal od wszystkich punktów.

## 11. Animacja: Interferencja dwóch szczelin

Napisz animację HTML symulującą doświadczenie Younga, w którym dwie szczeliny działają jako punktowe źródła fal koherentnych. Wychylenie fali wypadkowej jest sumą fal cząstkowych opisanych wzorem:

$$
u(\vec{r},t) = \frac{A}{|\vec{r}-\vec{r_1}|} \sin(k |vec{r} - \vec{r_1}| - \omega t) + \frac{A}{|\vec{r}-\vec{r_2}|} \sin(k |vec{r} - \vec{r_2}| - \omega t)
$$

gdzie $\vec{r_1}$ oraz $\vec{r_2}$ są wektorami położeń szczelin. Użytkownik powinien mieć możliwość zmiany odległości między szczelinami $d = |\vec{r_1} - \vec{r_2}|$ oraz długości fali $\lambda$. Animacja powinna wizualizować w czasie rzeczywistym powstający obraz interferencyjny.