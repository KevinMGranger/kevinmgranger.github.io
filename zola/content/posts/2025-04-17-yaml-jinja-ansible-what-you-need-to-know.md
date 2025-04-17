+++
title = "What You Need to Know About YAML and Jinja in Ansible"
date = 2025-04-17
draft = true
+++

These technologies all seem simple on the surface,
and easy enough to learn through examples.
But once we start using them in more complex ways,
it's important to make sure our understanding is deep and formal.

Please note: much of the information here might seem redundant or obvious,
but this post is meant for a wide audience,
and seeks to emphesize some info usually taken for granted or widely misunderstood!

Some info also might be oversimplified--
this document is meant to help you learn
Enough To Get By, not to be an expert.

## What is YAML?

Yaml is a:

1. **Standardized**
2. **Serialization Format**.

Let's review what I mean by that.

### Standardized
There is a [formal specification][yaml-spec] for it.
It's not just some slapdash assortment of various libraries for
working with something that looks YAML-ish[^1]

But you don't have to read the whole thing!
The wonderous
[Learn X in Y minutes where X = YAML](https://learnxinyminutes.com/yaml/)
is good enough!

There is also the wonderful
[YAML Multiline Strings site][yaml-multiline],
which will be important later.

### Serialization format
It is a way to encode almost any data structure you can think of,
but we're basically using it as an easier-to-write-and-read JSON[^2].


[yaml-spec]: https://yaml.org/spec/
[yaml-multiline]: https://yaml-multiline.info/

[^1]: Buggy implementations aside :)

[^2]: It's technically not a superset of JSON, as many claim.
      Still, it's unlikely you'll find that out the hard way.