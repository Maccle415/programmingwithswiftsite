---
layout: post
title: Swift Protocols - Programming with Swift
description: "iOS app development - Learning Swift Protocols - Programming with Swift"
modified: 2016-04-10 4:11:00
tags: [iOS, Swift 2.2]
---

## What is a Protocol?

A protocol is a guideline for properties and methods etc. Protocols do not have an implementation they are only a set of rules that the implementation needs to follow.

If you create a protocol for drawing a square then you might create a method called rect in the protocol. If you then create a class which adopts the protocol then that class would need to implement the rect function.

## Basic Example:

We know that when a class, struct or enumeration adopts a protocol that it needs to implement the protocols functions, properties and anything else that it has.

Below I created a simple protocol that has a function called toUpper which will take a string argument and convert the string to be uppercase.

{% highlight swift %}

protocol StringToUpperCase
{
    func toUpper(input: String) -> String
}

class StringClass: StringToUpperCase
{
    /*

    If you comment out this protocol function you will get an error

    */
    func toUpper(input: String) -> String
    {
        return input.uppercaseString
    }
}

var stringVar: StringClass = StringClass()
var uppcaseString: String = stringVar.toUpper("test string")

print(uppcaseString)


{% endhighlight %}

In the first line we are declaring thenew protocol by doing the following

{% highlight swift %}

protocol StringToUpperCase
{
    // functions, properties and anything else goes in here
}

{% endhighlight %}

Then to implement the protocol we add the protocol to the class by writing a colon after the class name and then writing the protocol name.

{% highlight swift %}

class StringClass: StringToUpperCase
{
    // class code goes here, and the protocol's functions, properties etc need
    // need to be added to this class
}

{% endhighlight %}

In the class we will need to implement the functions or properties that were added to the protocol.

## Adding properties to a Protocol:

{% highlight swift %}

var propOne: Int { get }
var propTwo: Int { get set }

{% endhighlight %}