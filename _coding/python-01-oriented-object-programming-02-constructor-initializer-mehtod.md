---
layout: post
title: "Constructor/Initializer method"
# excerpt: ""
# modified: 2017-11-22T14:17:25-04:00
categories: Python
subcategory: 01 - object oriented programming
tags: [Object oriented programming, Python]
comments: true
share: true
---

The **constructor** is a special method that runs automatically when we create (instantiate) an object. In most languages, the constructor creates and returns the object instance and initializes its attributes.
<br><br>
In **Python**, this operation is divided into two methods:

  - `__new__` (builder)
  - `__init__` (initializer)

The method `__new__` is responsible for creating and returning a new instance of the class. It is an important part of Python metaprogramming, as it allows developers to customize object creation and control how instances are created. It also accepts any arguments that would otherwise be passed to the method `__init__`, which are captured by the ***args** and ****kwargs** parameters. Python already implements these methods by default for each new class created, but you can implement them again, that is, override them. This is how we customize the constructor (initializer).
<br><br>
Although the method `__init__` is just the initializer, it is common to see it as **the constructor**. We rarely need to change the `__new__` to customize our classes, because the community has already adopted the method `__init__` as the constructor of an object in Python.
<br><br>
With that, just recreate the method `__init__` within the class, as shown in the following example: