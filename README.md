# Spabs
Spabs are an attempt to end the war between developers over Spaces vs. Tabs once and for all.

## What is a Spab?
Spabs _look_ like Spaces but can be indented or dedented like Tabs.

The idea is simply that when indenting, your code editor would insert Spabs instead of just spaces or tabs.

For example, if your project is configured to indent with two spaces, when you press the Tab key you would get:
```
SPAB_START, SPAB_END
```

If your project is configured to indent with four spaces, you would get:
```
SPAB_START, SPACE, SPACE, SPAB_END
```

## Spab-Spans
A spab-span is a `SPAB_START` to `SPAB_END` chararacter span with any number of `SPACE` characters in between. If any other 
character appears between `SPAB_START` and `SPAB_END` (including new line characters) then the span is broken and both 
`SPAB_START` and `SPAB_END` characters are to be treated as normal space characters.

Nesting spab-spans is not suported. A `SPAB_START` character will break a spab-span like any other non-space character.

#### example

```
SPAB_START, SPACE, SPAB_START, SPACE, SPAB_END, SPACE, SPAB_END
                   ^                         ^
                   └────────────┬────────────┘
                            SPAB_SPAN
```

# Editing

## Spab aware editor
When using a spab-aware text editor...

* deleting any character in a spab-span should delete the entire spab-span.
* selecting any character in a spab-span should select the entire spab-span.
* moving a cursor onto a spab-span from above, below or jumping, the cursor should move onto the start or end of the spab-span
based on if the cursor is attempting to move onto the front half or back half of the span respectively.
* when the cursor is at the start or end of a spab-span, moving onto the span should jump the cursor to the
opposite side of the span.
* using a find-all or multi-cursor function, spaces inside of a spab-span should not be considered space characters.
* using a find-all or multi-corsor function to select spab-spans, should cause other spab-spans to be selected as individual entities.
* a spab span should be rendered based on a users configured tab size regardless of how many space characters are actually in the spab span.
* inserting a spab-span should insert a number of spaces consistent with the files tab size such that the sum of all characters in the span
equals the tab size, including the `SPAB_START` and `SPAB_END` characters.
* a files tab size should be inferred by the first spab-span in the file.
* formatting a file with mixed spaces, tabs and spabs should replace all leading tabs, spaces and spab-spans with spab-spans. Tabs will be replaced
with spab-spans 1 for 1 while a number of sequential spaces based on the files tab-size will be replaced with an equal sized spab-span.

## Spab unaware editor
When using a spab-unaware editor the `SPAB_START` and `SPAB_END` characters are treated as normal unicode characters, and rendered as a space.

## Programming languages
All languages should treat spabs as spaces for the purposes of parsing and whitespace-significant indentation purposes. Languages such as python or yaml will see them
as normal space characters.

# Reference
- [Spab Proposal](PROPOSAL.md)
- [Unicode, Inc proposal page](http://www.unicode.org/pending/proposals.html)

    

     
