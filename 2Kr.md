Вот подробное решение задач 575—581 методом вариации произвольных постоянных (метод Лагранжа).

### Общая теория (Метод вариации постоянных)

Для линейного неоднородного дифференциального уравнения второго порядка с постоянными коэффициентами вида:
$$y'' + py' + qy = f(x)$$

Метод решения состоит из следующих шагов:

1.  **Находим общее решение однородного уравнения** ($y'' + py' + qy = 0$).
    Находим корни характеристического уравнения $\lambda^2 + p\lambda + q = 0$.
    Записываем решение в виде $y_{oo} = C_1 y_1(x) + C_2 y_2(x)$, где $y_1, y_2$ — фундаментальная система решений.

2.  **Варьируем постоянные.**
    Ищем решение неоднородного уравнения в виде:
    $$y = C_1(x)y_1(x) + C_2(x)y_2(x)$$
    где $C_1(x)$ и $C_2(x)$ — неизвестные функции от $x$.

3.  **Составляем систему для производных $C_1'(x)$ и $C_2'(x)$.**
    Согласно методу, функции должны удовлетворять системе:
    $$
    \begin{cases}
    C_1'(x)y_1(x) + C_2'(x)y_2(x) = 0 \\
    C_1'(x)y_1'(x) + C_2'(x)y_2'(x) = f(x)
    \end{cases}
    $$
    *(Примечание: если коэффициент при $y''$ не равен 1, то в правой части второго уравнения должно стоять $f(x)/a_0$).*

4.  **Находим $C_1(x)$ и $C_2(x)$.**
    Решаем систему относительно $C_1'$ и $C_2'$, затем интегрируем полученные выражения.
    $$C_1(x) = \int C_1'(x)dx + C_1, \quad C_2(x) = \int C_2'(x)dx + C_2$$

5.  **Записываем итоговый ответ**, подставляя найденные функции в формулу из шага 2.

---

### Решение задач

#### 575. $y'' - 2y' + y = \frac{e^x}{x}$

**1. Однородное уравнение:**
$y'' - 2y' + y = 0$
Характеристическое уравнение: $\lambda^2 - 2\lambda + 1 = 0 \Rightarrow (\lambda - 1)^2 = 0 \Rightarrow \lambda_{1,2} = 1$ (кратный корень).
Фундаментальная система решений: $y_1 = e^x$, $y_2 = xe^x$.
Общее решение однородного: $y_{oo} = C_1 e^x + C_2 xe^x$.

**2. Система для вариации постоянных:**
Ищем решение в виде $y = C_1(x)e^x + C_2(x)xe^x$.
Находим производные базисных функций:
$y_1' = e^x$
$y_2' = (xe^x)' = e^x + xe^x = e^x(1+x)$

Система:
$$
\begin{cases}
C_1' e^x + C_2' xe^x = 0 \\
C_1' e^x + C_2' e^x(1+x) = \frac{e^x}{x}
\end{cases}
$$

**3. Решение системы:**
Сократим оба уравнения на $e^x$ ($e^x \neq 0$):
$$
\begin{cases}
C_1' + C_2' x = 0 \quad \Rightarrow \quad C_1' = -xC_2' \\
C_1' + C_2'(1+x) = \frac{1}{x}
\end{cases}
$$
Подставим $C_1'$ во второе уравнение:
$-xC_2' + C_2' + xC_2' = \frac{1}{x}$
$C_2' = \frac{1}{x}$

Тогда:
$C_1' = -x \cdot \frac{1}{x} = -1$

**4. Интегрирование:**
$C_1(x) = \int -1 \, dx = -x + C_1$
$C_2(x) = \int \frac{1}{x} \, dx = \ln|x| + C_2$

**5. Общее решение:**
$y = (-x + C_1)e^x + (\ln|x| + C_2)xe^x$
Раскроем скобки для красоты:
**Ответ:** $y = e^x(C_1 + C_2 x - x + x\ln|x|)$.

---

#### 576. $y'' + 3y' + 2y = \frac{1}{e^x + 1}$

**1. Однородное уравнение:**
$\lambda^2 + 3\lambda + 2 = 0 \Rightarrow D = 9-8=1 \Rightarrow \lambda_1 = -1, \lambda_2 = -2$.
$y_1 = e^{-x}, \quad y_2 = e^{-2x}$.

**2. Система:**
$$
\begin{cases}
C_1' e^{-x} + C_2' e^{-2x} = 0 \\
-C_1' e^{-x} - 2C_2' e^{-2x} = \frac{1}{e^x + 1}
\end{cases}
$$

**3. Решение:**
Сложим уравнения:
$-C_2' e^{-2x} = \frac{1}{e^x + 1} \Rightarrow C_2' = -\frac{e^{2x}}{e^x + 1}$

Из первого уравнения $C_1' e^{-x} = -C_2' e^{-2x} = \frac{1}{e^x + 1}$.
$C_1' = \frac{e^x}{e^x + 1}$

**4. Интегрирование:**
$C_1(x) = \int \frac{e^x \, dx}{e^x + 1} = \ln(e^x + 1) + C_1$

$C_2(x) = -\int \frac{e^{2x} \, dx}{e^x + 1}$.
Замена $t = e^x + 1 \Rightarrow e^x = t-1, \, dt = e^x dx$.
$C_2(x) = -\int \frac{(t-1) \, dt}{t} = -\int (1 - \frac{1}{t}) \, dt = -(t - \ln|t|) = \ln(e^x + 1) - (e^x + 1) + C_2$.
(Константу $-1$ можно включить в $C_2$, поэтому оставим $\ln(e^x+1) - e^x$).

**5. Ответ:**
$y = C_1 e^{-x} + C_2 e^{-2x} + e^{-x}\ln(e^x+1) + e^{-2x}(\ln(e^x+1) - e^x)$.
Упростим частное решение:
$y_p = (e^{-x} + e^{-2x})\ln(e^x+1) - e^{-x}$.

---

#### 577. $y'' + y = \frac{1}{\sin x}$

**1. Однородное:**
$\lambda^2 + 1 = 0 \Rightarrow \lambda = \pm i$.
$y_1 = \cos x, \quad y_2 = \sin x$.

**2. Система:**
$$
\begin{cases}
C_1' \cos x + C_2' \sin x = 0 \\
-C_1' \sin x + C_2' \cos x = \frac{1}{\sin x}
\end{cases}
$$

**3. Решение:**
Умножим первое на $\sin x$, второе на $\cos x$ и сложим:
$C_2'(\sin^2 x + \cos^2 x) = \frac{\cos x}{\sin x} \Rightarrow C_2' = \operatorname{ctg} x$.

Из первого уравнения: $C_1' = -C_2' \frac{\sin x}{\cos x} = -\frac{\cos x}{\sin x} \cdot \frac{\sin x}{\cos x} = -1$.

**4. Интегрирование:**
$C_1(x) = -x + C_1$
$C_2(x) = \int \frac{d(\sin x)}{\sin x} = \ln|\sin x| + C_2$

**5. Ответ:**
$y = (C_1 - x)\cos x + (C_2 + \ln|\sin x|)\sin x$.

---

#### 578. $y'' + 4y = 2 \operatorname{tg} x$

**1. Однородное:**
$\lambda^2 + 4 = 0 \Rightarrow \lambda = \pm 2i$.
$y_1 = \cos 2x, \quad y_2 = \sin 2x$.

**2. Система:**
$$
\begin{cases}
C_1' \cos 2x + C_2' \sin 2x = 0 \\
-2C_1' \sin 2x + 2C_2' \cos 2x = 2 \operatorname{tg} x
\end{cases}
$$
Разделим второе уравнение на 2:
$$
\begin{cases}
C_1' \cos 2x + C_2' \sin 2x = 0 \\
-C_1' \sin 2x + C_2' \cos 2x = \operatorname{tg} x
\end{cases}
$$

**3. Решение:**
Определитель Вронского $W = \cos^2 2x + \sin^2 2x = 1$.
$C_1' = - \sin 2x \cdot \operatorname{tg} x = -(2\sin x \cos x) \cdot \frac{\sin x}{\cos x} = -2\sin^2 x$.
$C_2' = \cos 2x \cdot \operatorname{tg} x = (\cos^2 x - \sin^2 x) \frac{\sin x}{\cos x} = \sin x \cos x - \frac{\sin^3 x}{\cos x} = \sin x \cos x - \frac{(1-\cos^2 x)\sin x}{\cos x} = \sin x \cos x - \frac{\sin x}{\cos x} + \sin x \cos x = 2\sin x \cos x - \operatorname{tg} x = \sin 2x - \operatorname{tg} x$.

**4. Интегрирование:**
$C_1(x) = \int -2\sin^2 x \, dx = \int (\cos 2x - 1) \, dx = \frac{1}{2}\sin 2x - x + C_1$.
$C_2(x) = \int (\sin 2x - \operatorname{tg} x) \, dx = -\frac{1}{2}\cos 2x - (-\ln|\cos x|) = -\frac{1}{2}\cos 2x + \ln|\cos x| + C_2$.

**5. Ответ:**
$y = C_1 \cos 2x + C_2 \sin 2x + (\frac{1}{2}\sin 2x - x)\cos 2x + (-\frac{1}{2}\cos 2x + \ln|\cos x|)\sin 2x$.
Упрощение: $\frac{1}{2}\sin 2x \cos 2x - x\cos 2x - \frac{1}{2}\cos 2x \sin 2x + \sin 2x \ln|\cos x| = -x\cos 2x + \sin 2x \ln|\cos x|$.
$y = C_1 \cos 2x + C_2 \sin 2x - x\cos 2x + \sin 2x \ln|\cos x|$.

---

#### 579. $y'' + 2y' + y = 3e^{-x}\sqrt{x+1}$

**1. Однородное:**
Аналогично №575: $\lambda_{1,2} = -1$.
$y_1 = e^{-x}, \quad y_2 = xe^{-x}$.

**2. Система:**
$$
\begin{cases}
C_1' e^{-x} + C_2' xe^{-x} = 0 \\
C_1' (-e^{-x}) + C_2' e^{-x}(1-x) = 3e^{-x}\sqrt{x+1}
\end{cases}
$$
Сократим на $e^{-x}$:
$$
\begin{cases}
C_1' + C_2' x = 0 \Rightarrow C_1' = -xC_2'\\
-C_1' + C_2'(1-x) = 3\sqrt{x+1}
\end{cases}
$$
Подставим $C_1'$ во второе:
$-(-xC_2') + C_2' - xC_2' = 3\sqrt{x+1} \Rightarrow C_2' = 3\sqrt{x+1}$.
$C_1' = -3x\sqrt{x+1}$.

**3. Интегрирование:**
$C_2(x) = 3 \int (x+1)^{1/2} dx = 3 \cdot \frac{2}{3}(x+1)^{3/2} = 2(x+1)^{3/2} + C_2$.

$C_1(x) = -3 \int x\sqrt{x+1} \, dx$.
Замена $t = x+1 \Rightarrow x = t-1, dx = dt$.
$-3 \int (t-1)t^{1/2} dt = -3 \int (t^{3/2} - t^{1/2}) dt = -3 (\frac{2}{5}t^{5/2} - \frac{2}{3}t^{3/2}) = -\frac{6}{5}(x+1)^{5/2} + 2(x+1)^{3/2} + C_1$.

**4. Ответ:**
$y = e^{-x} \left[ C_1 + C_2 x - \frac{6}{5}(x+1)^{5/2} + 2(x+1)^{3/2} + 2x(x+1)^{3/2} \right]$.
Можно упростить выражение в скобках, вынеся $2(x+1)^{3/2}$.

---

#### 580. $y'' + y = 2 \sec^3 x$

(Примечание: $\sec x = \frac{1}{\cos x}$).
**1. Однородное:** $\lambda = \pm i \Rightarrow y_1 = \cos x, y_2 = \sin x$.

**2. Система:**
$$
\begin{cases}
C_1' \cos x + C_2' \sin x = 0 \\
-C_1' \sin x + C_2' \cos x = \frac{2}{\cos^3 x}
\end{cases}
$$

**3. Решение:**
$C_1' = -\sin x \cdot \frac{2}{\cos^3 x} = -2 \frac{\sin x}{\cos^3 x}$.
$C_2' = \cos x \cdot \frac{2}{\cos^3 x} = \frac{2}{\cos^2 x}$.

**4. Интегрирование:**
$C_1(x) = -2 \int \cos^{-3}x \sin x \, dx = -2 \cdot \frac{\cos^{-2}x}{-2} (-1)?$
Проще: $u = \cos x, du = -\sin x dx$. $\int -2 u^{-3} (-du) = 2 \int u^{-3} du = 2 \frac{u^{-2}}{-2} = -\frac{1}{\cos^2 x} = -\sec^2 x + C_1$.
$C_2(x) = 2 \int \frac{dx}{\cos^2 x} = 2 \operatorname{tg} x + C_2$.

**5. Ответ:**
$y = (C_1 - \frac{1}{\cos^2 x})\cos x + (C_2 + 2\frac{\sin x}{\cos x})\sin x$
$y = C_1 \cos x + C_2 \sin x - \frac{1}{\cos x} + 2\frac{\sin^2 x}{\cos x}$
$y = C_1 \cos x + C_2 \sin x + \frac{2\sin^2 x - 1}{\cos x}$.
Так как $2\sin^2 x - 1 = -\cos 2x$, можно записать как $y = C_1 \cos x + C_2 \sin x - \frac{\cos 2x}{\cos x}$.

---

#### 581. $x^3(y'' - y) = x^2 - 2$

Приведем к каноническому виду, разделив на $x^3$:
$$y'' - y = \frac{1}{x} - \frac{2}{x^3}$$

**1. Однородное:**
$y'' - y = 0 \Rightarrow \lambda = \pm 1$.
$y_1 = e^x, \quad y_2 = e^{-x}$.

**2. Система:**
$$
\begin{cases}
C_1' e^x + C_2' e^{-x} = 0 \\
C_1' e^x - C_2' e^{-x} = \frac{1}{x} - \frac{2}{x^3}
\end{cases}
$$

**3. Решение:**
Складываем уравнения:
$2C_1' e^x = \frac{1}{x} - \frac{2}{x^3} \Rightarrow C_1' = \frac{1}{2} e^{-x} (\frac{1}{x} - \frac{2}{x^3})$.
Вычитаем уравнения:
$2C_2' e^{-x} = -(\frac{1}{x} - \frac{2}{x^3}) \Rightarrow C_2' = -\frac{1}{2} e^x (\frac{1}{x} - \frac{2}{x^3})$.

**4. Интегрирование (хитрость):**
Прямое интегрирование ведет к интегральной экспоненте, но заметим структуру производных.
Заметим, что $(\frac{e^{-x}}{x^2})' = \frac{-e^{-x}x^2 - 2xe^{-x}}{x^4} = -e^{-x}(\frac{1}{x^2} + \frac{2}{x^3})$.
И $(\frac{e^{-x}}{x})' = -e^{-x}(\frac{1}{x} + \frac{1}{x^2})$.
Попробуем подобрать функцию $F(x) = \frac{e^{-x}}{2}(\frac{A}{x} + \frac{B}{x^2})$ для $C_1$.
После вычислений (или методом подбора, как в черновике) выясняется, что интегралы берутся в конечном виде.
$$C_1(x) = \frac{1}{2} e^{-x} \left( -\frac{1}{x} + \frac{1}{x^2} \right)$$
Проверка производной:
$( \frac{1}{2} e^{-x} ( -x^{-1} + x^{-2} ) )' = \frac{1}{2} [ -e^{-x}(-x^{-1} + x^{-2}) + e^{-x}(x^{-2} - 2x^{-3}) ]$
$= \frac{1}{2} e^{-x} [ x^{-1} - x^{-2} + x^{-2} - 2x^{-3} ] = \frac{1}{2} e^{-x} [ x^{-1} - 2x^{-3} ]$. Верно!

Аналогично для $C_2$:
$$C_2(x) = -\frac{1}{2} e^{x} \left( \frac{1}{x} + \frac{1}{x^2} \right)$$

**5. Общий ответ:**
$y = C_1 e^x + C_2 e^{-x} + y_p$.
$y_p = \left[ \frac{1}{2} e^{-x} (-\frac{1}{x} + \frac{1}{x^2}) \right] e^x + \left[ -\frac{1}{2} e^{x} (\frac{1}{x} + \frac{1}{x^2}) \right] e^{-x}$.
$y_p = \frac{1}{2}(-\frac{1}{x} + \frac{1}{x^2}) - \frac{1}{2}(\frac{1}{x} + \frac{1}{x^2}) = -\frac{1}{2x} + \frac{1}{2x^2} - \frac{1}{2x} - \frac{1}{2x^2} = -\frac{1}{x}$.

**Ответ:** $y = C_1 e^x + C_2 e^{-x} - \frac{1}{x}$.

---

Вот подробное решение задач 796—799.

### Общая теория (Решение систем линейных однородных дифференциальных уравнений)

Система линейных дифференциальных уравнений с постоянными коэффициентами имеет вид:
$$
\begin{cases}
\dot{x} = a_{11}x + a_{12}y + a_{13}z \\
\dot{y} = a_{21}x + a_{22}y + a_{23}z \\
\dot{z} = a_{31}x + a_{32}y + a_{33}z
\end{cases}
$$
Или в матричной форме $\dot{\mathbf{X}} = A\mathbf{X}$.

**Алгоритм решения:**

1.  **Найти собственные числа ($\lambda$).**
    Для этого решается характеристическое уравнение $\det(A - \lambda I) = 0$.
    *В данных задачах корни $\lambda_1, \lambda_2, \lambda_3$ уже даны в условии, что значительно упрощает работу.*

2.  **Найти собственные векторы ($\mathbf{v}$).**
    Для каждого найденного $\lambda_i$ решается система линейных алгебраических уравнений:
    $$(A - \lambda_i I)\mathbf{v} = \mathbf{0}$$
    Мы ищем ненулевой вектор $\mathbf{v} = (k_1, k_2, k_3)^T$, удовлетворяющий этому условию.

3.  **Записать общее решение.**
    Если все корни $\lambda$ действительные и различные, то общее решение записывается как линейная комбинация:
    $$
    \begin{pmatrix} x(t) \\ y(t) \\ z(t) \end{pmatrix} = C_1 e^{\lambda_1 t} \mathbf{v}_1 + C_2 e^{\lambda_2 t} \mathbf{v}_2 + C_3 e^{\lambda_3 t} \mathbf{v}_3
    $$

---

### Решение задач

#### 796.
$$
\begin{cases} \dot{x} = x - y + z \\ \dot{y} = x + y - z \\ \dot{z} = 2x - y \end{cases}
\quad (\lambda_1 = 1, \lambda_2 = 2, \lambda_3 = -1)
$$
Матрица системы: $A = \begin{pmatrix} 1 & -1 & 1 \\ 1 & 1 & -1 \\ 2 & -1 & 0 \end{pmatrix}$.

**1) $\lambda_1 = 1$:**
Решаем $(A - 1I)\mathbf{v} = 0$:
$$
\begin{pmatrix} 0 & -1 & 1 \\ 1 & 0 & -1 \\ 2 & -1 & -1 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} = 0
$$
Из 1-й строки: $-y + z = 0 \Rightarrow y = z$.
Из 2-й строки: $x - z = 0 \Rightarrow x = z$.
Пусть $z = 1$, тогда вектор $\mathbf{v}_1 = (1, 1, 1)^T$.

