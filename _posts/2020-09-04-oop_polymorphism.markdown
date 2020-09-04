---
layout: post
title: "oop_polymorphism"
date: "2020-09-04 16:22:10"
category: blog
---

## Polymorphism

In this post I'll explain what is polymorphism and how to use it.

As Bjarne Stroustrup (C++ creator) describes in his definition, what is polymorphism:

### Definition

> Providing a single interface to entities of different types. Virtual functions provide dynamic (run-time) polymorphism through an interface provided by a base class. Overloaded functions and templates provide static (compile-time) polymorphism.

## Implementation

Now some code:

The ```Equipment``` class, is an abstract class that will be used as a base class.
An abstract class can't be instantiated.

```
public abstract class Equipment
{
    private readonly string _name
    private readonly int _voltage

    protected Equipment(string name, int voltage)
    {
        _name = name;
        _voltage = voltage;
    }

    public abstract void TurnOn();

    public abstract void TurnOff();
}
```

The ```ComputerEquipment``` class, is the specialization class from the base class ```Equipment```. As we can see the base methods were implemented using the the keyword ```override```, now the methods have their own implementations, their own logic.

```
public class ComputerEquipment : Equipment
{
    public ComputerEquipment(string name, int voltage)
        : base(name, voltage) { }
    
    public ComputerEquipment()
        : base("Laptop", 220) { }

    public override TurnOn()
    {
        // TODO:
    }

    public override TurnOff()
    {
        // TODO: 
    }
}
```
