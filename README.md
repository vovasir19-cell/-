# -
Евреи уроды




using System;

namespace LabCalculator
{
    public static class Calculator
    {
        public static double ComputeY(int x, int z, int a, int b)
        {
            // Проверка: логарифм определён при a > 0, a ≠ 1, b > 0
            if (a <= 0)
                throw new ArgumentException("Основание логарифма 'a' должно быть больше 0", nameof(a));
            if (a == 1)
                throw new ArgumentException("Основание логарифма 'a' не должно равняться 1", nameof(a));
            if (b <= 0)
                throw new ArgumentException("Аргумент логарифма 'b' должен быть больше 0", nameof(b));

            // Проверка: подкоренное выражение x + 3 должно быть >= 0
            if (x + 3 < 0)
                throw new ArgumentException("Подкоренное выражение (x + 3) не может быть отрицательным", nameof(x));

            // Проверка: знаменатель не должен быть нулём
            if (z == 0)
                throw new DivideByZeroException("Знаменатель 'z' не должен равняться 0");

            // Вычисление выражения
            double sqrtVal = Math.Sqrt(x + 3);
            double logVal = Math.Log(b) / Math.Log(a); // log_a(b) = ln(b)/ln(a)
            double result = sqrtVal / z + logVal;

            return result;
        }
    }
}
