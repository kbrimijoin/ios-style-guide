# Coding Standards

## iOS Objective-C

### Naming conventions

* names should be as self-explanatory as possible (requiring the least amount of comments as possible)
* names should be clear, not abbreviated and descriptive
```
  //good
  -(void)setBackgroundColor:(UIColor *)color;

  //bad
  -(void)setBgClr:(UIColor *)clr;
```

* names should start with lowercase letter and be camel case

### Syntax

* dot-notation should be used for accessing and mutating properties; bracket notation is preferred in all other instances

```
//good
view.backgroundColor = [UIColor orangeColor];
[UIApplication sharedApplication].delegate;

//bad
[view setBackgroundColor:[UIColor orangeColor]];
UIApplication.sharedApplication.delegate;
```

* method braces and other braces (if/else/switch/while etc.) always open on the same line as the statement but close on a new line.

```
if (thisIsTrue) {
  //do something
} else {
  //do something else
}
```

* ternary operator should only be used when it increases the clarity or neatness of code

```
//good
result = (a > b) ? x : y;

//bad
result = a > b ? x = c > d ? c : d : y;
```

* there should be a space after the method scope and a space between method segments

```
- (void)setExampleText:(NSString *)text image:(UIImage *)image;
```

* asterisks indicating pointers belong with the the variable

```
//good
NSString *text;

//bad
NSString* text;
```

### Interface Files

* should include a description of what the class does
* system imports precede project imports
```
  #import <SystemImport.h>

  #import "MyProjectClass.h"
```

* only expose the minimum necessary for other classes to interact; everything else goes into the implementation file

### Implementation Files

* declare any internal variable and methods in the implementation
* use pragma mark to group methods into sections

```
#pragma mark - 
#pragma mark My Section Name
```

### General

* it is best to use as many storyboards as possible to avoid git issues.  http://blog.mugunthkumar.com/articles/avoiding-merge-conflicts-with-storyboards/

* files that are to be shared across many files should not be imported into each file; instead they should be added to the project's pch file

```
#ifdef __OBJC__
    #import <UIKit/UIKit.h>
    #import <Foundation/Foundation.h>
    #import <SystemConfiguration/SystemConfiguration.h>
    #import <MobileCoreServices/MobileCoreServices.h>
    #import <CoreData/CoreData.h>
    #import "Config.h"
    #import "Colors.h"
#endif
```

* the preferred third party library package manager currently is Cocoapods http://cocoapods.org/




#### Further Reading

* https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/CodingGuidelines/CodingGuidelines.html

* http://dev.ios.wordpress.org/guidelines/