**2) $\lambda_2 = 2$:**
Решаем $(A - 2I)\mathbf{v} = 0$:
$$
\begin{pmatrix} -1 & -1 & 1 \\ 1 & -1 & -1 \\ 2 & -1 & -2 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} = 0
$$
Сложим 1-ю и 2-ю строки: $(-x - y + z) + (x - y - z) = 0 \Rightarrow -2y = 0 \Rightarrow y = 0$.
Подставим $y=0$ в 1-ю строку: $-x + z = 0 \Rightarrow x = z$.
Пусть $z = 1$, тогда вектор $\mathbf{v}_2 = (1, 0, 1)^T$.

**3) $\lambda_3 = -1$:**
Решаем $(A + 1I)\mathbf{v} = 0$:
$$
\begin{pmatrix} 2 & -1 & 1 \\ 1 & 2 & -1 \\ 2 & -1 & 1 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} = 0
$$
Строка 3 дублирует строку 1.
Сложим строки 1 и 2: $(2x - y + z) + (x + 2y - z) = 0 \Rightarrow 3x + y = 0 \Rightarrow y = -3x$.
Из 1-й строки: $z = y - 2x = -3x - 2x = -5x$.
Пусть $x = 1$, тогда вектор $\mathbf{v}_3 = (1, -3, -5)^T$.

