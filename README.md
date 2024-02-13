# Available-Encapsulation
Library to add the `own` keyword to a programming language to make properties or methods only public to instances of the same class.

### Crazy ideas

Let's create a keyword to avoid declaring a constructor that is just going to use the base/super one. (Let's say a way to mark it as one)

Class A only allows objects of class B to use its properties.

public class A
{
  internal void Foo();
}

public class B 
{
  private void Bar()
  {
    A.Foo();
  }
}

But this is in the case A and B are in the script or assembly, what keyword do we need to allow B use members of A without exisiting in the same script? something obvious is to extend A from B or use an interface between them, but in the case we need more complex relation between both clases? Well in first place why would we need to have such disposion in first place? Something we can address is the dependency relation we would need, in a UML diagram only calling A without any other presence (signature type, field type)

Script: A.cs

public class A
{
  keyword void Foo();
}


Script: B.cs

public class B
{
  private void Bar()
  {
    A.Foo();
  }
}
