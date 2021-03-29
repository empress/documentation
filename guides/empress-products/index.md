There are a few different ways to define the similarities between Empress Products. We could take a historical approach and follow the innovations and how they were shared between the products after they were discoverd, or we could create a grid that compared each feature in each Empress Product like a Software as a Service pricing page.

I think a good way to start is to list out every official Empress Project and then explain the set of things that is common about each of products. There may be some fundemental differences between Empress Projects but there are always some core fundemental similarities.

## List of Empress Products

| Product      | Link                                     | Status | Exmple Site    |
| ------------ | ---------------------------------------- | ------ | -------------- |
| empress-blog | https://github.com/empress/empress-blog/ | Stable | [The Ember Blog] |
|              |                                          |        |                |

from talk:
- compare to starters - nit forking - not updates
- list of products (grouped by stability?)
-  

section about architecture
host app - empty shell - apart from ultimately markdown
system addon - creates a set of default content using blueprints
template addon - just html and css - swap templates by chaning a single dependency

npm init empress-blog-template - talk about template builders





1) you should have an extremely fast "quick start"
if you have a look at any of the readmes there is usually a quickstart of 2 or 3 lines that can get you started with a docs site with an example set of docs ready to go :thumbsup:
2) Markdown is the majority way to actually write the docs
this is intended to be a nice easy onramp for anyone wanting to participate, especially with field-guide because the code samples are "just Markdown code snippets" and you don't have to do anything special to get them to work
3) there needs to be a separation between the "brains" of the product and the "template"
this is why you see things like field-guide and field-guide-default-template and you can theoretically have any number of templates that provide some style. This may seem like it's not high-order enough to be part of the philosophy but it's extremely key in the way that everything works because you essentially have a public api between the brains addon and the template addon
4) you need to be able to download content dynamically
again this may seem odd to add to the philosophy list but it means that we're not doing any of this "pre compiling templates" solutions that some people have done to solve some of the more difficult problems with dynamic template rending
because of (2) I have been thinking that the API solution might not actually be something that dynamically loads API docs (like ember-cli-addon-docs) but instead it could just be a process that takes your code as in input and outputs Markdown (in a particular structure) that is pre-populated with your ESDocs or something
that way you can intervene and edit things that didn't work out right, but we would have a process where you could verify if your API docs are up to date during build time
alternatively we could have a set of components that could "render" the API docs, but again because of (4) that would mean that the API docs processing system would need to output consumable JSON (and in fact everything Empress is using JSON:API so that could be the common format here)
