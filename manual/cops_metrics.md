# Metrics

## Metrics/AbcSize

Enabled by default | Safe | Supports autocorrection | VersionAdded | VersionChanged
--- | --- | --- | --- | ---
Enabled | Yes | No | 0.27 | 0.66

This cop checks that the ABC size of methods is not higher than the
configured maximum. The ABC size is based on assignments, branches
(method calls), and conditions. See http://c2.com/cgi/wiki?AbcMetric
and https://en.wikipedia.org/wiki/ABC_Software_Metric.

### Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
Max | `15` | Integer

### References

* [http://c2.com/cgi/wiki?AbcMetric](http://c2.com/cgi/wiki?AbcMetric)
* [https://en.wikipedia.org/wiki/ABC_Software_Metric](https://en.wikipedia.org/wiki/ABC_Software_Metric)

## Metrics/BlockLength

Enabled by default | Safe | Supports autocorrection | VersionAdded | VersionChanged
--- | --- | --- | --- | ---
Enabled | Yes | No | 0.44 | 0.66

This cop checks if the length of a block exceeds some maximum value.
Comment lines can optionally be ignored.
The maximum allowed length is configurable.
The cop can be configured to ignore blocks passed to certain methods.

### Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
CountComments | `false` | Boolean
Max | `25` | Integer
ExcludedMethods | `refine` | Array
Exclude | `**/*.gemspec` | Array

## Metrics/BlockNesting

Enabled by default | Safe | Supports autocorrection | VersionAdded | VersionChanged
--- | --- | --- | --- | ---
Enabled | Yes | No | 0.25 | 0.47

This cop checks for excessive nesting of conditional and looping
constructs.

You can configure if blocks are considered using the `CountBlocks`
option. When set to `false` (the default) blocks are not counted
towards the nesting level. Set to `true` to count blocks as well.

The maximum level of nesting allowed is configurable.

### Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
CountBlocks | `false` | Boolean
Max | `3` | Integer

### References

* [https://rubystyle.guide#three-is-the-number-thou-shalt-count](https://rubystyle.guide#three-is-the-number-thou-shalt-count)

## Metrics/ClassLength

Enabled by default | Safe | Supports autocorrection | VersionAdded | VersionChanged
--- | --- | --- | --- | ---
Enabled | Yes | No | 0.25 | -

This cop checks if the length a class exceeds some maximum value.
Comment lines can optionally be ignored.
The maximum allowed length is configurable.

### Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
CountComments | `false` | Boolean
Max | `100` | Integer

## Metrics/CyclomaticComplexity

Enabled by default | Safe | Supports autocorrection | VersionAdded | VersionChanged
--- | --- | --- | --- | ---
Enabled | Yes | No | 0.25 | -

This cop checks that the cyclomatic complexity of methods is not higher
than the configured maximum. The cyclomatic complexity is the number of
linearly independent paths through a method. The algorithm counts
decision points and adds one.

An if statement (or unless or ?:) increases the complexity by one. An
else branch does not, since it doesn't add a decision point. The &&
operator (or keyword and) can be converted to a nested if statement,
and ||/or is shorthand for a sequence of ifs, so they also add one.
Loops can be said to have an exit condition, so they add one.

### Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
Max | `6` | Integer

## Metrics/LineLength

Enabled by default | Safe | Supports autocorrection | VersionAdded | VersionChanged
--- | --- | --- | --- | ---
Enabled | Yes | Yes  | 0.25 | 0.68

This cop checks the length of lines in the source code.
The maximum length is configurable.
The tab size is configured in the `IndentationWidth`
of the `Layout/Tab` cop.
It also ignores a shebang line by default.

This cop has some autocorrection capabilities.
It can programmatically shorten certain long lines by
inserting line breaks into expressions that can be safely
split across lines. These include arrays, hashes, and
method calls with argument lists.

If autocorrection is enabled, the following Layout cops
are recommended to further format the broken lines.

  - ParameterAlignment
  - ArgumentAlignment
  - ClosingParenthesisIndentation
  - FirstArgumentIndentation
  - FirstArrayElementIndentation
  - FirstHashElementIndentation
  - FirstParameterIndentation
  - HashAlignment
  - MultilineArrayLineBreaks
  - MultilineHashBraceLayout
  - MultilineHashKeyLineBreaks
  - MultilineMethodArgumentLineBreaks

Together, these cops will pretty print hashes, arrays,
method calls, etc. For example, let's say the max columns
is 25:

### Examples

```ruby
# bad
{foo: "0000000000", bar: "0000000000", baz: "0000000000"}

# good
{foo: "0000000000",
bar: "0000000000", baz: "0000000000"}

# good (with recommended cops enabled)
{
  foo: "0000000000",
  bar: "0000000000",
  baz: "0000000000",
}
```

### Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
AutoCorrect | `false` | Boolean
Max | `80` | Integer
AllowHeredoc | `true` | Boolean
AllowURI | `true` | Boolean
URISchemes | `http`, `https` | Array
IgnoreCopDirectives | `true` | Boolean
IgnoredPatterns | `[]` | Array

### References

* [https://rubystyle.guide#80-character-limits](https://rubystyle.guide#80-character-limits)

## Metrics/MethodLength

Enabled by default | Safe | Supports autocorrection | VersionAdded | VersionChanged
--- | --- | --- | --- | ---
Enabled | Yes | No | 0.25 | 0.59.2

This cop checks if the length of a method exceeds some maximum value.
Comment lines can optionally be ignored.
The maximum allowed length is configurable.

### Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
CountComments | `false` | Boolean
Max | `10` | Integer
ExcludedMethods | `[]` | Array

### References

* [https://rubystyle.guide#short-methods](https://rubystyle.guide#short-methods)

## Metrics/ModuleLength

Enabled by default | Safe | Supports autocorrection | VersionAdded | VersionChanged
--- | --- | --- | --- | ---
Enabled | Yes | No | 0.31 | -

This cop checks if the length a module exceeds some maximum value.
Comment lines can optionally be ignored.
The maximum allowed length is configurable.

### Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
CountComments | `false` | Boolean
Max | `100` | Integer

## Metrics/ParameterLists

Enabled by default | Safe | Supports autocorrection | VersionAdded | VersionChanged
--- | --- | --- | --- | ---
Enabled | Yes | No | 0.25 | -

This cop checks for methods with too many parameters.
The maximum number of parameters is configurable.
Keyword arguments can optionally be excluded from the total count.

### Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
Max | `5` | Integer
CountKeywordArgs | `true` | Boolean

### References

* [https://rubystyle.guide#too-many-params](https://rubystyle.guide#too-many-params)

## Metrics/PerceivedComplexity

Enabled by default | Safe | Supports autocorrection | VersionAdded | VersionChanged
--- | --- | --- | --- | ---
Enabled | Yes | No | 0.25 | -

This cop tries to produce a complexity score that's a measure of the
complexity the reader experiences when looking at a method. For that
reason it considers `when` nodes as something that doesn't add as much
complexity as an `if` or a `&&`. Except if it's one of those special
`case`/`when` constructs where there's no expression after `case`. Then
the cop treats it as an `if`/`elsif`/`elsif`... and lets all the `when`
nodes count. In contrast to the CyclomaticComplexity cop, this cop
considers `else` nodes as adding complexity.

### Examples

```ruby
def my_method                   # 1
  if cond                       # 1
    case var                    # 2 (0.8 + 4 * 0.2, rounded)
    when 1 then func_one
    when 2 then func_two
    when 3 then func_three
    when 4..10 then func_other
    end
  else                          # 1
    do_something until a && b   # 2
  end                           # ===
end                             # 7 complexity points
```

### Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
Max | `7` | Integer
