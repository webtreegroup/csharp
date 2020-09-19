## Объявление переменных (названия регистрозависимые)
**тип имя_переменной;** 
```
string name;
string Name;
name = "Tom";
string name = "Tom";
```

## Типы данных
**bool**: хранит значение true или false (логические литералы). Представлен системным типом System.Boolean
```
bool alive = true;
bool isDead = false;
```
**byte**: хранит целое число от 0 до 255 и занимает 1 байт. Представлен системным типом System.Byte
```
byte bit1 = 1;
byte bit2 = 102;
```
**sbyte**: хранит целое число от -128 до 127 и занимает 1 байт. Представлен системным типом System.SByte
```
sbyte bit1 = -101;
sbyte bit2 = 102;
```
**short**: хранит целое число от -32768 до 32767 и занимает 2 байта. Представлен системным типом System.Int16
```
short n1 = 1;
short n2 = 102;
```
**ushort**: хранит целое число от 0 до 65535 и занимает 2 байта. Представлен системным типом System.UInt16
```
ushort n1 = 1;
ushort n2 = 102;
```
**int**: хранит целое число от -2147483648 до 2147483647 и занимает 4 байта. Представлен системным типом System.Int32. Все целочисленные литералы по умолчанию представляют значения типа int:
```
int a = 10;
int b = 0b101;  // бинарная форма b =5
int c = 0xFF;   // шестнадцатеричная форма c = 255
```
**uint**: хранит целое число от 0 до 4294967295 и занимает 4 байта. Представлен системным типом System.UInt32
```
uint a = 10;
uint b = 0b101;
uint c = 0xFF;
```
**long**: хранит целое число от –9 223 372 036 854 775 808 до 9 223 372 036 854 775 807 и занимает 8 байт. Представлен системным типом System.Int64
```
long a = -10;
long b = 0b101;
long c = 0xFF;
```
**ulong**: хранит целое число от 0 до 18 446 744 073 709 551 615 и занимает 8 байт. Представлен системным типом System.UInt64
```
ulong a = 10;
ulong b = 0b101;
ulong c = 0xFF;
```
**float**: хранит число с плавающей точкой от -3.4*1038 до 3.4*1038 и занимает 4 байта. Представлен системным типом System.Single  
**double**: хранит число с плавающей точкой от ±5.0*10-324 до ±1.7*10308 и занимает 8 байта. Представлен системным типом System.Double  
**decimal**: хранит десятичное дробное число. Если употребляется без десятичной запятой, имеет значение от ±1.0*10-28 до ±7.9228*1028, может хранить 28 знаков после запятой и занимает 16 байт. Представлен системным типом System.Decimal  
**char**:
```
char a = 'A';
char b = '\x5A';
char c = '\u0420';
```
**string**: хранит набор символов Unicode. Представлен системным типом System.String. Этому типу соответствуют символьные литералы.
```
string hello = "Hello";
string word = "world";
```
**object**: может хранить значение любого типа данных и занимает 4 байта на 32-разрядной платформе и 8 байт на 64-разрядной платформе. Представлен системным типом System.Object, который является базовым для всех других типов и классов .NET.
```
object a = 22;
object b = 3.14;
object c = "hello code";
```
**enum или перечисление**. Перечисления представляют набор логически связанных констант. Тип перечисления - он обязательно должен представлять целочисленный тип (byte, int, short, long), по умолчанию используется тип int.
```
enum Days
{
    Monday,
    Tuesday,
    Wednesday,
    Thursday,
    Friday,
    Saturday,
    Sunday
}

enum Time : byte
{
    Morning,
    Afternoon,
    Evening,
    Night
}
```
**Неявная типизация**: компиляции компилятор сам выводит тип данных исходя из присвоенного значения
```
var hello = "Hell to World";
var c = 20;
```
## Консольный вывод
```
Console.WriteLine("Добро пожаловать в C#!");

string name = "Tom";
int age = 34;
double height = 1.7;
Console.WriteLine($"Имя: {name}  Возраст: {age}  Рост: {height}м");
Console.WriteLine("Имя: {0}  Возраст: {2}  Рост: {1}м", name, height, age);
```
## Консольный ввод
```
Console.Write("Введите свое имя: ");
string name = Console.ReadLine();
Console.WriteLine($"Привет {name}");
```
Однако минусом этого метода является то, что Console.ReadLine считывает информацию именно в виде строки.
```
int age = Convert.ToInt32(Console.ReadLine()); // (преобразует к типу int)
double height = Convert.ToDouble(Console.ReadLine()); // (преобразует к типу double)
decimal salary = Convert.ToDecimal(Console.ReadLine()); // (преобразует к типу decimal)
```
## Преобразования базовых типов данных
Тип / В какие типы безопасно преобразуется  
byte -> short, ushort, int, uint, long, ulong, float, double, decimal  
sbyte -> short, int, long, float, double, decimal  
short -> int, long, float, double, decimal  
ushort -> int, uint, long, ulong, float, double, decimal  
int -> long, float, double, decimal  
uint -> long, ulong, float, double, decimal  
long -> float, double, decimal  
ulong -> float, double, decimal  
float -> double  
char -> ushort, int, uint, long, ulong, float, double, decimal  
## Условные конструкции
**Конструкция if/else**
```
int num1 = 8;
int num2 = 6;
if(num1 > num2)
{
    Console.WriteLine($"Число {num1} больше числа {num2}");
}
else
{
    Console.WriteLine($"Число {num1} меньше числа {num2}");
}
```
**Конструкция switch**
```
Console.WriteLine("Нажмите Y или N");
string selection = Console.ReadLine();
switch (selection)
{
    case "Y":
        Console.WriteLine("Вы нажали букву Y");
        break;
    case "N":
        Console.WriteLine("Вы нажали букву N");
        break;
    default:
        Console.WriteLine("Вы нажали неизвестную букву");
        break;
}
```
**Тернарная операция**
```
int x=3;
int y=2;
Console.WriteLine("Нажмите + или -");
string selection = Console.ReadLine();
 
int z = selection=="+"? (x+y) : (x-y);
Console.WriteLine(z);
```
## Циклы
```
for (int i = 0; i < 9; i++)
{
    Console.WriteLine($"Квадрат числа {i} равен {i*i}");
}

int i = 6;
do
{
    Console.WriteLine(i);
    i--;
}
while (i > 0);

int i = 6;
while (i > 0)
{
    Console.WriteLine(i);
    i--;
}

for (int i = 0; i < 9; i++)
{
    if (i == 5)
        break;
    Console.WriteLine(i);
}

for (int i = 0; i < 9; i++)
{
    if (i == 5)
        continue;
    Console.WriteLine(i);
}

int[] numbers = new int[] { 1, 2, 3, 4, 5 };
foreach (int i in numbers)
{
    Console.WriteLine(i);
}
```
## Массивы
**тип_переменной[] название_массива;**
```
int[] numbers;
int[] nums = new int[4]; // длина массива - 4
int[] nums2 = new int[4] { 1, 2, 3, 5 }; 
int[] nums3 = new int[] { 1, 2, 3, 5 }; 
int[] nums4 = new[] { 1, 2, 3, 5 }; 
int[] nums5 = { 1, 2, 3, 5 };

int[] nums = new int[4];
nums[0] = 1;
nums[1] = 2;
nums[2] = 3;
nums[3] = 5;
Console.WriteLine(nums[3]);  // 5
```
**Многомерные массивы**
```
int[] nums1 = new int[] { 0, 1, 2, 3, 4, 5 }; // Одномерный массив nums1 
int[,] nums2 = { { 0, 1, 2 }, { 3, 4, 5 } }; // Двухмерный массив nums2
```
Все возможные способы определения двухмерных массивов:
```
int[,] nums1;
int[,] nums2 = new int[2, 3];
int[,] nums3 = new int[2, 3] { { 0, 1, 2 }, { 3, 4, 5 } };
int[,] nums4 = new int[,] { { 0, 1, 2 }, { 3, 4, 5 } };
int[,] nums5 = new [,]{ { 0, 1, 2 }, { 3, 4, 5 } };
int[,] nums6 = { { 0, 1, 2 }, { 3, 4, 5 } };
```
**Массив массивов**  
Здесь две группы квадратных скобок указывают, что это массив массивов, то есть такой массив, который в свою очередь содержит в себе другие массивы. Причем длина массива указывается только в первых квадратных скобках, все последующие квадратные скобки должны быть пусты: new int[3][]. В данном случае у нас массив nums содержит три массива.
```
int[][] nums = new int[3][];
nums[0] = new int[2] { 1, 2 };          // выделяем память для первого подмассива
nums[1] = new int[3] { 1, 2, 3 };       // выделяем память для второго подмассива
nums[2] = new int[5] { 1, 2, 3, 4, 5 }; // выделяем память для третьего подмассива
```
**Основные понятия массивов**  
- Ранг (rank): количество измерений массива  
- Длина измерения (dimension length): длина отдельного измерения массива  
- Длина массива (array length): количество всех элементов массива  
```
int[,] numbers = new int[3, 4];
```
Массив numbers двухмерный, то есть он имеет два измерения, поэому его ранг равен 2. Длина первого измерения - 3, длина второго измерения - 4. Длина массива (то есть общее количество элементов) - 12.
## Методы
**Общее определение методов выглядит следующим образом:**
```
[модификаторы] тип_возвращаемого_значения название_метода ([параметры])
{
    // тело метода
}

название_метода (значения_для_параметров_метода);
```
```
namespace HelloApp
{
    class Program
    {
        static void Main(string[] args)
        {
            SayHello();
            SayGoodbye();
            
            int result = Sum(10, 15);
            Console.WriteLine(result);  // 25
 
            Console.ReadKey();  
        }
 
        static void SayHello()
        {
            Console.WriteLine("Hello");
        }
        static void SayGoodbye()
        {
            Console.WriteLine("GoodBye");
        }
        static int Sum(int x, int y)
        {
            return x + y;
        }
    }
}
```
**Сокращенная запись методов**. Если метод в качестве тела определяет только одну инструкцию, то мы можем сократить определение метода.
```
static string GetHello()
{
    return "hello";
}

static void SayHello() => Console.WriteLine("Hello");
```
**Необязательные параметры**, значение по умолчанию.
```
static int OptionalParam(int x, int y, int z=5, int s=4)
{
    return x + y + z + s;
}
```
**Именованные параметры**, выше при вызове методов значения для параметров передавались в порядке объявления этих параметров в методе. Но мы можем нарушить подобный порядок, используя именованные параметры.
```
static int OptionalParam(int x, int y, int z=5, int s=4)
{
    return x + y + z + s;
}
static void Main(string[] args)
{
    OptionalParam(x:2, y:3);
     
    //Необязательный параметр z использует значение по умолчанию
    OptionalParam(y:2, x:3, s:10);
 
    Console.ReadKey();
}
```
## Передача параметров по ссылке и значению. Выходные параметры.
**Передача параметров по значению**
```
class Program
{
    static void Main(string[] args)
    {
        Sum(10, 15);        // параметры передаются по значению
        Console.ReadKey();
    }
    static int Sum(int x, int y)
    {
        return x + y;
    }
}
```
**Передача параметров по ссылке и модификатор ref**
```
static void Main(string[] args)
{
    int x = 10;
    int y = 15;
    Addition(ref x, y); // вызов метода
    Console.WriteLine(x);   // 25
 
    Console.ReadLine();
}
// параметр x передается по ссылке
static void Addition(ref int x, int y)
{
    x += y;
}
```
**Выходные параметры. Модификатор out**  
Здесь результат возвращается не через оператор return, а через выходной параметр, мы можем вернуть из метода не один вариант, а несколько. По сути, как и в случае с ключевым словом ref, ключевое слово out применяется для передачи аргументов по ссылке. Однако в отличие от ref для переменных, которые передаются с ключевым словам out, не требуется инициализация. И кроме того, вызываемый метод должен обязательно присвоить им значение.
```
static void Sum(int x, int y, out int a)
{
    a = x + y;
}

static void Main(string[] args)
{
    int x = 10;
     
    int z;
     
    Sum(x, 15, out z);
     
    Console.WriteLine(z);
 
    Console.ReadKey();
}

static void Main(string[] args)
{
    int x = 10;
    int area;
    int perimetr;
    GetData(x, 15, out area, out perimetr);
    Console.WriteLine("Площадь : " + area);
    Console.WriteLine("Периметр : " + perimetr);
 
    Console.ReadKey();
}
static void GetData(int x, int y, out int area, out int perim)
{
    area= x * y;
    perim= (x + y)*2; 
}
```
**Входные параметры. Модификатор in**  
Модификатор in указывает, что данный параметр будет передаваться в метод по ссылке, однако внутри метода его значение параметра нельзя будет изменить.
```
static void GetData(in int x, int y, out int area, out int perim)
{
    // x = x + 10; нельзя изменить значение параметра x, т.к. он с модификатором in
    y = y + 10;
    area = x * y;
    perim = (x + y) * 2;
}
```
## Ключевое слово params  
Используя ключевое слово params, мы можем передавать неопределенное количество параметров.
```
static void Main(string[] args)
{
    MethodWithParams(3, 2);
}

public static void MethodWithParams(params int[] val)
{
    Console.WriteLine(val[1]);
}
```
## Область видимости (контекст) переменных
**Контекст класса**. Переменные, определенные на уровне класса, доступны в любом методе этого класса.  
**Контекст метода**. Переменные, определенные на уровне метода, являются локальными и доступны только в рамках данного метода. В других методах они недоступны.  
**Контекст блока кода**. Переменные, определенные на уровне блока кода, также являются локальными и доступны только в рамках данного блока. Вне своего блока кода они не доступны.  
```
class Program // начало контекста класса
{
    static int a = 9; // переменная уровня класса
     
    static void Main(string[] args) // начало контекста метода Main
    {
        int b = a - 1; // переменная уровня метода
 
        { // начало контекста блока кода
             
            int c = b - 1; // переменная уровня блока кода
 
        }  // конец контекста блока кода, переменная с уничтожается
 
        //так нельзя, переменная c определена в блоке кода
        //Console.WriteLine(c);
 
        //так нельзя, переменная d определена в другом методе
        //Console.WriteLine(d);
 
        Console.Read();
 
    } // конец контекста метода Main, переменная b уничтожается
 
    void Display() // начало контекста метода Display
    {
        // переменная a определена в контексте класса, поэтому доступна
        int d = a + 1;
 
    } // конец конекста метода Display, переменная d уничтожается
 
} // конец контекста класса, переменная a уничтожается
```
