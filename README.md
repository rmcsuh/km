# Алгоритм работы сети Хопфилда

## Блок-схема

```mermaid
flowchart TD
    A[Начало] --> B[/Ввод параметров/]
    B --> C[Расчёт матрицы весов W]
    C --> D[S = Xin, iter = 0]
    D --> E{iter < max_iter?}
    E -->|Нет| F[/Вывод S/]
    F --> G[Конец]
    E -->|Да| H[S_old = S]
    H --> I[Обновление: S_new = sign(W * S)]
    I --> J{S_new == S_old?}
    J -->|Да| F
    J -->|Нет| K[iter = iter + 1, S = S_new]
    K --> E
