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
#include "stdio.h"
#include "conio.h"

int main() {
    int numbers[5];
    int max, middle;

    // Ввод пяти различных целых чисел
    printf("Введите пять различных целых чисел:\n");
    for (int i = 0; i < 5; i++) {
        printf("Число %d: ", i + 1);
        scanf("%d", &numbers[i]);
    }

    // Сортировка массива для нахождения максимального и среднего значения
    for (int i = 0; i < 4; i++) {
        for (int j = i + 1; j < 5; j++) {
            if (numbers[i] > numbers[j]) {
                int temp = numbers[i];
                numbers[i] = numbers[j];
                numbers[j] = temp;
            }
        }
    }

    // Максимальное значение
    max = numbers[4];

    // Среднее значение (третье в отсортированном массиве)
    middle = numbers[2];

    // Разность между максимальным и средним значением
    int difference = max - middle;

    // Вывод результата
    printf("Разность между максимальным и средним значением: %d\n", difference);

    // Ожидание нажатия клавиши
    getch();
    return 0;
} 

//Задача3
#include "stdio.h"
#include "conio.h"
#include "math.h"

// Функция для проверки, является ли число простым
bool isPrime(int n) {
    if (n <= 1) return false;
    if (n <= 3) return true;
    if (n % 2 == 0 || n % 3 == 0) return false;
    for (int i = 5; i * i <= n; i += 6) {
        if (n % i == 0 || n % (i + 2) == 0) return false;
    }
    return true;
}

int main() {
    // Перебор чисел от 200 до 500
    printf("Числа из промежутка от 200 до 500 с ровно шестью делителями:\n");
    for (int n = 200; n <= 500; n++) {
        int count = 0;
        for (int i = 1; i <= sqrt(n); i++) {
            if (n % i == 0) {
                if (n / i == i) // i является квадратным корнем из n
                    count += 1;
                else
                    count += 2; // пара делителей (i и n/i)
            }
        }
        if (count == 6) {
            printf("%d\n", n);
        }
    }

    // Ожидание нажатия клавиши
    getch();
    return 0;
} 

//Задача4
#include "stdio.h"
#include "conio.h"

void rearrangeArray(int arr[], int n) {
    int count = 0;  // Счетчик для подсчета нулевых элементов

    // Перемещение всех нулевых элементов в начало массива
    for (int i = 0; i < n; i++) {
        if (arr[i] == 0) {
            arr[count++] = 0;
        }
    }

    // Заполнение оставшихся элементов в массиве ненулевыми значениями
    for (int i = 0; i < n; i++) {
        if (arr[i] != 0) {
            arr[count++] = arr[i];
        }
    }
}

int main() {
    int n;

    // Ввод размера массива
    printf("Введите размер массива: ");
    scanf("%d", &n);

    int arr[n];

    // Ввод элементов массива
    printf("Введите элементы массива:\n");
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }

    // Преобразование массива
    rearrangeArray(arr, n);

    // Вывод преобразованного массива
    printf("Преобразованный массив:\n");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }

    // Ожидание нажатия клавиши
    getch();
    return 0;
}
