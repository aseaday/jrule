Rule.js
===

Rule.js is a fast calculator for rule engine. Because there is no good package for rule engine.

### Summary
In an rule engine, a simple rule could be like:

```json
{
    "fact": "index",
    "operator": "greaterThan",
    "value": 4000
}
```
When rules grows, it is very slow for node.js and other javascript engine to work out it. Streaming messages could happens at a very high speed. We need a more effective library to get it done. It is why rule.js emerge and what it solves.

### Rule intermidate language

rule intermidate language has the following rules:

```
ops := greaterThan | in
fact := reference | imm value;
rule := when :fact :ops :value
rule: = when :fact not :ops :value
rule := when :rule and :rule
rule := when :rule or :rule
```

### Benchmark
