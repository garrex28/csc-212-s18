# Lab 12: #hashtable spel checkinng

## 1. Introduction
In today's lab we will be spell checking large text files using Hash Tables and Balanced Binary Search Trees. This may sound like a lot of work, but luckily you don't actually have to implement the data structures you're going to be using this time. Instead, you will be utilizing the C++ implementations of four different types of containers, provided through the C++11 Standard Template Library (STL). Specfically we will use the following classes:

+ [`unordered_set`](http://en.cppreference.com/w/cpp/container/unordered_set)
+ [`set`](http://en.cppreference.com/w/cpp/container/set)
+ [`unordered_map`](http://en.cppreference.com/w/cpp/container/unordered_map), and
+ [`map`](http://en.cppreference.com/w/cpp/container/map)

The STL implements `set` and `map` as Red-Black Trees, and `unordered_set` and `unordered_map` as Hash Tables.

## 2. Unordered Sets (a la Hash Tables)

The first implementation we will look at is an [`unordered_set`](http://en.cppreference.com/w/cpp/container/unordered_set), named as such for a good reason. Consider a hash table, are the elements sorted in a specific order? Not really, as you can't simply read the elements low to high for example. Additionally, the reason for being called a "set" comes directly from set theory, a branch of mathematics, in which a set is a collection of distinct object. In other words, each element that *could* be in the set is either in the set or not in the set, there is no "amount" associated with a given element. The linked reference below suggests that unordered sets are typically implemented using hash tables with separate chaining. There are a myriad of operations that you can perform on a set. Look at the site below on sets to familiarize yourself with the basic operations. [Unordered Sets (reference)](http://en.cppreference.com/w/cpp/container/unordered_set)

Here is an example of creating a basic set:

```C++
#include <unordered_set>
#include <string>

int main()
{
	std::unordered_set<std::string> myset; // creating a set of strings
	
	myset.insert("cat");
	myset.insert("dog");
	myset.insert("horse");
	
	// ...
}

```

Congrats you just made a Hash Table!
<p><img src="http://www.staples-3p.com/s7/is/image/Staples/s0105150_sc7?$splssku$" width="144"></p>

### 2.1 Your Turn
Your job is to write a program to determine if the words of the three books that we used in [lab 9](https://github.com/URI-CSC/csc-212-f17/tree/master/lab-09) are in a dictonary. The script used to download the books has been included in this repository once again, and the command is once again:

```bash
$ source getbooks.sh
```

We will also be comparing against the words that are part of your docker images' built in dictionary. I have include a dictionary for the students that are not using docker. But if you are using docker, all you need to do is run:

```bash
$ cp /usr/share/dict/american-english .
```

and the dictionary will be copied to you directory. 

Your goal is to read all of the words in the 'american-english' dictionary to the unordered set, and then you will read each of the book, and output words that have spelling errors. The starter code will include the necessary code to open the files, and get the tokens.

## 3. Sets (a la Red-Black Trees)

Sets are very similar to unordered sets, except that the data inside is arranged in a specfic order (shocking, isn't it?). The way the STL achieves this is through a Red-Black Tree. If you look at the [reference site for a set](http://en.cppreference.com/w/cpp/container/set), you will note that most of the operations are similar to that of an unordered set. This goes to show that even though these two types of containers have so much in common in terms of functionality, their underlying data structures are actually very different.

### 3.1 Your Turn

In your main file, you will find a section where you can implement the spell checker using a set. Once you are done, you can use the main file to time the two data structures to see which one is faster.

Make sure you compile with C++11, as we are using the chrono library to time the methods. For example:

```bash
g++ -g -Wall -std=c++11 main.cc -o hashtables
```

## 4. Unordered Maps



## 5. Maps



## 6. Questions

The google form is linked [here](https://docs.google.com/forms/d/e/1FAIpQLSdCnVWK7FqA3pbFfQaxuawVdiGuEUW9E2dWSw7S3Oja9p921A/viewform?usp=sf_link).

* What is the time needed to run the spell checker across the three books using an unordered set?
* What is the time needed to run the spell checker across the three books using a set?
* Which one is faster, can you think of some reason why?