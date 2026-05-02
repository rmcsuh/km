flowchart TD
    A[Начало] --> B["Ввод параметров:<br>N, M, образы, Xin, max_iter"]
    B --> C[Расчёт матрицы весов W]
    C --> D["S = Xin<br>iter = 0"]
    D --> E{iter < max_iter?}
    E -->|Нет| F["Вывод S<br>(восстановленный образ)"]
    F --> G[Конец]
    E -->|Да| H["S_old = S"]
    H --> I["Обновление:<br>S_new = sign(W × S)"]
    I --> J{S_new == S_old?}
    J -->|Да| F
    J -->|Нет| K["iter = iter + 1<br>S = S_new"]
    K --> E
