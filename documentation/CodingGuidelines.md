# Coding Guidelines
Employees and contractors alike should use the following guide as a reference for managing software source code, file organization, code organization, and styles. Most of the guidelines below follow common industry practicies, but there are also common industry disagreements which we are resolved upon for ourselves.

There are a handful of capitalized keywords which are significant to the guidelines themselves:
* MUST - This is a requirement; a pull request will be rejected for failing to meet these requirements. There aren't many of these though
* SHOULD - This is a strongly opinionated suggestion; a pull request might generate a snarky comment or two for violating these, but won't be rejected in a pinch
* MAY - This is an optional, open door invitation to utilize this in your projects
* NOT - The logical inversion requires no introduction!

## Project Organization
 * Source files SHOULD be placed into a /src subdirectory of the project
   * i.e. NOT into the project root
 * A given source file SHOULD represent only a single class for object oriented languages
   * Exception: inner/private classes
 * Resources such as reference data and translation strings SHOULD be placed into a /res subdirectory of the project
   * i.e. NOT into the project root
   * i.e. NOT nested below /src

## Naming Conventions
 * Contsants SHOULD be `ALL_CAPS` with underscores separating words
 * Type, Class, and Interface declarations SHOULD be `UpperCamelCase`
 * Variable, Class Instance, Function/Method names SHOULD be `lowerCamelCase`
 * Function/Method names SHOULD start with an imperative verb reflecting what it does
   * e.g. `getName()`, NOT `name()`
   * e.g. `flushCache()`, NOT `flush()`
 * Function/Method generic arguments SHOULD be named to reflect their type
   * e.g. `setFlag(Flag flag)`, NOT `setFlag(Flag f)`
 * Contextualized names SHOULD lean on implicity for brevity
   * e.g. `Point.getX()`, NOT `Point.getPointX()`
 * Boolean names SHOULD reflect truthiness
   * e.g. `isDone`, NOT `done`
   * e.g. `hasBananas`, NOT `bananas`
   * e.g. `needsCleanup`, NOT `cleanup`
   * e.g. `canRead`, NOT `read`
 * Boolean names MUST reflect positive case
   * e.g. `isPositiveCondition = true`, NOT `isNegativeCondition = true`
   * e.g. `wasSuccessful`, NOT `hadError`
 * Single-letter/non-meaningful variable names SHOULD only be used sparingly
   * e.g. Iteration as `for (var i = 0; i < 10; i++) {}`
   * e.g. Temporary as `swapThings(this, that) { t = this; this = that; that = t; }`
 * Complementary Functions/Methods MUST have complementary names
   * e.g. `getThings()` and  `setThings()`
   * e.g. `startActivity()` and  `stopActivity()`
   * e.g. `incrementCounter()` and  `decrementCounter()`

## Constants
 * Names of related constants MUST be grouped together with common prefix
   * e.g. `STATUS_OK = 200; STATUS_CLIENT_ERROR = 400;`
 * Static numeric values SHOULD be defined as constants
   * Exception: -1, 0, 1, 2 when used as elementary control/sentinel values
 * Literal string values SHOULD use single-quotes where possible
   * e.g. `message = 'This is a literal message';`
 * Interpreted string values SHOULD use double-quotes where possible
   * e.g. `logEvent("Got event $event from somewhere");`

## Internationalization
 * Static string messages SHOULD either:
   1. Be programmatically referenced by name in code where the name is an index into a string resource collection which can be updated without rebuilding the application
   2. Be stored as English language literals in code where the English string itself is an index into a string resource collection which can be updated without rebuilding the application
   3. Be stored as English language literal templates into which data variables are injected
      * e.g. `message = _T("You now have $d points", userPoints);`
      * e.g. NOT `message = _T('Assembled messaging is %s in most languages', 'BAD and will break translation');`
 * String representation in user interfaces MUST:
   1. Be encapsulated such that the string will present properly for Left-to-Right OR Right-to-Left languages

## Source Formatting
 * Source code SHOULD be indented with TAB characters
 * Statements / expression SHOULD have spaces inserted between names, operators, and control characters
   * e.g. `function raiseCount( int amount = 1 ) { this.counter += amount; }`
   * e.g. NOT `function raiseCount(int amount=1){this.counter+=amount;}`
 * Statements MAY use single-line instead of block statements if the line fits under 100 character width, and legibility is good
   * e.g. `if (foundOne) break;` 
   * e.g. NOT `if (isFlagRaised) { isDone = true; newLimit = oldLimit << 16 | 255; setTimeout(newLimit); }`
 * Block open statements SHOULD have the curly brace on the same line as the control structure
   * e.g. `if (hasCondition) {`
   * e.g. `function doSomething() {`
 * Block close statements SHOULD have the curly brace on a line by itself
   * e.g. `}`
   * e.g. NOT `return true; }`
   * e.g. NOT `} else {`
 * Continuations of long lines SHOULD be indented on the next line if the line substantially breaks 100 character width
 * Conditional expressions MUST be enclosed in parentheses for each condition
   * e.g. `if ((x > 0) && (x < 10) && (y > 0) && (y < 10)) {}`
   * e.g. NOT `if (x>0 && x<10 && y>0 && y<10) {}`
 * SQL keywords SHOULD be ALL CAPS in queries

## Coding Tactics
 * Static properties of a class MUST be referenced via the class
   * e.g. `MyClass.convenientStaticMethod();`
   * e.g. NOT `instance = new MyClass(); instance.convenientStaticMethod();`
 * On-the-fly code evaluation such as eval() MUST NOT be used if it is available
 * Common object oriented design patterns SHOULD be used when possible
 * Singleton object oriented pattern MAY be used where there is a sound argument to do so
 * Large chunks of HTML, JSON, XML, SQL, etc SHOULD be represented with whatever form of block quote is supported by the language (similar to / AKA "heredoc")

## Code Comments
 * Source file head, and definition/declaration of Classes, Methods / Functions, and variables SHOULD use JavaDoc style block comments
 * Method / Function internal implementation SHOULD use C++ style single-line comment
   * e.g. `// Everything after the // is ignored for the rest of the line!`
 * Method / Function internal implementation SHOULD use comments to convey intent
   * e.g. `isFound = findUnicorn(); // See if we have any unicorns afield`
   * e.g. NOT `isFound = findUnicorn(); // Set isFound to result of findUnicorn function call`
 * Obscure logic / magic SHOULD be explained
   * e.g. `isReady = ((getGate() ^ 255) & 4); // PHP truthiness: third bit from gate == 0 for shift register to be ready`
 * Recursive algorithms MUST be clearly documented / indicated

## Code Complexity
 * Functions, Methods, and other Code Blocks SHOULD be small enough to fit on a single screen (~50 lines or less)
 * The depth of nested loops, iterators, closures SHOULD be less than five
 * Conditional expressions SHOULD be broken into "bite" size pieces for legibility to fit under 100 char line length

## Code Organization
* Generally reusable things SHOULD be grouped together into an externally referenced library/dependency
* Things related by function SHOULD be grouped together into a package/module
* Code SHOULD be structured to present the references/dependencies before the things that use it, roughly in this order:
1. Dependencies
2. Definitions (Constants, Interfaces, Classes)
3. Variable declarations, regardless of scope
4. Function / Method / Inner Class declarations for public, protected, default (package-private), then private, in that order
5. For overloaded Functions / Methods, less specific (more general) come first, followed by more specific