**Ответ:**
$$
\begin{cases}
x = C_1 e^t + C_2 e^{2t} + C_3 e^{-t} \\
y = C_1 e^t \quad \quad \quad - 3C_3 e^{-t} \\
z = C_1 e^t + C_2 e^{2t} - 5C_3 e^{-t}
\end{cases}
$$

---

#### 797.
$$
\begin{cases} \dot{x} = x - 2y - z \\ \dot{y} = -x + y + z \\ \dot{z} = x - z \end{cases}
\quad (\lambda_1 = 0, \lambda_2 = 2, \lambda_3 = -1)
$$
*(Внимание: в условии порядок переменных во втором уравнении нестандартный $y-x+z$, перепишем как $-x+y+z$ для матрицы).*
Матрица системы: $A = \begin{pmatrix} 1 & -2 & -1 \\ -1 & 1 & 1 \\ 1 & 0 & -1 \end{pmatrix}$.

**1) $\lambda_1 = 0$:**
$$
\begin{pmatrix} 1 & -2 & -1 \\ -1 & 1 & 1 \\ 1 & 0 & -1 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} = 0
$$
Из 3-й строки: $x - z = 0 \Rightarrow x = z$.
Подставим в 2-ю строку: $-x + y + z = 0 \Rightarrow -z + y + z = 0 \Rightarrow y = 0$.
Пусть $z = 1$, вектор $\mathbf{v}_1 = (1, 0, 1)^T$.

