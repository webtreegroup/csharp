- [Объявление переменных (названия регистрозависимые)](https://github.com/webtreegroup/csharp/blob/master/README.md#%D1%82%D0%B8%D0%BF%D1%8B-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85---%D1%8D%D0%BB%D0%B5%D0%BC%D0%B5%D0%BD%D1%82%D0%B0%D1%80%D0%BD%D1%8B%D0%B5-%D1%82%D0%B8%D0%BF%D1%8B-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85)
- [Типы данных - элементарные типы данных](https://github.com/webtreegroup/csharp/blob/master/README.md#%D1%82%D0%B8%D0%BF%D1%8B-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85---%D1%8D%D0%BB%D0%B5%D0%BC%D0%B5%D0%BD%D1%82%D0%B0%D1%80%D0%BD%D1%8B%D0%B5-%D1%82%D0%B8%D0%BF%D1%8B-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85)

## Объявление переменных (названия регистрозависимые)
**тип имя_переменной;** 
```
string name;
string Name;
name = "Tom";
string name = "Tom";
```
## Типы данных - элементарные типы данных
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
## Типы данных - сложные типы данных
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
**Кортежи - tuple**  
Набор значений. В дальнейшем мы можем обращаться к каждому из этих значений через поля с названиями Item[порядковый_номер_поля_в_кортеже].
```
static void Main(string[] args)
{
    var tuple = (5, 10); // В данном случае тип определяется неявно.
    (int, int) tuple2 = (5, 10); // Тип определяется явно.    
    (string, int, double) tuple3 = ("Tom", 25, 81.23);
    
    Console.WriteLine(tuple.Item1); // 5
    Console.WriteLine(tuple.Item2); // 10
    tuple.Item1 += 26;
    Console.WriteLine(tuple.Item1); // 31
    Console.Read();
    
    var tuple4 = (count:5, sum:10); // Мы также можем дать названия полям кортежа.
    Console.WriteLine(tuple4.count); // 5
    Console.WriteLine(tuple4.sum); // 10
    
    var (name, age) = ("Tom", 23); // Мы даже можем не использовать переменную для определения всего кортежа, а использовать отдельные переменные для его полей.
    
    var tuple6 = GetValues();
    Console.WriteLine(tuple6.Item1); // 1
    Console.WriteLine(tuple6.Item2); // 3
     
    Console.Read();
}

private static (int, int) GetValues()
{
    var result = (1, 3);
    return result;
}
```
**Структуры**    
Наряду с классами структуры представляют еще один способ создания собственных типов данных в C#. Более того многие примитивные типы, например, int, double и т.д., по сути являются структурами.
```
struct User
{
    public string name;
    public int age;
 
    public void DisplayInfo()
    {
        Console.WriteLine($"Name: {name}  Age: {age}");
    }
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
## Преобразования типов данных
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

**Восходящие преобразования. Upcasting**. Преобразование от производного к базовому.
```
class Person
{
    public string Name { get; set; }
    public Person(string name)
    {
        Name = name;
    }
    public void Display()
    {
        Console.WriteLine($"Person {Name}");
    }
}
 
class Employee : Person
{
    public string Company { get; set; }
    public Employee(string name, string company) : base(name)
    {
        Company = company;
    }
}

static void Main(string[] args)
{
    Employee employee = new Employee("Tom", "Microsoft");
    Person person = employee;   // преобразование от Employee к Person, будет доступна только часть общего с Employee функционала
 
    Console.WriteLine(person.Name);
    Console.ReadKey();
}
```
**Нисходящие преобразования. Downcasting**. Преобразование от базового к производному.
```
Employee employee = new Employee("Tom", "Microsoft");
Person person = employee;   // преобразование от Employee к Person, будет доступна только часть общего с Employee функционала
 
//Employee employee2 = person;    // так нельзя, нужно явное преобразование
Employee employee2 = (Employee)person;  // преобразование от Person к Employee
```
**Еще примеры**
```
// Объект Employee также представляет тип object
object obj = new Employee("Bill", "Microsoft");
 
// преобразование к типу Person для вызова метода Display
((Person)obj).Display();
// либо так
// ((Employee)obj).Display();
 
// преобразование к типу Employee, чтобы получить свойство Company
string comp = ((Employee)obj).Company;
```
**Способы преобразований**
```
// Ключевое слово as, в случае неудачного преобразования выражение будет содержать значение null
Person person = new Person("Tom");
Employee emp = person as Employee; 
if (emp == null)
{
    Console.WriteLine("Преобразование прошло неудачно");
}
else
{
    Console.WriteLine(emp.Company);
}

// Отлавливание исключения InvalidCastException, которое возникнет в результате преобразования

Person person = new Person("Tom");
try 
{
    Employee emp = (Employee)person;
    Console.WriteLine(emp.Company);
}
catch (InvalidCastException ex)
{
    Console.WriteLine(ex.Message);
}

// Третий способ заключается в проверке допустимости преобразования с помощью ключевого слова is
Person person = new Person("Tom");
if(person is Employee)
{
    Employee emp = (Employee)person;
    Console.WriteLine(emp.Company);
}
else
{
    Console.WriteLine("Преобразование не допустимо");
}
```

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
## Классы и объекты
По сути класс представляет новый тип, который определяется пользователем. Класс определяется с помощью ключевого слова сlass:
```
class Person
{
 
}
```
Класс можно определять внутри пространства имен, вне пространства имен, внутри другого класса. Как правило, классы помещаются в отдельные файлы.
```
using System;
 
namespace HelloApp
{
    class Person
    {
         
    }
    class Program
    {
        static void Main(string[] args)
        {
             
        }
    }
}
```
Вся функциональность класса представлена его членами - полями (полями называются переменные класса), свойствами, методами, событиями.
```
using System;
 
namespace HelloApp
{
    class Person
    {
        public string name; // имя - поле
        public int age = 18; // возраст - поле
 
        public void GetInfo() // метод
        {
            Console.WriteLine($"Имя: {name}  Возраст: {age}");
        }
    }
    class Program
    {
        static void Main(string[] args)
        {
            Person tom; // null по умолчанию, т.к. не указывает ни на какой объект
        }
    }
}
```
**Конструкторы**  
Конструкторы вызываются при создании нового объекта данного класса. Конструкторы выполняют инициализацию объекта. Если в классе не определено ни одного конструктора, то для этого класса автоматически создается конструктор по умолчанию. Такой конструктор не имеет параметров и не имеет тела.
```
class Person
{
    public string name; // имя
    public int age;     // возраст
 
    public void GetInfo()
    {
        Console.WriteLine($"Имя: {name}  Возраст: {age}");
    }
}
class Program
{
    static void Main(string[] args)
    {
        Person tom = new Person();
        tom.GetInfo();      // Имя: Возраст: 0
 
        tom.name = "Tom";
        tom.age = 34;
        tom.GetInfo();  // Имя: Tom Возраст: 34
        Console.ReadKey();
    }
}

//------------------------

class Person
{
    public string name;
    public int age;
 
    public Person() { name = "Неизвестно"; age = 18; }      // 1 конструктор
     
    public Person(string n) { name = n; age = 18; }         // 2 конструктор
     
    public Person(string n, int a) { name = n; age = a; }   // 3 конструктор
     
    public void GetInfo()
    {
        Console.WriteLine($"Имя: {name}  Возраст: {age}");
    }
}
static void Main(string[] args)
{
    Person tom = new Person();          // вызов 1-ого конструктора без параметров
    Person bob = new Person("Bob");     //вызов 2-ого конструктора с одним параметром
    Person sam = new Person("Sam", 25); // вызов 3-его конструктора с двумя параметрами
     
     
    bob.GetInfo();          // Имя: Bob  Возраст: 18
    tom.GetInfo();          // Имя: Неизвестно  Возраст: 18
    sam.GetInfo();          // Имя: Sam  Возраст: 25
}
```
**Статический конструктор**  
```
class User
{
    static User() // не принимает параметров, вызывается при самом первом создании объекта
    {
        Console.WriteLine("Создан первый пользователь");
    }
}
class Program
{
    static void Main(string[] args)
    {
        User user1 = new User(); // здесь сработает статический конструктор
        User user2 = new User();
         
        Console.Read();
    }
}
```
**Ключевое слово this**, представляет ссылку на текущий экземпляр класс.
```
lass Person
{
    public string name;
    public int age;
 
    public Person() : this("Неизвестно") // первый конструктор вызывает второй
    {
    }
    public Person(string name) : this(name, 18) // второй конструктор вызывает третий
    {
    }
    public Person(string name, int age)
    {
        this.name = name;
        this.age = age;
    }
    public void GetInfo()
    {
        Console.WriteLine($"Имя: {name}  Возраст: {age}");
    }
}
```
И чтобы разграничить параметры и поля класса, к полям класса обращение идет через ключевое слово this. Так, в выражении this.name = name; первая часть this.name означает, что name - это поле текущего класса, а не название параметра name. Если бы у нас параметры и поля назывались по-разному, то использовать слово this было бы необязательно. Также через ключевое слово this можно обращаться к любому полю или методу.  
**Инициализаторы объектов**  
С помощью инициализатора мы можем установить значения только доступных из внешнего кода полей и свойств объекта. Инициализатор выполняется после конструктора
```
Person tom = new Person { name = "Tom", age=31 };
tom.GetInfo();          // Имя: Tom  Возраст: 31
```
## Типы значений и ссылочные типы
**Типы значений**:
- Целочисленные типы (byte, sbyte, short, ushort, int, uint, long, ulong)
- Типы с плавающей запятой (float, double)
- Тип decimal
- Тип bool
- Тип char
- Перечисления enum
- Структуры (struct)

**Ссылочные типы**:
- Тип object
- Тип string
- Классы (class)
- Интерфейсы (interface)
- Делегаты (delegate)

В .NET память делится на два типа: **стек и куча (heap)**.  
Параметры и переменные метода, которые представляют типы значений, размещают свое значение в стеке. Физически стек - это некоторая область памяти в адресном пространстве.  
Ссылочные типы хранятся в куче или хипе, которую можно представить как неупорядоченный набор разнородных объектов. Физически это остальная часть памяти, которая доступна процессу. При создании объекта ссылочного типа в стеке помещается ссылка на адрес в куче (хипе). Когда объект ссылочного типа перестает использоваться, в дело вступает автоматический сборщик мусора.  

**Копирование значений**  
При присвоении данных объекту значимого типа он получает копию данных. При присвоении данных объекту ссылочного типа он получает не копию объекта, а ссылку на этот объект в хипе.

## Пространства имен, псевдонимы и статический импорт
```
namespace HelloApp // пространство имен, может иметь любое название, служит для группировки классов
{  
    class Program  
    {
        static void Main(string[] args) 
        {
        }
    }
}

// -------------------------

using System; // чтобы задействовать классы из других пространств имен, например из System
namespace HelloApp
{  
    class Program  
    {
        static void Main(string[] args) 
        {
            Console.WriteLine("hello"); // Console из ПИ System, без using было бы System.Console.WriteLine
        }
    }
}
```
**Псевдонимы**
```
using printer = System.Console;
class Program
{
    static void Main(string[] args)
    {
        printer.WriteLine("Hello from C#");
        printer.Read();
    }
}
```
**Статический импорт**  
Выражение using static подключает в программу все статические методы и свойства, а также константы. И после этого мы можем не указывать название класса при вызове метода.
```
using static System.Console;
namespace HelloApp
{
    class Program
    {
        static void Main(string[] args)
        {
            WriteLine("Hello from C# 8.0");
            Read();
        }
    }
}
```
## Модификаторы доступа  
Если для полей и методов не определен модификатор доступа, то по умолчанию для них применяется модификатор private  
Классы и структуры, объявленные без модификатора, по умолчанию имеют доступ internal  
Все классы и структуры, определенные напрямую в пространствах имен и не являющиеся вложенными в другие классы, могут иметь только модификаторы public или internal.  
- **public**: публичный, общедоступный класс или член класса. Такой член класса доступен из любого места в коде, а также из других программ и сборок.
- **private**: закрытый класс или член класса. Представляет полную противоположность модификатору public. Такой закрытый класс или член класса доступен только из кода в том же классе или контексте.
- **protected**: такой член класса доступен из любого места в текущем классе или в производных классах. При этом производные классы могут располагаться в других сборках.
- **internal**: класс и члены класса с подобным модификатором доступны из любого места кода в той же сборке, однако он недоступен для других программ и сборок (как в случае с модификатором public).
- **protected internal**: совмещает функционал двух модификаторов. Классы и члены класса с таким модификатором доступны из текущей сборки и из производных классов.
- **private protected**: такой член класса доступен из любого места в текущем классе или в производных классах, которые определены в той же сборке.

## Модификатор readonly  
```
class MathLib
{
    public readonly double K = 23;  // можно так инициализировать
 
    public MathLib(double _k)
    {
        K = _k; // поле для чтения может быть инициализировано или изменено в конструкторе после компиляции
    }
    public void ChangeField()
    {
        // так нельзя
        //K = 34;
    }
}
 
class Program
{
    static void Main(string[] args)
    {
        MathLib mathLib = new MathLib(3.8);
        Console.WriteLine(mathLib.K); // 3.8
 
        //mathLib.K = 7.6; // поле для чтения нельзя установить вне своего класса
        Console.ReadLine();
 
    }
}
```

## Модификатор static  
Статические поля, методы, свойства относятся ко всему классу (хранят состояние класса в целом, а не отдельного объекта) и для обращения к подобным членам класса необязательно создавать экземпляр класса.  

Таким образом, переменные и свойства, которые хранят состояние, общее для всех объектов класса, следует определять как статические. И также методы, которые определяют общее для всех объектов поведение, также следует объявлять как статические.  

Статические методы могут обращаться только к статическим членам класса.  
```
class Program
{
    static void Main(string[] args)
    {
        Console.WriteLine(Account.bonus);      // 100
        Account.bonus += 200;
         
        Account account1 = new Account(150);
        Console.WriteLine(account1.totalSum);   // 450
 
 
        Account account2 = new Account(1000);
        Console.WriteLine(account2.totalSum);   // 1300
        
        MethodWithParams(3, 2);
 
        Console.ReadKey();
    }
    
    public static void MethodWithParams(params int[] val)
    {
        Console.WriteLine(val[1]);
    }
}

class Account
{
    public static decimal bonus = 100; // На уровне памяти для статических полей будет создаваться участок в памяти (в куче), который будет общим для всех объектов класса.
    public decimal totalSum;
    public Account(decimal sum)
    {
        totalSum = sum + bonus; 
    }
}

// ---------------------------

static class Account // Классы объявляются с модификатором static и могут содержать только статические поля, свойства и методы
{
    private static decimal minSum = 100; // минимальная допустимая сумма для всех счетов
    public static decimal MinSum
    {
        get { return minSum; }
        set { if(value>0) minSum = value; }
    }
 
    // подсчет суммы на счете через определенный период по определенной ставке
    public static decimal GetSum(decimal sum, decimal rate, int period)
    {
        decimal result = sum;
        for (int i = 1; i <= period; i++)
            result = result + result * rate / 100;
        return result;
    }
}
```
## Модификатор virtual и override, sealed
```
class Person
{
    public string Name { get; set; }
    public Person(string name)
    {
        Name = name;
    }
    public virtual void Display() // Методы и свойства, которые мы хотим сделать доступными для переопределения помечаем как virtual
    {
        Console.WriteLine(Name);
    }
}

class Employee : Person
{
    public string Company { get; set; }
    public Employee(string name, string company)
        : base(name)
    {
        Company = company;
    }
 
    public override void Display() // Чтобы переопределить метод в классе-наследнике помечаем как override
    {
        Console.WriteLine($"{Name} работает в {Company}");
    }
}

static void Main(string[] args)
{
    Person p1 = new Person("Bill");
    p1.Display(); // вызов метода Display из класса Person
 
    Employee p2 = new Employee("Tom", "Microsoft");
    p2.Display(); // вызов метода Display из класса Employee
 
    Console.ReadKey();
}

// ------------------------

class Employee : Person
{
    public string Company { get; set; }
  
    public Employee(string name, string company)
                : base(name)
    {
        Company = company;
    }
 
    public override sealed void Display() // Запрет переопределения методов у наследников класса Employee
    {
        Console.WriteLine($"{Name} работает в {Company}");
    }
}
```
## Модификатор new (shadowing / hiding)
```
class Person
{
    public string FirstName { get; set; }
    public string LastName { get; set; }
    public Person(string firstName, string lastName)
    {
        FirstName = firstName;
        LastName = lastName;
    }
 
    public void Display()
    {
        Console.WriteLine($"{FirstName} {LastName}");
    }
}
 
class Employee : Person
{
    public string Company { get; set; }
    public Employee(string firstName, string lastName, string company)
            : base(firstName, lastName)
    {
        Company = company;
    }
    public new void Display() // Фактически сокрытие представляет определение в классе-наследнике метода или свойства (а также переменных и констант), которые соответствует по имени и набору параметров методу или свойству базового класса.
    {
        Console.WriteLine($"{FirstName} {LastName} работает в {Company}");
    }
}

// ---------------------

class ExampleBase
{
    public readonly int x = 10;
    public const int G = 5;
}
class ExampleDerived : ExampleBase
{
    public new readonly int x = 20;
    public new const int G = 15;
}
```

## Модификатор abstract
Абстрактный класс похож на обычный класс, за тем исключением, что мы не можем использовать конструктор абстрактного класса для создания его объекта.
```
abstract class Person // Общую функциональность лучше вынести в какой-то отдельный класс, например, Person, который описывает человека.
{
    public string Name { get; set; }
 
    public Person(string name) // конструктор класса Person не вызывается напрямую, тем не менее производные классы Client и Employee могут обращаться к нему
    {
        Name = name;
    }
 
    public void Display()
    {
        Console.WriteLine(Name);
    }
}
 
class Client : Person
{
    public int Sum { get; set; }    // сумма на счету
 
    public Client(string name, int sum)
        : base(name)
    {
        Sum = sum;
    }
}
 
class Employee : Person
{
    public string Position { get; set; } // должность
 
    public Employee(string name, string position) 
        : base(name)
    {
            Position = position;
    }
}
```
**Абстрактные члены классов** (Методы, Свойства, Индексаторы, События).  
Не имеют никакого функционала, но производный класс обязан переопределить и реализовать все абстрактные методы и свойства, которые имеются в базовом абстрактном классе. В случае с виртуальными методами мы говорим, что **класс-наследник наследует реализацию**, то в случае с абстрактными методами **наследуется интерфейс**, представленный этими абстрактными методами.
```
abstract class Person
{
    public string Name { get; set; }
 
    public Person(string name)
    {
        Name = name;
    }
 
    public abstract void Display();
}
 
class Client : Person
{
    public int Sum { get; set; }    // сумма на счету
 
    public Client(string name, int sum)
        : base(name)
    {
        Sum = sum;
    }
    public override void Display()
    {
        Console.WriteLine($"{Name} имеет счет на сумму {Sum}");
    }
}
 
class Employee : Person
{
    public string Position { get; set; } // должность
 
    public Employee(string name, string position) 
        : base(name)
    {
        Position = position;
    }
 
    public override void Display()
    {
        Console.WriteLine($"{Position} {Name}");
    }
}
```

## Константы
```
class MathLib
{
    public const double PI=3.141;
}
 
class Program
{
    static void Main(string[] args)
    {
        Console.WriteLine(MathLib.PI); // Неявно это статическое поле (не нужен модификатор static), для обращения к ней необходимо использовать имя класса
    }
}
```

## Свойства
```
[модификатор_доступа] возвращаемый_тип произвольное_название
{
    // код свойства
}
```
```
class Person
{
    private int age;
 
    public int Age
    {
        set
        {
            if (value < 18)
            {
                Console.WriteLine("Возраст должен быть больше 17");
            }
            else
            {
                age = value;
            }
        }
        get { return age; }
    }
}

// -----------------------------

class Person
{
    private string name;
    // свойство только для чтения
    public string Name
    {
        get
        {
            return name;
        }
    }
 
    private int age;
    // свойство только для записи
    public int Age
    {
        set
        {
            age = value;
        }
    }
}
```
**Сокращенная запись свойств**
```
class Person
{
    private string name;
     
    // эквивалентно public string Name { get { return name; } }
    public string Name => name;
}
```
**Автоматические свойства**
```
class Person
{
    public string Name { get; set; }
    public int Age { get; set; }
         
    public Person(string name, int age)
    {
        Name = name;
        Age = age;
    }
}

// ------------------------------

class Person
{
    public string Name { get; set; } = "Tom"; // значения по умолчанию
    public int Age { get; set; } = 23;
}
     
class Program
{
    static void Main(string[] args)
    {
        Person person = new Person();
        Console.WriteLine(person.Name); // Tom
        Console.WriteLine(person.Age);  // 23
         
        Console.Read();
    }
}
```
## Перегрузка методов
И в языке C# мы можем создавать в классе несколько методов с одним и тем же именем, но разной сигнатурой.  
Сигнатура складывается из следующих аспектов:
- Имя метода
- Количество параметров
- Типы параметров
- Порядок параметров
- Модификаторы параметров
```
class Calculator
{
    public void Add(int a, int b)
    {
        int result = a + b;
        Console.WriteLine($"Result is {result}");
    }
    public void Add(int a, int b, int c)
    {
        int result = a + b + c;
        Console.WriteLine($"Result is {result}");
    }
    public int Add(int a, int b, int c, int d)
    {
        int result = a + b + c + d;
        Console.WriteLine($"Result is {result}");
        return result;
    }
    public void Add(double a, double b)
    {
        double result = a + b;
        Console.WriteLine($"Result is {result}");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Calculator calc = new Calculator();
        calc.Add(1, 2); // 3
        calc.Add(1, 2, 3); // 6
        calc.Add(1, 2, 3, 4); // 10
        calc.Add(1.4, 2.5); // 3.9
         
        Console.ReadKey();
    }
}
```

## null
Переменные ссылочных типов могут принимать значение null, это их значение по умолчанию.
```
object o = null;
string s = null;
```
**null-объединения (??)**  
Оператор ?? возвращает левый операнд, если этот операнд не равен null. Иначе возвращается правый операнд.
```
object x = null;
object y = x ?? 100;  // равно 100, так как x равен null
 
object z = 200;
object t = z ?? 44; // равно 200, так как z не равен null

int x = 44;
int y = x ?? 100; // ошибка, x - значимый тип, не может принимать null
```
**Оператор условного null (?)** 
```
string companyName = user?.Phone?.Company?.Name; // Если же на каком-то этапе один из объектов окажется равным null, то companyName будет иметь значение по умолчанию, то есть null.

User user = new User();
string companyName = user?.Phone?.Company?.Name ?? "не установлено";
Console.WriteLine(companyName);
```
## Наследование  
По умолчанию все классы наследуются от базового класса Object, даже если мы явным образом не устанавливаем наследование. Поэтому выше определенные классы Person и Employee кроме своих собственных методов, также будут иметь и методы класса Object: ToString(), Equals(), GetHashCode() и GetType().
```
class Person // базовый класс
{
    private string _name;
 
    public string Name
    {
        get { return _name; }
        set { _name = value; }
    }
    public void Display()
    {
        Console.WriteLine(Name);
    }
}

class Employee : Person // производный класс : базовый класс
{
     
}

static void Main(string[] args)
{
    Person p = new Person { Name = "Tom"};
    p.Display();
    p = new Employee { Name = "Sam" };
    p.Display();
    
    Person p2 = new Employee(); // объект Employee является также и объектом Person
    Console.Read();
}
```
**Ключевое слово base**  
И если в базовом классе не определен конструктор по умолчанию без параметров, а только конструкторы с параметрами (как в случае с базовым классом Person), то в производном классе мы обязательно должны вызвать один из этих конструкторов через ключевое слово base.
```
class Person
{
    public string Name { get;  set; }
 
    public Person(string name)
    {
        Name = name;
    }
 
    public void Display()
    {
        Console.WriteLine(Name);
    }
}
 
class Employee : Person
{
    public string Company { get; set; }
 
    public Employee(string name, string company) : base(name) // вызываем конструктор базового класса для инициализации свойства Name
    {
        Company = company;
    }
}
```
Кроме конструкторов, мы можем обратиться с помощью ключевого слова base к другим членам базового класса.
```
class Employee : Person
{
    public string Company { get; set; }
  
    public Employee(string name, string company)
            :base(name)
    {
        Company = company;
    }
  
    public override void Display()
    {
        base.Display();
        Console.WriteLine($"работает в {Company}");
    }
}
```
**Порядок вызова конструкторов**
```
class Person
{
    string name;
    int age;
 
    public Person(string name)
    {
        this.name = name;
        Console.WriteLine("Person(string name)");
    }
    public Person(string name, int age) : this(name)
    {
        this.age = age;
        Console.WriteLine("Person(string name, int age)");
    }
}
class Employee : Person
{
    string company;
 
    public Employee(string name, int age, string company) : base(name, age)
    {
        this.company = company;
        Console.WriteLine("Employee(string name, int age, string company)");
    }
}

// Результат
// Person(string name)
// Person(string name, int age)
// Employee(string name, int age, string company)
```

## Обобщенные типы (generics)
```
class Account<T>
{
    public T Id { get; set; }
    public int Sum { get; set; }
}

Account<int> account1 = new Account<int> { Sum = 5000 };
Account<string> account2 = new Account<string> { Sum = 4000 };

account1.Id = 2;        // упаковка не нужна
account2.Id = "4356";

int id1 = account1.Id;  // распаковка не нужна
string id2 = account2.Id;

Console.WriteLine(id1);
Console.WriteLine(id2);

// ---------------------

class Transaction<U, V>
{
    public U FromAccount { get; set; }  // с какого счета перевод
    public U ToAccount { get; set; }    // на какой счет перевод
    public V Code { get; set; }         // код операции
    public int Sum { get; set; }        // сумма перевода
}
```
**Значения по умолчанию**. Присвоить переменным универсальных параметров некоторое начальное значение, в том числе и null.
```
T id = null; // Так сделать не получится, будет ошибка

class Account<T>
{
    T id = default(T); // Присваивает ссылочным типам в качестве значения null, а типам значений - значение 0
}
```
**Обобщенные методы**
```
class Program
{
    private static void Main(string[] args)
    {
        int x = 7;
        int y = 25;
        Swap<int>(ref x, ref y); // или так Swap(ref x, ref y);
        Console.WriteLine($"x={x}    y={y}");   // x=25   y=7
 
        string s1 = "hello";
        string s2 = "bye";
        Swap<string>(ref s1, ref s2); // или так Swap(ref s1, ref s2);
        Console.WriteLine($"s1={s1}    s2={s2}"); // s1=bye   s2=hello
             
        Console.Read();
    }
    public static void Swap<T> (ref T x, ref T y)
    {
        T temp = x;
        x = y;
        y = temp;
    }
}
```
**Ограничения универсальных типов**  
С помощью выражения where T : Account мы указываем, что используемый тип T обязательно должен быть классом Account или его наследником. Благодаря подобному ограничению мы можем использовать внутри класса Transaction все объекты типа T именно как объекты Account и соответственно обращаться к их свойствам и методам.
```
class Account
{
    public int Id { get; private set;} // номер счета
    public int Sum { get; set; }
    public Account(int _id)
    {
        Id = _id;
    }
}

class Transaction<T> where T: Account
{
    public T FromAccount { get; set; }  // с какого счета перевод
    public T ToAccount { get; set; }    // на какой счет перевод
    public int Sum { get; set; }        // сумма перевода
 
    public void Execute()
    {
        if (FromAccount.Sum > Sum)
        {
            FromAccount.Sum -= Sum;
            ToAccount.Sum += Sum;
            Console.WriteLine($"Счет {FromAccount.Id}: {FromAccount.Sum}$ \nСчет {ToAccount.Id}: {ToAccount.Sum}$");
        }
        else
        {
            Console.WriteLine($"Недостаточно денег на счете {FromAccount.Id}");
        }
    }
}
```
## Обработка исключений
```
try
{
     // вначале выполняются все инструкции в блоке try
}
catch (тип_исключения) // тип указывать не обязательно
{
     // если же в блоке try вдруг возникает исключение, то обычный порядок выполнения останавливается, и среда CLR начинает искать блок catch
}
finally
{
     // выполняется в любом случае
}
```
Если нужный блок catch не найден, то при возникновении исключения программа аварийно завершает свое выполнение.
```
class Program
{
    static void Main(string[] args)
    {
        try
        {
            int x = 5;
            int y = x / 0;
            Console.WriteLine($"Результат: {y}");
        }
        catch
        {
            Console.WriteLine("Возникло исключение!");
        }
        finally
        {
            Console.WriteLine("Блок finally");
        }
        Console.WriteLine("Конец программы");
        Console.Read();
    }
}
```
Таким образом, программа по-прежнему не будет выполнять деление на ноль и соответственно не будет выводить результат этого деления, но теперь она не будет аварийно завершаться, а исключение будет обрабатываться в блоке catch.  

**Фильтры исключений**
```
int x = 1;
int y = 0;
 
try
{
    int result = x / y;
}
catch(DivideByZeroException) when (y==0 && x == 0) // В этом случае обработка исключения в блоке catch производится только в том случае, если условие в выражении when истинно
{
    Console.WriteLine("y не должен быть равен 0");
}
catch(DivideByZeroException ex)
{
    Console.WriteLine(ex.Message);
}
```
**Типы исключений. Класс Exception**  
Базовым для всех типов исключений является тип Exception, свойства:  
- **InnerException**: хранит информацию об исключении, которое послужило причиной текущего исключения
- **Message**: хранит сообщение об исключении, текст ошибки
- **Source**: хранит имя объекта или сборки, которое вызвало исключение
- **StackTrace**: возвращает строковое представление стека вызывов, которые привели к возникновению исключения
- **TargetSite**: возвращает метод, в котором и было вызвано исключение
```
static void Main(string[] args)
{
    try
    {
        int x = 5;
        int y = x / 0;
        Console.WriteLine($"Результат: {y}");
    }
    catch (Exception ex)
    {
        Console.WriteLine($"Исключение: {ex.Message}");
        Console.WriteLine($"Метод: {ex.TargetSite}");
        Console.WriteLine($"Трассировка стека: {ex.StackTrace}");
    }
 
    Console.Read();
}
```
**Возможные типы исключений**
- **DivideByZeroException**: представляет исключение, которое генерируется при делении на ноль
- **ArgumentOutOfRangeException**: генерируется, если значение аргумента находится вне диапазона допустимых значений
- **ArgumentException**: генерируется, если в метод для параметра передается некорректное значение
- **IndexOutOfRangeException**: генерируется, если индекс элемента массива или коллекции находится вне диапазона допустимых значений
- **InvalidCastException**: генерируется при попытке произвести недопустимые преобразования типов
- **NullReferenceException**: генерируется при попытке обращения к объекту, который равен null (то есть по сути неопределен)
```
static void Main(string[] args)
{
    try
    {
        int[] numbers = new int[4];
        numbers[7] = 9;     // IndexOutOfRangeException
 
        int x = 5;
        int y = x / 0;  // DivideByZeroException
        Console.WriteLine($"Результат: {y}");
    }
    catch (DivideByZeroException)
    {
        Console.WriteLine("Возникло исключение DivideByZeroException");
    }
    catch (IndexOutOfRangeException ex)
    {
        Console.WriteLine(ex.Message);
    }
             
    Console.Read();
}
```
## Создание классов исключений
```
class PersonException : Exception // можно наследоваться от любого другого типа исключения
{
    public PersonException(string message)
        : base(message)
    { }
}

class Program
{
    static void Main(string[] args)
    {
        try
        {
            Person p = new Person { Name = "Tom", Age = 17 };
        }
        catch (PersonException ex)
        {
            Console.WriteLine("Ошибка: " + ex.Message);
        }
        Console.Read();
    }
}
class Person
{
    private int age;
    public int Age
    {
        get { return age; }
        set
        {
            if (value < 18)
                throw new PersonException("Лицам до 18 регистрация запрещена");
            else
                age = value;
        }
    }
}
```
Каждый тип исключений может определять какие-то свои свойства. Например, в данном случае мы можем определить в классе свойство для хранения устанавливаемого значения:
```
class PersonException : ArgumentException
{
    public int Value { get;}
    public PersonException(string message, int val)
        : base(message)
    {
        Value = val;
    }
}

class Person
{
    public string Name { get; set; }
    private int age;
    public int Age
    {
        get { return age; }
        set
        {
            if (value < 18)
                throw new PersonException("Лицам до 18 регистрация запрещена", value);
            else
                age = value;
        }
    }
}
class Program
{
    static void Main(string[] args)
    {
        try
        {
            Person p = new Person { Name = "Tom", Age = 13 };
        }
        catch (PersonException ex)
        {
            Console.WriteLine($"Ошибка: {ex.Message}");
            Console.WriteLine($"Некорректное значение: {ex.Value}");
        }
        Console.Read();
    }
}
```
## Делегаты (указатели на методы) 
```
class Program
{
    // delegate возвращаемый_тип название (параметры)
    delegate void Message(); // 1. Объявляем делегат
 
    static void Main(string[] args)
    {
        Message mes; // 2. Создаем переменную делегата
        Message mes2 = new Message(GoodMorning); // еще один способ создания объекта делегата
        
        if (DateTime.Now.Hour < 12)
        {
            mes = GoodMorning; // 3. Присваиваем этой переменной адрес метода
        }
        else
        {
            mes = GoodEvening;
        }
        mes(); // 4. Вызываем метод
        Console.ReadKey();
    }
    private static void GoodMorning()
    {
        Console.WriteLine("Good Morning");
    }
    private static void GoodEvening()
    {
        Console.WriteLine("Good Evening");
    }
}

// ------------------------

class Program
{
    delegate int Operation(int x, int y);
     
    static void Main(string[] args)
    {
        // присваивание адреса метода через контруктор
        Operation del = Add; // делегат указывает на метод Add
        int result = del(4,5); // фактически Add(4, 5)
        Console.WriteLine(result);
 
        del = Multiply; // теперь делегат указывает на метод Multiply
        result = del(4, 5); // фактически Multiply(4, 5)
        Console.WriteLine(result);
 
        Console.Read();
    }
    private static int Add(int x, int y)
    {
        return x+y;
    }
    private static int Multiply (int x, int y)
    {
        return x * y;
    }
}
```
**Добавление методов в делегат**
```
class Program
{
    delegate void Message();
 
    static void Main(string[] args)
    {
        Message mes1 = Hello;
        mes1 += HowAreYou;  // теперь mes1 указывает на два метода
        mes1(); // вызываются оба метода - Hello и HowAreYou
        mes1?.Invoke(); // еще один способ вызова делегата, тут также проверка на null, иначе если в делегате нет методов, т.е. он будет null может возникнуть исключение
        Console.Read();
    }
    private static void Hello()
    {
        Console.WriteLine("Hello");
    }
    private static void HowAreYou()
    {
        Console.WriteLine("How are you?");
    }
}
```
Если делегат возвращает некоторое значение, то возвращается значение последнего метода из списка вызова (если в списке вызова несколько методов)
