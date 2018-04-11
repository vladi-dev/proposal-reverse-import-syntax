# ECMAScript Reverse Import Syntax

## [Status](https://tc39.github.io/process-document/)

**Stage**: 0

**Author**: [@vladi-dev](https://github.com/vladi-dev)

## Introduction

This proposal allows new syntax for various import statements. With current order of keywords `import ... from ...` 
it is impossible for IDE's to hint which functions or modules are available for import. This syntax proposal intends to
remove unnecessary need of the user to remember the name of imports or spending time looking up the names in the source
file. Using syntax `from "module" import "..."` will allow IDE's to lookup which exports are available in 
the "module" and suggest them to the user.

This proposal was inspired by Python language
[Python Import Statement](https://docs.python.org/3/reference/simple_stmts.html#import)

## Motivating Examples

Example:

```
from 'foo' import { bar, baz as zaz };
```

Another example to avoid having `from` as a reserved keyword (props to [Thomas Wood](https://github.com/IgnoredAmbience)):
```
import from 'foo' {bar, baz as zaz};
```

Side-effecting imports should still work:
```
import 'foo';
```


## Implementations

* [Babylon Fork Proof of Concept Plugin](https://github.com/vladi-dev/babel/pull/1)
