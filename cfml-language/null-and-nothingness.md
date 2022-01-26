# Null & Nothingness

What is nothingness? Is there nothingness only in outer space? If a tree falls in the forest and nobody is there to listen, does it make a sound? Starting to see the point? Does nothing really mean nothing? To be or not to be? OK, I think we are going in a philosophical tangent, so let's get back to our geekiness:

`null` is Java's way to refer to "nothingness.", something that does not exist and has no value. Support for the`null`keyword itself was introduced as an option in ColdFusion 2018 \(as discussed in [this blog post](https://coldfusion.adobe.com/2018/07/null-support-in-coldfusion-2018/)\) and has existed as an option in Lucee \(as discussed in [this guide](https://docs.lucee.org/guides/cookbooks/NullSupport.html)\).

## Usage

Use the `isNull()` method to evaluate for nothingness and use the `null` keyword to create a null value (ACF 2018+, Lucee 4.1+). In previous versions, use the function call `javaCast( "null", "" )` for ACF or in Lucee you can use the `nullValue()` function. Take note that in Adobe CF 2018+ you must enable the setting. 

## In Practice

If you have three eggs, eat three eggs, then you might think you have "nothing", but in terms of eggs you have "0". Zero is something, it’s a number, and it’s not nothing.

If you’re working with words and have a string like "hello" then delete the "h", "e", "l"s, and "o" you might think you’d end up with nothing, but you really have "" which is an empty string. It’s still something.

Null in CFML is usually encountered when you ask for something that doesn’t exist. When looking at arrays, for instance, we created a list with five elements then asked CFML to give us the sixth element of that list. There is no sixth element, so CFML gave us null. It isn’t that there’s a blank in that sixth spot \(""\), it’s not a number 0, it’s nothingness – null.

**Examples**

```java
function getData( filter ){

    if( isNull( arguments.filter ) ){
      // then do this
    } else {
      // use the filter
    }

}

function returnsNull(){
  if( key.exists( "invalid" ) ){
    return key[ "invalid" ];
  }
}

results = returnsNull();

writeOutput( isNull( results ) );
```

Also note that if a function returns **nothing** it will be the same as returning `null`.

