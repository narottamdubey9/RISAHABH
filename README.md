# RISAHA









using System;
using System.Collections;
public class Formland_1
{


#pragma warning disable IDE0060 // Remove unused parameter
    public static void Main(string[] args)
#pragma warning restore IDE0060 // Remove unused parameter
    {
        int formland;
        Formland_1 form = new Formland_1();
        ArrayList cnames = new ArrayList(50);
        ArrayList ccolour = new ArrayList(50);
        ArrayList gnames = new ArrayList(50);
        ArrayList gcolour = new ArrayList(50);



        do
        {
            Console.WriteLine("Welcome To Formland");
            Console.WriteLine("Press 1: Add Animal");
            Console.WriteLine("Press 2: Show Animal");
            Console.WriteLine("Press 3: Sort the Animal Name");
            Console.WriteLine("Press 4 :Exit from formland");
            formland = Convert.ToInt32(Console.ReadLine());

            if (formland == 4)
            {
                Console.WriteLine("thanks for visit");
                break;
            }
            else
            {
                switch (formland)
                {
                    case 1:
                        form.addmember(cnames, ccolour, gnames, gcolour);
                        break;
                    case 2:
                        form.showmember(cnames, gnames);
                        break;
                    case 3:
                        form.sortmember(cnames, gnames);
                        break;
                    default:
                        Console.WriteLine("Enter the valid choice");
                        break;
                }
            }

        } while (true);

    }

    public void sortmember(ArrayList cnames, ArrayList gnames)
    {
        ArrayList allname = new ArrayList(20);
        allname.AddRange(cnames);
        allname.AddRange(gnames);

        allname.Sort();

        foreach (Object obj in allname)
         Console.Write( "   {0}", obj );
      Console.WriteLine();
    }
    public void showmember(ArrayList cnames, ArrayList gnames)
    {
        Console.WriteLine("Cow Present:");
        foreach (string element in cnames)
        {
            Console.WriteLine(element);

        }
        Console.WriteLine("Goat Present:");
        foreach (string element in gnames)
        {
            Console.WriteLine(element);

        }
    }
    public void addmember(ArrayList cnames, ArrayList ccolour, ArrayList gnames, ArrayList gcolour)
    {
        int choice;
        string name, colour;
        bool blnFound, blnFound1;
        Console.WriteLine("Press 1: For Cow");
        Console.WriteLine("Press 2: For Goat");
        choice = Convert.ToInt32(Console.ReadLine());
        switch (choice)
        {
            case 1:
                AddCow(cnames, ccolour, gnames);
                break;
            case 2:
                AddGoat(gnames, gcolour, cnames);
                break;
            default:
                Console.WriteLine("Wrong Choice");
                break;
        }
    }
    public void AddGoat(ArrayList gnames, ArrayList gcolour, ArrayList cnames)
    {
        string name, colour;
        bool blnFound, blnFound1;
        Console.WriteLine("Enter the Name of Goat");
        name = Console.ReadLine();
        blnFound = cnames.Contains(name);
        blnFound1 = gnames.Contains(name);
        if (blnFound || blnFound1)
        {
            Console.WriteLine("Animal of this name is already present in farmland");
        }
        else
        {
            gnames.Add(name);
            Console.WriteLine("Enter the colour of Cow");
            colour = Console.ReadLine();
            gcolour.Add(colour);
        }
    }
    public void AddCow(ArrayList cnames, ArrayList ccolour, ArrayList gnames)
    {
        string name,colour;
        bool blnFound, blnFound1;
        Console.WriteLine("Enter the Name of Cow");
        name = Console.ReadLine();
        blnFound = cnames.Contains(name);
        blnFound1 = gnames.Contains(name);
        if (blnFound || blnFound1)
        {
            Console.WriteLine("Animal of this name is already present in farmland");
        }
        else
        {
            cnames.Add(name);
            Console.WriteLine("Enter the colour of Cow");
            colour= Console.ReadLine();
            
        }
    }
}
