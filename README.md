1.ESP32 LED:https://wokwi.com/projects/336877332872561236<br>
2.ESP32 3 LED:https://wokwi.com/projects/336882445805683282 <br>
3.ESP32 RGB LED: https://wokwi.com/projects/336879976249819732<br>
4. ESP32 LCD: https://wokwi.com/projects/340854854168609362 <br>
5.servomotar with push button: https://wokwi.com/projects/340856211886834260<br>
6.servomotor with sliding potentiometer : https://wokwi.com/projects/340872161402028628<br>
7.Buzzor with push button:https://wokwi.com/projects/340857898569564756<br>
8.Ultrasonic sensor with buzzor:https://wokwi.com/projects/340950822622855764<br> 
9.https://wokwi.com/projects/340951268671357523  
10.   
11.    
12.      
13. LED_Chaser: https://wokwi.com/projects/340854632473428562<br>



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

![image](https://user-images.githubusercontent.com/97940064/154637406-2422a698-2464-406e-8a41-8e22f08019de.png)
![image](https://user-images.githubusercontent.com/97940064/154635722-34dfb8d7-4f17-48a1-a1a0-0f17205dd4ae.png)
<br>
<br>
<br>
<br>
*11.c# program to create a file,check the existence of a file and Read the contents of the file*

using System;<br>
using System.IO;<br>
namespace Exercise11<br>
{<br>
    class FileRead<br>
    {<br>
        public static void Main()<br>
        {<br>
            string fileName;<br>
            while (true)<br>
            {<br>
                Console.WriteLine("\n----MENU----\n");<br>
                Console.WriteLine("\n 1.create a file");<br>
                Console.WriteLine("\n 2.Existence of the file");<br>
                Console.WriteLine("\n 3.Read the contents of the file");<br>
                Console.WriteLine("\n 4.exit");<br>
                Console.Write("\n Enter your choice:");<br>
                int ch = int.Parse(Console.ReadLine());<br>
                switch (ch)<br>
                { <br>
                    case 1:<br>
                         Console.Write("\n Enter the file name to create:");<br>
                         fileName = Console.ReadLine();<br>
                         Console.WriteLine("\n Write the COntents to the File:\n");<br>
                         string r = Console.ReadLine();<br>
                         using (StreamWriter fileStr = File.CreateText(fileName))<br>
                         {<br>
                           fileStr.WriteLine(r);<br>
                         }<br>
                Console.WriteLine("File is created...");<br>
                break;<br>
                case 2:<br>
                Console.Write("\n Enter the file name:");<br>
                fileName = Console.ReadLine();<br>
                if (File.Exists(fileName))<br>
                   {<br>
                    Console.WriteLine("File exists...");<br>
                    }<br>
                else<br>
                    {<br>
                    Console.WriteLine("File does not exist in current directory!");<br>
                    }<br>
                break;<br>
                case 3:<br>
                Console.Write("Enter the file name to read the contents :\n");<br>
                fileName = Console.ReadLine();<br>
                if (File.Exists(fileName))<br>
                    {<br>
                    using(StreamReader sr = File.OpenText(fileName))<br>
                       {<br>
                        string s = "";<br>
                        Console.WriteLine("Here is the content of the file:");<br>
                        while ((s = sr.ReadLine())!= null)<br>
                        {<br>
                            Console.WriteLine(s);<br>
                        }<br>
                        Console.WriteLine("");<br>
                        }<br>
                     }<br>
                else<br>
                  {<br>
                    Console.WriteLine("File does not exists");<br>
                   }<br>
                break;<br>
                case 4:<br>
                Console.WriteLine("\n Exiting...");<br>
                return;<br>
                default:
        Console.WriteLine("\n Invalid choice");<br>
                break;<br>
                 }<br>
            }<br>
        }<br>
    }<br>
}<br>

![image](https://user-images.githubusercontent.com/97940064/155662119-7aa86a56-2b81-47a1-bb45-5009b4f0d8a8.png)
![image](https://user-images.githubusercontent.com/97940064/155662265-a1368d12-00ab-4be8-adb4-ce10b3f93da4.png)
![image](https://user-images.githubusercontent.com/97940064/155662386-b88ae40c-68fc-4ff0-9408-d14305dbf0a4.png)
<br>
<br>
<br>
<br>
*12.c# program to perform File Comparison*

using System;<br>
using System.IO;<br>
namespace Exercise12<br>
{<br>
    class FileRead<br>
    {<br>
        public static void Main()<br>
        {<br>
            string file1;<br>
            string file2;<br>
            Console.Write("Enter the first file path:");<br>
            file1 = Console.ReadLine();<br>
            Console.Write("Enter the second file path:");<br>
            file2 = Console.ReadLine();<br>
            if (!File.Exists(file1))<br>
            {<br>
                Console.WriteLine("First file does not exist!");<br>
            }<br>
            else if (!File.Exists(file2))<br>
            {<br>
                Console.WriteLine("Second file does not exists!");<br>
            }<br>
            else if (File.ReadAllText(file1) == File.ReadAllText(file2))<br>
            {<br>
                Console.WriteLine("Both files contain the same content");<br>
            }<br>
            else<br>
            {<br>
                Console.WriteLine("Contents of files are not same");<br>
            }<br>
         }<br>
     }<br>
}<br>

![image](https://user-images.githubusercontent.com/97940064/155664087-6f1579db-1163-42f4-a263-655d602adaed.png)
![image](https://user-images.githubusercontent.com/97940064/155664227-37ef34d5-58da-465d-9312-c3d482d79b23.png)
![image](https://user-images.githubusercontent.com/97940064/155664322-fc8f7de8-d259-458c-9764-b6e8f312cbe1.png)

![image](https://user-images.githubusercontent.com/97940064/155665201-635dd611-62dd-488a-b14d-60af4968b09f.png)
![image](https://user-images.githubusercontent.com/97940064/155665386-11531b8f-d6da-4f7d-ad25-9a8c4395dad7.png)
<br>
<br>
<br>
<br>


*13.c# Program to implement IComparable Interface *

using System;<br>
namespace Exercise13<br>
{<br>
    class Fraction : IComparable<br>
    {<br>
        int z, n; <br>
        public Fraction(int z,int n)<br>
        {<br>
            this.z = z;<br>
            this.n = n;<br>
        }<br>
        public static Fraction operator +(Fraction a, Fraction b)<br>
        {<br>
            return new Fraction(a.z * b.n + a.n * b.z , a.n * b.n);<br>
        }<br>
        public static Fraction operator*(Fraction a,Fraction b)<br>
        {<br>
            return new Fraction(a.z * b.z, a.n * b.n);<br>
        }<br>
        public int CompareTo(object obj)<br>
        {<br>
            Fraction f = (Fraction)obj;<br>
            if ((float)z / n < (float)f.z / f.n)<br>
                return -1;<br>
            else if ((float)z / n > (float)f.z / f.n)<br>
                return 1;<br>
            else<br>
                return 0;<br>
        }<br>
        public override string ToString()<br>
        {<br>
              return z+"/"+n;<br>
         }<br>
        class ICompInterface<br>
        {<br>
            public static void Main()<br>
            {<br>
                Fraction[] a =<br>
                {<br>
                    new Fraction(5 ,2),<br>
                    new Fraction(29, 6),<br>
                    new Fraction(4, 5),<br>
                    new Fraction(10,8),<br>
                    new Fraction(34,7)<br>
                };<br>
                Array.Sort(a);<br>
                Console.WriteLine("Implementing the IComparable Interface in " + "Displaying Fraction:");<br>
                foreach(Fraction f in a)<br>
                {<br>
                    Console.WriteLine(f + " ");<br>
                }<br>
                Console.WriteLine();<br>
                Console.ReadLine();<br>
            }<br>
        }<br>
     }<br>
}<br>

![image](https://user-images.githubusercontent.com/97940064/155667049-400bbd1e-82e2-4ca4-9efc-9edf65c040b3.png)
<br>
<br>
<br>
<br>

*14.c# Program to create Thread Pools*
using System;<br>
using System.Threading;<br>
namespace Exercises<br>
{<br>
    class ThreadPoolProg<br>
    {<br>
        public void ThreadFun1(object obj)<br>
        {<br>
            int loop = 0;<br>
            for (loop = 0; loop <= 4; loop++)<br>
            {<br>
                Console.WriteLine("Thread1 is executing");<br>
            }<br>
        }<br>
        public void ThreadFun2(object obj)<br>
        {<br>
            int loop = 0;<br>
            for (loop = 0; loop <= 4; loop++)<br>
            {<br>
                Console.WriteLine("Thread2 is executing");<br>
            }<br>
        }<br>
        public static void Main()<br>
        {<br>
            ThreadPoolProg TP = new ThreadPoolProg();<br>
            for (int i = 0; i < 2; i++)<br>
            {<br>
                ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun1)); ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun2));<br>
            }<br>
            Console.ReadKey();<br>
        }<br>
    }<br>
}<br>

![image](https://user-images.githubusercontent.com/97940064/155669545-f4a95734-8501-42ec-bb26-e0ab94a3b53c.png)
<br>
<br>
<br>
<br>

*15.c# Program to demonstrate error handling using Try , Catch and Finally block*
 
 using System;<br>
namespace Exercises<br>
{<br>
    class ExceptionHandling<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            Age a = new Age();<br>
            try<br>
            {<br>
                a.displayAge();<br>
            }<br>
            catch (AgeIsNegativeException e)<br>
            {<br>
                Console.WriteLine("AgeIsNegativeException: {0}", e.Message);<br>
            }<br>
            finally<br>
            {<br>
                Console.WriteLine("Execution of Finally block is done.");<br>
            }<br>
        }<br>
    }<br>
}<br>
public class AgeIsNegativeException : Exception<br>
{<br>
    public AgeIsNegativeException(string message) : base(message)<br>
    {<br>
    }<br>
}<br>
public class Age<br>
{<br>
    int age = -5;<br>
    public void displayAge()<br>
    {<br>
        if (age < 0)<br>
        {<br>
            throw (new AgeIsNegativeException("Age cannot be negative"));<br>
        }<br>
        else<br>
        {<br>
            Console.WriteLine("Age is: {0}", age);<br>
        }<br>
    }<br>
}<br>
![image](https://user-images.githubusercontent.com/97940064/155670685-5efbd4d3-78af-43c7-b1ae-c0a5f7fca1d9.png)
<br>
<br>
<br>
<br>

*16.c# Program to print fibonacci series without using recursion *

using System;<br>
namespace exercises<br>
{<br>
    public class FibonacciExample<br>
    {<br>
        public static void Main(string[] args)<br>
        {<br>
            int n1 = 0, n2 = 1, n3, i, number;<br>
            Console.Write("Enter the number of elements: ");<br>
            number = int.Parse(Console.ReadLine());<br>
            Console.Write(n1 + " " + n2 + " "); <br>
            for (i = 2; i < number; ++i) <br>  
            {<br>
                n3 = n1 + n2;<br>
                Console.Write(n3 + " ");<br>
                n1 = n2;<br>
                n2 = n3;<br>
            }<br>
        }<br>
    }<br>
}<br>

![image](https://user-images.githubusercontent.com/97940064/155671859-79412856-ead9-441c-bd32-469b75f00b74.png)
<br>
<br>
<br>
<br>

*17.c# program to check prime number*

using System;<br>
public class PrimeNumberExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, i, m = 0, flag = 0;<br>
        Console.Write("Enter the Number to check Prime: ");<br>
        n = int.Parse(Console.ReadLine());<br>
        m = n / 2;<br>
        for (i = 2; i <= m; i++)<br>
        {<br>
            if (n % i == 0)<br>
            {<br>
                Console.Write("Number is not Prime.");<br>
                flag = 1;<br>
                break;<br>
            }<br>
        }<br>
        if (flag == 0)<br>
            Console.Write("Number is Prime.");<br>
    }<br>
}<br>

![image](https://user-images.githubusercontent.com/97940064/156499333-46670d4e-afa3-4a63-a791-47ebe6d7cc6d.png)
![image](https://user-images.githubusercontent.com/97940064/156499522-253afbd5-459f-44ef-a943-da3a3a238183.png)
<br>
<br>
<br>
<br>

*18.c# program to check whether the given number is palindrome or not*

  using System;<br>
  public class PalindromeExample<br>
  {<br>
    public static void Main(string[] args)<br>
    {
        int n, r, sum = 0, temp;<br>
        Console.Write("Enter the number:");<br>
        n = int.Parse(Console.ReadLine());<br>
        temp = n;<br>
        while (n > 0)<br>
        {<br>
            r=n % 10;<br>
            sum = (sum * 10) + r;<br>
            n = n / 10;<br>
        }<br>
        if (temp == sum)<br>
            Console.Write("Number is Palindrome");<br>
        else<br>
            Console.Write("Number is not Palindrome");<br>
    }<br>
}<br>
![image](https://user-images.githubusercontent.com/97940064/156501777-2b41af05-8286-43eb-a85a-c8843789bd83.png)
![image](https://user-images.githubusercontent.com/97940064/156501874-88e9a303-bcfd-4790-8837-52a2e03becfc.png)
<br>
<br>
<br>
<br>

*19.C# program to print factorial of a number*

using System;<br>
public class FactorialExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int i, fact = 1, number;<br>
        Console.Write("Enter any Number: ");<br>
        number = int.Parse(Console.ReadLine());<br>
        for (i = 1; i <= number; i++)<br>
        {<br>
            fact = fact * i;<br>
        }<br>
        Console.Write("Factorial of " + number + " is: " + fact);<br>
    }<br>
}<br>

![image](https://user-images.githubusercontent.com/97940064/156502298-e41a7cf1-e6a1-444e-82ce-491f031d143f.png)
<br>
<br>
<br>
<br>

*20.c# program to check Armstrong number*

using System;<br>
public class ArmstrongExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, r, sum = 0, temp;<br>
        Console.Write("Enter the Number= ");<br>
        n = int.Parse(Console.ReadLine());<br>
        temp = n;<br>
        while (n > 0)<br>
        {<br>
            r = n % 10;<br>
            sum = sum + (r * r * r);<br>
            n = n / 10;<br>
        }<br>
        if (temp == sum)<br>
            Console.Write("Armstrong Number.");<br>
        else<br>
            Console.Write("Not Armstrong Number.");<br>
    }<br>
}<br>
![image](https://user-images.githubusercontent.com/97940064/156503052-809960f9-c18f-41a1-a140-e008fb0525a5.png)
![image](https://user-images.githubusercontent.com/97940064/156503273-d9163dac-e63f-4306-ad05-b0629d08112c.png)
<br>
<br>
<br>
<br>

*21.C# program to print Sum of digits*

using System;<br>
public class SumExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, sum = 0, m;<br>
        Console.Write("Enter a number: ");<br>
        n = int.Parse(Console.ReadLine());<br>
        while (n > 0)<br>
        {<br>
            m = n % 10;<br>
            sum = sum + m;<br>
            n = n / 10;<br>
        }<br>
        Console.Write("Sum is= " + sum);<br>
    }<br>
}<br>
![image](https://user-images.githubusercontent.com/97940064/156504443-3923c4cc-fbdd-470d-bbf0-ad7e94a59bca.png)
<br>
<br>
<br>
<br>

*22. C# program to reverse a given number*

using System;<br>
public class ReverseExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, reverse = 0, rem;<br>
        Console.Write("Enter a number: ");<br>
        n = int.Parse(Console.ReadLine());<br>
        while (n != 0)<br>
        {<br>
            rem = n % 10;<br>
            reverse = reverse * 10 + rem;<br>
            n /= 10;<br>
        }<br>
        Console.Write("Reversed Number: " + reverse);<br>
    }<br>
}<br>
![image](https://user-images.githubusercontent.com/97940064/156505392-d6f0a8f6-e837-4bc7-a671-cbf3da5374f7.png)


***********Windows Application***********
*23.c# program to convert digits to words*

Form1.cs [Code] <br>
using System;  <br>
using System.Collections.Generic;  <br>
using System.ComponentModel;  <br>
using System.Data; <br> 
using System.Drawing;  <br>
using System.Linq; <br> 
using System.Text; <br> 
using System.Threading.Tasks; <br> 
using System.Windows.Forms; <br> 
namespace WinFormsApp1  <br>
{  <br>
 public partial class Form1 : Form  <br>
 {  <br>
 public Form1() <br> 
 {  <br>
 InitializeComponent();  <br>
 }  <br>
 private void button1_Click(object sender, EventArgs e)  <br>
 {  <br>
 lbl_words.Text = NumtoWord(long.Parse(txt_num.Text)); <br> 
 }  <br>
 public string NumtoWord(long number) <br> 
 {  <br>
 string word = "";  <br>
 if (number == 0)  <br>
 {  <br>
 return "Zero";  <br>
 } <br> 
 if (number < 0)  <br>
 {  <br>
 return "Minus" + Math.Abs(number);  <br>
 }  <br>
 if (number / 10000000 > 0)  <br>
 {  <br>
 word += NumtoWord(number / 10000000) + "Corer";  number %= 10000000;  <br>
 } <br>
 if (number / 100000 > 0)  <br>
 {  <br>
 word += NumtoWord(number / 100000) + "Lacs";  <br>
 number %= 100000;  <br>
 }  <br>
 if (number / 1000 > 0)  <br>
 {  <br>
 word += NumtoWord(number / 1000) + "Thousand";  <br>
 number %= 1000;  <br>
 }  <br>
 if (number / 100 > 0)  <br>
 { <br> 
 word += NumtoWord(number / 100) + "Hundred";  <br>
 number %= 100;  <br>
 }  <br>
 if (number > 0)  <br>
 {  <br>
 string[] units = new string[] { "Zero", "One", "Two", "Three", "Four", "Five", "Six",  "Seven", "Eight", "Nine","Ten", "Eleven", "Twelve", "Thirteen", "Fourteen", "Fifteen", "Sixteen",  "Seventeen", "Eighteen", "Nineteen" };  <br>
 string[] Tens = new string[] { "Zero", "Ten", "Twenty", "Thirty", "Fourty", "Fifty",  "Sixty", "Seventy", "Eighty", "Ninety" };  <br>
 if (number < 20)  <br>
 { <br> 
 word += units[number];  <br>
 }  <br>
 else  <br>
 {  <br>
 word += Tens[number / 10];  <br>
 if (number % 10 > 0)  <br>
 {  <br>
 word += units[number % 10];  <br>
 }  <br>
 }  <br>
 }  <br>
 return word;  <br>
 }  <br>
 }  <br>
} <br>

![image](https://user-images.githubusercontent.com/97940064/160979846-74e1a93c-9726-4089-a80b-bce5581ef8ad.png)


*24.c# program to perform reversal,Paddong and Trimming operations on string*

using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace WindowsFormsApp2<br>
{<br>
public partial class Form1 : Form<br>
{<br>
public Form1()<br>
{<br>
InitializeComponent();<br>
}<br>
private void btnrev_Click(object sender, EventArgs e)<br>
{<br>
 string inputString, revstr = "";<br>
  int Length;<br>
  inputString = txtInput.Text;<br>
  Length = inputString.Length - 1;<br>
  while (Length >= 0)<br>
  {<br>
   revstr = revstr + inputString[Length];<br>
    Length--;<br>
    }<br>
   MessageBox.Show("Reverse String Is : " + revstr, "Result");<br>
   }<br>
  private void btntrim_Click(object sender, EventArgs e)<br>
  {<br>
   string inputString;<br>
   inputString = txtInput.Text;<br>
   MessageBox.Show("The String After Trimming : " + inputString.Trim(), "Result");<br>
   }<br>
    private void btnpad_Click(object sender, EventArgs e)<br>
   {<br>
   string inputString;<br>
    inputString = txtInput.Text;<br>
    inputString = inputString.PadLeft(10, '*');<br>
    inputString = inputString.PadRight(15, '*');<br>
   MessageBox.Show("String After Padding : " + inputString, "Result");<br>
  }<br>
  }<br>
}<br>


![image](https://user-images.githubusercontent.com/97940064/158742248-b95cec66-bb08-45a7-b291-fe0d30c1b0cd.png)
![image](https://user-images.githubusercontent.com/97940064/158742359-561c7407-040b-4772-a62e-79385488270f.png)
![image](https://user-images.githubusercontent.com/97940064/158742466-ab988232-df3e-4ab7-8e5f-4e7c912f20c5.png)


*25.C# program to create a Progress Bar Control*

using System; <br>
using System.ComponentModel;<br>  
using System.Threading;<br>  
using System.Windows.Forms;<br>  
namespace WindowsFormsApplication1<br>  
{<br>  
 public partial class Form1: Form<br>  
 {<br>  
 public Form1() <br> 
 {<br>  
 InitializeComponent();<br>  
 }<br> 
} <br>
private void Form1_Load(object sender, System.EventArgs e)<br>   
{<br>  
backgroundWorker1.WorkerReportsProgress = true;<br> 
 backgroundWorker1.RunWorkerAsync();<br>  
 }<br> 
private void backgroundWorker1_DoWork(object sender, DoWorkEventArgs e)<br>
{<br>  
 for (int i = 1; i <= 100; i++)<br>  
 { <br> 
 Thread.Sleep(50);<br>  
 backgroundWorker1.ReportProgress(i);<br> 
 } <br> 
 } <br> 
 private void backgroundWorker1_ProgressChanged(object sender,   ProgressChangedEventArgs e) <br> 
 { <br> 
 progressBar1.Value = e.ProgressPercentage;<br>  
 this.Text = "Progress: " + e.ProgressPercentage.ToString() + "%";<br> 
 }<br>  
 }<br>  
}<br> 

OUTPUT:

![image](https://user-images.githubusercontent.com/97940064/158745932-aa5452b7-08f0-47cb-9dd7-2e45f3dd33b2.png)


*26.Develop a winform application to create flat clock*

using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace Flat_Clock<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
        }<br>
        private void Form1_Load(object sender, EventArgs e)<br>
        {<br>
            System.Timers.Timer timer = new System.Timers.Timer();<br>
            timer.Interval = 1000;//1s <br>
            timer.Elapsed += Timer_Elapsed;<br>
            timer.Start();<br>
        }<br>
        private void Timer_Elapsed(object sender, System.Timers.ElapsedEventArgs e)<br>
        {<br>
            circularProgressBar1.Invoke((MethodInvoker)delegate<br>
            {<br>
                circularProgressBar1.Text = DateTime.Now.ToString("hh:mm:ss");<br>
                circularProgressBar1.SubscriptText = DateTime.Now.ToString("tt");//AM or PM  }); <br>
            });<br>
        }<br>
    }<br>
}<br>

![image](https://user-images.githubusercontent.com/97940064/158758052-ce487e76-186f-4d28-88eb-5d433a4b1a13.png)


*27.C# Program to perform a number guessing game*

using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace WindowsFormsApp2<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        static Random r = new Random();<br>
        int value;<br>
        int guessnum;<br>
        int win = 10;<br>
        int guess = 1;<br>
        TextBox textBox1;<br>
        Button button1;<br>
        RichTextBox richTextBox1;<br>
        RichTextBox richTextBox2;<br>
        Label label4;<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
            value = r.Next(10);<br>
            this.Controls.Clear();<br>
            this.BackColor = Color.Pink;<br>
            this.AutoSize = true;<br>
            this.Padding = new Padding(16);<br>
            Label label = new Label();<br>
            label.Text = "Pick a number between 1 and 100";<br>
            label.Bounds = new Rectangle(10, 20, 340, 40);<br>
            label.Font = new Font("Arial", 16);<br>
            textBox1 = new TextBox();<br>
            textBox1.Bounds = new Rectangle(20, 50, 120, 80);<br>
            textBox1.Font = new Font("Arial", 24);<br>
            button1 = new Button();<br>
            button1.Text = " Check Your Guess ";<br>
            button1.Bounds = new Rectangle(160, 50, 120, 40);<br>
            button1.BackColor = Color.LightGray;<br>
            button1.Click += new EventHandler(button1_Click);<br>
            Label label2 = new Label();<br>
            label2.Text = "Low Guess";<br>
            label2.Bounds = new Rectangle(20, 150, 160, 40);<br>
            label2.Font = new Font("Arial", 18);<br>
            richTextBox1 = new RichTextBox();<br>
            richTextBox1.Bounds = new Rectangle(20, 190, 160, 300);<br>
            richTextBox1.Font = new Font("Arial", 16);<br>
            Label label3 = new Label();<br>
            label3.Text = "High Guess";<br>
            label3.Bounds = new Rectangle(180, 150, 160, 40);<br>
            label3.Font = new Font("Arial", 18);<br>
            richTextBox2 = new RichTextBox();<br>
            richTextBox2.Bounds = new Rectangle(180, 190, 160, 300);<br>
            richTextBox2.Font = new Font("Arial", 16);<br>
            label4 = new Label();<br>
            label4.Bounds = new Rectangle(20, 100, 340, 40);<br>
            label4.Font = new Font("Arial", 16);<br>
            this.Controls.Add(label);<br>
            this.Controls.Add(textBox1);<br>
            this.Controls.Add(button1);<br>
            this.Controls.Add(label4);<br>
            this.Controls.Add(label2);<br>
            this.Controls.Add(label3);<br>
            this.Controls.Add(richTextBox1);<br>
            this.Controls.Add(richTextBox2);<br>
        }<br>
        private void Form1_Load(object sender, EventArgs e)<br>
        {<br>
        }<br>
        private void button1_Click(object sender, EventArgs e)<br>
        {<br>
            // Coding of game<br>
            if (textBox1.Text == "")<br>
            {<br>
                return;<br>
            }<br>
            guessnum = Convert.ToInt32(textBox1.Text);<br>
            textBox1.Text = String.Empty;<br>
            if (win >= 0)<br>
            {<br>
                if (guessnum == value)<br>
                {<br>
                    MessageBox.Show("You have guessed the number! \n The number was " + value);<br>
                    InitializeComponent();<br>
                }<br>
                else if (guessnum < value)<br>
                {<br>
                    richTextBox1.Text += guessnum + "\n";<br>
                    MessageBox.Show("wrong Guess and number of guesses left are  " + (10 - guess));<br>
                }<br>
                else if (guessnum > value)<br>
                {<br>
                    richTextBox2.Text += guessnum + "\n";<br>
                    MessageBox.Show("wrong Guess and number of guesses left are  " + (10 - guess));<br>
                }<br>
                guess++;<br>
                win--;<br>
            }<br>
            if (guess == 11)<br>
            {<br>
                label4.Text = "You loose,Correct Guess is " + value;<br>
            }<br>
        }<br>
    }<br>
}<br>
    
![image](https://user-images.githubusercontent.com/97940064/159852445-72c56c93-7c93-4180-8552-47a0c463a07d.png)

30. Develop an application to construct a graphical binary tree where you need to create,add, search and remove nodes.

using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>
using System.Drawing.Drawing2D;<br>

namespace WinFormBinaryTree<br>
{<br>
    public partial class BinTreeForm : Form<br>
    {<br>
        private Node root;<br>
        public BinTreeForm()<br>
        {<br>
            InitializeComponent();<br>
            this.root = null;<br>
            test();<br>
        }<br>
        void test()<br>
        {<br>
            textBox1.Text = "5";<br>
            btnAdd_Click(btnAdd, null);<br>
            textBox1.Text = "3";<br>
            btnAdd_Click(btnAdd, null);<br>
            textBox1.Text = "2";<br>
            btnAdd_Click(btnAdd, null);<br>
            textBox1.Text = "1";<br>
            btnAdd_Click(btnAdd, null);<br>
            textBox1.Text = "4";<br>
            btnAdd_Click(btnAdd, null);<br>
            textBox1.Text = "7";<br>
            btnAdd_Click(btnAdd, null);<br>
            textBox1.Text = "6";<br>
            btnAdd_Click(btnAdd, null);<br>
            textBox1.Text = "8";<br>
            btnAdd_Click(btnAdd, null);<br>
        }<br>
        private void BinTreeForm_Load(object sender, EventArgs e)<br>
        {<br>
        }<br>
        private void btnCreate_Click(object sender, EventArgs e)<br>
        {<br>
            root = null;<br>
            pictureBox1.Image = null;<br>
        }<br>
        private void btnAdd_Click(object sender, EventArgs e)<br>
        {<br>
            int value = int.Parse(textBox1.Text);<br>
            if (root == null)<br>
                root = new Node(value);<br>
            else<br>
            {<br><br>
                if (root.Add(value) == false)<br><br>
                    MessageBox.Show("The value already exists!");<br><br>
            }<br><br>
            drawTree();<br><br>
        }<br><br>
        private void btnRemove_Click(object sender, EventArgs e)<br><br>
        {<br><br>
            int value = int.Parse(textBox1.Text);<br><br>
            if (root != null)<br><br>
            {<br><br>
                bool status = root.Remove(value, root, ref root);<br><br>
                if (status == false)<br><br>
                {<br><br>
                    MessageBox.Show("the value does not exists");<br><br>
                }<br><br>
            }<br><br>
            drawTree();<br><br>
        }<br><br>
        private void btnSearch_Click(object sender, EventArgs e)<br>
        {<br>
            string msg;<br>
            int value = int.Parse(textBox1.Text);<br>
            if (root == null)<br>
            {<br>
                msg = "Tree is empty";<br>
            }<br>
            else<br>
            {<br>
                if (root.Exists(value))<br>
                {<br>
                    msg = "Value found";<br>
                }<br>
                else<br>
                {<br>
                    msg = "Value not found";<br>
                }<br>
            }<br>
            MessageBox.Show(msg);<br>
        }<br>
        void drawTree()<br>
        {<br>
            if (root != null)<br>
                pictureBox1.Image = root.Draw();<br>
            else<br>
                pictureBox1.Image = null;<br>
            this.Update();<br>
        }<br>
           }<br>
    class Node<br>
    {<br>
        internal Node left { get; set; }<br>
        internal Node right { get; set; }<br>
        internal int value;<br>
        internal int center = 12;
        private static Bitmap nodeBg = new Bitmap(30, 25);<br>
        private static Font font = new Font("Arial", 14);<br>
        internal Node(int value)<br>
        {<br>
            this.value = value;<br>
        }<br>
        internal bool Add(int value)<br>
        {<br>
            Node node = new Node(value);<br>
            if (value < this.value)<br>
            {<br>
                if (this.left == null)<br>
                {<br>
                    this.left = node;<br>
                    return true;<br>
                }<br>
                else<br>
                    return this.left.Add(value);<br>
            }<br>
            else if (value > this.value)<br>
            {<br>
                if (this.right == null)<br>
            {<br>
                    this.right = node;<br>
                    return true;
                }<br>
else<br>
                  return this.right.Add(value);<br>
            }<br>
            return false;<br>
        }<br>
        internal bool Remove(int value, Node parent, ref Node root)<br>
        {<br>
            if (value < this.value)<br>
            {<br>
                if (left != null)<br>
                {<br>
                    return left.Remove(value, this, ref root);<br>
                }<br>
            }<br>
            else if (value > this.value)<br>
            {<br>
                if (right != null)<br>
                {<br>
                    return right.Remove(value, this, ref root);<br>
                }<br>
            }<br>
            else if (value == this.value)<br>
            {<br>
                bool isLeft = (this == parent.left);<br>
                if (left == null && right == null)<br>
                {<br>
                    if (root == this)<br>
                        root = null;<br>
                    else<br>
                    if (isLeft) parent.left = null; else parent.right = null;<br>
                }<br>
                else if (right == null)<br>
                {<br>
                    if (isLeft) parent.left = left; else parent.right = left;<br>
                    if (root == this)<br>
                        root = left;<br>
                }<br>
                else<br>
                {<br>
                    if (right.left == null)<br>
                    {<br>
                        right.left = left;<br>
                        if (isLeft) parent.left = right;<br>
                        else<br>
                    parent.right = right;<br>
                        if (root == this)<br>
                            root = right;<br>
                    }<br>
                    else<br>
                    {<br>
                        Node node = right;<br>
                        while (node.left.left != null)<br>
                            node = node.left;<br>
                        Console.WriteLine("Node: " + node.value);<br>
                        this.value = node.left.value;<br>
                        Console.WriteLine("here");<br>
                        node.left = null;<br>
                    }<br>
                }<br>
                return true;<br>
            }<br>
            return false;<br>
        }<br>
        public Image Draw()<br>
                else<br>
                {<br>
                    if (right.left == null)<br>
                    {<br>
                        right.left = left;<br>
                        if (isLeft) parent.left = right;<br>
                        else<br>
                    parent.right = right;<br>
                        if (root == this)<br>
                            root = right;<br>
                    }<br>
                    else<br>
                    {<br>
                        Node node = right;<br>
                        while (node.left.left != null)<br>
                            node = node.left;<br>
                        Console.WriteLine("Node: " + node.value);<br>
                        this.value = node.left.value;<br>
                        Console.WriteLine("here");<br>
                        node.left = null;<br>
                    }<br>
                }<br>
                return true;<br>
            }<br>
            return false;<br>
        }<br>
        public Image Draw()<br>
        {
                else<br>
                {<br>
                    if (right.left == null)<br>
                    {<br>
                        right.left = left;<br>
                        if (isLeft) parent.left = right;<br>
                        else<br>
                    parent.right = right;<br>
                        if (root == this)<br>
                            root = right;<br>
                    }<br>
                    else<br>
                    {<br>
                        Node node = right;<br>
                        while (node.left.left != null)<br>
                            node = node.left;<br>
                        Console.WriteLine("Node: " + node.value);<br>
                        this.value = node.left.value;<br>
                        Console.WriteLine("here");<br>
                        node.left = null;<br>
                    }<br>
                }<br>
                return true;<br>
            }<br>
            return false;<br>
        }<br>
        public Image Draw()<br>
            Size lSize = new Size(nodeBg.Width / 2, 0);
                else<br>
                {<br>             
                if (right.left == null)<br>
                    {<br>
                        right.left = left;<br>
                        if (isLeft) parent.left = right;<br>
                        else<br>
                    parent.right = right;<br>
                        if (root == this)<br>
                            root = right;<br>
                    }<br>
                    else<br>
                    {<br>
                        Node node = right;<br>
                        while (node.left.left != null)<br>
                            node = node.left;<br>
                        Console.WriteLine("Node: " + node.value);<br>
                        this.value = node.left.value;<br>
                        Console.WriteLine("here");<br>
                        node.left = null;<br>
                    }<br>
                }<br>
                return true;<br>
            }<br>
            return false;<br>
        }<br>
        public Image Draw()<br>
            Size rSize = new Size(nodeBg.Width / 2, 0);
                else<br>
                {<br>
                    if (right.left == null)<br>
                    {<br>
                        right.left = left;<br>
                        if (isLeft) parent.left = right;<br>
                        else<br>
                    parent.right = right;<br>
                        if (root == this)<br>
                            root = right;<br>
                    }<br>
                    else<br>
                    {<br>
                        Node node = right;<br>
                        while (node.left.left != null)<br>
                            node = node.left;<br>
                        Console.WriteLine("Node: " + node.value);<br>
                        this.value = node.left.value;<br>
                        Console.WriteLine("here");<br>
                        node.left = null;<br>
                    }<br>
                }<br>
                return true;<br>
            }<br>
            return false;<br>
        }<br>
        public Image Draw()<br>
            Image lNodeImg = null;
                else<br>
                {<br>
                    if (right.left == null)<br>
                    {<br>
                        right.left = left;<br>
                        if (isLeft) parent.left = right;<br>
                        else<br>
                    parent.right = right;<br>
                        if (root == this)<br>
                            root = right;<br>
                    }<br>
                    else<br>
                    {<br>
                        Node node = right;<br>
                        while (node.left.left != null)<br>
                            node = node.left;<br>
                        Console.WriteLine("Node: " + node.value);<br>
                        this.value = node.left.value;<br>
                        Console.WriteLine("here");<br>
                        node.left = null;<br>
                    }<br>
                }<br>
                return true;<br>
            }<br>
            return false;<br>
        }<br>
        public Image Draw()<br>
            Image rNodeImg = null;
                else<br>
                {<br>
                    if (right.left == null)<br>
                    {<br>
                        right.left = left;<br>
                        if (isLeft) parent.left = right;<br>
                        else<br>
                    parent.right = right;<br>
                        if (root == this)<br>
                            root = right;<br>
                    }<br>
                    else<br>
                    {<br>
                       Node node = right;<br>
                        while (node.left.left != null)<br>
                            node = node.left;<br>
                        Console.WriteLine("Node: " + node.value);<br>
                        this.value = node.left.value;<br>
                        Console.WriteLine("here");<br>
                        node.left = null;<br>
                    }<br>
                }<br>
                return true;<br>
            }<br>
            return false;<br>
        }<br>
        public Image Draw()<br>
            int lCenter = 0, rCenter = 0;
                else<br>
                {<br>
                  if (right.left == null)<br>
                    {<br>
                        right.left = left;<br>
                        if (isLeft) parent.left = right;<br>
                        else<br>
                    parent.right = right;<br>
                        if (root == this)<br>
                            root = right;<br>
                    }<br>
                    else<br>
                    {<br>
                        Node node = right;<br>
                        while (node.left.left != null)<br>
                            node = node.left;<br>
                        Console.WriteLine("Node: " + node.value);<br>
                        this.value = node.left.value;<br>
                        Console.WriteLine("here");<br>
                        node.left = null;<br>
                    }<br>
                }<br>
                return true;<br>
           }<br>
           return false;<br>
        }<br>
        public Image Draw()<br>
            if (this.left != null)
                else<br>
                {<br>
                    if (right.left == null)<br>
                    {<br>
                        right.left = left;<br>
                        if (isLeft) parent.left = right;<br>
                        else<br>
                    parent.right = right;<br>
                        if (root == this)<br>
                            root = right;<br>
                    }<br>
                    else<br>
                    {<br>
                        Node node = right;<br>
                        while (node.left.left != null)<br>
                            node = node.left;<br>
                        Console.WriteLine("Node: " + node.value);<br>
                        this.value = node.left.value;<br>
                        Console.WriteLine("here");<br>
                        node.left = null;<br>
                    }<br>
               }<br>
                return true;<br>
            }<br>
            return false;<br>
        }<br>
        public Image Draw()<br>
            {
                else<br>
                {<br>
                    if (right.left == null)<br>
                    {<br>
                        right.left = left;<br>
                        if (isLeft) parent.left = right;<br>
                        else<br>
                    parent.right = right;<br>
                        if (root == this)<br>
                            root = right;<br>
                    }<br>
                    else<br>
                    {<br>
                        Node node = right;<br>
                        while (node.left.left != null)<br>
                            node = node.left;<br>
                        Console.WriteLine("Node: " + node.value);<br>
                        this.value = node.left.value;<br>
                        Console.WriteLine("here");<br>
                        node.left = null;<br>
                    }<br>
                }<br>
                return true;<br>
            }<br>
            return false;<br>
        }<br>
        public Image Draw()<br>
               lNodeImg = left.Draw();
                else<br>
                {<br>
                    if (right.left == null)<br>
                    {<br>
                        right.left = left;<br>
                        if (isLeft) parent.left = right;<br>
                        else<br>
                    parent.right = right;<br>
                        if (root == this)<br>
                            root = right;<br>
                    }<br>
                    else<br>
                    {<br>
                        Node node = right;<br>
                        while (node.left.left != null)<br>
                            node = node.left;<br>
                        Console.WriteLine("Node: " + node.value);<br>
                        this.value = node.left.value;<br>
                       Console.WriteLine("here");<br>
                        node.left = null;<br>
                    }<br>
                }<br>
                return true;<br>
            }<br>
            return false;<br>
        }<br>
        public Image Draw()<br>
                lSize = lNodeImg.Size;
                else<br>
                {<br>
                    if (right.left == null)<br>
                    {<br>
                        right.left = left;<br>
                        if (isLeft) parent.left = right;<br>
                        else<br>
                    parent.right = right;<br>
                        if (root == this)<br>
                            root = right;<br>
                    }<br>
                    else<br>
                    {<br>
                        Node node = right;<br>
                        while (node.left.left != null)<br>
                            node = node.left;<br>
                        Console.WriteLine("Node: " + node.value);<br>
                        this.value = node.left.value;<br>
                        Console.WriteLine("here");<br>
                        node.left = null;<br>
                    }<br>
                }<br>
                return true;<br>
            }<br>
            return false;<br>
        }<br>
        public Image Draw()<br>
                this.center = lSize.Width;
                else<br>
                {<br>
                    if (right.left == null)<br>
                    {<br>
                        right.left = left;<br>
                        if (isLeft) parent.left = right;<br>
                        else<br>
                    parent.right = right;<br>
                        if (root == this)<br>
                            root = right;<br>
                    }<br>
                    else<br>
                    {<br>
                        Node node = right;<br>
                        while (node.left.left != null)<br>
                            node = node.left;<br>
                        Console.WriteLine("Node: " + node.value);<br>
                        this.value = node.left.value;<br>
                        Console.WriteLine("here");<br>
                        node.left = null;<br>
                    }<br>
                }<br>
                return true;<br>
            }<br>
            return false;<br>
        }<br>
        public Image Draw()<br>
                lCenter = left.center;<br>
            }<br>
            if (this.right != null)<br>
            {<br>
                rNodeImg = right.Draw();<br>
                rSize = rNodeImg.Size;<br>
                rCenter = right.center;<br>
            }<br>
            int maxHeight = (lSize.Height < rSize.Height) ? rSize.Height : lSize.Height;<br>
            if (maxHeight > 0) maxHeight += 35;<br>
        Size resultSize = new Size(lSize.Width + rSize.Width, nodeBg.Size.Height + maxHeight);<br>
            Bitmap result = new Bitmap(resultSize.Width, resultSize.Height);<br>
            Graphics g = Graphics.FromImage(result);<br>
            g.SmoothingMode = SmoothingMode.HighQuality;<br>
            g.FillRectangle(Brushes.White, new Rectangle(new Point(0, 0), resultSize));<br>
            g.DrawImage(nodeBg, lSize.Width - nodeBg.Width / 2, 0);<br>
            string str = "" + value;<br>
            g.DrawString(str, font, Brushes.Black, lSize.Width - nodeBg.Width / 2 + 7, nodeBg.Height / 2f - 12);<br>
            Pen pen = new Pen(Brushes.Black, 1.2f);<br>
            float x1 = center;<br>
            float y1 = nodeBg.Height;<br>
            float y2 = nodeBg.Height + 35;<br>
            float x2 = lCenter;<br>
            var h = Math.Abs(y2 - y1);<br>
            var w = Math.Abs(x2 - x1);<br>
            if (lNodeImg != null)<br>
            {<br>
                g.DrawImage(lNodeImg, 0, nodeBg.Size.Height + 35);<br>
                var points1 = new List<PointF><br>
{<br>
new PointF(x1, y1),<br>
new PointF(x1 - w/6, y1 + h/3.5f),<br>
new PointF(x2 + w/6, y2 - h/3.5f),<br>
new PointF(x2, y2),<br>
};
                g.DrawCurve(pen, points1.ToArray(), 0.5f);<br>
            }<br>
            if (rNodeImg != null)<br>
            {<br>
                g.DrawImage(rNodeImg, lSize.Width, nodeBg.Size.Height + 35);<br>
                x2 = rCenter + lSize.Width;<br>
                w = Math.Abs(x2 - x1);<br>
                var points = new List<PointF><br>
{
new PointF(x1, y1),<br>
new PointF(x1 + w/6, y1 + h/3.5f),<br>
new PointF(x2 - w/6, y2 - h/3.5f),<br>
new PointF(x2, y2)<br>
};<br>
            g.DrawCurve(pen, points.ToArray(), 0.5f);<br>
            }<br>
            return result;<br>
        }<br>
        public bool Exists(int value)<br>
        {<br>
            bool res = value == this.value;<br>
            if (!res && left != null)<br>
                res = left.Exists(value);<br>
            if (!res && right != null)<br>
                res = right.Exists(value);<br>
            return res;<br>
        }<br>
    }<br>
}<br>
    
    

