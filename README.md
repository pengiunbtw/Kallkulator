using System;

namespace CalculatorApp
{
    class Program
    {
        static void Main(string[] args)
        {
            double num1, num2, result;
            string operation;

            Console.WriteLine("=== Консольный калькулятор ===");

            while (true)
            {
                try
                {
                    Console.Write("Введите первое число (или 'q' для выхода): ");
                    string input = Console.ReadLine();
                    if (input.ToLower() == "q") break;
                    num1 = Convert.ToDouble(input);

                    Console.Write("Введите второе число (или 'q' для выхода): ");
                    input = Console.ReadLine();
                    if (input.ToLower() == "q") break;
                    num2 = Convert.ToDouble(input);

                    Console.Write("Выберите операцию (+, -, *, /): ");
                    operation = Console.ReadLine();

                    switch (operation)
                    {
                        case "+":
                            result = num1 + num2;
                            Console.WriteLine($"Результат: {num1} + {num2} = {result}");
                            break;
                        case "-":
                            result = num1 - num2;
                            Console.WriteLine($"Результат: {num1} - {num2} = {result}");
                            break;
                        case "*":
                            result = num1 * num2;
                            Console.WriteLine($"Результат: {num1} * {num2} = {result}");
                            break;
                        case "/":
                            if (num2 == 0)
                            {
                                Console.WriteLine("Ошибка! Деление на ноль невозможно.");
                            }
                            else
                            {
                                result = num1 / num2;
                                Console.WriteLine($"Результат: {num1} / {num2} = {result}");
                            }
                            break;
                        default:
                            Console.WriteLine("Некорректная операция. Попробуйте снова.");
                            break;
                    }
                }
                catch (FormatException)
                {
                    Console.WriteLine("Некорректный ввод чисел. Попробуйте снова.");
                }

                Console.WriteLine(); 
            }

            Console.WriteLine("Программа завершена. Нажмите любую клавишу для выхода.");
            Console.ReadKey();
        }
    }
}
