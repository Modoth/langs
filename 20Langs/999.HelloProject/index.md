# Hello, projects!

## Projects

* SQL
* CPP: cmake
```sh
sudo apt install cmake
vi CMakeLists.txt # seen below
mkdir build && cd build
cmake ..
# make
```

```CMakeLists.txt
cmake_minimum_required(VERSION 3.0)
project(Simple LANGUAGES CXX)
add_executable(HelloProject main.cpp)
```
* Matlab: (thoses scripts' interpreters find modules by path, and isolated by env or by wrappering interpreters)
* Excel
* Perl
* Mathematica
* Bash
* Haskell
    * cabal
```sh
sudo apt install cabal-install-3.4
mkdir HelloProject && cd HelloProject
cabal init
cabal build # cabal run
```

    * stack
```sh
wget -qO- https://get.haskellstack.org/ | sh
stack new HelloProject # cd HelloProject
stack setup
stack build
stack exec ...
```
* Python: venv
```sh
sudo apt install python3-venv
python3 -m venv HelloProject
source HelloProject/bin/activate
```
* Lua
* Ruby
    * bundle
```sh
bundle init
bundle exec
```

    * rail
```sh
# todo
bin/rail --server
```
* Scala: sbt(interactive builder)
```sh
sbt new scala/scala3.g8
sbt > build # run
```
* Pwsh
* Go: go mod
```sh
go mod init my/test/HelloProject
go build # go run # go install
```
* Rust: cargo
```sh
cargo new HelloProject # cd HelloProject
cargo build # cargo run
```
* Dart
```sh
dart create -t console-full helloproject # cd helloproject
dart run
```
* Kotlin: gradle
```sh
sdk install gradle 7.2
# mkdir HelloProject && cd HelloProject
grade init
gradle build # gradle run
```
* Julia
```sh
# mkdir HelloProject && cd HelloProject
julia>pkg>activate .
# or
julia --project=. 
```
* Shortcuts
* Swift
```sh
# mkdir HelloProject && cd HelloProject
swift package init --type=executable
swift build # swift run
```

## Dependencies

* sql
* cpp: vcpkg
```sh
# global install and search
git clone https://github.com/microsoft/vcpkg
./vcpkg/bootstrap-vcpkg.sh
# ./vcpkg/vcpkg integrate install
# cmake -B [build directory] -S . -DCMAKE_TOOLCHAIN_FILE=[path to vcpkg]/scripts/buildsystems/vcpkg.cmake
# vcpkg search sqlite
# vcpkg install sqlite3
# vcpkg list
```

```CMakeLists.txt
find_package(unofficial-sqlite3 CONFIG REQUIRED)
target_link_libraries(main PRIVATE unofficial::sqlite3::sqlite3)
```

* Matlab: addons
* Excel
* Perl: cpan, cpanm
    * Mirrors
```sh
cpan[1]> o conf urllist push https://mirrors.aliyun.com/CPAN/
cpan[2]> o conf commit
```
```sh
cpan App::cpanminus
# cpanm HTTP::Tiny
```
* Mathematica: addons
* Bash: bpkg
* Haskell
    * cabal
```
-- cabal update
-- ~/.cabal/config
repository mirrors.tuna.tsinghua.edu.cn
  url: http://mirrors.tuna.tsinghua.edu.cn/hackage
```
```sh
cabal update
cabal install HaXml

```

    * stack
```
# ~/.stack/config.yaml
package-indices:
  - download-prefix: http://mirrors.tuna.tsinghua.edu.cn/hackage/
    hackage-security:
        keyids:
        - 0a5c7ea47cd1b15f01f5f51a33adda7e655bc0f0b0615baa8e271f4c3351e21d
        - 1ea9ba32c526d1cc91ab5e5bd364ec5e9e8cb67179a471872f6e26f0ae773d42
        - 280b10153a522681163658cb49f632cde3f38d768b736ddbc901d99a1a772833
        - 2a96b1889dc221c17296fcc2bb34b908ca9734376f0f361660200935916ef201
        - 2c6c3627bd6c982990239487f1abd02e08a02e6cf16edb105a8012d444d870c3
        - 51f0161b906011b52c6613376b1ae937670da69322113a246a09f807c62f6921
        - 772e9f4c7db33d251d5c6e357199c819e569d130857dc225549b40845ff0890d
        - aa315286e6ad281ad61182235533c41e806e5a787e0b6d1e7eef3f09d137d2e9
        - fe331502606802feac15e514d9b9ea83fee8b6ffef71335479a2e68d84adc6b0
        key-threshold: 3 # number of keys required

        # ignore expiration date, see https://github.com/commercialhaskell/stack/pull/4614
        ignore-expiry: no
```

* Python: pip
```txt
# $HOME/.config/pip/pip.conf
[global]
index-url=https://mirrors.aliyun.com/pypi/simple/
```
```sh
pip install 
pip freeze > deps.txt
pip install -r deps.txt
```

* Lua: luarocks
* Ruby: gem, bundle(Gemfile)
```sh
gem sources
gem sources --remove https://rubygems.org/
gem sources -a https://mirrors.aliyun.com/rubygems/
```

```sh
gem install xxx
```

* Scala: sbt
* Powershell
```pwsh
Find-Module -Name PowerShellGet
Install-Module XXX
Uninstall-Module 
```

* Go
```sh
go env -w GOPROXY=https://goproxy.cn,direct
go vendor # cache deps
```

* Rust
```
# ~/.cargo/config
replace-with = "rustcc"
[source.rustcc]
registry = "https://code.aliyun.com/rustcc/crates.io-index.git"
```
```sh
# cargo install x # install bins
```
```
vi Cargo.toml
```

* Dart
```sh
vi pubspec.yaml
dart pub get
# or
dart pub add vector_math
# or
flutter pub add vector_math
```

* Kotlin: gradle
```
# build.gradle
repositories {
maven{ url 'http://maven.aliyun.com/nexus/content/groups/public/'}
mavenCentral()
}
```
```
# global
# ~/.gradle/init.gradle
allprojects{
    repositories {
        def ALIYUN_REPOSITORY_URL = 'http://maven.aliyun.com/nexus/content/groups/public'
        def ALIYUN_JCENTER_URL = 'http://maven.aliyun.com/nexus/content/repositories/jcenter'
        all { ArtifactRepository repo ->
            if(repo instanceof MavenArtifactRepository){
                def url = repo.url.toString()
                if (url.startsWith('https://repo1.maven.org/maven2')) {
                    project.logger.lifecycle "Repository ${repo.url} replaced by $ALIYUN_REPOSITORY_URL."
                    remove repo
                }
                if (url.startsWith('https://jcenter.bintray.com/')) {
                    project.logger.lifecycle "Repository ${repo.url} replaced by $ALIYUN_JCENTER_URL."
                    remove repo
                }
            }
        }
        maven {
            url ALIYUN_REPOSITORY_URL
            url ALIYUN_JCENTER_URL
        }
    }
}
```
```sh
vi build.gradle
```
* Julia
```sh
export JULIA_PKG_SERVER=https://mirrors.tuna.tsinghua.edu.cn/julia
```

```julia
>]
Pkg> add JSON
PKg> rm JSON
```

* Shortcuts
* Swift
```sh
vi Package.swift
```
```swift
dependencies: [
        .package(
            url: "https://github.com/johnsundell/files.git", 
            from: "4.0.0"
        )
    ],
targets: [
        .target(
            name: "TodoKit",
            dependencies: ["Files"]
        ),
```
