---
layout: post
title: Swift Extensions - Programming with Swift
description: "Just about everything you'll need to style in the theme: headings, paragraphs, blockquotes, tables, code blocks, and more."
modified: 2016-04-09 4:11:00
tags: [iOS, Swift 2.2]
---

## What is an Extension in Swift?

Extensions allow the developer to add new functionality to an existing class, structure or enumeration. This allows you to extend types which you do not have access to, or you could extend a type so that it can follow a new protocol.

## Example:

If you are building a program and that program needs to run a Double through a specific formula or process, then you can use an extension to extend the native Double functionality like I did below to convert Celsius to Fahrenheit and vice versa.

{% highlight swift %}

// this is how you start an extension, with the extension keyword
// followed by the type that you want to extend

extension Double {

    // Computed properties
    var fahrenheitToCelsius: Double
    {
        let converted: Double = (self - 32) / 1.8
        return converted
    }

    var celsiusToFahrenheit: Double
    {
        let converted: Double = (self * 1.8) + 32
        return converted
    }
}

print("34,5 degress Celsius is \(34.5.celsiusToFahrenheit) Fahrenheit")
print("98,2 degress Fahrenheit is \(98.2.fahrenheitToCelsius) Celsius")

{% endhighlight %}


So what is going on in this code? First thing that I am doing is declaring the extension for type Double with

{% highlight swift %}

extension Double {
    // code goes here
}

{% endhighlight %}

The code inside the extension will become accessible when using that type. So in the print functions I am using the value of 34.5 degrees celsius and then using the .celsiusToFahrenheit property of type Double to convert 34.5C to 94.1F

## Conclusion:

Extensions are extremely powerful. They really allow one to keep ones code clean and easily readable. Another great thing about extensions is that the dev does not need to name the file in any special way like one had to with Objective C.

Example code : <a href="https://github.com/Maccle415/ProgrammingWithSwift/tree/master/Extensions.playground" target="_blank">GitHub</a> 