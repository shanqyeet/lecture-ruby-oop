# Introduction to OOP 

*Object Oriented Programming* 

+++

### What is it?
OOP is a programming language model organized around **objects** rather than **actions** *and* **data** rather than **logic**

+++

### Example 

```
program Fibonacci;

function fib(n: Integer): Integer;
var a: Integer = 1;
    b: Integer = 1;
    f: Integer;
    i: Integer;
begin
  if (n = 1) or (n = 2) then
     fib := 1
  else
    begin
      for i := 3 to n do
      begin
         f := a + b;
         b := a;
         a := f;
      end;
      fib := f;
    end;
end;

begin
  WriteLn(fib(6));
end.

```

+++

### working without class

How would you store and manipulate information of a student?

+++

### Example

```ruby
students = [["first_name", "last_name", "age"]]

p "#{students[0] #{student[1]}"

#or

john = {"first_name":"john", "last_name":"Coder","age":"23"}

p "#{john[first_name]} #{john[last_name]}"

```

How would you call the student's full name? No so efficient isnt it?

+++

### How OOP boosts speed and efficiency

In our daily life - it is natural that we think of things as objects with attribute and behavior hence the way we interact with them.

---

# Class in Ruby 

put simply - an Object:
  1. has common attributes
  2. has common functions/methods
  3. is reusable

+++

### Example of class

```ruby
class Student 
  def initialize(first_name, last_name, age)
    @first_name = first_name 
    @last_name = last_name
    @age = age.to_i 
  end  
end 

```
+++
You already know **Local  & Global Variable**

### Introducing :
  * Instance Variable - available across methods, example **@name** 

  * Class Variable - available across different object, example **@@name**

---

# Methods in class

+++

### Reading the object's attributes

```ruby
class Student 

  *some other codes here*

  def name 
    @name
  end 

end 

```
+++

### Make changes to the object's attributes

```ruby
class Student
 
  *some other codes*

  def name=(name)
  	@name = name 
  end

end

```
+++

### There is actually shortcuts

```ruby
class Student 
	#you can write this 
	attr_accessor :first_name, :last_name, :age
end 

```  
+++

### Or.. you can write them this way
```
class Student
  attr_reader :name, :age 
  attr_writer :name, :age 
end
```

+++

### How about some custom functions?

```ruby
class Student 
	
	*some other codes here*

	def hello 
	  print "@name says: Hello Everyone I'm @name"
	end 

	def age_plus 
		@age += 1 
	end 
end

``` 

---
# "Self" in Ruby

You may have heard people say that everything in Ruby is an object. **If that's true it means that every piece of code you write "belongs" to some object.**

+++

### What????

Basically, "self" refers gives you access to the current object

+++

### Using Self -  Inside an instance method

```
class Random
  def reflect
    self
  end 
end 

g = Random.new

p g.reflect #=> <Random: some alphanumerics>

p g  #=> <Random: same alphanumerics>

p g.reflect == g #=> true

```

+++

### Using Self - inside of a class method

```
class Random
  def self.reflect
    self 
  end
end 

p Random.reflect == Random #=> true

```





