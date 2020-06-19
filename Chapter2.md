## Naming

![](https://www.aliens-sci.com/wp-content/uploads/2019/01/CleanCode.jpg)


## How much time do you spend writing code vs reading code?! <br/> Indeed, the ratio of time spent reading versus writing is well over 10 to 1 <br/> "Uncle Bob"

## Table of contents
* [Use Intention-Revealing Names](#Use-Intention-Revealing-Names)
* [Avoid Disinformation and Encodings](#Avoi-Disinformation-and-Encodings)
* [Make Meaningful Distinctions](#Make-Meaningful-Distinctions)
* [Use Pronounceable Names](#Use-Pronounceable-Names)
* [Use Searchable Names](#Use-Searchable-Names)
* [Don't Be Cute/Don't Use Offensive Words](#Don't-Be-Cute/Don't-Use-Offensive-Words)
* [Pick One Word per Concept](#Pick-One-Word-per-Concept)
* [Don't Pun ](#Don't-Pun)
* [Solution Domain Names vs Problem Domain Names](#Solution-Domain-Names-vs-Problem-Domain-Names)
* [Add Meaningful Context as a Last Resort ](#Add-Meaningful-Context-as-a-Last-Resort)



Names are everywhere in software. <br\>
We name our variables, our functions, our arguments, classes, and packages.  <br\>
We name our source files and the directories that contain them.  <br\>
We name our jar files and war files and ear files.  <br\>
We name and name and name.  <br\>
Because we do so much of it, we’d better do it well.  <br\>
What follows are some simple rules for creating good names.  <br\>


# Use Intention-Revealing Names
Basically, don't name a variable, class, or method which needs some explanation in comments.

For example:
```swift
var d: Int? // elapsed time in days  
var s: Int?  // elapsed time in seconds
```
Can be named as:
```swift
var timeInDays: Int? // elapsed time in days  
var timeInseconds: Int?  // elapsed time in seconds
```

# Avoid Disinformation and Encodings
Don't refer to a group of accounts as "accountList," whereas it is actually not a List. Instead, name it "accountGroup," "accounts," or "bunchOfAccounts."

Avoid unnecessary encodings of datatypes along with the variable name.

```swift
var accountGroup: String?
var bunchOfAccounts: String
```
It may not be necessary where it is very well known to the entire world that in an employee context, the name is going to have a sequence of characters. The same goes for Salary, which is decimal/float.

# Make Meaningful Distinctions
If there are two different things in the same scope, you might be tempted to change one name in an arbitrary way.

What is stored in emp, which is different from employee or employer ?
```swift
var emp: String?
var employee: String?
var employer: String?

```
How are these classes different?

```swift

class ProductInfo  
class ProductData

```
How do you differentiate between these methods in the same class?

```swift
func getActiveAccount()
func getActiveAccounts()
func getActiveAccountsInfo()

```
So, the suggestion here is to make meaningful distinctions.


# Use Pronounceable Names
Ensure that names are pronounceable. Nobody wants a tongue twister.

This
```swift

var absdegpoi123: Date?
var  modymdhms: AccountGroup?
Int pszqint;
```

vs
```swift

var generationTimeStamp: Date?
var employeeAccount: AccountGroup?
var employeeAccessCount: Int?
```

# Use Searchable Names
Sounds stupid? No. <br/>

You need to search the code to see the different fields used.<br/>
Yes, it is true that the new IDE"s can make the job for us,<br/>
but we still have to use names that can be easily searched. <br/>

For example, how easy it is to find where "i" or "j" was used.<br/>
The same thing is happening with magic words that are used inline, without extracting them as constants.<br/>

For example searching and replacing a number value in an application can be a nightmare <br/>
if the same value was used in line for different use cases.

# Don't Be Cute/Don't Use Offensive Words

Don't use funny names or any sort of slang while naming your items.<br/>
Don't use culture dependent jokes.<br/>
Again , focus on the clarity. Say what you mean , Mean what you say.<br/>
```swift
deleteAllItems()
```
vs
```swift
whack()
```
vs
```swift
kill()
```
vs
```swift
eatMyShorts()
```
vs
```swift
abort()
```

# Pick One Word per Concept

Use the same concept across the codebase.
```swift
FetchValue() vs GetValue() vs RetrieveValue()
```
If you are using fetchValue() to return a value of something, use the same concept; instead of using fetchValue() in all the code, using getValue(), retrieveValue() will confuse the reader.
```swift
dataFetcher() vs dataGetter() vs dataFetcher()
```
If all three methods do the same thing, don't mix and match across the code base. Instead, stick to one.
```swift
FeatureManager vs FeatureController
```
Stick to either Manager or Controller. Again, consistency across the codebase for the same thing.


# Don't Pun
This is exactly opposite of previous rule.<br/>
Avoid using the same word for two different purposes.<br/>
Using the same term for two different ideas is essentially pun.

For example, say you have two classes having the same add() method.<br/>
In one class, it performs addition of two values, in another, it inserts an element into a list.<br/>
So, choose wisely; in the second class use insert() or append() instead of add().

# Solution Domain Names vs Problem Domain Names
The clean code philosophy suggests using solution domain names such as the name of algorithms or the name <br/>
of design patterns whenever needed, and use a problem domain name as the second choice.<br/>

For example, accountVisitor means a lot to a programmer who is familiar with the Visitor design pattern.<br/>
A "JobQueue" definitely make more sense to a programmer.

# Add Meaningful Context as a Last Resort 

While there are a few names which are meaningful themselves, most are not.<br/>
Instead, you have to place names in context for your reader by enclosing them<br/>
in well-named classes, functions, or namespaces. <br/>
If not possible, prefixing the names may be necessary as a last resort.
<br/>
For example, the member variable named "state" inside the address class shows what it contains. <br/>
But the same "state" may be misleading if used to store "Name of The State" without context.<br/>
So, in this scenario, name it something like "addressState" or "StateName."<br/>

The "state" may make more sense in a context where you are coding about addresses when named "addrState."<br/>


# Avoid Encoding
Don"t try to reinvent the wheel and define your own encoding for things that were already defined and standardized. <br/>
The last thing that you want to have is your own custom language.<br/>

Because of this, try to use prefix like "I" for interfaces or "Base" suffix for abstract classes.<br/>
Don"t use "C" prefix for class implementation or "m_" for variables.<br/>

If you end up with a custom encoding, take a step back and try to see why you have ended up in this situation.<br/>
Based on that response, you should make a decision.

# Avoid Mental Mapping
Let"s start with an example:
```swift 
r
t
p
```
Even if we are developers, we don"t want to learn and memorize that "r" means full url of Dacia server from Romania,<br/>
"t" is the same url but without protocol information and "p" represent the query parameters<br/>
that we need to send to the server to be able to login.<br/>

Even if mental mapping is bad, there are some names that are standard in our days.<br/>
For example, when we see an "i" or "j" we know from the first moment that we are talking about an iteration.

# Class and Method naming
There are two simple rules that can help us a lot when we need to find a good name to our class or methods:<br/>

* A class name should have a noun or noun phrase
* A method name should have a verb of a verb phrase <br/>
Try to avoid naming classes with prefixes/suffixes like "Service", "Factory", "Processor", "Data", "Info".<br/>
These class names are overused (especially when we don"t find better names).

# Use names from Solution and Problem domain name
Don"t use names that are out of context and are not from that specific domain. It is more natural for someone that works in automotive industry to use "engine" and not "power source". You should use the specific domain names and not developers naming, that can be wrong.

This can be a cause of misunderstanding between clients and developers.

# Don"t Add Gratuitous Context
It is pretty easy to add context to things that are already clear. <br/>
For example in a class called "Car" you don"t need to name the color field of the class "carColor" or "colorCar".<br/>
You are already in the car class and all information from this class is related to "Car".<br/>

