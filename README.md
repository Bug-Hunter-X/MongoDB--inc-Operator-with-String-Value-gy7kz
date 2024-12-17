# MongoDB $inc Operator with String Value

This repository demonstrates a common error when using the `$inc` operator in MongoDB update queries.  The `$inc` operator is designed to increment a numerical field by a specified value.  However, if a string is provided instead of a number, the update operation might fail or produce unexpected behavior.

## Bug

The `bug.js` file contains an example of incorrect usage of the `$inc` operator:

```javascript
// Incorrect usage of $inc operator
db.collection('myCollection').updateOne({ _id: 1 }, { $inc: { count: '1' } });
```

This code attempts to increment the `count` field by '1' (a string). This will likely result in a failure or incorrect update.  MongoDB will likely return an error.

## Solution

The `bugSolution.js` file shows the correct usage of the `$inc` operator:

```javascript
// Correct usage of $inc operator
db.collection('myCollection').updateOne({ _id: 1 }, { $inc: { count: 1 } });
```

This corrected version provides the number 1 to `$inc`, ensuring that the `count` field is correctly incremented.