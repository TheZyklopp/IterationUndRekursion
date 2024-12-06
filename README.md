# IterationUndRekursion
````csharp
namespace IterationUndRekursion
{
    internal class Program
    {
        static void Main(string[] args)
        {
            // Testen der Umdrehen-Methoden
            string testString = "HTW Berlin";
            Console.WriteLine($"Original: {testString}");
            Console.WriteLine($"Iterativ umgedreht: {UmdrehenIterativ(testString)}");
            Console.WriteLine($"Rekursiv umgedreht: {UmdrehenRekursiv(testString)}");

            // Testen der CountDown-Methoden
            int countdownStart = 5;
            Console.WriteLine("Iterativer Countdown:");
            CountDownIterativ(countdownStart);
            Console.WriteLine("Rekursiver Countdown:");
            CountDownRekursiv(countdownStart);
        }

        public static string UmdrehenIterativ(string eingabe)
        {
            char[] charArray = eingabe.ToCharArray();
            Array.Reverse(charArray);
            return new string(charArray);
        }

        public static string UmdrehenRekursiv(string eingabe)
        {
            if (eingabe.Length <= 1)
                return eingabe;
            return UmdrehenRekursiv(eingabe.Substring(1)) + eingabe[0];
        }


        public static void CountDownIterativ(int t)
        {
            for (int i = t; i >= 0; i--)
            {
                Console.WriteLine(i);
                Thread.Sleep(1000);
            }
        }


        public static void CountDownRekursiv(int t)
        {
            if (t < 0)
                return;
            Console.WriteLine(t);
            Thread.Sleep(1000);
            CountDownRekursiv(t - 1);
        }
    }
}