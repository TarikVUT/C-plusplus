# VUT SCP-C++
### Exercis 3

***Napište třídu pro reprezentaci komplexní čísla, která bude zapouzdřovat následující metody:***\
–Konstruktor se dvěma parametry pro zadání reálné a imaginární části\
–Nastavení hodnoty reálné částivoidsetr(doubler)\
–Nastavení hodnoty imaginární částivoidseti(doublei)\
–Vracení hodnoty reálné částidoublegetr(void)\
–Vracení hodnoty imaginární částidoublegeti(void)\
–Výpočet modulu KČdoublemodul(void)\
–Výpočet fáze KČdoublefaze(void)\
–Funkce pro výpis komplexního čísla na konzolivoidtisk(void)\
–Implementované funkce vyzkoušejte v programu. Vytvořte statickou i dynamickou instanci objektu komplexního čísla.\

### Code in C++
```C++
#include <iostream>
#include <math.h>

using namespace std;

class Complex
{
	double real;
	double image;

public:
	Complex(double r, double i)
	{
		real = r;
		image = i;

	}
	void setr(double r)
	{
		real = r;
	}
	void seti(double i)
	{
		image = i;
	}
	double getr()
	{
		return real;
	}
	double geti()
	{
		return image;
	}
	double modul()
	{
		return sqrt(real * real + image * image);
	}
	double faze()
	{
		return acos(real / modul());
	}
	void tisk()
	{
		cout << "Your Comlex number = " << getr() << " + " << geti() << "i" << endl;

	}
	void All_in_one()
	{
		tisk();
		cout << "Modul = " << modul() << endl;
		cout << "Faze  = " << faze() << endl;
	}

};



int main()
{		//Static object 
	Complex number1(10, 20);
	number1.All_in_one();

		// Dynamic object
	Complex* number2;
	number2 = new Complex(15,25);
	number2->All_in_one();

	return 0;
}
```
![Code after running](./images/image 1.png)
