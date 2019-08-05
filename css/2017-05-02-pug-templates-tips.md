---
layout: post
title: Pug templates tips
published: true
---

# PUG templates tips

Pug templating recipes and debug tricks.

## Recipes

### Compile  pug file locally in command line

Useful to debug what pug files compile if you do not have access to compiles html \(with webpac for example\)

```text
pug -O '{"pretty": true}' sr-order.template.pug
```

### Mixins with block \(to wrap content inside a mixin\)

[https://github.com/neuland/jade4j/issues/11](https://github.com/neuland/jade4j/issues/11)

### How to use a json for data in commande line

[https://github.com/visionmedia/jade/issues/833](https://github.com/visionmedia/jade/issues/833)

```text
Option 1

This insane mixin works:

mixin json()
  - var oldbuf = buf; buf = [];
  block
  - var res = JSON.stringify(JSON.parse(buf.join('')));
  - buf = oldbuf;
  != res
You can then call it:

+json().
  [
    {
      "name": "ABC-Logistic",
      "file":  "Abc-logistic",
      "link":  "abc-logistic.co.jp"
    }
  ]
And the resulting file will contain:

[{"name":"ABC-Logistic","file":"Abc-logistic","link":"abc-logistic.co.jp"}]
```

### How to load data in a grunt base environnement

[https://github.com/gruntjs/grunt-contrib-jade\#data](https://github.com/gruntjs/grunt-contrib-jade#data)

```text
options: {
                pretty: true, // Output HTML in indented style
                doctype: 'html',
                data: {
                    links: grunt.file.readJSON("app/Resources/views/mixins/_vars.json"),
                },
            },
```

`#{link.title}` will be available  
Potentially we can load sevral data objects

### Multiline js in jade \(work in progress\)

[https://github.com/visionmedia/jade/issues/796](https://github.com/visionmedia/jade/issues/796)

### unescaped html tags inside a variable

[http://html2jade.org/](http://html2jade.org/)

```text
-var title = "blabla bl <br/> szlkjs mlklj ";

h3(class="fs1")
            | !{title}
```

### Conditional attributes

How to print an attributes, only if a js value is available to feed it For example angular directive attributes ng-click... should not be printed if there has no value.

div\(\#{myAttributes}\) just don't work \#{t} nterpolation work only in the attribute ""

To check [http://html2jade.org/](http://html2jade.org/)

```text
- var t = "la valeur de t"
- var z ="lkj"
p(class="klj" sdsd="#{t}")(title=s)(blang=z)
```

```markup
<p sdsd="la valeur de t" blang="lkj" class="klj"></p>
```

### Multiline tag content

```text
        .tip.
          Enter a valid
          email address
          such as <em>tj@vision-media.ca</em>.
```

### Dynamic Mixin call

[http://stackoverflow.com/questions/24392055/jade-templates-dynamically-calling-a-mixin?rq=1](http://stackoverflow.com/questions/24392055/jade-templates-dynamically-calling-a-mixin?rq=1)

```text
mixin blue
  div(class="blue") Blue
    block

mixin red
  div(class="red") red
    block

mixin para(type)
  - console.log(type);
  +#{type}()
    div Nice dynamic mixin call !


+para('blue')
+para('red')
```

Result

```markup
<div class="blue">Blue
  <div>Nice dynamic mixin call !</div>
</div>
<div class="red">red
  <div>Nice dynamic mixin call !</div>
</div>
```

### Dynamic attributes

[http://jade-lang.com/reference/attributes/](http://jade-lang.com/reference/attributes/)

```text
- var customAttributes = {'set-nav-pattern': true, 'calamar': "setCalamar()"}
div(class="blue")&attributes(customAttributes)
```

Result

```markup
<div class="blue" set-nav-pattern calamar="setCalamar()"></div>
```

## Debug pug or jade

### **unexpected token "indent"** :

Check if there is no added space at the end of a mixin definition.  
You can switch on the invisible character display to look up more easily...

### "Unexpected token 'tag' expected 'text', 'code', ':', 'newline' or 'eos'"

Wrong because their is no space between "Polaziste" and it's tag

```text
   label(for="polaziste")Polaziste
```

Fixed

```text
   label(for="polaziste") Polaziste
```