**2) $\lambda_2 = 2$:**
$$
\begin{pmatrix} -1 & -2 & -1 \\ -1 & -1 & 1 \\ 1 & 0 & -3 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} = 0
$$
Из 3-й строки: $x - 3z = 0 \Rightarrow x = 3z$.
Подставим в 2-ю: $-x - y + z = 0 \Rightarrow -(3z) - y + z = 0 \Rightarrow -y - 2z = 0 \Rightarrow y = -2z$.
Пусть $z = 1$, вектор $\mathbf{v}_2 = (3, -2, 1)^T$.

**3) $\lambda_3 = -1$:**
$$
\begin{pmatrix} 2 & -2 & -1 \\ -1 & 2 & 1 \\ 1 & 0 & 0 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} = 0
$$
Из 3-й строки: $x = 0$.
Подставим $x=0$ в 1-ю строку: $-2y - z = 0 \Rightarrow z = -2y$.
Пусть $y = 1$, тогда $z = -2$, вектор $\mathbf{v}_3 = (0, 1, -2)^T$.

**Ответ:**
$$
\begin{cases}
x = C_1 + 3C_2 e^{2t} \\
y = \quad - 2C_2 e^{2t} + C_3 e^{-t} \\
z = C_1 + C_2 e^{2t} - 2C_3 e^{-t}
\end{cases}
$$

---

#### 798.
$$
\begin{cases} \dot{x} = 2x - y + z \\ \dot{y} = x + 2y - z \\ \dot{z} = x - y + 2z \end{cases}
\quad (\lambda_1 = 1, \lambda_2 = 2, \lambda_3 = 3)
$$
Матрица системы: $A = \begin{pmatrix} 2 & -1 & 1 \\ 1 & 2 & -1 \\ 1 & -1 & 2 \end{pmatrix}$.

**1) $\lambda_1 = 1$:**
$$
\begin{pmatrix} 1 & -1 & 1 \\ 1 & 1 & -1 \\ 1 & -1 & 1 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} = 0
$$
Сложим 1-ю и 2-ю строки: $(x-y+z) + (x+y-z) = 0 \Rightarrow 2x = 0 \Rightarrow x = 0$.
Подставим $x=0$ в 1-ю строку: $-y + z = 0 \Rightarrow y = z$.
Пусть $z = 1$, вектор $\mathbf{v}_1 = (0, 1, 1)^T$.

**2) $\lambda_2 = 2$:**
$$
\begin{pmatrix} 0 & -1 & 1 \\ 1 & 0 & -1 \\ 1 & -1 & 0 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} = 0
$$
Из 1-й строки: $-y + z = 0 \Rightarrow y = z$.
Из 2-й строки: $x - z = 0 \Rightarrow x = z$.
Вектор $\mathbf{v}_2 = (1, 1, 1)^T$.

**3) $\lambda_3 = 3$:**
$$
\begin{pmatrix} -1 & -1 & 1 \\ 1 & -1 & -1 \\ 1 & -1 & -1 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} = 0
$$
Сложим 1-ю и 2-ю строки: $(-x - y + z) + (x - y - z) = 0 \Rightarrow -2y = 0 \Rightarrow y = 0$.
Подставим $y=0$ в 1-ю: $-x + z = 0 \Rightarrow x = z$.
Вектор $\mathbf{v}_3 = (1, 0, 1)^T$.

**Ответ:**
$$
\begin{cases}
x = \quad \quad C_2 e^{2t} + C_3 e^{3t} \\
y = C_1 e^t + C_2 e^{2t} \\
z = C_1 e^t + C_2 e^{2t} + C_3 e^{3t}
\end{cases}
$$

---

#### 799.
$$
\begin{cases} \dot{x} = 3x - y + z \\ \dot{y} = x + y + z \\ \dot{z} = 4x - y + 4z \end{cases}
\quad (\lambda_1 = 1, \lambda_2 = 2, \lambda_3 = 5)
$$
Матрица системы: $A = \begin{pmatrix} 3 & -1 & 1 \\ 1 & 1 & 1 \\ 4 & -1 & 4 \end{pmatrix}$.

**1) $\lambda_1 = 1$:**
$$
\begin{pmatrix} 2 & -1 & 1 \\ 1 & 0 & 1 \\ 4 & -1 & 3 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} = 0
$$
Из 2-й строки: $x + z = 0 \Rightarrow z = -x$.
Подставим в 1-ю: $2x - y + (-x) = 0 \Rightarrow x - y = 0 \Rightarrow y = x$.
Пусть $x=1$, вектор $\mathbf{v}_1 = (1, 1, -1)^T$.

