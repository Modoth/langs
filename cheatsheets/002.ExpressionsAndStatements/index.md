# Expressions And Statements

## Jumps
* SQl
```sql
GOTO label --Transact-SQL
```

* Cpp: `goto label`
```cpp
goto start
```

* Matlab
* Excel
* Perl
```pl
goto LABEL # EXPR or &FUNC_NAME
```

* Mathematica
```wl
f[a_] := Module[{x = 1., xp},
  Label[begin];
  If[Abs[xp - x] < 10^-8, Goto[end]];
  xp = x;
  x = (x + a/x)/2;
  Goto[begin];
  Label[end];
  x]
```

* Bash
* Haskell
* Python

* Lua
```lua
::done::
goto done
```

* Ruby
* Scala
* Powershell
* Go
```go
goto label
```

## Selections
* SQL
```sql
if(win, tob, not2b) # ifnull, nullif
case win when true then '2b' else 'not 2b' ed

# IF THEN ELSEIF THEN ELSE ENF IF
# CASE WHEN THEN ELSE END CASE
IF n > m THEN SET s = '>';
ELSEIF n = m THEN SET s = '=';
ELSE SET s = '<';
END IF;
```

* Cpp
```cpp
// if constexpropt ( init-statementopt condition ) statement
// if constexpropt ( init-statementopt condition ) statement else statement
// switch ( init-statementopt condition ) statement; default, break
```

* Matlab
```m
% if, elseif, else
% switch, case, otherwise
switch dayString
   case 'Monday'
      disp('Start of the work week')
   otherwise
      disp('Weekend!')
      end
```

* Excel
```fx
IF(C2=1,”Yes”,”No”)
IFS(A2>89,"A",A2>79,"B",A2>69,"C",A2>59,"D",TRUE,"F")

# IF(logical_test, value_if_true, [value_if_false])
# IFS(logical_test1, value_if_true1, [logical_test2, value_if_true2], [logical_test3, value_if_true3],…)
# SWITCH(expression, value1, result1, [default or value2, result2],…[default or value3, result3])
```

* Perl
```pl
# if|unless elsif else 
# for|given when
# Statement Modifiers
print "Basset hounds got long ears" if length $ear >= 10;

use v5.10.1;
given|for ($var) {
    when (/^abc/) { $abc = 1 }
    when (/^def/) { $def = 1 }
    when (/^xyz/) { $xyz = 1 }
    default       { $nothing = 1 }
}
```

* Mathematica
```wl
abs[x_] := If[x < 0, -x, x]
Which[a == 1, x, a == 2, b]
f[b_] := Switch[b, True, 1, False, 0, _, Message[f::boole, b]; 0]
# others
Plot[Piecewise[{{x^2, x < 0}, {x, x > 0}}], {x, -2, 2}] 
```

* Bash
```sh
# if ;then;elif ;then;else;fi
# case in pat) ;; esac
# select name [in words]; do; done
echo -n "Enter the name of an animal: "
read ANIMAL
echo -n "The $ANIMAL has "
case $ANIMAL in
  horse | dog | cat) echo -n "four";;
  man | kangaroo ) echo -n "two";;
  *) echo -n "an unknown number of";;
esac
echo " legs."
```

* Haskell
```hs
-- if then else
describeLetter c =
    if c >= 'a' && c <= 'z'
        then "Lower case"
        else if c >= 'A' && c <= 'Z'
            then "Upper case"
            else "Not an ASCII letter"

-- guards
describeLetter c
   | c >= 'a' && c <= 'z' = "Lower case"
   | c >= 'A' && c <= 'Z' = "Upper case"
   | otherwise            = "Not an ASCII letter"

-- case
f x = case x of
    0 -> 18
    1 -> 15
    2 -> 12
    _ -> 12 - x
```

* Python
```py
# if elif else
# match case if
match (100, 200):
   case (100, 300):  # Mismatch: 200 != 300
       print('Case 1')
   case (100, 200) if flag:  # Successful match, but guard fails
       print('Case 2')
   case (100, y):  # Matches and binds y to 200
       print(f'Case 3, y: {y}')
   case _:  # Pattern not attempted
       print('Case 4, I match anything!')
```

* Lua
```lua
# if then else elseif endo
if op == "/" then
  r = a/b
else
  error("invalid operation")
end
```

* Ruby
```rb
# if then elsif else end
input_type =
  if gets =~ /hello/i
    "greeting"
  else
    "other"
  end

input_type = gets =~ /hello/i ? "greeting" : "other"

# unless else end
a += 1 unless a.zero?

case "12345"
when /^1/
  puts "the string starts with one"
else
  puts "I don't know what the string starts with"
end
```

