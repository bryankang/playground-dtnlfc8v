## Introduction
Delegates are objects that act as methods. These methods can be static, instance, lambda, etc. Internally, a delegate is transformed into a class of its own. This is why people typically define them outside of a class.

```cs
public delegate int Transformer (int x);
```

This delegate takes an int argument and returns an int.

```cs
static int Square (int x) = x * x;
Transformer t = Square; // shorthand for: new Transformer(Square)
```

Because `Square` follows `Transformer`'s signature, we can assign it as a `Transformer` type.

```cs
int x = t(4) // x = 16
```

As you can see, a delegate is very abstract as it can be described as something that takes in a number of certain types of arguments and returns a certain type. So how do you name a delegate type? In our example above, we used the name `Transformer`. It really depends on the context.

```cs
static int Add (int x) => x + x;
t += Add;
int x = t(3) // x = 6
```

You can also multicast delegates. Each method is called in the order it was added to the delegate. However, the return value will be the result of the last method.


## Practice
* Create a delegate that takes in an int and returns void.
* Create and attach 2 static methods to a delegate object. Each static method should use `Console.WriteLine` to output the int that was passed in.
* Call the delegate and observe the order in which the methods were called.

```C# runnable
using System;

namespace App
{
    class DelegateExample
    {
        static void Main(string[] args)
        {
            
        }
    }
}
```