***************************************NOTEPAD**************************

using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>
namespace notepad<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        private string fileName;<br>
        private RichTextBox txtContent;<br>
        private ToolBar toolBar;<br>
        public Form1()<br>
        {<br>
            fileName = null;<br>
            initializeComponents();<br>
        }<br>
        private void Form1_Load(object sender, EventArgs e)<br>
        {<br>
        }<br>
        void initializeComponents()<br>
        {<br>
            this.Text = "My notepad";<br>
            this.MinimumSize = new Size(600, 450);<br>
            this.FormClosing += new FormClosingEventHandler(NotepadClosing); this.MaximizeBox = true;<br>
            toolBar = new ToolBar();<br>
            toolBar.Font = new Font("Arial", 16);<br>
            toolBar.Padding = new Padding(4);<br>
            toolBar.ButtonClick += new ToolBarButtonClickEventHandler(toolBarClicked);<br>
            ToolBarButton toolBarButton1 = new ToolBarButton();<br>
            ToolBarButton toolBarButton2 = new ToolBarButton();<br>
            ToolBarButton toolBarButton3 = new ToolBarButton();<br>
            toolBarButton1.Text = "New";<br>
            toolBarButton2.Text = "Open";<br>
            toolBarButton3.Text = "Save";<br>
            toolBar.Buttons.Add(toolBarButton1);<br>
            toolBar.Buttons.Add(toolBarButton2);<br>
            toolBar.Buttons.Add(toolBarButton3);<br>
            txtContent = new RichTextBox();<br>
            txtContent.Size = this.ClientSize;<br>
            txtContent.Height -= toolBar.Height;<br>
            txtContent.Top = toolBar.Height;<br>
            txtContent.Anchor = AnchorStyles.Left | AnchorStyles.Right | AnchorStyles.Top | AnchorStyles.Bottom;<br>
            txtContent.Font = new Font("Arial", 16);<br>
            txtContent.AcceptsTab = true;<br>
            txtContent.Padding = new Padding(8);<br>
            this.Controls.Add(toolBar);<br>
            this.Controls.Add(txtContent);
        }<br><br><br>
        private void toolBarClicked(Object sender, ToolBarButtonClickEventArgs e)<br><br><br>
        {<br><br><br>
            saveFile();<br><br><br>
            switch (toolBar.Buttons.IndexOf(e.Button))<br><br><br>
            {<br><br><br>
                case 0:<br><br><br>
                    this.Text += "My notepad";<br><br><br>
                    txtContent.Text = string.Empty;<br><br><br>
                    fileName = null;<br><br><br>
                    break;<br><br><br>
                case 1:<br><br><br>
                    OpenFileDialog openDlg = new OpenFileDialog();<br><br><br>
                    if (DialogResult.OK == openDlg.ShowDialog())<br><br><br>
                    {<br><br><br>
                        fileName = openDlg.FileName; txtContent.LoadFile(fileName); this.Text = "My notepad " + fileName;<br><br><br>
                    }<br><br><br>
                    break;<br><br><br>
            }<br><br>
        }<br><br>
        void saveFile()<br><br>
        {<br><br>
            if (fileName == null)<br><br>
            {<br><br>
                SaveFileDialog saveDlg = new SaveFileDialog();<br><br>
                if (DialogResult.OK == saveDlg.ShowDialog())<br><br>
                {<br><br>
                    fileName = saveDlg.FileName;<br><br>
                    this.Text += " " + fileName;<br><br>
                }<br><br>
            }<br><br>
            else<br><br>
            {<br><br>
                txtContent.SaveFile(fileName, RichTextBoxStreamType.RichText);<br><br>
            }<br><br>
        }<br><br>
        private void NotepadClosing(Object sender, FormClosingEventArgs e)<br><br>
        {<br><br>
            saveFile();<br><br>
        }<br><br>
        /* static void Main(String[] args)<br><br>
         {<br>
             Application.Run(new Form());<br>
         }*/<br>
    }<br>
}<br>

    
    ![image](https://user-images.githubusercontent.com/97940064/161210268-ea31beda-fce3-4b6b-9a9f-a0809bf2b2c3.png)
