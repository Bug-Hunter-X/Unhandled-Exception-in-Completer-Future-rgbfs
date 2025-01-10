# Unhandled Exception in Completer Future

This repository demonstrates an uncommon error in Dart involving the use of `Completer` and `Future`. The `bug.dart` file contains code that, under certain timing conditions, can throw an unhandled exception. The `bugSolution.dart` file provides a corrected version.

The core issue lies in the potential for an exception to occur before the `Completer` has a chance to complete.   This is a subtle race condition that isn't always easily reproducible. 

## How to reproduce (in some cases): 

While the error is not guaranteed to occur on every run due to timing, running the code may reveal this unhandled exception. The error is highly timing-dependent and may only appear under specific conditions. 

## Solution:

The solution involves better exception handling, as shown in `bugSolution.dart`, either by adding a `catchError` to the future or with a `try-catch` block.