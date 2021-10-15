# Functions

## Definitions And Call
* SQL
```sql
CREATE PROCEDURE citycount (IN country CHAR(3), OUT cities INT)
BEGIN
 SELECT COUNT(*) INTO cities FROM world.city
 WHERE CountryCode = country;
END

CALL citycount('JPN', @cities);

CREATE FUNCTION hello (s CHAR(20))
RETURNS CHAR(50) DETERMINISTIC
RETURN CONCAT('Hello, ',s,'!');

SELECT hello('world');
```
* Cpp
```cpp
auto g() { return f(); }
```

* Matlab
```m
% single file
function [m,s] = stat3(x)
    arguments
        x (1,:) {mustBeNumeric, mustBeFinite}
    end
    n = length(x);
    m = avg(x,n);
    s = sqrt(sum((x-m).^2/n));
end

function m = avg(x,n)
    m = sum(x)/n;
end
```

* Excel

* Perl
```perl
# @_, $_[0]
sub PrintHash {
   my (%hash) = @_;

   foreach my $key ( keys %hash ) {
      my $value = $hash{$key};
      print "$key : $value\n";
   }
}
%hash = ('name' => 'Tom', 'age' => 19);

sub Average {
   # get total number of arguments passed.
   $n = scalar(@_);
   $sum = 0;

   foreach $item (@_) {
      $sum += $item;
   }
   $average = $sum / $n;

   return $average;
}
$num = Average(10, 20, 30);
```

* Mathematica
```wl
f[x_] := x^2
f[a]

f[#, a, #, b] &[x, y] --f[x,a,y,b]
f[#1, #2, #1, #3] &[x, y, z]

f[x, ##, y, ##] &[a, b, c, d]
f[##2] &[a, b, c, d] -- f[b,c,d]

Map[f, {a, b, c, d, e}]
f /@ {a, b, c, d, e}

Apply[f, {a, b, c, d}]
f @@ {a, b, c, d}

```

* Bash
```sh
hello_world () {
   echo 'hello, world'
}
function function_name { commands; }
```

* Haskell
```hs
map                     :: (a->b) -> [a] -> [b]
map f  []               =  []
map f (x:xs)            =  f x : map f xs

map (add 1) [1,2,3] -- [2,3,4]
-- $ pri
```

* Python
```py
def whats_on_the_telly(penguin=None):
    if penguin is None:
        penguin = []
    penguin.append("property of the zoo")
    return penguin
```

* Lua
```lua
function f(a, b) return a or b end
```

* Ruby
```rb
def multiply(val1, val2 )
     result = val1 * val2
     puts result
end
```

* Scala
```scala
def add(x: Int, y: Int): Int = x + y
def addThenMultiply(x: Int, y: Int)(multiplier: Int): Int = (x + y) * multiplier
def name: String = System.getProperty("user.name")

val add = (x: Int, y: Int) => x + y
```

* Powershell
```pwsh
function Test-MrSupportsShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param (
        $ComputerName
    )
    Write-Output $ComputerName
}
```

* Go
```go
func add(x int, y int) int {
	return x + y
}
```

* Rust
```rs
fn another_function() {
    println!("Another function.");
}
```

* Dart
```dart
bool isNoble(int atomicNumber) {
  return _nobleGases[atomicNumber] != null;
}
bool isNoble(int atomicNumber) => _nobleGases[atomicNumber] != null;
```

* Kotlin
```kt
fun double(x: Int): Int {
    return 2 * x
}
```

* Julia
```jl
f(x,y) = x + y
function g(x, y)::Int8
   return x * y
end;
```

* Shortcuts
* Swift
```swift
```

## FunctionExpressions
* SQL
* Cpp
```cpp
auto vglambda = [](auto printer) {
    return [=](auto&&... ts) // generic lambda, ts is a parameter pack
    { 
        printer(std::forward<decltype(ts)>(ts)...);
        return [=] { printer(ts...); }; // nullary lambda (takes no parameters)
    };
};
```

* Matlab
```m
sqr = @(x) x.^2;
```

* Excel
* Perl
```perl
sub walkDir {
    my ($dir, $function) = @_;
    ref($function) eq 'CODE' or 
        die "Error: second argument to walkDir must be an anonymous function $!";
    ...
}

walkDir($ARGV[0], sub { say shift });
```

* Mathematica
```wl
Rotate[#, 90 Degree] & /@ {"one", "two", "three"}
```

* Bash

* Haskell
```hs
inc = \x -> x+1
```

* Python
```py
pairs.sort(key=lambda pair: pair[1])
```

* Lua
```lua
table.sort(network, function (a,b)
  return (a.name > b.name)
end)
```

* Ruby
```rb
# lambda = lambda {}
# lambda = ->() {}  
lambda_with_args = lambda {| s | puts "Hello "+ s }
lambda_with_args = -> (s) { puts "Hello "+ s }
```

* Scala
```scala
val add = (x: Int, y: Int) => x + y
```

* Powershell
```pwsh
using namespace System.Collections.Generic

$List = [List[int]](1..100)
$List.FindAll(
    {
        param($Item)
        $Item % 4 -eq 0
    }
) -join ', '
```

* Go
```go
area = func(l int, b int) int {
  return l * b
}
```

* Rust
```rs
let closure_annotated = |i: i32| -> i32 { i + 1 };
let closure_inferred  = |i     |          i + 1  ;
```

* Dart
```dart
const list = ['apples', 'bananas', 'oranges'];
list.forEach((item) {
  print('${list.indexOf(item)}: $item');
});
```

* Kotlin
```kt
val a = { i: Int -> i + 1 }
```

* Julia
```jl
map(x -> x^2 + 2x - 1, [1, 3, -1])
```

* Shortcuts
* Swift
```swift
func greet(person: String) -> String {
    let greeting = "Hello, " + person + "!"
    return greeting
}
```

## Generic Functions
* SQL
* Cpp
```cpp
template<class T> auto f(T t) { return t; }
```

* Matlab
* Excel
* Perl
* Mathematica
* Bash
* Haskell
* Python
* Lua
* Ruby
* Scala
```scala
def listOfDuplicates[A](x: A, length: Int): List[A] =
```

* Powershell
* Go

* Rust
```rs
fn generic<T>(_s: SGen<T>) {}
```

* Dart
```dart
// <Type>
```

* Kotlin
```kt
fun <T, R> Collection<T>.fold(
    initial: R,
    combine: (acc: R, nextElement: T) -> R
): R {
    var accumulator: R = initial
    for (element: T in this) {
        accumulator = combine(accumulator, element)
    }
    return accumulator
}
```

* Julia
```jl
```

* Shortcuts
* Swift
```swift
reversedNames = names.sorted(by: { s1, s2 in return s1 > s2 } )
reversedNames = names.sorted(by: { s1, s2 in s1 > s2 } )
reversedNames = names.sorted(by: { $0 > $1 } )
reversedNames = names.sorted(by: >)
reversedNames = names.sorted { $0 > $1 }
```

