using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Change_Tiles
{
    class Program
    {
        static void Main(string[] args)
        {
            decimal saveMoney = decimal.Parse(Console.ReadLine());
            double width = double.Parse(Console.ReadLine());
            double lenght = double.Parse(Console.ReadLine());
            double sideOfTriangle = double.Parse(Console.ReadLine());
            double hightOfTriangle = double.Parse(Console.ReadLine());
            decimal priceOfTile = decimal.Parse(Console.ReadLine());
            decimal master = decimal.Parse(Console.ReadLine());

            double floorArea = width * lenght;
            double tileArea = (sideOfTriangle * hightOfTriangle) / 2;
            double neededTile = Math.Ceiling(floorArea / tileArea) + 5;

            decimal totalSum = (decimal)neededTile * priceOfTile + master;

            if (saveMoney >= totalSum)
            {
                decimal moneyLeft = saveMoney - totalSum;
                Console.WriteLine($"{moneyLeft:f2} lv left.");
            }
            else
            {
                decimal moneyNeeded = totalSum - saveMoney;
                Console.WriteLine($"You'll need {moneyNeeded:f2} lv more.");
            }
        }
    }
}
