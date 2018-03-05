# How to write JavaScript on Sourcico projects

1. Thou shall not use `var`. Thou shall prefer `const` where applicable, otherwise thou shall use `let`.

E.g.

```javascript
// bad
var x = 3;

// very, very, bad
for (var i = 0; i < buttons.length; i++) {
    buttons.addEventListener("click", function() {
        console.log(i)
    });
}

// good
const x = 3;

for (let i = 0; i < buttons.length; i++) {
    buttons.addEventListener("click", function() {
        console.log(i)
    });
}
```

2. Thou shall not concatenate strings yourself. Just treat `+` as being an invalid operator for manipulating strings. Use template literals exclusively if the string is dynamic, or use regular quotes if the string is not.

```javascript
// bad
const greeting = "Hi, " + name + "!";

// worse
const heading = "<" + heading + ">" + title + "</"+ heading + "><div class='" + subtitleClass + "'>" + subtitle + "</div>";

// good
const greeting  = `Hi, ${name}!`;

const heading = `
        <${heading}>
            ${title}
        </${heading}>
        <div class='${subtitleClass}'>
            ${subtitle}
        </div>
`
```

3. Thou shall not use type coercion to check if things are equal, i.e. don't use the `==` and `!=` operator, use the `===` and `!==` operators instead.