* Scala
```scala
# if else 
val minValue = if (a < b) a else b

count match {
    case 1 => println("one, a lonely number")
    case x if x == 2 || x == 3 => println("two's company, three's a crowd")
    case x if x > 3 => println("4+, that's a party")
    case _ => println("i'm guessing your number is zero or less")
}
```

* Powershell
```pwsh
# if elseif else
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
$message = (Test-Path $path) ? "Path exists" : "Path not found"

switch (4, 2)
{
    1 {"It is one."; Break}
    2 {"It is two." ; Break }
    3 {"It is three." ; Break }
    4 {"It is four." ; Break }
    3 {"Three again."}
}

$target = 'https://bing.com'
switch -Regex ($target)
{
    '^ftp\://.*$' { "$_ is an ftp address"; Break }
    '^\w+@\w+\.com|edu|org$' { "$_ is an email address"; Break }
    '^(http[s]?)\://.*$' { "$_ is a web address that uses $($matches[1])"; Break }
}
```

* Go
```go
// if else
if x := f(); x < y {
	return x
} else {
	return y
}


switch tag {
default: s3()
case 0, 1, 2, 3: s1()
case 4, 5, 6, 7: s2()
}

switch i := x.(type) {
case nil:
	printString("x is nil")                // type of i is type of x (interface{})
default:
	printString("don't know the type")     // type of i is type of x (interface{})
}

select {
case i1 = <-c1:
	print("received ", i1, " from c1\n")
default:
	print("no communication\n")
}
```

## Iterations
* SQL
```sql
# LOOP END LOOP
# REPEAT UNTIL END REPEAT
# WHILE DO END WHILE
# ITERATE label, LEAVE label
WHILE v1 > 0 DO
  SET v1 = v1 - 1;
END WHILE;
```
* Cpp
```cpp
// while ( condition ) statement
// do statement while ( expression ) ;
// for ( init-statement conditionopt ; expressionopt ) statement
// for ( init-statementopt for-range-declaration : for-range-initializer ) statement
// break; continue;
int array[5] = { 1, 2, 3, 4, 5 };
start: 
for (int& x : array)
	x *= 2;
```

* Malab
```m
% for
% while
% parfor
%  parfor loopvar = initval:endval; statements; end
%  parfor (loopvar = initval:endval, M); statements; end
% break, continue
for n = 2:6
    x(n) = 2 * x(n - 1);
end

parpool(3)
parfor i=1:3, c(:,i) = eig(rand(1000)); end
```

* Excel
```sh
# Loop to aggregate
# AGGREGATE(function_num, options, ref1, [ref2], …)
# AGGREGATE(function_num, options, array, [k])
# SUM, MAX, AVERAGE

AGGREGATE(14,3,A1:A100*(A1:A100>0),1) # 14: LARGE, 3: ignore hidden rows, error values, nested SUBTOTAL and AGGREGATE functions
```

* Perl
```pl
# while
# do until
# for(;;); for item (arr);
# for when
# next, redo(next without condition), last + label
print "Hello $_!\n" for qw(world Dolly nurse);
```

* Mathematica
```wl
# Break, Continue
Do[Print[n], {n, -3, 5, 2}]
While[n<4;Print[n];n++]
For[i = 0, i < 4, i++, Print[i]]
Table[f[i], {i, 0, 20, 2}]
Do[Print[i]; If[i > 2, Break[]], {i, 10}]
# Others
Nest[(1 + #)^2 &, 1, 3]
```

* Bash
```sh
# while|until;do;done
# for name [in words;]do;done
# for((;;);do;done
# break,continue
```

* Haskell

* Python
```py
# while else
# for in else
for i in range(10):
    print(i)
    i = 5 

for x in a[:]:
    if x < 0: a.remove(x)
```

* Lua
```lua
# break, 
while a[i] do
  print(a[i])
  i = i + 1
end

repeat
  line = io.read()
until line ~= ""

for i=10,1,-1 do print(i) end
for i,v in ipairs(a) do print(v) end
```

* Ruby
```rb
# while end
# until do end
# for in do end
# break, next, redo

a = 0
begin
  a += 1
end while a < 10

selected = []

0.upto 10 do |value|
  selected << value if value==2..value==8
end

p selected # prints [2, 3, 4, 5, 6, 7, 8]
```

* Scala
```scala
for ((name,rating) <- ratings) println(s"Movie: $name, Rating: $rating")
for(i <- 1 to 10) println(i)

val doubledNums = for (n <- nums) yield n * 2
```

