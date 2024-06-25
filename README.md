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

//Задача3.
#include <iostream>
using namespace std;

// Функция для вычисления суммы цифр числа
int sum_of_digits(int num) {
    int sum = 0;
    while (num > 0) {
        sum += num % 10;
        num /= 10;
    }
    return sum;
}

int find_number_with_max_digit_sum(int a, int b) {
    int max_sum = -1; // Инициализируем максимальную сумму цифр как -1 (недопустимое значение)
    int result_number = -1; // Инициализируем результат как -1 (недопустимое значение)

    for (int i = a; i <= b; ++i) {
        int current_sum = sum_of_digits(i);
        if (current_sum > max_sum || (current_sum == max_sum && i < result_number)) {
            max_sum = current_sum;
            result_number = i;
        }
    }

    return result_number;
}

int main() {
    int a, b;
    cout << "Введите интервал [a, b]: ";
    cin >> a >> b;

    int result = find_number_with_max_digit_sum(a, b);
    
    if (result == -1) {
        cout << "В заданном интервале нет натуральных чисел.\n";
    } else {
        cout << "Число с максимальной суммой цифр в интервале [" << a << ", " << b << "]: " << result << endl;
    }

    return 0;
}

