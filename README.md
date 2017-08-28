# Templating and Serverside rendering


## What is Server-Side Rendering ?
`Server-Side rendering ` is the most common method for displaying information onto the screen. It works by converting HTML files in the server into usable information for the browser.

Whenever you visit a website, your browser makes a request to the server that contains the contents of the website. The request usually only takes a few milliseconds, but that ultimately depends on a multitude of factors:
- Your internet speed
- The location of the server
- How many users are trying to access the site

Once the request is done processing, your browser gets back the fully rendered HTML and displays it on the screen. If you then decide to visit a different page on the website, your browser will once again make another request for the new information. This will occur each and every time you visit a page that your browser does not have a cached version of.


### Client-Side Rendering

When developers talk about `client-side rendering`, they’re talking about rendering content in the browser using JavaScript. So instead of getting all of the content from the HTML document itself, you are getting a bare-bones HTML document with a JavaScript file that will render the rest of the site using the browser.

This is a relatively new approach to rendering websites, and it didn't really become popular until JavaScript libraries started incorporating it into their style of development. Some notable examples are `Vue.js` and `React.js`


## What are the pros and cons of serverside rendering vs clientside ?

#### Server-Side pros:

- Search engines can crawl the site for better SEO.
- The initial page load is faster.
- Great for static sites.

#### Server-Side cons:
- Frequent server requests.
- An overall slow page rendering.
- Full page reloads.
- Non-rich site interactions.

#### Client-Side pros:
- Rich site interactions
- Fast website rendering after the initial load.
- Great for web applications.
- Robust selection of JavaScript libraries.

#### Client-Side cons:
- Low SEO if not implemented correctly.
- Initial load might require more time.
- In most cases, requires an external library.


## What problems do templating languages solve ?

#### Templating Languages

This allows for reuse of the static elements of a web page, while allowing the dynamic elements to be defined based on the parameters of the web request. Web templates are also used in the creation of static content, providing a basic structure and appearance characteristic for web content.

##### Pros:

- Encourages good code organization (data generation is separate from presentation code)
- Output generation is more expressive (template syntax doesn't require a sea of string concatenation)
- Better productivity (common problems such as output encoding, iterating, conditionals, etc. have been handled)
- Generally requires less code overall (jade in particular has a very terse syntax)

##### Cons:

- Some performance overhead
- Yet another thing to learn


## Examples of functionality that templating languages provide ?

Functions are called by using their name followed by the required parameters separated by spaces.

### Functions:

#### *Example 1:*  Adding Numbers

> {{ add 1 2 }}

> => 3

#### *Example 2:*  Comparing Numbers
> {{ lt 1 2 }}

> => true (i.e., since 1 is less than 2)

### Logic

#### *Example 1:*   Using Context

>{{ range array }}

>    {{ . }}

>{{ end }}

### Conditionals

`if`, `else`, `with`, `or`, and `and` provide the framework for handling conditional logic. Like `range`, each statement is closed with an `{{end}}`.


#### *Example 1:* `if`

>{{ if isset .Params "title" }} ``` <h4> {{ index .Params "title" }}</h4>``` {{ end }}


#### *Example 2:* `if` … `else`

>{{ if isset .Params "alt" }}

>    {{ index .Params "alt" }}

>{{else}}

>    {{ index .Params "caption" }}

> {{ end }}

#### *Example 3:* `and` & `or`
> {{ if and (or (isset .Params "title") (isset .Params "caption")) (isset .Params "attr")}}
