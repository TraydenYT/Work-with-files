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



	cout << "�������� ����� ������ ��� ����� ?" << endl; // �������� ���� � ������� ������
	cout << "1 - �����" << endl;
	cout << "2 - ������" << endl;
	cout << "3 - ��� �������" << endl;
	cout << "��� �����: ";
	cin >> c;

	if (c >= 4) // �������� ���� ������������ ����� �������� ����� 1 ��� 2
	{
		cout << "�� ����� ������������ ��������" << endl;
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
		if (!fs.is_open()) // ��������,������� �� ������� ���� ��� ���.
			cout << "���� �� ������";
		else
		{
			cout << fs.rdbuf();
			fs.close();
		}
	}
	cout << endl << endl << "��� �������� ������� �� ����� �������" << endl;
	system("pause");
	return 0;
}