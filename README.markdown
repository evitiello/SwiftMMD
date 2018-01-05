SwiftMMD
========

This is a Swift wrapper around [MultiMarkdown 5](https://github.com/fletcher/MultiMarkdown-5). 

This software is exteremly young, untested, and is likely to catch your computer on fire. I haven't even tried running all the functions I've written. _Caveat computer_. 

I've defined a few methods in an extension on String.

```swift
let myMarkdown: String = ...
let myDoc: String = myMarkdown.mmdToHTMLDocument()
let myOutput: String = myMarkdown.mmeRenderToFormat(...)
//and others
```

It's designed to be very thin. The primary aim is to sheild you from the indelicacies of `UnsafeMutablePointer<Int8>` when all you want is a `String`, and other unsavory aspects of C interop.

## To Build

### MultiMarkdown

If you don't already have cmake installed, you will need it. you can get it from homebrew:

```
brew install cmake
```

Then, init the MultiMarkdown submodule

 ```cd <your SwiftMMD directory>
git submodule init
git submodule update
git submodule foreach git branch --set-upstream master origin/master
git submodule foreach git checkout master
```
Next, update the submodules in the MultiMarkdown submodule

```cd submodules\MultiMarkdown-5
./link_git_modules
./update_git_modules
```
Next, build.

```
make
cd build
make
```

now you should have a nice libMultiMarkdown.a in submodules/MultiMarkdown-5/build

### SwiftMMD

1. Open the Xcode project.
2. Build.
3. Profit.
