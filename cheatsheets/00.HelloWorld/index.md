# Hello, world!

## Installation

* SQL: mariadb, mysql-client

```sh
# server in docker container
docker run -p localhost:3306:3306 --name mariadb -e MARIADB_ROOT_PASSWORD="<passwd>" -d mariadb:latest
# client on ubuntu
sudo apt install mysql-client
# optional: save password
mysql_config_editor set --host=localhost --user=root --password
```

* CPP: clang, lldb
```sh
# ubuntu
sudo apt install clang lldb
```

* Matlab: octave compatible

```sh
sudo apt install octave
```

* Excel
* Perl
* Mathematica: wolframengine
```sh
#docker
docker run -it arnoudbuzing/wolframengine bash
```
* Bash
* Haskell: ghc
```sh
sudo apt install ghc
```
* Python: python3
* Lua
```sh
sudo apt install lua5.3
```

* Ruby
```sh
sudo apt install ruby
```

* Scala
```sh
sudo apt install scala
```

* Powershell
```sh
wget -q https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
sudo apt update
sudo apt install -y powershell
```

* Go
```sh
sudo apt install golang
```

* Rust
```sh
wget https://sh.rustup.rs -O - | sh
```

* Dart
```sh
wget 'https://storage.googleapis.com/dart-archive/channels/stable/release/latest/linux_packages/dart_2.14.3-1_amd64.deb' -O dart.deb
sudo apt install ./dart.deb
```

* Kotlin
```sh
curl -s "https://get.sdkman.io" | bash
sdk install kotlin
```

* Julia
```sh
wget https://julialang-s3.julialang.org/bin/linux/x64/1.7/julia-1.7.0-rc1-linux-x86_64.tar.gz -O julia.tar.gz
tar -xzvf julia.tar.gz
```

* Shortcuts
* Swift
```sh
sudo apt install binutils git gnupg2 libc6-dev libcurl4 libedit2 libgcc-9-dev libpython2.7 libsqlite3-0 libstdc++-9-dev libxml2 libz3-dev pkg-config tzdata uuid-dev zlib1g-dev
wget https://swift.org/builds/swift-5.5-release/ubuntu2004/swift-5.5-RELEASE/swift-5.5-RELEASE-ubuntu20.04.tar.gz -O  swift.tar.gz
tar -xzvf swift.tar.gz
```

## Hello, world!

### Source code

* SQL

``` sql
select "Hello, world!";
```

* C++
```cpp
#include <iostream>
using namespace std;

int main(int argc, char** args){
    cout << "Hello, world!" << endl;
}
```

* Matlab

```m
disp "Hello, world!";
```

* Excel
* Perl

```perl
print "Hello, world!\n"
```

* Mathematica
```wls
Print["Hello, world!"]
```
* Bash
```sh
echo Hello world
```

* Haskell
```hs
main=putStrLn "Hello, world!"  
```

* Python
```py
print("Hello, world!")
```

* Lua
```lua
print("Hello, world!")
```

* Ruby
```ruby
print "Hello, world!\n"
```

* Scala
```scala
object HelloWorld {
  def main(args: Array[String]): Unit = {
    println("Hello, world!")
  }
}
```
* Powershell
```ps
Write-Host "Hello world"
```

* Go
```go
import "fmt"

func main() {
        fmt.Println("Hello, world!")
}
```

* Rust
```rs
fn main() {
    println!("Hello, world!");
}
```

* Dart
```dart
void main() {
  print('Hello world!');
}
```

* Kotlin
```kotlin
//kts
println("Hello, world!")
```
```kotlin
//kt
fun main() {
    println("Hello, world!")
}
```

* Julia
```jl
println("Hello, world")
```

* Shortcuts
* Swift

```swift
print("Hello, world!")
```

### Interpreter \[compiler\]

#### File

* SQL: `mysql < helloworld.sql`
* C++
* Matlab: `octave helloworld.m`
* Excel
* Perl: `perl helloworld.pl`
* Mathematica: `wolframscript -f|-script helloworld.wls`
* Bash: `bash helloworld.sh`
* Haskell: (load only)`ghci helloworld.hs`
* Python: `python3 helloworld.py`
* Lua: `lua helloworld.lua`
* Ruby: `ruby helloworld.rb`
* Scala
* Powershell: `pwsh helloworld.ps`
* Go: (compile and run) `go run helloworld.go`
* Rust
* Dart: `dart \[run\] helloworld.dart`
* Kotlin: `kotlin helloworld.kts`
* Julia: `julia helloworld.jl`
* Shortcuts
* Swift

#### Cmdline args

* SQL: `mysql <<< ''`
* C++
* Matlab: `octave --eval ''`
* Excel
* Perl: `perl -e ''`
* Mathematica: `wolframscript -c ''`
* Bash: `bash -c ''`
* Haskell
* Python: `python3 -c ''`
* Lua: `lua -e ''`
* Ruby: `ruby -e ''`
* Scala
* Powershell: `pwsh -c|-Command`
* Go
* Rust
* Dart
* Kotlin
* Julia: `julia -e ''`
* Shortcuts
* Swift

#### Repl

* SQL: `sql`
* C++
* Matlab: `octave`
* Excel
* Perl: `perl -de0`
* Mathematica: `wolframscript`
* Bash: `bash`
* Haskell: `ghci`
```hs
putStrLn "Hello, world!"
```
* Python: `python3`
* Lua: `lua`
* Ruby: `ruby`
* Scala: `scala`
```scala
println("Hello, world!")
```
* Powershell: `pwsh`
* Go
* Rust
* Dart
* Kotlin: `kotlin`
* Julia: `julia`
* Shortcuts
* Swift: `swift`

### Compiler & Run

* SQL
* C++

```sh
clang++ helloworld.cpp
./a.out
```

* Matlab
* Excel
* Perl
* Mathematica
* Haskell
```sh
ghc helloworld.hs
./helloworld
```
* Python
* Lua
* Ruby
* Scala
```sh
scalac helloworld.scala
scala HelloWorld
```
* Powershell
* Go
```sh
go build helloworld.go
./helloworld
```
* Rust
```sh
rustc helloworld.rs
./helloworld
```
* Dart
```sh
dart compile \[exe aot-snapshot jit-snapshot js kernel\] helloworld.dart
./helloworld.exe
node out.js
```
* Kotlin
```sh
kotlinc helloworld.kt
kotlin AKt
kotlinc-js helloworld.kt -output helloworld.js
```
* Julia
* Shortcuts
* Swift
```sh
swiftc helloworld.swift
./helloworld
```

