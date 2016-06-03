# Spabs
Spabs are an attempt to end the war between developers over Spaces vs. Tabs once and for all.

## What is a Spab?
Spabs _look_ like Spaces but can be indented or dedented like Tabs.

The idea is simply that when indenting, your code editor would insert Spabs instead of just spaces or tabs.

For example, if your project is configured to two spaces, when you press the Tab key you would get:
```
SPAB START, SPAB END
```

If your project is configured to four spaces, you would get:
```
SPAB START, SPACE, SPACE, SPAB END
```
When your cursor is located after a `SPAB END` and you press the `Backspace` key, it would delete all of the characters from `SPAB END` to `SPAB START`.


## Reference
- [Spab Proposal](PROPOSAL.md)
- [Unicode, Inc proposal page](http://www.unicode.org/pending/proposals.html)
 