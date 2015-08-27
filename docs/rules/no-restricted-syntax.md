# Disallow certain syntax (no-restricted-syntax)

Some code bases prefer to not use certain features of JavaScript such as `FunctionExpression` or `WithStatement`. This rule warns on the passed node types.

## Rule Details

This rule is aimed at eliminating certain syntax from your JavaScript. As such, it warns whenever it sees a node type that is restricted by its options.

### Options

This rule takes a list of strings where strings denote the node types:

```json
{
    "rules": {
        "no-restricted-syntax": [2, "FunctionExpression", "WithStatement"]
    }
}
```

The following patterns are considered warnings:

```js
/* eslint no-restricted-syntax: [2, "FunctionExpression", "WithStatement"] */

with (me) {
    dontMess();
}

var doSomething = function () {};
```

The following patterns are not considered warnings:

```js
/* eslint no-restricted-syntax: [2, "FunctionExpression", "WithStatement"] */

me.dontMess();

function doSomething() {};
```

## When Not To Use It

If you don't want to restrict your code from using any JavaScript features or syntax, you should not use this rule.

## Related Rules

* [no-alert](no-alert.md)
* [no-console](no-console.md)
* [no-debugger](no-debugger.md)
