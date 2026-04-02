using System;
using System.Threading;

class MultiThreadExample
{
    // Method 1
    public static void Method1()
    {
        for (int i = 1; i <= 5; i++)
        {
            Console.WriteLine("Method 1: " + i);
            Thread.Sleep(500); // Pause for 0.5 sec
        }
    }

    // Method 2
    public static void Method2()
    {
        for (int i = 1; i <= 5; i++)
        {
            Console.WriteLine("Method 2: " + i);
            Thread.Sleep(500);
        }
    }

    // Method 3
    public static void Method3()
    {
        for (int i = 1; i <= 5; i++)
        {
            Console.WriteLine("Method 3: " + i);
            Thread.Sleep(500);
        }
    }

    static void Main()
    {
        // Create Threads
        Thread t1 = new Thread(Method1);
        Thread t2 = new Thread(Method2);
        Thread t3 = new Thread(Method3);

        // Start Threads
        t1.Start();
        t2.Start();
        t3.Start();

        // Wait for threads to finish
        t1.Join();
        t2.Join();
        t3.Join();

        Console.WriteLine("All threads completed.");
    }
}