**2) $\lambda_2 = 2$:**
$$
\begin{pmatrix} 1 & -1 & 1 \\ 1 & -1 & 1 \\ 4 & -1 & 2 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} = 0
$$
Из 1-й строки: $x - y + z = 0 \Rightarrow y = x + z$.
Подставим в 3-ю: $4x - (x+z) + 2z = 0 \Rightarrow 3x + z = 0 \Rightarrow z = -3x$.
Тогда $y = x + (-3x) = -2x$.
Пусть $x=1$, вектор $\mathbf{v}_2 = (1, -2, -3)^T$.

**3) $\lambda_3 = 5$:**
$$
\begin{pmatrix} -2 & -1 & 1 \\ 1 & -4 & 1 \\ 4 & -1 & -1 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} = 0
$$
Вычтем из 1-й строки 2-ю: $(-2x-y+z) - (x-4y+z) = 0 \Rightarrow -3x + 3y = 0 \Rightarrow x = y$.
Подставим $y=x$ в 1-ю строку: $-2x - x + z = 0 \Rightarrow -3x + z = 0 \Rightarrow z = 3x$.
Пусть $x=1$, вектор $\mathbf{v}_3 = (1, 1, 3)^T$.

**Ответ:**
$$
\begin{cases}
x = C_1 e^t + C_2 e^{2t} + C_3 e^{5t} \\
y = C_1 e^t - 2C_2 e^{2t} + C_3 e^{5t} \\
z = -C_1 e^t - 3C_2 e^{2t} + 3C_3 e^{5t}
\end{cases}
$$

---

Вот решение задач 796—799 с подробным описанием метода и пошаговыми выкладками.

### Общая теория (Метод собственных векторов)

Для решения системы линейных однородных дифференциальных уравнений с постоянными коэффициентами вида:
$$
\begin{cases}
\dot{x} = a_{11}x + a_{12}y + a_{13}z \\
\dot{y} = a_{21}x + a_{22}y + a_{23}z \\
\dot{z} = a_{31}x + a_{32}y + a_{33}z
\end{cases}
$$
(или в векторной форме $\dot{\mathbf{X}} = A\mathbf{X}$) используется следующий алгоритм:

1.  **Составляем характеристическое уравнение** $\det(A - \lambda I) = 0$ и находим его корни (собственные числа $\lambda$).
    *В данных задачах корни $\lambda_1, \lambda_2, \lambda_3$ уже даны в условии, что значительно ускоряет решение.*

2.  **Находим собственные векторы.**
    Для каждого $\lambda_i$ решаем систему линейных алгебраических уравнений:
    $$(A - \lambda_i I)\mathbf{v} = \mathbf{0}$$
    Находим ненулевой вектор $\mathbf{v}_i = (p_i, q_i, r_i)^T$.

3.  **Записываем общее решение.**
    Если все корни действительные и различные, решение имеет вид:
    $$
    \begin{pmatrix} x(t) \\ y(t) \\ z(t) \end{pmatrix} = C_1 e^{\lambda_1 t} \mathbf{v}_1 + C_2 e^{\lambda_2 t} \mathbf{v}_2 + C_3 e^{\lambda_3 t} \mathbf{v}_3
    $$

---

### Решение задач

#### Задача 796
$$
\begin{cases} \dot{x} = x - y + z \\ \dot{y} = x + y - z \\ \dot{z} = 2x - y \end{cases}
\quad (\lambda_1 = 1, \lambda_2 = 2, \lambda_3 = -1).
$$
Обратите внимание на порядок переменных в уравнениях (например, в первом уравнении $x + z - y$ переписываем как $x - y + z$).
Матрица системы:
$$A = \begin{pmatrix} 1 & -1 & 1 \\ 1 & 1 & -1 \\ 2 & -1 & 0 \end{pmatrix}$$

**1. Корень $\lambda_1 = 1$.**
Решаем систему $(A - 1I)\mathbf{v} = 0$:
$$
\begin{pmatrix} 0 & -1 & 1 \\ 1 & 0 & -1 \\ 2 & -1 & -1 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} = 0
$$
Из 1-го уравнения: $-y + z = 0 \Rightarrow y = z$.
Из 2-го уравнения: $x - z = 0 \Rightarrow x = z$.
Полагая $z=1$, получаем собственный вектор $\mathbf{v}_1 = (1, 1, 1)^T$.

**2. Корень $\lambda_2 = 2$.**
Решаем систему $(A - 2I)\mathbf{v} = 0$:
$$
\begin{pmatrix} -1 & -1 & 1 \\ 1 & -1 & -1 \\ 2 & -1 & -2 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} = 0
$$
Сложим 1-е и 2-е уравнения: $(-x - y + z) + (x - y - z) = 0 \Rightarrow -2y = 0 \Rightarrow y = 0$.
Подставим $y=0$ в 1-е уравнение: $-x + z = 0 \Rightarrow x = z$.
Полагая $z=1$, получаем $\mathbf{v}_2 = (1, 0, 1)^T$.

**3. Корень $\lambda_3 = -1$.**
Решаем систему $(A - (-1)I)\mathbf{v} = (A + I)\mathbf{v} = 0$:
$$
\begin{pmatrix} 2 & -1 & 1 \\ 1 & 2 & -1 \\ 2 & -1 & 1 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} = 0
$$
Сложим 1-е и 2-е уравнения: $(2x - y + z) + (x + 2y - z) = 0 \Rightarrow 3x + y = 0 \Rightarrow y = -3x$.
Из 1-го уравнения: $z = y - 2x = -3x - 2x = -5x$.
Полагая $x=1$, получаем $\mathbf{v}_3 = (1, -3, -5)^T$.

**Общее решение:**
$$ \mathbf{X} = C_1 e^t \begin{pmatrix} 1 \\ 1 \\ 1 \end{pmatrix} + C_2 e^{2t} \begin{pmatrix} 1 \\ 0 \\ 1 \end{pmatrix} + C_3 e^{-t} \begin{pmatrix} 1 \\ -3 \\ -5 \end{pmatrix} $$

**Ответ:**
$\begin{cases} x = C_1 e^t + C_2 e^{2t} + C_3 e^{-t} \\ y = C_1 e^t \quad \quad \quad - 3C_3 e^{-t} \\ z = C_1 e^t + C_2 e^{2t} - 5C_3 e^{-t} \end{cases}$

---

#### Задача 797
$$
\begin{cases} \dot{x} = x - 2y - z \\ \dot{y} = -x + y + z \\ \dot{z} = x - z \end{cases}
\quad (\lambda_1 = 0, \lambda_2 = 2, \lambda_3 = -1).
$$
(Во втором уравнении $y-x+z$ упорядочено как $-x+y+z$).
Матрица системы:
$$A = \begin{pmatrix} 1 & -2 & -1 \\ -1 & 1 & 1 \\ 1 & 0 & -1 \end{pmatrix}$$

