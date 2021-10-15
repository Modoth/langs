# Types And Modules

## Types
* SQL
```sql
CREATE TABLE test (blob_col BLOB, INDEX(blob_col(10)));
CREATE TABLE #test (blob_col BLOB, INDEX(blob_col(10))); # sqlserver; or directly select into
CREATE TEMPORARY TABLE new_tbl SELECT * FROM orig_tbl LIMIT 0;
```

* Cpp
```cpp
class Vector; // forward declaration
class Matrix {
    // ...
    friend Vector operator*(const Matrix&, const Vector&);
};
class Vector {
    // ...
    friend Vector operator*(const Matrix&, const Vector&);
};

struct MyStruct {
    int value;
    friend std::ostream& operator<<(std::ostream& os, const S& s);
    // definition provided in MyStruct.cpp file which uses #include <ostream>
};

class M {
    std::size_t C;
    std::vector<int> data;
 public:
    M(std::size_t R, std::size_t C) : C(C), data(R*C) {} // constructor definition 
    int operator()(size_t r, size_t c) const { // member function definition
        return data[r*C+c];
    }
    int& operator()(size_t r, size_t c) {  // another member function definition
        return data[r*C+c];
    }
};

union S
{
    std::int32_t n;     // occupies 4 bytes
    std::uint16_t s[2]; // occupies 4 bytes
    std::uint8_t c;     // occupies 1 byte
};                      // the whole union occupies 4 bytes


template<class T> 
  class Y // template definition
  { 
    void mf() { } 
  }; 
```

* Matlab
```m
typedef struct{
    int8_T   a;
    uint16_T b;
}myStruct;

classdef BasicClass
   properties
      Value {mustBeNumeric}
   end
   methods
      function r = roundOff(obj)
         r = round([obj.Value],2);
      end
      function r = multiplyBy(obj,n)
         r = [obj.Value] * n;
      end
   end
end
a = BasicClass
```

* Excel
* Perl
```perl
# class-> package, method-> sub, obj -> {}
package File;

sub new {
    my $class = shift;

    return bless {}, $class;
}

# sets @File::MP3::ISA = ('File'); Inheritance
# SUPER
```

* Mathematica
* Bash
* Haskell
```hs
data Point = Point Float Float deriving (Show)  
data Shape = Circle Point Float | Rectangle Point Point deriving (Show)  
```

* Python
```py
class Dog:
    kind = 'canine'         # class variable shared by all instances
    def __init__(self, name):
        self.name = name

# class DerivedClassName(Base1, Base2, Base3):
class Reverse:
    """Iterator for looping over a sequence backwards."""
    def __init__(self, data):
        self.data = data
        self.index = len(data)

    def __iter__(self):
        return self

    def __next__(self):
        if self.index == 0:
            raise StopIteration
        self.index = self.index - 1
        return self.data[self.index]
```

* Lua
* Ruby
```rb
class B < A
  def m
    2
  end
end
```

* Scala
```scala
class User
val user1 = new User

class Point(var x: Int, var y: Int) {

  def move(dx: Int, dy: Int): Unit = {
    x = x + dx
    y = y + dy
  }

  override def toString: String =
    s"($x, $y)"
}

val point1 = new Point(2, 3)

class Point(var x: Int = 0, var y: Int = 0)
trait Iterator[A] {
  def hasNext: Boolean
  def next(): A
}

class IntIterator(to: Int) extends Iterator[Int] {}
class Stack[A] {}
```

* Powershell
```pwsh
class Device {
    [string]$Brand
    [string]$Model
    [string]$VendorSku

    [string]ToString(){
        return ("{0}|{1}|{2}" -f $this.Brand, $this.Model, $this.VendorSku)
    }
}
$surface = [Device]::new()

enum MediaTypes {
    unknown
    music = 10
    mp3
}

$myHashtable = @{
    Name     = 'Kevin'
    Language = 'PowerShell'
    State    = 'Texas'
}
$myObject = [pscustomobject]$myHashtable
```

* Go
```go
type Vertex struct {
	X, Y float64
}

func (v Vertex) Abs() float64 {
	return math.Sqrt(v.X*v.X + v.Y*v.Y)
}

type I interface {
	M()
}

const (
	Summer Season = iota
	Autumn
	Winter
	Spring
)

```

* Rust
```rs
struct Rectangle {
    width: u32,
    height: u32,
}

impl Rectangle {
    fn area(&self) -> u32 {
        self.width * self.height
    }
}
enum Coin {
    Penny,
    Nickel,
    Dime,
    Quarter(UsState),
}

pub trait Summary {
    fn summarize(&self) -> String {
        String::from("(Read more...)")
    }
}

impl Summary for Tweet {
    fn summarize(&self) -> String {
        format!("{}: {}", self.username, self.content)
    }
}

struct Point<T> {
    x: T,
    y: T,
}

```

* Dart
```dart
class Musician {
  // ...
}
mixin MusicalPerformer on Musician {
  // ...
}
class SingerDancer extends Musician with MusicalPerformer {
  // ...
}
```

* Kotlin
```kt
class Empty
class Person constructor(firstName: String) { /*...*/ }
class InitOrderDemo(name: String) {
    val firstProperty = "First property: $name".also(::println)
    
    init {
        println("First initializer block that prints ${name}")
    }
    
    val secondProperty = "Second property: ${name.length}".also(::println)
    
    init {
        println("Second initializer block that prints ${name.length}")
    }
}
data class User(val name: String, val age: Int)
enum class Direction {
    NORTH, SOUTH, WEST, EAST
}
value class Password(private val s: String)
val securePassword = Password("Don't try this in production")

val helloWorld = object {
    val hello = "Hello"
    val world = "World"
    // object expressions extend Any, so `override` is required on `toString()`
    override fun toString() = "$hello $world"
}

interface MyInterface {
    fun bar()
    fun foo() {
      // optional body
    }
}
```

* Julia
```jl
[mutable] struct Foo
  x :: Int
end
```

* Shortcuts
* Swift
```swift
struct SomeStructure {
    // structure definition goes here
}
class SomeClass {
    // class definition goes here
}


enum CompassPoint {
    case north, south, east, west
    mutating func turnNorth() {
        self = .north
    }
}

protocol SomeProtocol {
    // protocol definition goes here
}
struct SomeStructure: FirstProtocol, AnotherProtocol {
    // structure definition goes here
}
```
