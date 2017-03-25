# Solar System 

### Declaration of an indexer is to some extent similar to a property. The difference is that indexer accessors require an index. 
#### Like a property, you use get and set accessors for defining an indexer. However, where properties return or set a specific data member, indexers return or set a particular value from the object instance. 
#### ndexers are defined with the<b> this</b> keyword.
#### For example:
```C#
class Clients {
  private string[] names = new string[10];

  public string this[int index] {
    get {
      return names[index];
    }
    set {
      names[index] = value;
    }
  }
}
```
#### The <b>indexer</b> definition includes the <b>this keyword and an index</b>, which is used to get and set the appropriate value.
#### Now, when we declare an object of class Clients, we use an index to refer to specific objects like the elements of an array:
```C#
Clients c = new Clients();
c[0] = "Dave";
c[1] = "Bob";

Console.WriteLine(c[1]);
//Outputs "Bob"  
```

<h2>In the program were  using  <i><b>Indexer methods</b></i>,  <i><b>Exception handlings</b></i> and <i><b>Extension Methods.</b></i></h2>
```C#
namespace Solar_System
{
    class SolarSystem
    {
        string[] planets = { "The Sun", "Mercury", "Venus", "Earth",
            "Mars", "Jupiter", "Saturn","Uranus", "Neptune", "Pluto" };
        private int GetPlanet(string testPlanet)
        {
            for (int j = 0; j < planets.Length; j++)
            {
                if (planets[j] == testPlanet)
                {
                    return j;
                }
            }
            throw new ArgumentOutOfRangeException
                (testPlanet, "testPlanet must be correct name of the planet");
        }
        public int this[string planet]
        {
            get
            {
                return GetPlanet(planet);
            }
        }
    }
    class Program
    {
        static void Main(string[] args)
        {
            SolarSystem plan = new SolarSystem();
            Console.WriteLine("Please enter name of planet to know its number from the set \"The Sun, Mercury, Venus, Earth,Mars, Jupiter, Saturn, Uranus, Neptune, Pluto\" ");
            string st =Console.ReadLine();
            st = st.UppercaseFirstLetter();
            Console.WriteLine(plan[st]);

            //Console.WriteLine(plan["Marsss"]);

            Console.WriteLine("Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```
![solar-system](https://cloud.githubusercontent.com/assets/20840005/22181403/0fe123d2-e0a5-11e6-8e16-444ea69f484b.jpg)

<h3> When we are entering the correct name of the planet, the program is returning its <i><b>number</b></i> of Galaxy.<br>
And if the name of the planet is in the incorrect form, there is happening <i><b>exception</b></i>.<br>
For example <i><b>Marssss</b></i>.</h3>

![sol sys3](https://cloud.githubusercontent.com/assets/25159667/22185455/5025a86e-e0ff-11e6-89c4-fca26855e3b0.gif)