**1. Корень $\lambda_1 = 0$.**
$(A - 0I)\mathbf{v} = 0$:
$$ \begin{pmatrix} 1 & -2 & -1 \\ -1 & 1 & 1 \\ 1 & 0 & -1 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} = 0 $$
Из 3-го: $x - z = 0 \Rightarrow x = z$.
Из 2-го: $-x + y + z = 0 \Rightarrow -z + y + z = 0 \Rightarrow y = 0$.
$\mathbf{v}_1 = (1, 0, 1)^T$.

**2. Корень $\lambda_2 = 2$.**
$(A - 2I)\mathbf{v} = 0$:
$$ \begin{pmatrix} -1 & -2 & -1 \\ -1 & -1 & 1 \\ 1 & 0 & -3 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} = 0 $$
Из 3-го: $x = 3z$.
Из 2-го: $-x - y + z = 0 \Rightarrow -3z - y + z = 0 \Rightarrow y = -2z$.
$\mathbf{v}_2 = (3, -2, 1)^T$.

**3. Корень $\lambda_3 = -1$.**
$(A + I)\mathbf{v} = 0$:
$$ \begin{pmatrix} 2 & -2 & -1 \\ -1 & 2 & 1 \\ 1 & 0 & 0 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} = 0 $$
Из 3-го: $x = 0$.
Из 2-го: $-x + 2y + z = 0 \Rightarrow 2y + z = 0 \Rightarrow z = -2y$.
Пусть $y=1$, тогда $\mathbf{v}_3 = (0, 1, -2)^T$.

**Ответ:**
$\begin{cases} x = C_1 + 3C_2 e^{2t} \\ y = \quad - 2C_2 e^{2t} + C_3 e^{-t} \\ z = C_1 + C_2 e^{2t} - 2C_3 e^{-t} \end{cases}$

---

#### Задача 798
$$
\begin{cases} \dot{x} = 2x - y + z \\ \dot{y} = x + 2y - z \\ \dot{z} = x - y + 2z \end{cases}
\quad (\lambda_1 = 1, \lambda_2 = 2, \lambda_3 = 3).
$$
Матрица системы:
$$A = \begin{pmatrix} 2 & -1 & 1 \\ 1 & 2 & -1 \\ 1 & -1 & 2 \end{pmatrix}$$

**1. Корень $\lambda_1 = 1$.**
$(A - I)\mathbf{v} = 0$:
$$ \begin{pmatrix} 1 & -1 & 1 \\ 1 & 1 & -1 \\ 1 & -1 & 1 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} = 0 $$
Из 1-го и 2-го уравнений:
$\begin{cases} x - y + z = 0 \\ x + y - z = 0 \end{cases}$
Сложим их: $2x = 0 \Rightarrow x = 0$.
Подставим в 1-е: $-y + z = 0 \Rightarrow y = z$.
$\mathbf{v}_1 = (0, 1, 1)^T$.

**2. Корень $\lambda_2 = 2$.**
$(A - 2I)\mathbf{v} = 0$:
$$ \begin{pmatrix} 0 & -1 & 1 \\ 1 & 0 & -1 \\ 1 & -1 & 0 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} = 0 $$
Из 1-го: $y = z$.
Из 2-го: $x = z$.
$\mathbf{v}_2 = (1, 1, 1)^T$.

**3. Корень $\lambda_3 = 3$.**
$(A - 3I)\mathbf{v} = 0$:
$$ \begin{pmatrix} -1 & -1 & 1 \\ 1 & -1 & -1 \\ 1 & -1 & -1 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} = 0 $$
Сложим 1-е и 2-е: $-2y = 0 \Rightarrow y = 0$.
Из 1-го: $-x + z = 0 \Rightarrow x = z$.
$\mathbf{v}_3 = (1, 0, 1)^T$.

**Ответ:**
$\begin{cases} x = \quad \quad C_2 e^{2t} + C_3 e^{3t} \\ y = C_1 e^t + C_2 e^{2t} \\ z = C_1 e^t + C_2 e^{2t} + C_3 e^{3t} \end{cases}$

---

#### Задача 799
$$
\begin{cases} \dot{x} = 3x - y + z \\ \dot{y} = x + y + z \\ \dot{z} = 4x - y + 4z \end{cases}
\quad (\lambda_1 = 1, \lambda_2 = 2, \lambda_3 = 5).
$$
Матрица системы:
$$A = \begin{pmatrix} 3 & -1 & 1 \\ 1 & 1 & 1 \\ 4 & -1 & 4 \end{pmatrix}$$

**1. Корень $\lambda_1 = 1$.**
$(A - I)\mathbf{v} = 0$:
$$ \begin{pmatrix} 2 & -1 & 1 \\ 1 & 0 & 1 \\ 4 & -1 & 3 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} = 0 $$
Из 2-го: $x = -z$.
Из 1-го: $2x - y + z = 0 \Rightarrow 2(-z) - y + z = 0 \Rightarrow -z - y = 0 \Rightarrow y = -z$.
Пусть $z = -1$, тогда $x=1, y=1$.
$\mathbf{v}_1 = (1, 1, -1)^T$.

**2. Корень $\lambda_2 = 2$.**
$(A - 2I)\mathbf{v} = 0$:
$$ \begin{pmatrix} 1 & -1 & 1 \\ 1 & -1 & 1 \\ 4 & -1 & 2 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} = 0 $$
Из 1-го: $y = x + z$.
Подставим в 3-е: $4x - (x+z) + 2z = 0 \Rightarrow 3x + z = 0 \Rightarrow z = -3x$.
Тогда $y = x + (-3x) = -2x$.
$\mathbf{v}_2 = (1, -2, -3)^T$.

**3. Корень $\lambda_3 = 5$.**
$(A - 5I)\mathbf{v} = 0$:
$$ \begin{pmatrix} -2 & -1 & 1 \\ 1 & -4 & 1 \\ 4 & -1 & -1 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} = 0 $$
Вычтем из 1-го уравнения 2-е: $(-2x - y + z) - (x - 4y + z) = 0 \Rightarrow -3x + 3y = 0 \Rightarrow x = y$.
Подставим в 1-е: $-2x - x + z = 0 \Rightarrow z = 3x$.
$\mathbf{v}_3 = (1, 1, 3)^T$.

**Ответ:**
$\begin{cases} x = C_1 e^t + C_2 e^{2t} + C_3 e^{5t} \\ y = C_1 e^t - 2C_2 e^{2t} + C_3 e^{5t} \\ z = -C_1 e^t - 3C_2 e^{2t} + 3C_3 e^{5t} \end{cases}$

---

