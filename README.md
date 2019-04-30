#Work-with-files
#include <iostream>
#include <string>
#include <fstream>
#include <Windows.h>

#define sp /n

using namespace std;

int main()
{
	setlocale(LC_ALL, "Russian");


	int c;
	string text = "lenta.txt";
	string text2 = "gazeta.txt";
	string text3 = "ria.txt";
	ifstream fs;
	//fs.open(text,ifstream::in);



	cout << "Выберите какая статья вам нужна ?" << endl; // Выбираем файл с текстом внутри
	cout << "1 - Лента" << endl;
	cout << "2 - Газета" << endl;
	cout << "3 - Рио новости" << endl;
	cout << "Ваш выбор: ";
	cin >> c;

	if (c >= 4) // Проверка если пользователь нажал значение кроме 1 или 2
	{
		cout << "Вы ввели неправильное значение" << endl;
	}
	else
	{
		string fname;

		if (c == 1)
		{
			fname = text;
		}
		if (c == 2)
		{
			fname = text2;
		}
		if (c == 3)
		{
			fname = text3;
		}
		fs.open(fname, ifstream::in);
		if (!fs.is_open()) // Проверка,удалось ли открыть файл или нет.
			cout << "Файл не открыт";
		else
		{
			cout << fs.rdbuf();
			fs.close();
		}
	}
	cout << endl << endl << "Для закрытия нажмите на любую клавишу" << endl;
	system("pause");
	return 0;
}