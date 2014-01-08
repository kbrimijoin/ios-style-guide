# Coding Standards

## iOS Objective-C

### Naming conventions

* names should be clear and not abbreviated
```
  //good
  -(void)setBackgroundColor:(UIColor *)color;

  //bad
  -(void)setBgClr:(UIColor *)clr;
```

* names should start with lowercase letter and be camel case
* names should be as self-explanatory as possible

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

* method bracesand other braces (if/else/switch/while etc.) always open on the same line as the statement but close on a new line.

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

### Interface Files

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





#### Further Reading
* https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/CodingGuidelines/CodingGuidelines.html
* http://dev.ios.wordpress.org/guidelines/