Вот подробное решение задач 899—906 на исследование устойчивости по первому приближению.

### Общая теория (Теорема Ляпунова по первому приближению)

Для исследования устойчивости нелинейной системы $\dot{\mathbf{x}} = \mathbf{f}(\mathbf{x})$ в окрестности точки покоя (обычно начала координат $x_i=0$) используют метод линеаризации.

**Алгоритм:**
1.  **Линеаризация:** Разлагаем функции правой части в ряд Тейлора (или Маклорена) в окрестности нуля, оставляя только слагаемые первой степени (линейную часть).
    *   Используем приближения для малых величин:
        *   $\sin u \approx u, \quad \operatorname{tg} u \approx u$
        *   $e^u \approx 1 + u$
        *   $\ln(1+u) \approx u$
        *   $(1+u)^\alpha \approx 1 + \alpha u$
        *   $\cos u \approx 1$ (так как следующий член $u^2/2$ — второго порядка малости).
2.  **Матрица системы:** Составляем матрицу $A$ линейной системы $\dot{\mathbf{x}} = A\mathbf{x}$.
3.  **Собственные числа:** Находим корни характеристического уравнения $\det(A - \lambda I) = 0$.
4.  **Вывод об устойчивости:**
    *   Если у **всех** корней вещественная часть отрицательна ($\operatorname{Re} \lambda_i < 0$) — нулевое решение **асимптотически устойчиво**.
    *   Если хотя бы у одного корня вещественная часть положительна ($\operatorname{Re} \lambda_i > 0$) — решение **неустойчиво**.
    *   Если есть корни с нулевой вещественной частью (чисто мнимые или 0), а остальные отрицательны — это *критический случай*, первое приближение ответа не дает (требуется более глубокий анализ, но в рамках задачника это обычно не требуется).

---

### Решение задач

#### 899.
$\begin{cases} \dot{x} = 2xy - x + y \\ \dot{y} = 5x^4 + y^3 + 2x - 3y \end{cases}$

1.  **Линеаризация:** Отбрасываем нелинейные члены ($xy, x^4, y^3$):
    $\begin{cases} \dot{x} = -x + y \\ \dot{y} = 2x - 3y \end{cases}$
2.  **Матрица:** $A = \begin{pmatrix} -1 & 1 \\ 2 & -3 \end{pmatrix}$.
3.  **Характеристическое уравнение:**
    $\lambda^2 - \operatorname{tr}(A)\lambda + \det(A) = 0$
    $\operatorname{tr}(A) = -1 - 3 = -4$.
    $\det(A) = 3 - 2 = 1$.
    $\lambda^2 + 4\lambda + 1 = 0$.
4.  **Корни:** $D = 16 - 4 = 12$. Оба корня вещественные. По теореме Виета $\lambda_1 + \lambda_2 = -4$ (отрицательная сумма), $\lambda_1 \lambda_2 = 1$ (положительное произведение). Следовательно, оба корня отрицательны ($\lambda_{1,2} = -2 \pm \sqrt{3}$).
**Ответ: Асимптотически устойчиво.**

#### 900.
$\begin{cases} \dot{x} = x^2 + y^2 - 2x \\ \dot{y} = 3x^2 - x + 3y \end{cases}$

1.  **Линеаризация:**
    $\begin{cases} \dot{x} = -2x \\ \dot{y} = -x + 3y \end{cases}$
2.  **Матрица:** $A = \begin{pmatrix} -2 & 0 \\ -1 & 3 \end{pmatrix}$.
3.  Так как матрица треугольная, собственные числа стоят на диагонали:
    $\lambda_1 = -2, \quad \lambda_2 = 3$.
4.  Есть положительный корень ($\lambda_2 = 3$).
**Ответ: Неустойчиво.**

#### 901.
$\begin{cases} \dot{x} = e^{x+2y} - \cos 3x \\ \dot{y} = \sqrt{4+8x} - 2e^y \end{cases}$

1.  **Линеаризация:**
    *   $e^{x+2y} \approx 1 + (x+2y)$
    *   $\cos 3x \approx 1$
    *   $\sqrt{4+8x} = 2\sqrt{1+2x} \approx 2(1 + \frac{1}{2}\cdot 2x) = 2 + 2x$
    *   $2e^y \approx 2(1+y) = 2 + 2y$
    Подставляем:
    $\begin{cases} \dot{x} = (1 + x + 2y) - 1 = x + 2y \\ \dot{y} = (2 + 2x) - (2 + 2y) = 2x - 2y \end{cases}$
2.  **Матрица:** $A = \begin{pmatrix} 1 & 2 \\ 2 & -2 \end{pmatrix}$.
3.  **Характеристическое уравнение:** $\lambda^2 - (1-2)\lambda + (-2-4) = 0 \Rightarrow \lambda^2 + \lambda - 6 = 0$.
4.  **Корни:** $\lambda_1 = -3, \lambda_2 = 2$. Есть положительный корень.
**Ответ: Неустойчиво.**

#### 902.
$\begin{cases} \dot{x} = \ln(4y + e^{-3x}) \\ \dot{y} = 2y - 1 + \sqrt[3]{1-6x} \end{cases}$

1.  **Линеаризация:**
    *   $e^{-3x} \approx 1 - 3x$
    *   $\ln(4y + 1 - 3x) = \ln(1 + (4y - 3x)) \approx 4y - 3x$
    *   $\sqrt[3]{1-6x} \approx 1 + \frac{1}{3}(-6x) = 1 - 2x$
    Система:
    $\begin{cases} \dot{x} = -3x + 4y \\ \dot{y} = 2y - 1 + 1 - 2x = -2x + 2y \end{cases}$
2.  **Матрица:** $A = \begin{pmatrix} -3 & 4 \\ -2 & 2 \end{pmatrix}$.
3.  **Характеристическое уравнение:** $\lambda^2 - (-3+2)\lambda + (-6 - (-8)) = 0 \Rightarrow \lambda^2 + \lambda + 2 = 0$.
4.  **Корни:** $D = 1 - 8 = -7$. Корни комплексно-сопряженные: $\lambda_{1,2} = \frac{-1 \pm i\sqrt{7}}{2}$.
    Вещественная часть $\operatorname{Re}(\lambda) = -0.5 < 0$.
**Ответ: Асимптотически устойчиво.**

#### 903.
$\begin{cases} \dot{x} = \ln(3e^y - 2\cos x) \\ \dot{y} = 2e^x - \sqrt[3]{8+12y} \end{cases}$

