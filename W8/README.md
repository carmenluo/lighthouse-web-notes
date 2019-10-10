## Strongly typed VS weakly typed
Strongly typed: will check variable's type before excution whereas weakly typed doesn't.
Strongly typed: will need to explicitely cast variable whereas weakly typed doesn't

## Dynamically typed VS Statically typed
Statically typed: Every name is bound to a type at compile time and an object
Dynamiclly typed: Every name is bound to an object
```
employeeName = 9
employeeName = "Steve Ferg"
```
The above code is illegle in statically type
Dynamically typed and weakly typed language can provide flexibility for developer, but for strongly typed and statically we 
are expected to check the type at compile time so that it can have better performance
Ruby is strongly typed, so "4.0" / 2 is illeagal. we need to convert it to int first with "4.0".to_i

when we bring in argv, basically it won't work with gets.chomp anymore. we need to use $stdin.gets.chomp

## Ruby block, yields
When a method expects a block, it invokes it by calling the <code>yield</code> function.
```
class Person 
    def initialize( name ) 
         @name = name
    end

    def do_with_name 
        yield( @name ) 
    end
end
```

In this case, we initialize Person then we can use do_with_name to do differnent things with the name.
```
person = Person.new("Oscar")

#invoking the method passing a block
person.do_with_name do |name|
    puts "Hey, his name is #{name}"
end

person.do_with_name do |name|
  puts "#{name.reverse}"
end
```

Another example:
```
def foo(x)
  puts "call from foo and params #{x}"
  yield"You want this!!" if block_given?
end

foo(10)
foo(123) do |name|
  puts "are you going to give me something? #{name}"
end
```
output:
```
call from foo and params 10
call from foo and params 123
are you going to give me something? You want this!!
```

Block is kinda like method, in normal method, we pass arguments into method, so it is just like we pass behavior into method.
we use yield to pass whatever in there to the block 
Below is an experiment: when we see yield on the right hand side of =, it means that it would invoke the block and get the 
result to send back to result_from_block.
if yield is on the left hand side, we can see it as a hint to send whatever follows yield to the block and compute the result.
```
def print_result
  result_from_block =yield
  puts "print_result: #{result_from_block}"
end

# this is going to print the number "9"
print_result{3 * 3}

def send_params
  yield 3
end
#this would also print number 9
send_params do |item|
  puts "#{item * item}"
end

```
