using System;
using System.Collections.Generic;
using System.Linq;

namespace VacunacionCOVID
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.OutputEncoding = System.Text.Encoding.UTF8;

            // --- 1) Conjunto total de ciudadanos (50 ficticios) ---
            var ciudadanos = new HashSet<string>();
            for (int i = 1; i <= 50; i++)
            {
                ciudadanos.Add($"Ciudadano {i}");
            }

            // --- 2) Vacunados con Pfizer (ficticios) ---
            var vacunadosPfizer = new HashSet<string>
            {
                "Ciudadano 1","Ciudadano 2","Ciudadano 3","Ciudadano 4","Ciudadano 5",
                "Ciudadano 10","Ciudadano 12","Ciudadano 14","Ciudadano 15","Ciudadano 18",
                "Ciudadano 20","Ciudadano 22","Ciudadano 25","Ciudadano 28","Ciudadano 30",
                "Ciudadano 33","Ciudadano 35","Ciudadano 38","Ciudadano 40","Ciudadano 45"
            };

            // --- 3) Vacunados con AstraZeneca (ficticios) ---
            var vacunadosAstraZeneca = new HashSet<string>
            {
                "Ciudadano 3","Ciudadano 4","Ciudadano 5","Ciudadano 6","Ciudadano 7",
                "Ciudadano 15","Ciudadano 18","Ciudadano 19","Ciudadano 22","Ciudadano 24",
                "Ciudadano 28","Ciudadano 29","Ciudadano 30","Ciudadano 32","Ciudadano 33",
                "Ciudadano 36","Ciudadano 38","Ciudadano 39","Ciudadano 40","Ciudadano 50"
            };

            // --- 4) Operaciones de teoría de conjuntos ---
            // No vacunados = U - (P ∪ A)
            var noVacunados = ciudadanos.Except(vacunadosPfizer.Union(vacunadosAstraZeneca));

            // Ambas dosis = P ∩ A
            var ambasDosis = vacunadosPfizer.Intersect(vacunadosAstraZeneca);

            // Solo Pfizer = P - A
            var soloPfizer = vacunadosPfizer.Except(vacunadosAstraZeneca);

            // Solo AstraZeneca = A - P
            var soloAstraZeneca = vacunadosAstraZeneca.Except(vacunadosPfizer);

            // --- 5) Mostrar resultados ---
            ImprimirResumen(ciudadanos.Count, vacunadosPfizer.Count, vacunadosAstraZeneca.Count,
                            noVacunados.Count(), ambasDosis.Count(), soloPfizer.Count(), soloAstraZeneca.Count());

            Imprimir("Ciudadanos que NO se han vacunado", noVacunados);
            Imprimir("Ciudadanos con AMBAS dosis", ambasDosis);
            Imprimir("Ciudadanos con SOLO Pfizer", soloPfizer);
            Imprimir("Ciudadanos con SOLO AstraZeneca", soloAstraZeneca);
        }

        static void ImprimirResumen(
            int total, int nPfizer, int nAstra, int nNoVac, int nAmbas, int nSoloPf, int nSoloAz)
        {
            Console.WriteLine("===================================================");
            Console.WriteLine("   RESUMEN CAMPAÑA DE VACUNACIÓN (DATOS FICTICIOS) ");
            Console.WriteLine("===================================================");
            Console.WriteLine($"Total ciudadanos:                 {total}");
            Console.WriteLine($"Vacunados con Pfizer:             {nPfizer}");
            Console.WriteLine($"Vacunados con AstraZeneca:        {nAstra}");
            Console.WriteLine($"Con ambas dosis (Pfizer y Astra): {nAmbas}");
            Console.WriteLine($"Solo Pfizer:                      {nSoloPf}");
            Console.WriteLine($"Solo AstraZeneca:                 {nSoloAz}");
            Console.WriteLine($"No vacunados:                     {nNoVac}");
            Console.WriteLine("===================================================\n");
        }

        static void Imprimir(string titulo, IEnumerable<string> lista)
        {
            Console.WriteLine($"\n--- {titulo} ---");
            foreach (var c in lista.OrderBy(x => x))
            {
                Console.WriteLine(c);
            }
        }
    }
}
