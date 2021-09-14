# .net-core-syntax
# .Net Core 3.1

---
//Notlar tamamen Escan Dönmeze e aittir

kod sonları **( ; )** ile belirtilir, stringler alert veya console.log **( ``,''," )( option+, )** ile belirtilir

.Net Core de **{ }** kullanılır.

---

## Veri Yapıları

### Değişkenler

- Değişken tipi

    int = sayı değerleri girildiğinde

    string = kelime değerleri girildiğinde

    bool = true false sorguları için

    float = 12.34f şeklinde ondalık sayılarda kullanılır

    double = float gibi onladık sayılarda kullanılır daha büyük değerler içindir 123.04; kullanımı bu şekilde

    decimal = 12.34m; şeklinde kullanılır float ve double gibidir
    
    var = string ve int türünden değerler atıyabilirsiniz

- Değişken adı

    Sayı ile başlamaz = 1sayi

    Arada boşluk olmamalı = birinci sayi

    Türkçe karakter kullanılmaz = sayı

    Dile özgü anahtar kelimeler kullanılmaz = for,switch,if

```csharp
//Örnek
int sayi = 10;

long sayi2 = 5432142150; //tarzda daha karmaşık yapıları değer atayabiliriz

short sayi3 = 5;  //gibi daha basit yapılı değişkenler atamak için kullanılabilir

byte sayi4 = 0-255 ; //byte da ise 0 ile 255 arası bir değişken atanabilir

console.writeline(sayi); // 10

// ondalıklı sayılarda

float a = 10.5f; //float da ondalık yazdıkdan sonra f yazılmalıdır
double b = 20.6; //double da ise böyle bir zorunlulık yokdur float la aynı işlevd
decimal c = 100.56m;//decimal olduğunu belirtmek için sayı sonuna m ekle

//Daha karmaşık yapılar için decimal kullanılır
//basit eylemler için float

//karakter
string name = "Escan Dönmez"; //veri değişkeni için
char ch = 'a'; //tek heceli değişkenler için

//boolean
bool isRetired = true;
bool isActive = false;

//Null 

byte? kilo = null; /* Eğer bir değişkenin verisini bir kullanıcının vermesini 
										istiyorsanız null kullanarak orayı boş bırakabilirsiniz */

//string değişkeninde ise
string plaka; //şeklinde kullanabilirsiniz

//boolda ise
bool? cinsiyetErkek = true
bool? cinsiyetKadın = true /*eğer kişi cinsiyetini belirtmek istemiyorsa hiçbirini
seçmeyebilir */

//Notlar tamamen Escan Dönmeze e aittir
```

---
// notlar tamamen Escan'a aittir
### Veri tipi dönüşümü

```csharp
//EXPLİCİT
Console.Write("1. sayı"); // write komutu kodu yazar ve alt satıra geçmez
int sayi1 = int.pars(Console.Readline()); //bizden değer girmemizi ister
						//değerimizi int e çevirir
Console.Write("2. sayı"); // write komutu kodu yazar ve alt satıra geçmez
int sayi2 = int.pars(Console.Readline());//bizden değer girmemizi ister
					//değerimizi int e çevirir
int toplam =sayi1 + sayi2;
Console.Writeline($"girilen toplam değer: {toplam}");

//İMPLİCİT int-long-float-double
int a = 10;
long b = a; //longun kapasitesi int den büyük olduğu için bize bir hata vermez

long c = 10;
int d = c; /*burda büyük bir veri türünü küçük bir veri türüne eklemeye çalışır
buyüzden bu kod hatalı dır  */

long c = 10;
int d = (int)c; //bu şekilde bilinçli tür dönüşümü yapabiliriz bu kod çalışır

float e = 10.5f;
double f = e; //bu kod hatasızdır çünkü float double a göre daha az yer kaplar

double g = 10.6;
float f = (float)g; //bu kod hatalı değildir

//int to string
int x = 10;
string z = x.ToString; //koduyla sayıyı stringe çevirebiliriz
```

### Strings

```csharp
string name = "escan";
string surname ="dönmez";
int age = 18;

string str = string.Format("my name is {0} {1} and I'm {2} ",name,surname,age);
//0 name in yerine 1 surname in yerine age ise 2 nin. yerine gelir

string str = $"My name is {name}"; //şeklinde de kullanılır
```
// notlar tamamen Escan'a aittir
### String metodları

```csharp
string msg = "Hello I'm Escan" ;

Console.Writleline(msg.Length); //msg değişkenin kaç karakterli olduğunu yazar
Console.Writleline(msg.ToLower);//msg değişkenin deki tüm karakterleri küçültür
Console.Writleline(msg.ToUpper);//msg değişkenin deki tüm karakterleri büyütür
Console.Writleline(msg.Trim());//msg deki tüm gereksiz boşlukları kapatır
Console.Writleline(msg.Split(0));//msg deki ilk kelime alır ve bize sunar
Console.Writleline(msg[0]);//msg deki ilk harfi alır ve bize sunar
Console.Writleline(msg.StartsWith("h"));//msg de h harfi varmı varsa true yazar
Console.Writleline(msg.EndWith("Escan"));//cümle escan ile bitiyorsa true yazar
Console.Writleline(msg.Contains("@"));//cümlede @ işareti varmı varsa true
Console.Writleline(msg.İndexOf("hello"));//bize 0 verir çünkü cümlede başta
Console.Writleline(msg.Substring(5));//5. indexden itibaren bize bilgiyi verir
Console.Writleline(msg.Replace(" ",","));//boşlukları , yapar
Console.Writleline(msg.Insert(0,"..."));//en başa 3 nokta koyar

string msg ="Hello There";

var result = msg.Split();
Console.Writeline(result[0]); //hello yu yazdırır
Console.Writeline(result[1]);//There yazdırır
//Eğer split kullanmasaydık hello yu h e l l o şeklinde bize ayıracakdı
```

### Diziler

```csharp

string[] isimler = new string[3];

isimler[0] = "ahmet"
isimler[1] = "Escan"
isimler[2] = "Yiğit"

Console.Writeline(isimler[2]); //Yiğit adını yazdırır

int[] numaralar = new int[3];

numaralar[0] = 101;
numaralar[1] = 102;
numaralar[2] = 103;

Console.Writeline($"öğrenci adı: {isimler[0] ve numara {numaralar[0]}}");
//çıktı: ahmet ve numara 101 şeklinde çıktıyı verir

//alternatif olarak

string[] isimler = {"ahmet,escan,demirhan"}; //şeklindede kullanabilirsiniz

Console.Writeline($"öğrenci adı {isimler[0]}");

//Eğer diziden bir elemanı değiştirmek istiyorsan

isimler[0] = "Murat";
```

### Dizi metodları

```csharp
string[] isimler = {"ahmet,murat,escan,esra"};
int[] numaralar = {"5,4,3,2,1"};

isimler.SetValue("Ali",0); //0. indexi Ali ile değiştirdik

console.writeline(isimler[0]);

console.writeline(Array.IndexOf(isimler,"Escan"));// index numarası yani 2 i verir

console.writeline(isimler.Length);//isimlerin uzunluğunu sayı olarak verir yani 3

Array.Sort(isimler); //alfabetik olarak diziyi sıralar
Array.Sort(numaralar); //sayı numaralarına göre sıralar

Array.Reverse(isimler);//alfabede en sondaki elementi alır
Array.Reverse(numaralar);//en büyük sayıyı alır

var result = isimler[1..4];// 1 den 4. elemana kadar
```
// notlar tamamen Escan'a aittir
### Date time

```csharp
DateTime simdi = DateTime.Now; //kullanılan bilgisayarın zaman dilimini. yazar

console.writeline(simdi);

console.writeline(simdi.Year); //sadece yıl ı yazdırır 

console.writeline(simdi.Month);

console.writeline(simdi.day);

console.writeline(simdi.DayOfWeek);//haftanın günü

console.writeline(simdi.hour);

console.writeline(simdi.minute);

console.writeline(simdi.second);

DateTime dt = new DateTime(2021,2,22,14);//saat ve dakikasına kadar belirtebilir

CultureInfo culture = new CultureInfo("tr");
Console.Writeline(simdi.ToString("F",culture))
//kullanmak için using System.Globalization ı en üste eklemelisin
```

## Operatörler

### Aritmerik Operatörler

```csharp
// (+,-,*,/,%,++,--)
int a = 10;
int b = 20;
int val;
//Notlar tamamen Escan Dönmeze e aittir
Console.Writeline("value "+ val);

val = a + b; // 30

val = a - b; // -10 

val = a * b; // 200

val = (float)a / (float)b; // 0.5

val = b % a; //0 b yi 10 a böler sayı çift mi tekmi onu öğreniriz

val = a++; // 11

val = b-- // 19
```
// notlar tamamen Escan'a aittir
### Atama Operatörleri

```csharp
// (=,+=,-=,*=,/=,%=)
int x=5,y=10,z=20;

x += 5; // 10

x -= 5; // 0

x *= 5; // 25

x /= 10; // 2

x %= 5; // 1 yani tektir

val = Math.Round(4.4); // 4 e yuvarlar
```

### Karşılaştırma Operatörleri

```csharp
// (==,!=,<,>,<=,>=,?:)
int a=5,b=5,c=10,d=4;

a == b; //a b ye eşit mi ?

a != b; // a b ye eşit DEĞİL mi ?

a < b; // a b den küçük mü ?

a > b; // a b den büyük mü ?

a <= b;// a b den küçükmü yada eşit mi ?

a >= b;// a b den büyükmü yada eşit mi ?

string sonuc = (usurname == escan)?"şifre doğru":"şifre yanlış";
```
// notlar tamamen Escan'a aittir
### Mantıksal Operatörler

```csharp
// (&&,||,!)
int x = 5;

var result = (x<5);
result = (x<10);

result = (x<5) && (x<10);// And operatörü ikiside doğru olmalı yani cvp false

result =  (x<5) || (x<10)// Or opreatörü ikisinden biri doğru olması yeter True

result =  !(x<10) // true => false | false => true çevirir
```
// notlar tamamen Escan'a aittir
## koşul ifadeleri

### if/else

```csharp
if(3>2){
	Console.Writeline("hoşgeldin");  //eğer 3 2 den. büyükse hoşgeldin yazdır
}
else{
	Console.Writeline("sistemden çıkıldı")//döngü tutmuyorsa else yazar
}

//önrek 2
var isLoggedin = true;

if (isLoggedin == true){
	Console.Writeline("sisteme girdi"); //koşul tutarda sisteme girer
}
else{
	Console.Writeline("sistemden çıkıldır");// koşul false olsaydı sisteme girilemezdi
}

//örnek 3

string usurname = "Escan"
string password = "12345"

if ((usurname == "Escan") && (password == "12345")){
	Console.WriteLine("hoş geldin");
}
else{
	Console.WriteLine("usurname ya da password yanlış")
}

```

### if/else if

```csharp
Console.WriteLine("1.sayı")
int x = int.Parse(Console.ReadLine())
Console.WriteLine("2.sayı")
int y = int.Parse(Console.ReadLine())

if (x > y){
	Console.WriteLine("x y den büyük");
}
else if(x==y){
	Console.Writeline("x y ye eşit")//alternatif döngü
}
else{
	Console.WriteLine("y x den büyük");
}

```
// notlar tamamen Escan'a aittir
### switch

```csharp
int ay = 5;
//switch if koşullarını ard arda yazmatansa bize kolaylık sağlar
switch(ay){

case 12:
	console.writeline("kış mevsimi");
	break; //kodun diğer case e geçmesini engeller
case 1:
	console.writeline("kış mevsimi");
	break;
case 2:
	console.writeline("kış mevsimi");
	break;

default: // eğer kodlardan hiçbiri gerçekleşmezse burdaki kod gerçekleşir else gibi
}
```

## Döngüler

### For

```csharp
for (int i = 0; i < 5; i++)//i 5 olana kadar i ye 1 eklenir
{
Console.WriteLine(i);
}

//Yada

for (int i = 50; i >= 1;i=i -2)//i 1 den büyük olana kadar 2 çıkartır
{
Console.WriteLine(i);
}
```
// notlar tamamen Escan'a aittir
### While

```csharp
while(şart){
//yapılacak işlemler
}

//Örnek

int i = 0;
while(i <= 10){ //başlangıç değeri döngünün dışında
Console.Write(i);
i++ // arttırma ise döngü içinde
}

//while içinde if gibi koşul larda kullanılabilir

string name = "";

while(string.IsNullOrEmpty(name)){ //eğer name değişkeni boş ise True çkts verir
	Console.Write("isminiz: ");
	name = Console.ReadLine();
}
```

### Do while

```csharp
//do while while döngüsünün ters halidir do while döngüsünde şart en alta yaz

do {
//yapılacak işlemler
}
while(şart);

//Örnek

int i = 0;

do{
Console.Write(i);
i++
}while(i < 10);
```

### break & continue

```csharp
string name = "Escan";
for(int i = 0; i < name.Length; i++){
if(name[i] == 'c'){
	break;             //Döngü bittiğinde döngüden çıkmak için break kullanılır
Console.Writeline(name[i]);
}
}

//eğer break yerine continue dersek
string name = "Escan";
for(int i = 0; i < name.Length; i++){
if(name[i] == 'd'){
	continue;         //Döngünün turunu bitirir ve sonraki döngüden devam eder
Console.Writeline(name[i]);
}
}
//Notlar tamamen Escan Dönmeze e aittir
```

## Nesne tabanlı (OOP)

### Class

```csharp
int[] ogrno = {100,200,300};
string[] ad = {"Escan,demirhan,aslan"};
string[] sube = {"10A,10B,10C"};

//class da ise

namespace ConsoleApp //yani class program üstüne
{
 class Ogrenci{
//prop yazıp tab tuşuna basarsanız gelecekdir
public int ogrno {get; set;}
public string ad {get; set;}
public string sube {get; set;}
//bunları yazdıkdan sonra normal kodları yazdığımız yere dönüp
Ogrenci ogr1 = new Ogrenci() ;
ogr1.ogrno = 100; //ogrno ad ve sube otomatik çıkacakdır
ogr1.ad = "Escan";
ogr1.sube = "10A";

//alttaki gibide kullanabilirsin

Ogrenci ogr2 = new Ogrenci() 
{
	ogrno = 200,
	ad = "demirhan",
	sube = "10B"
};

Ogrenci[] ogrenciler = new Ogrenci[3]; //3 elemanlı olduğunu söyledik
ogrenciler[0] = ogr1; //yani classıda diziye ekleye biliriz

	Console.Writeline($"no: {ogr1.OgrNo} ad: {ogr1.ad} sube:  {ogr1.sube}");
}
```

### Metotlar

```csharp
//                 **INTRO METODU**

class Person{
public string name {get; set; }
public int year {get; set; }

**public string Intro(){ //Intro metodu
return  $"name: {this.name} age: {2021-this.calculateAge}";
}

public int calculateAge(){
return DateTime.Now.Year - this.year;//günümüzden year değişkenini çıkarcak
}**
}
//static voide Main(string[]) args) yani kod yazma alanı
Person p1 = new Person(){ name="ada",year=2012}; //p1.name den bir farkı yok
Person p2 = new Person(){ name="escan",year=2007};
Person p3 = new Person(){ name="demirhan",year=2006};

//public string Intro metodu sayesinde daha kolay ve pratik yazdırabiliyoruz

Console.Writeline(p1.Intro());
Console.Writeline(p1.Intro());      //çıktı aşağıdaki kod la aynı olacak
Console.Writeline(p1.Intro());

//üst de kullandığımız Intro() metodu sayesinde bunları yazdırmamıza gerek yok
//Console.Write($"name: {p1.name} age: {2021-p1.year}");
//Console.Write($"name: {p2.name} age: {2021-p2.year}");
//Console.Write($"name: {p3.name} age: {2021-p3.year}");

//ÖRNEK

using System;

namespace consoleapp
{
    class araba{
        public string marka { get; set; }
        public string model { get; set; }
        public string renk { get; set; }
        public bool otomatik { get; set; }

        //methods

        public void start(){
            Console.WriteLine($"{this.marka} araç çalıştırıldı");
        }
         public void stop(){
            Console.WriteLine($"{this.marka} araç durdu");
        }
         public void hizlan(){
            Console.WriteLine($"{this.marka} araç hızlandı");
        }
        public void ozellik(){
            Console.WriteLine($"{this.marka}, {this.model}, {this.renk}, otomatik:{this.otomatik},");
        }
         public void menu(){
            string secim = "";

            do
            {
                Console.WriteLine("******************");
                Console.WriteLine("1-start 2-stop 3-hız 4-özellik çıkış-ç");
                Console.Write("Seçiminiz: ");
                secim = Console.ReadLine();
                

                switch (secim)
                {
                    case "1":
                    this.start();
                    break;
                    case "2":
                    this.stop();
                    break;
                    case "3":
                    this.hizlan();
                    break;
                    case "4":
                    this.ozellik();
                    break;
                    case "ç":
                    break;

                    default:
                    Console.WriteLine("yanlış seçim");
                    break;
                }
            } while (secim!="ç");

        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            var opel = new araba();
                opel.marka = "opel";
                opel.model = "astra";
                opel.renk = "kırmızı";
                opel.otomatik = true;

            var mazda = new araba();
                mazda.marka = "mazda";
                mazda.model = "gamaro";
                mazda.renk = "kırmızı";
                mazda.otomatik = true;

            string araç = "";
            
            
                Console.Write("araç seçimin: ");
                araç = Console.ReadLine();
                
                switch (araç)
                {
                    case "mazda":
                    mazda.menu();
                    break;
                    case "opel":
                    opel.menu();
                    break;

                    default:
                    Console.Write("yanlış seçim");
                    break;
                }
        }
    }
}
```
// notlar tamamen Escan'a aittir
### Metot parametreleri

```csharp
class Islem {

public int Toplam(int x, int y){ // x ve y parametresi tanımladık
	return x+y;;
}
} 
//kod alanı
var islem = new Islem();

Console.Writeline(islem.Toplam(x:10,y:20));//named parameters

//yada
class Islem {
public int Toplam(params int[] sayilar){ 
	foreach (var sayi in sayilar){
	toplam += sayi;
}
return toplam;
}
}
//kod alanı
var islem = new Islem();

Console.Writeline(islem.Toplam(10));
Console.Writeline(islem.Toplam(10,20));
Console.Writeline(islem.Toplam(10,20,30)); 
//şeklinde daha da pratik kullanabilirsin
```

### Yapıcı metot

```csharp
class araba{
public araba (string marka,string model){ //ctor yazarak otomatik getirebilirsiniz
	this.marka = marka;
	this.model = model;
	
} 
}

var opel = new araba("opel","astra");

//     opel.marka = "opel";   Yukarıda yaptığımız kod sayesinde böyle uğraşmamıza
//     opel.model = "astra";  gerek kalmadı
               
```

### properties

```csharp
class product{

private string _name;

public string name{
get{
return _name; //kullanıcı name istediğinde _name i vericek
}
set{
	if(!string.isNullOrEmpty(value)){ //string boş değil se
	_name = value; //_name value ayarla
	}
	else{
	Console.Writeline("name alanı boş geçilemez"); //eğer boş ise yazdır
	}
}
}

private double _price;

public double Price{

get{
 return _price;  //_price ı sunucak
}

set{             //0 dan küçük değişken gelirse onu 0 a sabitliyicek
	 if(value<0){
		_price = 0;
		}
		else{
		_price = value;
		}
}
}

}
}
//kod alanı
var p = new product();

	p.name = "samsung";

	p.Price=2000;

/*turuncu alanda _price a özel izinli değişken atadık */

/*mavi alanda _price ı özel eleman yaptık yani sadece özel değişkenler burdaki
değişkeni değiştirebilir */
console.Write(p.name);
console.Write(p.Price);//Price ekrana yazıyor yani _price ı
```
// notlar tamamen Escan'a aittir
### Static member

```csharp
/* Static bir class ın tüm içeriği statik olmalıdır statik class lardan normalde
kaçınılır çünkü static bir class a tüm client lar ulaşabilir fakat bazı durumlarda
static hayat kurtarır*/

class student{
public string name {get;set;}

public int StudentNumber {get;set;}

static class HelperMethods{

public static string karakterDuzelt(string str){
return str.Replace("c"); //c harflerini silecek
}
}

public static string school = "my school"; //static member

public Student(string name,int studentnumber){
this.name = name;
this.StudentNumber=studentnumber;
}
public void DisplayStudentDetails(){
Console.writeline($"name: {this.Name} number: {this.StudentNumber}")
}
public void DisplaySchoolDetails(){
Console.Writeline($"school name: {school}"); 
}
}
//kod bölümü
var s1 = new Student("Çınar",100);
var s2 = new Student("Seçil",200);
var s3 = new Student("Escan",300);

student.DisplaySchoolDetails();

s1.DisplayStudentDetails();
s2.DisplayStudentDetails();
s3.DisplayStudentDetails();

string str = "ölcme be değerlemdirme"; //c harfi silindi
var result = HelperMethods.KarakterDuzelt(str);
Console.Write(result);

//sarı kodlar konuyla alakalı static member 
```

### Kalıtım (Inheritance)

```csharp
// Person => name, surname, age, eat(), drink()
// student(Person) => studentnumber()
// Teacher(Person) => brach(), tech()

/* bir öğrenci veya bir öğretmen temelde bir insandır ve en basitinden yeme içme
tarzı basit ve temel ihtiyaçları gidermelidir bu temel ihtiyaçları gideren 
değişkenimiz Person, bir öğrencinin numarası illaki olmalı bu ekstra bir özelliği
yani temel özelliklerinden farklı olarak aynı şekilde öğretmen temel özelliği
dışında bir branşa ve öğretme özelliğine sahip olmalı.*/

class Person{

public string Name {get;set;}

public string SurName {get;set;}

//Method
public Person(){
Console.Write("Person nesnesi oluşturuldu");
}

}

class Student: Person // Student sınıfına Person özelliklerini atadım {
Console.Write("student nesnesi oluşturuldu");
}

//Kod alanı

var s = new Student(); /*iki yazıyıda konsola yazdırır ama ilk önce person u yazdı
rır çünkü en temel özelliklerini Person dan alıcak ve sonrasında kendi ekstraları
nı ekleyecek. */

//EĞER bir değişken eklersek nasıl olur ?

class Person{

public string Name {get;set;}

public string SurName {get;set;}

public void Intro(){
Console.WriteLine($"name: {this.Name} Surname: {this.SurName}");/* kod alanı ile
buranın iletişimi olmadığından dolayı buraya this. yazıyoruz bizim yerimize
p ile s değişkenlerini yazdıracak*/
}

public Person(string name, string surname){ /*bir değişken eklersem bu değişkeni
Student ada eklemeliyim */

this.Name = name;
this.SurName = surname;

}
}

class Student: Person{

public Student(string name, string surname): base(name,surname){ /*persondan this
.Name komutunu çalıştırdı fakat Student için*/

}
}

//Kod alanı

var p = new Person("Ali","Yılmaz");
var s = new Student("Çınar","Turan");

p.Intro();
s.Intro();
```
// notlar tamamen Escan'a aittir
### Abstract sınıf

```csharp
abstract class shape{ 

public int width {get;set;}

public int height {get;set;}

public abstract void draw(); /*draw metodu şu anda sadece sanal bir metod oyüzden
bunu sadece diğer sanal olmayan classlar kullanabilir */

}

class Square: shape{

public override void draw(){ //draw ı override ederek onu değiştirdik
// Not: bu değişiklik sadece square drawı çağrıldığında olur
Console.Writeline("Draw a square");
}

}

class rectangle: shape{

public override void draw(){ //draw ı override ederek onu değiştirdik
// Not: bu değişiklik sadece rectangle drawı çağrıldığında olur
Console.Writeline("Draw a rectangle");
}

}

//Kod alanı

var shape = new shape [3]

shape[0] = new rectangle();
shape[1] = new Square();
shape[2] = new rectangle();

foreach (var shapes in shape)
          {
              shapes.draw();
          }
```

### interface

```csharp
interface IPersonel{ /*Mantığı tamamen kalıtım ile aynı tek fark burda tanımlanan
herşey abstract ve public olarak çalışır*/
	string adSoyad {get;set;}
	string adres {get;set;}
  string Departman {get;set;}
	void bilgi();
}

class Yonetici: IPersonel{ //IPersonel üzerine gelip control+. yapınca ilk sıraya tıklarsan tüm değişkenker otomatik gelicek
	public string adSoyad {get;set;}
	public string adres {get;set;}
  public string Departman {get;set;}

	void bilgi(){
	Console.WriteLine($"{this.adSoyad} isimli personel {this.departman} bölümünde
	yönetici");
	}

	public Yonetici(string _adsoyad,string _adres,string _departman){
	this.adSoyad = _adsoyad;
	this.adres = _adres;
	this.Departman = _departman;
	}

}
class Iscı: IPersonel{
	public string adSoyad {get;set;}
	public string adres {get;set;}
  public string Departman {get;set;}

	void bilgi(){
	Console.WriteLine($"{this.adSoyad} isimli personel {this.departman} bölümünde
	işci");

	public Iscı(string _adsoyad,string _adres,string _departman){
	this.adSoyad = _adsoyad;
	this.adres = _adres;
	this.Departman = _departman;
	}

	
}

//kod alanı

var personeller = new IPersonel[3];

personeller[0] = new Yonetici("Escan","istanbul","Finans")
personeller[1] = new Iscı("ahmet","izmir","üretim")
personeller[2] = new Iscı("mehmet","izmir","üretim")

foreach (var personel in personeller){
personel.bilgi();
}
```
// notlar tamamen Escan'a aittir
### ArrayList

```csharp
//metodların ne işe yaradığını veya Icollection gibi yerlerde hangi metodlar var
//öğrenmek için şu linke tıkla 

//https://docs.microsoft.com/tr-tr/dotnet/api/system.collections.arraylist?view=net-5.0

// ArrayList yazıp control+. ya bastığımızda ilk sıradaki ne tıklamalıyız

ArrayList myList = new ArrayListy();

//myList. burda tüm metodlar görünücek 
myList.Add("abc"); //listeye abc eklendi

MyList.InsertRange(3,mylist2);//3. index den sonra mylist2 yi aktar

// YADA

ArrayList myList2 = new ArratList(){10,"10","abc"}. //şeklindede kullanılabilir

myList2.Insert(20);//listenin sonuna 20 yi ekler

Console.Writeline(myList[0]); //ilk elemana ulaşırsın yani 10'a

int sayi = mylist2[1];  //"10" stringini int e çevirdik

//Remove Items

myList2.Remove(10);//mylist2 deki 10 elemanı gitti
```

### Generic List <T>

```csharp
// Konu hakkında rehber için : https://docs.microsoft.com/tr-tr/dotnet/api/system.collections.generic.list-1?view=net-5.0#methods

//Generic List tipi başta belirtilmeli ve hep o kullanılmalı

//List yazdıkdan sonra control+. yaparak ilk sıradakine tıkla

List<int> sayilar = new list<int>();

sayilar.Add(10); //sadece int atayabilirim
sayilar.Add(20);
sayilar.Add(30);

List<string> harfler2 = new list<string>();

sayilar2.Add("a"); //sadece string atayabilirim
sayilar2.Add("b");
sayilar2.Add("c");

sayilar2.AddRange(sayilar);//bu geçerli olmaz çünkü sayilar int türünden
```

### Dictionary <Tkey><KValue>

```csharp
//Dictionary yazıp control+. yapıp ilk sıradakine tıkla

Dictionary<int,string> plakalar = new Dictionary<int,string>(); //keyi int
//değeri value olarak ayarladık

plakalar.Add(34,"istanbul"); //key 34 değer ise istanbul
plakalar.Add(35,"izmir");

```
// notlar tamamen Escan'a aittir
## Hata Yönetimi

### Hata Yönetimi

```csharp
Console.Write("a: ")
int a = int.Parse(Console.Readline());

Console.Write("b: ")
int a = int.Parse(Console.Readline());

var sonuc = a/b;
Console.WriteLine($"{0} / {1} = {2}"a,b,c,sonuc)
//Burda 0 a bölünemedi hatası verir ve program durdurulur bunu çözmek için

try{

Console.Write("a: ")
int a = int.Parse(Console.Readline());

Console.Write("b: ")
int a = int.Parse(Console.Readline());

var sonuc = a/b;
Console.WriteLine($"{0} / {1} = {2}"a,b,c,sonuc)

}
catch(DvideByZeroException)//hatanın adı konsolda görünücek onu yaz
{
Console.WriteLine("b sıfır olamaz");
}

//Diyelimki formatexeption yani int yazılması gereken yere string girdiniz

catch(FormatException){
Console.Writeline("Sayısal bir değer girmelisin");
}

//Eğer hata hakkında bilgi vermek istemiyorsanız sonuna ex ekleyin

catch(Exception ex){
Console.WriteLine("Bir hata oluştu");
Console.WriteLine(ex.Message);
}
finally{
Console.WriteLine("blok çalıştırıldı");
}

```

### Hata fırlatma

```csharp
int sayi = 10;

if (sayi>5){
throw new Exception("sayi 5 den büyük olamaz") /*program çalıştığında hata vericek
ve hata açıklaması olarak yazdırır buna hata fırlatma denir Not: kod hatalı değil
biz hata vermesini istediğimiz için verdi */
}
/*------------------------------------------------------*/

static void check_password(string password){
 if(password.Length<8 || password.Length>15){ /* şifre 8 den küçük yada 15 den
büyük ise Parola 7-15 karakter arasında olmalı hatası ver */
	throw new Exception("Parola 7-15 karakter arasında olmalı")
	}
}

//kod alanı

string parola = "1234567a";

try{
check_password(parola)
Console.WriteLine("parola geçerli.");
}
catch(Exception ex){
Console.Weiteline(ex.Message)
}
```
### Veri Tabanı Bağlantısı

```csharp
//Main alanı
GetSqlConnection();

// Main alanın altına
static void GetMySqlConnection{
	 string connectionString = @"server=localhost;port:3306;database=ShopApp;user=
root;password=1234"

using(var connection = new MySqlConnection(connectionString)){
	try{
		connection.Open();
		Console.WriteLine("Bağlantı sağlandı");
  }
	catch(Exception e){
   Console.Writeline(e.Message)
	}
	finally{
	connection.Close
	}
}
}

//View+ çıkan arama çubuğuna MySql.Data tıklayın son
//versiyonu onaylayın
//ardından çıkan ConsoleApp.csproj da konsole dotnet restore yaz

```

### Veri tabanı tüm ürün bilgilerinin alınması

```csharp
//Main alanı
GetAllProduct();
//Main alanın altı
static void GetAllProduct()
        {
            using(var connection = GetMySqlConnection()) //anahtar ve kili burda
// birleştirdik
            {
                try
                {
                    connection.Open();
                    //connection sağla

                    string sql = "select * from Product";
										//Product tablosunu seç

                    MySqlCommand command = new MySqlCommand(sql,connection);
										//sql ile connection ı bağladık böylece komut işe yarayacak

                    MySqlDataReader reader = command.ExecuteReader();
										//bu reader değişkeni sayesinde bu bilgileri okuycaz

                    while(reader.Read())
                    {
                        Console.WriteLine($"name: {reader[1]} price:{reader[2]}");
                      //Burda reader ile okuyacağı kolonu seçtik
                    }
                    reader.Close();
										//okuyucuyu kapattık
                }
                catch(Exception e)
                {
                    Console.WriteLine(e.Message);
                }
                finally
                {
                    connection.Close();
                }
            }
        }

        static MySqlConnection GetMySqlConnection()
        {
            string connectionString = @"server=localhost;port=3306;database=ShopApp;user=root;password=er266914";
//Veri tabanına gireceğimiz anahtarı oluşturduk
            return new MySqlConnection(connectionString);    
//burda da kilidi çağırdık yani connectionString i     
        }
```

### verileri nesne ile taşıma

```csharp
//namespace alanı ayrı bir program.cs alanında
 class Program{
public int ProductId {get;set;}
public string Name {get;set;}  //Altta yazdığımız kodlar sayesinde veri tabanını buraya taşıdık
public double Price {get;set;}
}

//Main alanı

var products = GetAllProduct();

foreach (var pr in products){
Console.WriteLine($"name: {pr.Name} price: {pr.Price}")
}

//Main alanın altı
static List<Product> GetAllProduct()
        {
						List<Product> products = null;
						
            using(var connection = GetMySqlConnection()) //anahtar ve kili burda
// birleştirdik
            {
		return products;
                try
                {
                    connection.Open();
                    //connection sağla

                    string sql = "select * from Product";
		   //Product tablosunu seç

                    MySqlCommand command = new MySqlCommand(sql,connection);
		//sql ile connection ı bağladık böylece komut işe yarayacak

                    MySqlDataReader reader = command.ExecuteReader();
			//bu reader değişkeni sayesinde bu bilgileri okuycak

				products = new List<Product>();
				 //list e gelip command+. ile using ini ekleyin

                    while(reader.Read())
                    {
			products.Add(
			  new Product
		           {
				 ProductId=int.Parse(reader["id"].ToString()),
				//ProductId yi veri tabanındaki id ile eşliyoruz
		               Name = reader["product_name"].ToString(),
		      	      //Name i veritabanındaki product_name ile eşliyoruz
		              Price = double.Parse(reader["list_price"]?.ToString()),
				//Price ı veri tabanındaki lisr_price ile eşliyoruz
		           }
			    );

                        Console.WriteLine($"name: {reader[1]} price:{reader[2]}");
                      //Burda reader ile okuyacağı kolonu seçtik
                    }
                    reader.Close();
		  //okuyucuyu kapattık
                }
                catch(Exception e)
                {
                    Console.WriteLine(e.Message);
                }
                finally
                {
                    connection.Close();
                }
            }
        }

        static MySqlConnection GetMySqlConnection()
        {
            string connectionString = @"server=localhost;port=3306;database=ShopApp;user=root;password=er266914";
//Veri tabanına gireceğimiz anahtarı oluşturduk
            return new MySqlConnection(connectionString);    
//burda da kilidi çağırdık yani connectionString i     
        }
```

### Scaler ile çalışmak

<img width="712" alt="Screen Shot 2021-08-31 at 17 25 58" src="https://user-images.githubusercontent.com/84273839/131520596-f859f266-767c-4bba-83a9-5dda930dbf31.png">

### Verilere Ürün Ekleme Çıkarma Güncelleme

<img width="712" alt="Screen Shot 2021-08-31 at 17 26 44" src="https://user-images.githubusercontent.com/84273839/131520714-a814e71f-d23f-4dd3-8de0-f9cb36bb0eed.png">


<img width="699" alt="Screen Shot 2021-08-31 at 17 27 21" src="https://user-images.githubusercontent.com/84273839/131520820-b9781cdb-65c1-45c2-983b-cc37a57cf653.png">
<img width="712" alt="image" src="https://user-images.githubusercontent.com/84273839/131520931-a0a53a88-6995-471d-a7d8-9aadff6a32a1.png">


## ORM - Entity Framework

### Entity sınıflar

```csharp
//Product (Id,Name,Price) => Product(Id,Name,Price)

public class Product{
//primary key (Id, <type_name>Id)

public int Id {get;set;}
[MaxLength(100)]//Maksimum 100 değer atanabilir dedik command+. namespace ekle
[Required] //zorunlu bir değer olduğunu söyledik
public string Name {get;set;}

public decimal Price {get;set;}
}

public class Category
{
public int Id {get;set;}

public string Name {get;set;}
}
```

### Context sınıfın eklenmesi ve Veri tabanı oluşturma

<img width="620" alt="Screen Shot 2021-08-31 at 17 25 23" src="https://user-images.githubusercontent.com/84273839/131520498-05fab448-2c46-401e-be9f-f6583b694ee5.png">


```csharp
/* Aşağıdaki kodları yazdıkdan sonra veri tabanı ile sekronize oluyoruz üstteki
Üstteki görseldeki kodları sırasıyla terminale yazdığımızda veri tabnımızı bize
oluşturur*/

// Model First (Yeni Veritabanı Oluşturma Visual Studio İle)(Şuan yaptığımız)
// Database First (Var Olan Veritabanını Kullanma)
// Code First (Yeni Veritabanı Kod Yazarak)
// Code First(Var Olan Veritabanını Kullanma)

public class ShopContext:DbContext //command+. yapıp using ini ekle
{
public DbSet<Product> Products {get;set;}
public DbSet<Category> Categories {get;set;}

protected override void OnConfiguring(DbContextOpitonsBuilder optionsBuilder){
//DbContextOptionsBuilder a cmd+. diyerek change ile başlayan seçeneğe tıklayın
optionsBuilder.UseMysql(@"server=localhost;port=3306;database=Shop;user=root;password=er266914");

}
}

public class Product{
//primary key (Id, <type_name>Id)

public int Id {get;set;}
[MaxLength(100)]//Maksimum 100 değer atanabilir dedik command+. namespace ekle
[Required] //zorunlu bir değer olduğunu söyledik
public string Name {get;set;}

public decimal Price {get;set;}
}

public class Category
{
public int Id {get;set;}

public string Name {get;set;}
}
```

### Kayıt ekleme

```csharp

public class ShopContext:DbContext 
{
public DbSet<Product> Products {get;set;}
public DbSet<Category> Categories {get;set;}

protected override void OnConfiguring(DbContextOpitonsBuilder optionsBuilder){

optionsBuilder.UseMysql(@"server=localhost;port=3306;database=Shop;user=root;password=er266914");

}
}

public class Product{

public int Id {get;set;}
[MaxLength(100)]
[Required] 
public string Name {get;set;}

public decimal Price {get;set;}
}

public class Category
{
public int Id {get;set;}

public string Name {get;set;}
}

//MAİN alanı

using(var db = new ShopContext()){

var p = new Product {Name = "Samsung S5",Price = 2000};
// p değişkenine Name ve price değerlerini atadık

db.Products.Add(p);
//başta atadoğomız db komutuyla products tablosuna p yi ekledik

db.SaveChanges
// yaptığımız herşeyi save ledik ki görünsün

Console.WriteLine("Veriler eklendi");
}

**Eğer birden fazla kategori eklemek istiyorsak**

using(var db = new ShopContext()){

var products = new List<Product>//cmd+. ile namespace ini ekle
{
	//products değişkenine bütün listeyi atadık
	 new Product {Name = "Samsung S6",Price = 2000},
	 new Product {Name = "Samsung S7",Price = 4000},
	 new Product {Name = "Samsung S8",Price = 5000}
	
};

db.Products.AddRange(products);//Products tablosuna products değişkenini yolladık

db.SaveChanges
// yaptığımız herşeyi save ledik ki görünsün

Console.WriteLine("Veriler eklendi");
}

```

### Kayıt seçme

```csharp
//Main alan
GetAllProducts();

//main alanın altına
static void GetAllProducts(){
using(var context = new ShopContext()){

	var products = context
.Products
.Select(product => new {
	p.name,
	p.price
})
.ToList(); //cmd+. ile namespace ekle ToList SaveChanges ile aynı görevde
	
	foreach(var p in products){
	Console.WriteLine($"name: {p.Name} price: {p.Price}");
	}
	
	
}
}
```

### Kayıt güncelleme

```csharp
//Main alan
UpdateProduct();
//main alanı altı
static void UpdateProduct(){
	using(var db = new ShopContext()){

	var entity = new Product(){Id=1};
	//Id 1 i değiştireceğimiz söyledik

	db.Products.Attach(entity);
	//attach anlamı ise entity yi takip etmek olarak atadık eğer entity takip etmez
  // ise kod başarısız olur

	entity.Price = 3000;
	//fiyatı 3000 olarak değiştirdik

	db.SaveChanges();

	}
}
```

### kayıt silme

```csharp
// Main alan
DeleteProduct();

//Main alan altı

static void DeleteProduct(int id){

using(var db = new ShopContext()){
	var p = new Product(){Id==6};

	db.Products.Remove(p);
	db.SaveChanges();	

 }
}
```

### Şema güncellemesi veri tabanına aktarımı - migration

```csharp
public class ShopContext:DbContext 
{
public DbSet<Product> Products {get;set;}
public DbSet<Category> Categories {get;set;}
public DbSet<Order> Orders {get;set;}

protected override void OnConfiguring(DbContextOpitonsBuilder optionsBuilder){

optionsBuilder.UseMysql(@"server=localhost;port=3306;database=Shop;user=root;password=er266914");

}
}

public class Product{

public int Id {get;set;}
[MaxLength(100)]
[Required] 
public string Name {get;set;}

public decimal Price {get;set;}

public int CategoryId {get;set;}
/*Örneğin biz CategoryId yi ekledik fakat biz bunu eklediğimizde başta eklediğimiz
migration a eklenmez bunun için bir aktarım yapmamız gerek terminal'e dotnet ef
--help yazarak görebilirsiniz*/

/*Terminale şu kodları girmeliyiz dotnet ef migrations add addColumnProductCategoryId
üstte yazdığımız kodda şunu söyledik Product alanına CategoryId kolonunu ekleyin
Ama bunlar ile bitmiyor ayriyetden terminale dotnet ef database update yazarak
databesi i güncellemelisiniz
*/
}

public class order{
//Burayı ekledikden sonra order dbcontext eklemelisiniz
public int Id {get;set;}

public int ProductId{get;set;}

public DateTime DateAdded {get;set;}

//dotnet ef migrations add addTableOrder terminale yazın ardından
//dotnet ef database update diyerek güncelleye bilirsiniz
//Eğer ki yaptığınız son işlemden pişman oldunuz yani eklemek istemediniz 
//Merak etme çözümü çok basit 
//dotnet ef database update addCollumnProductCategoryId yani bundan önceki ekledi-
//ğiniz kolon veya table ın adını girdiğinizde ozamana kadar eklediklerinizi askıya alır
//Eğer ben silicem derseniz dotnet ef migrations remove diyerek son eklediğinizi siler
//Not: silmeden önce migration ı databse den çıkarmış olmalısnız yani dotnet ef database update addCollumnProductCategoryId yazarak eylem dışı bırakmalısınız
//Peki tamamen 0 a dönmek yani hepsini silmek isterseniz dotnet ef database update 0 yazman yeterli
}

```
