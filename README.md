*c# program to print the statement Hello World*


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
*1.c# program to print a Binary Triangle*

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
*2.c# program to check whether the entered number is a Amicable number or not*

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

![image](https://user-images.githubusercontent.com/97940064/154623079-566ffa56-09bf-4dce-a892-e96992073f1c.png)
<br>
<br>
<br>
<br>
*3.c# program to illustrate Multilevel Inheritance with Virtual Methods(displaying student details)*

using System;<br>
namespace DetailsConsoleApp1<br>
{<br>
    class PersonalDetails<br>
    {<br>
        string name;<br>
        int age;<br>
        string gender;<br>
        public PersonalDetails(string name,int age,string gender)<br>
        {<br>
            this.name = name;<br>
            this.age = age;<br>
            this.gender = gender;<br>
        }<br>
        public virtual void Display()<br>
        {<br>
            Console.WriteLine("\n----PERSONAL DETAILS----\n");<br>
             Console.WriteLine("Name     :" + name);<br>
             Console.WriteLine("Age      :" + age);<br>
             Console.WriteLine("Gender  :" + gender);<br>
            }<br>
        }<br>
    class CourseDetails : PersonalDetails<br>
    {<br>
        int regNo;<br>
        string course;<br>
        int semester;<br>
        public CourseDetails(string name, int age, string gender, int regNo, string course, int semester) : base(name, age, gender)<br>
        {<br>
            this.regNo = regNo;<br>
            this.course = course;<br>
            this.semester = semester;<br>
        }<br>
        public override void Display()<br>
        {<br>
            base.Display();<br>
            Console.WriteLine("\n----COURSE DETAILS----\n");<br>
            Console.WriteLine("Register Number  :" + regNo);<br>
            Console.WriteLine("Course           :" + course);<br>
            Console.WriteLine("Semester          :" + semester);<br>
        }<br>
    }<br>
    class MarksDetails : CourseDetails<br>
    {<br>
        int[] marks = new int[5];<br>
        int total;<br>
        float average;<br>
        string grade;<br>
        int flagfail;<br>
        public MarksDetails(string name,int age,string gender,int regNo,string course,int semester,int[] marks ):base(name,age,gender,regNo,course,semester)<br>
        {<br>
            total = 0;<br>
            for(int i=0;i<5;i++)<br>
            {<br>
                this.marks[i] = marks[i];<br>
                total += marks[i];<br>
                if(marks[i]<35)<br>
                {<br>
                    flagfail = 1;<br>
                }<br>
            }<br>
            Calculate();<br>
        }<br>
        private void Calculate()<br>
        {<br>
            average = total / 5;<br>
            if (flagfail == 1 || average < 40)<br>
                grade = "Fail";<br>
            else if (average >= 70)<br>
                grade = "Distinction";<br>
            else if (average >= 60)<br>
                grade = "First Class";<br>
            else if (average >= 50)<br>
                grade = "Second Class";<br>
            else<br>
                grade = "Pass Class";<br>
        }<br>
        public override void Display()<br>
        {<br>
            base.Display();<br>
            Console.WriteLine("\n----MARKS DETAILS----\n");<br>
            Console.Write("Marks in 5 subjects:");<br>
            for (int i = 0; i < 5; i++)<br>
                Console.Write(marks[i] + " ");<br>
            Console.WriteLine();<br>
            Console.WriteLine("Total    :" +total);<br>
            Console.WriteLine("Average   :" + average);<br>
            Console.WriteLine("Grade      :" + grade);<br>
        }<br>
    }<br>
    class MultiLevel<br>
    {<br>
        public static void Main(string[] args)<br>
        {<br>
            MarksDetails Student1 = new MarksDetails("Abhijith", 22, "Male", 20190001, "MCA", 5, new int[] { 77, 80, 98, 95, 90 });<br>
            Student1.Display();<br>
     }<br>
    }<br>
}<br>

![image](https://user-images.githubusercontent.com/97940064/154624792-91a7f142-cf54-44da-9b9c-6169de930154.png)
<br>
<br>
<br>
<br>
*4.c# program to create a Gray Code*

using System;<br>
namespace program4<br>
{<br>
    class GrayCode<br>
    {<br>
        static int getGray(int n)<br>
        {<br>
            return n ^ (n >> 1);<br>
        }<br>
        static void Main(string[] args)<br>
        {<br>
            int InputNum, GrayNum;<br>
            Console.Write("\nEnter the decimal number:");<br>
            InputNum = Convert.ToInt32(Console.ReadLine());<br>
            Console.WriteLine("\nBinary equivalent of {0}:{1}",InputNum,Convert.ToString(InputNum,2));<br>
            GrayNum = getGray(InputNum);<br>
            Console.WriteLine("\nGray Code equivalent of {0}:{1}", InputNum, Convert.ToString(GrayNum, 2));<br>
            }<br>
    }<br>
}<br>

![image](https://user-images.githubusercontent.com/97940064/154626319-d4bbd15f-9539-41c1-8610-0d7f8ad63023.png)
<br>
<br>
<br>
<br>
*5.c# program to calculate volume of 2 boxes and find the resultant volume after addition of 2 boxes by implementing operator overloading*

using System;<br>
namespace Exercises<br>
{<br>
    class Box<br>
    {<br>
        float width;<br>
        float height;<br>
        float length;<br>
        public float Volume<br>
        {<br>
            get { return width * height * length; }<br>
        }<br>
        public Box(float width, float height, float length)<br>
        {<br>
            this.width = width;<br>
            this.height = height;<br>
            this.length = length;<br>
        }<br>
        public static float operator +(Box box1, Box box2)<br>
        {<br>
            return box1.Volume + box2.Volume;<br>
        }<br>
        public override String ToString()<br>
        {<br>
            return "box with width " + width + ", height " + height + " and length " + length;<br>
        }<br>
    }<br>
    class OperatorOverloading<br>
    {<br>
        public static void Main()<br>
        {<br>
            Box box1 = new Box(10, 20, 30);<br>
            Box box2 = new Box(25, 32, 15);<br>
            Console.WriteLine("Volume of {0} is: {1}", box1, box1.Volume);<br>
            Console.WriteLine("Volume of {0} is: {1}", box2, box2.Volume);<br>
            Console.WriteLine("Volume after adding boxes: {0}", box1 + box2);<br>
        }<br>
    }<br>
}<br>

![image](https://user-images.githubusercontent.com/97940064/154627700-df2ab9df-ca8d-4586-9711-5515cfe67117.png)
<br>
<br>
<br>
<br>
*6.c# program to implement principles of Delegates (converting input string to uppercase first,last and entire string)*

using System;<br>
namespace Exercise6<br>
{<br>
    class Delegates<br>
    {<br>
        delegate string UppercaseDelegate(string input);<br>
        static string UppercaseFirst(string input)<br>
        {<br>
            char[] buffer = input.ToCharArray();<br>
            buffer[0] = char.ToUpper(buffer[0]);<br>
            return new string(buffer);<br>
        }<br>
        static string UppercaseLast(string input)<br>
        {<br>
            char[] buffer = input.ToCharArray();<br>
            buffer[buffer.Length - 1] = char.ToUpper(buffer[buffer.Length - 1]);<br>
            return new string(buffer);<br>
        }<br>
        static string UppercaseAll(string input)<br>
        {<br>
            return input.ToUpper();<br>
        }<br>
        static void writeOutput(string input,UppercaseDelegate del)<br>
        {<br>
            Console.WriteLine("Input String:{0}", input);<br>
            Console.WriteLine("Output string:{0}", del(input));<br>
        }<br>
       static void Main()<br>
        {<br>
            writeOutput("tom", new UppercaseDelegate(UppercaseFirst));<br>
            writeOutput("tom", new UppercaseDelegate(UppercaseLast));<br>
            writeOutput("tom" ,new UppercaseDelegate(UppercaseAll));<br>
             Console.ReadLine();<br>
        }<br>
    }<br>
}<br>
 
 ![image](https://user-images.githubusercontent.com/97940064/154629011-9ceb2aa7-66ca-4232-93bf-7c80aed30c9c.png)
 <br>
<br>
<br>
<br>
*7.c# program to Generate Register Number automatically for 100 students using static constructor*

using System;<br>
namespace Exercise7<br>
{<br>
    class RegisterNum<br>
    {<br>
        int regNo;<br>
        static int startNum;<br>
        static RegisterNum()<br>
        {<br>
            startNum = 20210000;<br>
        }<br>
        RegisterNum()<br>
        {<br>
            regNo = ++startNum;<br>
        }<br>
        public static void Main(string[]args)<br>
        {<br>
            for(int i=0;i<100;i++)<br>
            {<br>
                RegisterNum Student = new RegisterNum();<br>
                Console.WriteLine("Student {0}:{1}", i + 1, Student.regNo);<br>
            }<br>
        }<br>
    }<br>
}<br>

![image](https://user-images.githubusercontent.com/97940064/154631250-0aa54236-c0ca-4a88-aa72-32b0d79ec4fd.png) ![image](https://user-images.githubusercontent.com/97940064/154631380-7bd72416-8114-48a3-a690-2c0880ae89e8.png) ![image](https://user-images.githubusercontent.com/97940064/154631681-10f60fa3-e980-4da1-adcb-69224b36c80a.png) ![image](https://user-images.githubusercontent.com/97940064/154631865-c6416edb-98de-4ac4-b488-390be1de7146.png)
 <br>
<br>
<br>
<br>
*8.c# program to find the frequency of the word "is" in a given sentence*

using System;<br>
namespace Exercise8<br>
{<br>
    class FrequencyIS<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            int count = 0;<br>
            string inputstring;<br>
            Console.WriteLine("\n------Freaquency of word 'is'------");<br>
            Console.Write("\nEnter the input string:");<br>
            inputstring = Console.ReadLine();<br>
            char[] separator = { ',', ' ', '.', '!', '\n' };<br>
            string testString = inputstring.ToLower();<br>
            String[] outcomes = testString.Split(separator);<br>
            foreach (String s in outcomes)<br>
            {<br>
                Console.WriteLine(s);<br>
                if (s == "is")<br>
                    count++;<br>
            }<br>
            Console.WriteLine("\n Number of 'is' in''') + inputstring + '''is :" + count);<br>
        }<br>
    }<br>
}<br>

![image](https://user-images.githubusercontent.com/97940064/154633658-65aa579f-d90c-4375-ba56-9212fda3c2b9.png)
<br>
<br>
<br>
<br>
*9.c# program that benchmarks 2D,jagged array allocation*

using System;<br>
using System.Diagnostics;<br>
namespace Exercise9<br>
{<br>
    class BenchmarkAllocation<br>
    {<br>
        const int max= 100000;<br>
        static void Main(string[] args)<br>
        {<br>
            var Arr2D = new int[100, 100];<br>
            var ArrJagged = new int[100][];<br>
            for(int i=0;i<100;i++)<br>
            {<br>
                ArrJagged[i] = new int[100];<br>
            }<br>
            var Stopwatch2D = Stopwatch.StartNew();<br>
            for (int i = 0; i <max; i++)<br>
            {<br>
                for (int j = 0; j < 100; j++)<br>
                {<br>
                    for (int k = 0; k < 100; k++)<br>
                    {<br>
                        Arr2D[j, k] = k;<br>
                    }<br>
                }<br>
            }<br>
            Stopwatch2D.Stop();<br>
            var StopwatchJagged = Stopwatch.StartNew();<br>
            for(int i=0;i<max;i++)<br>
            {<br>
                for(int j=0;j<100;j++)<br>
                {<br>
                    for(int k=0;k<100;k++)<br>
                    {<br>
                        ArrJagged[j][k] = k;<br>
                     }<br>
                }<br>
            }<br>
            StopwatchJagged.Stop();<br>
            Console.Write("\nTime taken for allocation in case of 2D array:");<br>
            Console.WriteLine(Stopwatch2D.Elapsed.TotalMilliseconds+ "milliseconds");<br>
            Console.Write("\nTime taken for alocation in case of Jagged array:");
            Console.WriteLine(StopwatchJagged.Elapsed.TotalMilliseconds + "milliseconds");
        }<br>
    }<br>
}<br>
  
  ![image](https://user-images.githubusercontent.com/97940064/154634839-d16e7d45-5f35-4fb9-915d-933cfe196eb1.png)
 <br>
<br>
<br>
<br>
*10.c# program to find the sum of the values on Diagonal of the matrix*

using System;<br>
namespace Exercise10<br>
{<br>
    class SumOfDiagonals<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            int MaxRow, MaxCol, Sum = 0;<br>
            int[,] Matrix;<br>
            Console.WriteLine("\n----SUM OF DIAGONAL OF A MATRIX----\n");<br>
            Console.Write("\nEnter the number of rows:");<br>
            MaxRow = Convert.ToInt32(Console.ReadLine());<br>
            Console.Write("\nEnter the number of columns:");<br>
            MaxCol = Convert.ToInt32(Console.ReadLine());<br>
            if (MaxRow != MaxCol)<br>
            {<br>
                Console.WriteLine("\n The dimensions entered are not of Square matrix.");<br>
                Console.WriteLine("\nExisting the program");<br>
                return;<br>
            }<br>
            Matrix = new int[MaxRow, MaxCol];<br>
            for (int i = 0; i < MaxRow; i++)<br>
            {<br>
                for (int j = 0; j < MaxCol; j++)<br>
                {<br>
                    Console.Write("\nEnter the ({0},{1})th element of the matrix:", (i + 1), (j + 1));<br>
                    Matrix[i, j] = Convert.ToInt32(Console.ReadLine());<br>
                }<br>
            }<br>
            Console.WriteLine("\nthe entered matrix is:");<br>
            for (int i = 0; i < MaxRow; i++)<br>
            {<br>
                for (int j = 0; j < MaxCol; j++)<br>
                {<br>
                    Console.Write(" " + Matrix[i, j]);<br>
                    if (i == j)<br>
                    {<br>
                        Sum += Matrix[i, j];<br>
                    }<br>
                }<br>
                Console.WriteLine();<br>
                }<br>
            Console.WriteLine("\n The Sum of Diagonal is" + Sum);<br>
        }<br>
    }<br>
}<br>

![image](https://user-images.githubusercontent.com/97940064/154635722-34dfb8d7-4f17-48a1-a1a0-0f17205dd4ae.png)
<br>
<br>
<br>
<br>





