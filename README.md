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

//Задача4 
#include <iostream>
#include <cstdio> // Для использования printf и scanf

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

    // Не используем функцию getch(), так как она специфична для Windows и не является стандартной в C++.

    return 0;
}

//Задача 5
#include <iostream>
#include <limits> // Для использования std::numeric_limits
using namespace std;

const int MAX_SIZE = 100; // Максимальный размер массива, можно увеличить при необходимости

void printArray(int arr[MAX_SIZE][MAX_SIZE], int n) {
    for (int i = 0; i < n; ++i) {
        for (int j = 0; j < n; ++j) {
            cout << arr[i][j] << " ";
        }
        cout << endl;
    }
}

void replaceMinWithZeroInColumns(int arr[MAX_SIZE][MAX_SIZE], int n) {
    for (int j = 0; j < n; ++j) {
        // Находим минимальный элемент в столбце j
        int min_element = arr[0][j];
        for (int i = 1; i < n; ++i) {
            if (arr[i][j] < min_element) {
                min_element = arr[i][j];
            }
        }
        
        // Заменяем минимальный элемент в столбце j на ноль
        for (int i = 0; i < n; ++i) {
            if (arr[i][j] == min_element) {
                arr[i][j] = 0;
                break; // Найден минимальный элемент, выходим из цикла
            }
        }
    }
}
void swapRows(int arr[MAX_SIZE][MAX_SIZE], int row1, int row2, int n) {
    for (int j = 0; j < n; ++j) {
        int temp = arr[row1][j];
        arr[row1][j] = arr[row2][j];
        arr[row2][j] = temp;
    }
}

int main() {
    int n;
    int arr[MAX_SIZE][MAX_SIZE];

    // Ввод размерности массива
    cout << "Введите размерность двумерного массива (n): ";
    cin >> n;

    // Ввод элементов массива
    cout << "Введите элементы массива:" << endl;
    for (int i = 0; i < n; ++i) {
        for (int j = 0; j < n; ++j) {
            cin >> arr[i][j];
        }
    }

    // Заменяем минимальный элемент каждого столбца на ноль
    replaceMinWithZeroInColumns(arr, n);

    // Меняем местами первую и предпоследнюю строки
    swapRows(arr, 0, n - 2, n);

    // Выводим измененный массив
    cout << "Массив после выполнения операций:" << endl;
    printArray(arr, n);

    return 0;
}

