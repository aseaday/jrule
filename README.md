Rule.js
===

Rule.js is a calc driver for rule engine. Because there is no good package for rule engine.

### Summary

In an rule engine, a simple rule could be like:

```json
{
    'fact': 'index',
    'operator': 'greaterThan',
    'value': 100
}
```

But acctually, A rule shoud be 

```json
{
    'and': [
        {
           'fact': 'index',
            'operator': 'greaterThan',
            'value': 100 
        }, 
        {
            'fact': 'deviceName',
            'operator': 'equals',
            'value': 'sensor'
        }
    ]
}
```

When rules grows, it is very slow for node.js and other javascript framework to handle it, because stream data usually recevies at a very high speed. We need a more effective framework to work out it. It is why rule.js emerge and what rule.js solves.

### rule intermidate language

rule intermidate language has the following rules:

```
ops := greaterThan | in
fact := reference | imm value;
rule := when :fact :ops :value
rule: = when :fact not :ops :value
rule := when :rule and :rule
rule := when :rule or :rule
```