1.  **Линеаризация:**
    *   $3e^y - 2\cos x \approx 3(1+y) - 2(1) = 1 + 3y$.
    *   $\ln(1 + 3y) \approx 3y$.
    *   $\sqrt[3]{8+12y} = 2\sqrt[3]{1 + \frac{12}{8}y} = 2\sqrt[3]{1 + 1.5y} \approx 2(1 + \frac{1}{3}\cdot 1.5y) = 2(1+0.5y) = 2 + y$.
    *   $2e^x \approx 2(1+x) = 2+2x$.
    Система:
    $\begin{cases} \dot{x} = 3y \\ \dot{y} = (2+2x) - (2+y) = 2x - y \end{cases}$
2.  **Матрица:** $A = \begin{pmatrix} 0 & 3 \\ 2 & -1 \end{pmatrix}$.
3.  **Характеристическое уравнение:** $\lambda^2 + \lambda - 6 = 0$.
4.  **Корни:** $\lambda_1 = -3, \lambda_2 = 2$.
**Ответ: Неустойчиво.**

#### 904.
$\begin{cases} \dot{x} = \operatorname{tg}(y - x) \\ \dot{y} = 2^y - 2\cos(\frac{\pi}{3} - x) \end{cases}$

1.  **Линеаризация:**
    *   $\operatorname{tg}(y-x) \approx y - x = -x + y$.
    *   $2^y = e^{y \ln 2} \approx 1 + y \ln 2$.
    *   $\cos(\frac{\pi}{3} - x) = \cos \frac{\pi}{3} \cos x + \sin \frac{\pi}{3} \sin x \approx \frac{1}{2}\cdot 1 + \frac{\sqrt{3}}{2} \cdot x = \frac{1}{2} + \frac{\sqrt{3}}{2}x$.
    Система:
    $\begin{cases} \dot{x} = -x + y \\ \dot{y} = (1 + y \ln 2) - 2(\frac{1}{2} + \frac{\sqrt{3}}{2}x) = -\sqrt{3}x + y \ln 2 \end{cases}$
2.  **Матрица:** $A = \begin{pmatrix} -1 & 1 \\ -\sqrt{3} & \ln 2 \end{pmatrix}$.
3.  **Характеристическое уравнение:** $\lambda^2 - (\ln 2 - 1)\lambda + (-\ln 2 + \sqrt{3}) = 0$.
    *   Свободный член: $\sqrt{3} - \ln 2 \approx 1.73 - 0.69 > 0$.
    *   Коэффициент при $\lambda$: $p = -(\ln 2 - 1) = 1 - \ln 2 > 0$ (так как $\ln 2 \approx 0.69 < 1$).
    По критерию Рауса-Гурвица (или просто знакам коэффициентов для квадратного уравнения), если все коэффициенты положительны, то вещественные части корней отрицательны.
**Ответ: Асимптотически устойчиво.**

#### 905.
$\begin{cases} \dot{x} = \operatorname{tg}(z - y) - 2x \\ \dot{y} = \sqrt{9+12x} - 3e^y \\ \dot{z} = -3y \end{cases}$

1.  **Линеаризация:**
    *   $\dot{x} \approx z - y - 2x = -2x - y + z$.
    *   $\sqrt{9+12x} = 3\sqrt{1+\frac{4}{3}x} \approx 3(1 + \frac{1}{2}\cdot\frac{4}{3}x) = 3 + 2x$.
    *   $3e^y \approx 3(1+y) = 3 + 3y$.
    *   $\dot{y} \approx (3+2x) - (3+3y) = 2x - 3y$.
    Система:
    $\begin{cases} \dot{x} = -2x - y + z \\ \dot{y} = 2x - 3y \\ \dot{z} = -3y \end{cases}$
2.  **Матрица:** $A = \begin{pmatrix} -2 & -1 & 1 \\ 2 & -3 & 0 \\ 0 & -3 & 0 \end{pmatrix}$.
3.  **Характеристическое уравнение:**
    $\det(A - \lambda I) = \begin{vmatrix} -2-\lambda & -1 & 1 \\ 2 & -3-\lambda & 0 \\ 0 & -3 & -\lambda \end{vmatrix} = 0$.
    Раскроем по третьей строке:
    $-(-3) \cdot \begin{vmatrix} -2-\lambda & 1 \\ 2 & 0 \end{vmatrix} + (-\lambda) \cdot \begin{vmatrix} -2-\lambda & -1 \\ 2 & -3-\lambda \end{vmatrix} = 0$
    $3 \cdot (-2) - \lambda [(-2-\lambda)(-3-\lambda) - (-2)] = 0$
    $-6 - \lambda [\lambda^2 + 5\lambda + 6 + 2] = 0$
    $-6 - \lambda^3 - 5\lambda^2 - 8\lambda = 0 \Rightarrow \lambda^3 + 5\lambda^2 + 8\lambda + 6 = 0$.
4.  **Критерий Гурвица:**
    Для уравнения $a_0\lambda^3 + a_1\lambda^2 + a_2\lambda + a_3 = 0$ ($1, 5, 8, 6$).
    Условия устойчивости:
    1) Все $a_i > 0$ — выполнено.
    2) $a_1 a_2 - a_0 a_3 > 0 \Rightarrow 5 \cdot 8 - 1 \cdot 6 = 40 - 6 = 34 > 0$ — выполнено.
**Ответ: Асимптотически устойчиво.**

#### 906.
$\begin{cases} \dot{x} = e^x - e^{-3z} \\ \dot{y} = 4z - 3\sin(x+y) \\ \dot{z} = \ln(1 + z - 3x) \end{cases}$

1.  **Линеаризация:**
    *   $\dot{x} \approx (1+x) - (1-3z) = x + 3z$.
    *   $\dot{y} \approx 4z - 3(x+y) = -3x - 3y + 4z$.
    *   $\dot{z} \approx z - 3x = -3x + z$.
    Матрица: $A = \begin{pmatrix} 1 & 0 & 3 \\ -3 & -3 & 4 \\ -3 & 0 & 1 \end{pmatrix}$.
2.  **Характеристическое уравнение:**
    $\begin{vmatrix} 1-\lambda & 0 & 3 \\ -3 & -3-\lambda & 4 \\ -3 & 0 & 1-\lambda \end{vmatrix} = 0$.
    Разложим по второму столбцу:
    $(-3-\lambda) \cdot \begin{vmatrix} 1-\lambda & 3 \\ -3 & 1-\lambda \end{vmatrix} = 0$.
    Первый корень: $\lambda_1 = -3$ (отрицательный).
    Оставшиеся корни из определителя:
    $(1-\lambda)^2 - (-9) = 0 \Rightarrow (1-\lambda)^2 + 9 = 0$.
    $(1-\lambda)^2 = -9 \Rightarrow 1-\lambda = \pm 3i \Rightarrow \lambda_{2,3} = 1 \pm 3i$.
3.  **Анализ:**
    У корней $\lambda_{2,3}$ вещественная часть $\operatorname{Re}(\lambda) = 1 > 0$.
**Ответ: Неустойчиво.**

---

