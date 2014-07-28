Protocol-1
==========

Realisation for Protocol 1 in C#
================================
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

class Program
{
    static void Main()
    {
        Console.WriteLine("Enter the range of the endomorphisms:");
        int n = int.Parse(Console.ReadLine());
        Console.WriteLine("Enter the common endomorphism for Alice and Bob:");
        int[] x = new int[n];
        for (int i = 0; i < n; i++)
        {
            x[i] = int.Parse(Console.ReadLine());
        }
        Console.WriteLine("Enter Alice`s endomorphism:");
        int[] a = new int[n];
        for (int i = 0; i < n; i++)
        {
            a[i] = int.Parse(Console.ReadLine());
        }
        Console.WriteLine("Enter Bob`s endomorphism:");
        int[] b = new int[n];
        for (int i = 0; i < n; i++)
        {
            b[i] = int.Parse(Console.ReadLine());
        }
        int[] aliceFirstStep = new int[n];
        for (int i = 0; i < n;i++ )
        {
            aliceFirstStep[i] = a[i];
        }
        for (int i = 0; i < n; i++)
        {
            aliceFirstStep[i] = x[aliceFirstStep[i]];
        }
        Console.WriteLine();
        Console.WriteLine("Alice`s public key a o x ======>");
        for (int k = 0; k < n; k++)
        {
            Console.Write("{0} ", aliceFirstStep[k]);
        }
        Console.WriteLine();
        Console.WriteLine();
        int[] bobFirstStep = new int[n];
        for (int i = 0; i < n; i++)
        {
            bobFirstStep[i] = x[i];
        }
        for (int i = 0; i < n; i++)
        {
            bobFirstStep[i] = b[bobFirstStep[i]];
        }
        Console.WriteLine();
        Console.WriteLine("Bob`s public key x o b ======>");
        for (int k = 0; k < n; k++)
        {
            Console.Write("{0} ", bobFirstStep[k]);
        }
        Console.WriteLine();
        Console.WriteLine();
        for(int i=0;i<n;i++)
        {
            a[i] = bobFirstStep[a[i]];
        }
        Console.WriteLine("Alice computes kA = a o (x o b) ======>");
        for(int i=0;i<n;i++)
        {
            Console.Write("{0} ", a[i]);
        }
        Console.WriteLine();
        Console.WriteLine();
        for (int i = 0; i < n; i++)
        {
            aliceFirstStep[i] = b[aliceFirstStep[i]];
        }
        Console.WriteLine("Bob computes kB = (a o x) o b ======>");
        for (int i = 0; i < n; i++)
        {
            Console.Write("{0} ", aliceFirstStep[i]);
        }
        Console.WriteLine();
        Console.ReadLine();
    }
}
