using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using CsvHelper;
using MathNet.Numerics.Statistics;

namespace BankDataAnalysis
{
    class Program
    {
        static void Main(string[] args)
        {
            // Read in dataset
            List<BankData> bankData;
            using (var reader = new StreamReader("bank_data.csv"))
            using (var csv = new CsvReader(reader, System.Globalization.CultureInfo.InvariantCulture))
            {
                bankData = csv.GetRecords<BankData>().ToList();
            }

            // Print the first few rows of the data
            foreach (var record in bankData.Take(5))
            {
                Console.WriteLine($"Expected Recovery Amount: {record.ExpectedRecoveryAmount}, Age: {record.Age}, Recovery Strategy: {record.RecoveryStrategy}");
            }

            // Scatter plot of Age vs. Expected Recovery Amount
            // Note: Visualization in C# can be more complex; here, we're just printing the data
            Console.WriteLine("Age vs. Expected Recovery Amount:");
            foreach (var record in bankData.Take(5))
            {
                Console.WriteLine($"Age: {record.Age}, Expected Recovery Amount: {record.ExpectedRecoveryAmount}");
            }

            // Compute average age just below and above the threshold
            var era_900_1100 = bankData.Where(d => d.ExpectedRecoveryAmount < 1100 && d.ExpectedRecoveryAmount >= 900);
            var byRecoveryStrategy = era_900_1100.GroupBy(d => d.RecoveryStrategy);
            foreach (var group in byRecoveryStrategy)
            {
                Console.WriteLine($"Recovery Strategy: {group.Key}, Average Age: {group.Select(d => d.Age).Average()}");
            }

            // Perform Kruskal-Wallis test
            var level0Age = era_900_1100.Where(d => d.RecoveryStrategy == "Level 0 Recovery").Select(d => d.Age).ToArray();
            var level1Age = era_900_1100.Where(d => d.RecoveryStrategy == "Level 1 Recovery").Select(d => d.Age).ToArray();
            var kruskalTestResult = HypothesisTest.KruskalWallis(level0Age, level1Age);
            Console.WriteLine($"Kruskal-Wallis Test p-value: {kruskalTestResult.PValue}");

            // Other statistical tests, modeling, and analysis can be implemented similarly
        }
    }

    public class BankData
    {
        public double ExpectedRecoveryAmount { get; set; }
        public int Age { get; set; }
        public string RecoveryStrategy { get; set; }
        // Add other properties as needed
    }
}


//In this C# version:

   // We use the CsvHelper library to read CSV data into a list of BankData objects.
  //For visualization, we simply print the data rather than creating scatter plots. Visualization in C# can be more complex and typically involves using external libraries or building custom graphical components.
  //  We compute average ages and perform statistical tests using methods provided by the MathNet.Numerics library, which offers functionality similar to SciPy in Python.

//You may need to install the CsvHelper and MathNet.Numerics packages using NuGet Package Manager in Visual Studio or through the command line using dotnet add package. Additionally, ensure that your project is targeting .NET Core or .NET Framework compatible with these libraries.
