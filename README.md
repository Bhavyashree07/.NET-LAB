*c# program to print the statement Hello World *<br>


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
*c# program to print a Binary Triangle*<br>

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

