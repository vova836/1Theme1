//Задача1.
#include "stdio.h"
#include "conio.h"

int main() {
    // Переменные
    double x, a, b, y;

    // Ввод значений
    printf("Введите значение x: ");
    scanf("%lf", &x);
    printf("Введите значение a: ");
    scanf("%lf", &a);
    printf("Введите значение b: ");
    scanf("%lf", &b);

    // Вычисление выражения
    y = 4 * x * x - b * b + (2 * a * a * a * a) / (b * b);

    // Вывод результата
    printf("Значение y: %lf\n", y);

    // Ожидание нажатия клавиши
    getch();
    return 0;
} 

//Задача2.
#include <stdio.h>
#include <conio.h>
#include <cmath> // Для использования sqrt()

int main() {
    float a, b, c, q;
    printf("Введите длины сторон сундука (a, b, c): ");
    scanf("%f %f %f", &a, &b, &c);
    printf("Введите радиус отверстия q: ");
    scanf("%f", &q);

    // Вычисляем диагональ сундука
    float d = sqrt(a * a + b * b + c * c);

    // Проверяем условие прохождения
    if (d <= 2 * q) {
        printf("Сундук пройдет через отверстие.\n");
    } else {
        printf("Сундук не пройдет через отверстие.\n");
    }

    getch(); // Ждем нажатия клавиши перед выходом
    return 0;
}
