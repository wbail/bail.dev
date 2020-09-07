---
layout: post
title: "oop_why_use_interface"
date: "2020-09-04 21:00:00"
category: blog
---

# Why use Interface instead of Implementation

Prefer an **interface** instead of an inplementation.

Why?

Because you'll avoid a high coesion, your code will be independent of other code parts.

Eg:

Let's say we have an interface that will be responsible for persistence into the database.

```
public interface IClientRepository
{
    void AddClient(Client client);
}
```

And we have the class ```ClientRepository``` implementing the interface ```IClientRepository```, implementing the methods.

```
public class ClientRepository : IClientRepository
{
    public void AddClient(Client client)
    {
        //TODO: Save into database
    }
}
```