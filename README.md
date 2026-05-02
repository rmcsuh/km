flowchart TD
    A[Начало] --> B[/Ввод: N, M, образы X[1..M], тестовый Xin, max_iter/]
    B --> C[Инициализация матрицы W N×N нулями]
    C --> D[Для всех i ≠ j:<br>W[i][j] = 1/N * Σ_{m=1..M} X[m][i] * X[m][j]]
    D --> E[W[i][i] = 0 для всех i]
    E --> F[S = Xin<br>iter = 0]
    F --> G[iter = iter + 1<br>old_S = S]
    
    G --> H[Синхронное обновление:<br>Для i = 1..N:<br>sum = Σ_{j=1..N} W[i][j] * S[j]<br>S_new[i] = sign(sum)]
    H --> I[S = S_new]
    
    I --> J{S == old_S?}
    J -->|Да| K[/Вывод: S - восстановленный образ/]
    K --> L[Конец]
    
    J -->|Нет| M{iter >= max_iter?}
    M -->|Нет| G
    M -->|Да| N[/Вывод: "Сходимость не достигнута", S/]
    N --> L
