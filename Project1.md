#include <tchar.h>
#include <iostream>
#include <string>
#include <ctime>
using namespace std;

int _tmain(int argc, wchar_t argv[]) // функция для работы со всеми символами юникода и нет
{
	srand(time(NULL)); // генерация псевдослучайных чисел основывающаяся на точном времени даты
	setlocale(LC_ALL, "Russian"); // поддержка работы с русскими символами
	int arr[30];
	for (int i = 0; i < 30; i++)
	{
		arr[i] = rand() % 2000 - 1000;
		cout << " " << arr[i]; // заполнение и вывод элементов массива со случайными числами от -1000 до 1000
	}
	cout << endl;
	int sum = 0;
	int c = 0;
	int a = 0;
	for (int j = 0; j<30; j++)
	{
		if (arr[j] % 5 == 0) // проверка числа в элементе массива на кратность 5
		{ 
			sum = sum + arr[j]; 
			c = c + 1; 
		}
	}
	a = sum / c;
	cout << "В массиве " << c << " элементов, заканчивающихся на 5";
	cout << endl;
	cout << "Среднее арифметическое всех элементов массива, заканчивающихся на 5 равно " << a;
	cin.get(); // завершение работы с потоками
	return 0;
}