* Powershell
```pwsh
# do until|while, while
# break, continue

'ActiveDirectory', 'SQLServer' | ForEach-Object {Get-Command -Module $_}

$ComputerName = 'DC01', 'WEB01'
foreach ($Computer in $ComputerName) {
  Get-ADComputer -Identity $Computer
}

for ($i = 1; $i -lt 5; $i++) {
  Write-Output "Sleeping for $i seconds"
  Start-Sleep -Seconds $i
}
```

* Go
```go
for a < b {
	a *= 2
}

for i := 0; i < 10; i++ {
	f(i)
}

for      { S() } 

var a [10]string
for i, s := range a {
	g(i, s)
}
```

## Exceptions
* SQL
```sql
DECLARE no_such_table CONDITION FOR 1051;
DECLARE CONTINUE HANDLER FOR no_such_table --CONTINUE|EXIT|UNDO
  BEGIN
    -- body of handler
  END;

DECLARE CONTINUE HANDLER FOR 1051
  BEGIN
    -- body of handler
  END;
```

* Cpp
```cpp
try {
  throw C();
} catch(const C p) {
  // handle character string exceptions here
}
```

* Matlab
```m
try
    a = notaFunction(5,6);
catch
    warning('Problem using function.  Assigning a value of 0.');
    a = 0;
end
```

* Excel
```
IFERROR (value, value_if_error)
```

* Perl
```pl
try {
    my $x = call_a_function();
    $x < 100 or die "Too big";
    send_output($x);
}
catch ($e) {
}
```

* Mathematica
```wl
f[x_] := If[x > 10, Throw[overflow], x!]
Catch[f[2] + f[11]]

Catch[Do[If[i! > 10^10, Throw[i]], {i, 100}]]
```

* Bash
```sh
tempfile=/tmp/tmpdata
trap "rm -f $tempfile" EXIT
```

* Haskell
```hs
main = do
    result <- try (evaluate (5 `div` 0)) :: IO (Either SomeException Int)
    case result of
        Left ex  -> putStrLn $ "Caught exception: " ++ show ex
        Right val -> putStrLn $ "The answer was: " ++ show val

main = catch (print $ 5 `div` 0) handler
  where
    handler :: SomeException -> IO ()
    handler ex = putStrLn $ "Caught exception: " ++ show ex
```

* Python
```py
# try except as else finally
try:
    raise TypeError
except:
    print(sys.exc_info())
    try:
         raise ValueError
    except:
        print(sys.exc_info())
    print(sys.exc_info())
```

* Lua
```lua
local status, err = pcall(function () error({code=121}) end)
print(err.code)  -->  121
```

* Ruby
```rb
begin  
  raise 'A test exception.'  
rescue StandardError => e  
  puts e.message  
  puts e.backtrace.inspect  
end
```

* Scala
```scala
# try catch final
try {
} 
catch {
    case foo: FooException => handleFooException(foo)
    case _: Throwable => println("Got some other kind of Throwable exception")
} finally {
}
```

* Powershell
```pwsh
try {
   $wc = new-object System.Net.WebClient
   $wc.DownloadFile("http://www.contoso.com/MyDoc.doc","c:\temp\MyDoc.doc")
   throw "This is an error."
}
catch [System.Net.WebException],[System.IO.IOException] {
    "Unable to download MyDoc.doc from http://www.contoso.com."
}
catch {
    "An error occurred that could not be resolved."
}

function TrapTest {
    trap {"Error found."}
    nonsenseString
}

TrapTest
```

* Go
```go
defer func() {      // recovers panic
  if e := recover(); e != nil {
    fmt.Println("Recovered from panic")
  }
}()
panic(s) 
```

## Others
* SQL
* Cpp
```cpp
task<> tcp_echo_server() {
  char data[1024];
  while (true) {
    size_t n = co_await socket.async_read_some(buffer(data));
    co_await async_write(socket, buffer(data, n));
  }
}
```

* Matlab
* Excel
* Perl
```pl
# ... statement
sub unimplemented { ... }
```

* Mathematica
* Bash
* Haskell
```hs
# do <-
greetAndSeeYou :: IO ()
greetAndSeeYou = nameReturn >>= (\ name -> putStrLn ("See you, " ++ name ++ "!"))
greetAndSeeYou = do
  name <- nameReturn
  putStrLn("See tou, " ++ name ++ "!")
```

* Python
```py
async def func(param1, param2):
    do_stuff()
    await some_coroutine()

with EXPRESSION as TARGET: # Resource dispose
    SUITE
```

* Lua
* Ruby
* Scala
* Powershell
* Go
```go
go Server()
defer fmt.Println("world")
```

##
