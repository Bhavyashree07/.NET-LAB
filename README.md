*c# program to print the statement Hello World*<br>


using System;<br>
namespace ConsoleApp3<br>
{<br>
    class Program<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            Console.WriteLine("Hello World!");<br>
        }<br>
    }<br>
}<br>
![image](https://user-images.githubusercontent.com/97940064/154424956-5d2f431b-078e-4bae-bf0e-c0d808030cc1.png)
<br>
<br>
<br>
<br>
*1.c# program to print a Binary Triangle*<br>

using System;<br>
namespace  Excercises<br>
{<br>
    class BinaryTriangle<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            int number, digit = 1;<br>
            Console.Write("\nEnter the no. of lines:");<br>
            number = Convert.ToInt32(Console.ReadLine());<br>
            for(int i=1;i<=number;i++)<br>
            {<br>
                for (int space = number - i; space > 0; space--)<br>
                {<br>
                    Console.Write(" ");<br>
                }<br>
                for (int j = 0; j < i; j++)<br>
                {<br>
                    Console.Write(digit + " ");<br>
                    digit = (digit == 1) ? 0 : 1;<br>
                }Console.Write("\n");<br>
            }<br>
        }<br>
    }<br>
}<br>

![image](https://user-images.githubusercontent.com/97940064/154621779-620c2b89-d51a-41d5-94fe-3da5f89480d2.png)
<br>
<br>
<br>
<br>
*2.c# program to check whether the entered number is a Amicable number or not*<br>

using System;<br>
namespace AmicableConsoleApp1<br>
{<br>
    class AmicableNumber<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            int num1, num2, sum1 = 0, sum2 = 0;<br>
            Console.WriteLine("\n----AMICABLE NUMBER----\n");<br>
            Console.Write("\nEnter the First number:");<br>
            num1 = Convert.ToInt32(Console.ReadLine());<br>
            Console.Write("\nEnter the second number:");<br>
            num2 = Convert.ToInt32(Console.ReadLine());<br>
            for (int i = 1; i < num1; i++)<br>
            {<br>
                if (num1 % i == 0)<br>
                {<br>
                    sum1 += i;<br>
                }<br>
            }<br>
            for (int i = 1; i < num2; i++)<br>
            {<br>
                if (num2 % i == 0)<br>
                {<br>
                    sum2 += i;<br>
                }<br>
            }<br>
            if (sum1 == num2 && sum2 == num1)<br>
            {<br>
                Console.WriteLine("\nThe number {0} and {1} are amicable.", num1, num2);<br>
            }<br>
            else<br>
            {<br>
                Console.WriteLine("\nThe number {0} and {1} are not amicable.", num1, num2);<br>
            }<br>
        }<br>
    }<br>
}<br>
<br>
<br>
<br>
<br>
![image](https://user-images.githubusercontent.com/97940064/154623079-566ffa56-09bf-4dce-a892-e96992073f1c.png)
<br>
<br>
<br>
<br>
*3.c# program to illustrate Multilevel Inheritance with Virtual Methods(displaying student details)*

