# Variables

* SQL
```sql
set @fn = 'Tom';
select @fn;
select @ln:= 'Page';
// local variable
declare age INT default 0
set age = age + 1
```

* Cpp
```cpp
auto fn = "Tom";
char* const ln = "Page";
int age {0}
```

* Matlab
```m
fn = "Tom";
clear fn; # usefull in repl
```

* Excel
* Perl
```perl
my $fn = "Tom";
our @friends = ("Jerry") # package variable
%infos = ("age", 1)
$rinfos = \%infos
$infos = { "age"=> 1 }
$do = \&some_func
print($infos->{age})
print(${$infos}{age})
# variable context
```

* Mathematica
```wl
fb = "Tom"
F[x_] := Expand[x^2]
fb =.
Clear[F]
# symbols
```

* Bash
```sh
fn="Tom"
export fn
age=12 do_something
echo $fn ${#fn}
fn=
# parameters expand
```

* Haskell
```hs
pi = 3.14
```

* Python
```py
fn = "Tom"
global ln = "Page" # inside a block only
```

* Lua
```lua
local fn = "Tom"
ln = "Page"
```

* Ruby
```
age = 0
$fn = "Tom"
# @age , @@info instance var, class var
LN = "Page"
```

* Scala
```scala
var age : Int = 0
val fn = "Page" # can redefined in repl
```

* Powershell
```pwsh
$fn = "Tom"
$Env:PATH += ":$Env:HOME/.local/bin"
Set-Item -Path xxx -Value
Clear-Variable -Name fn
# or
$fn = $null
# variable scope: Alias, Env, Function, Variable or <customize>
# Using:var use in remote like Invoke-Command to access local machine variable
```

* Go
```go
var age int = 1
fn := "Tom"
const ln = "Page"
```

* Rust
```rs
let ln = "Page"; //shadow
let mut age : i32 = 0;
```

* Dart
```dart
var age = 0
String fn = "Tom"
final ln = "Page"
const pi = 3.14 # compile time
```

* Kotlin
```kt
var age : Int = 1
val ln = "Page
```

* Julia
```jl
age = 1
# local assignment causes shadow
# defining before using
```

* Shortcuts
* Swift
```swift
var age : Int = 0
let ln = "Page"
```
