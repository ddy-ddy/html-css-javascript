## Purpose

Accessibility is making your webpage easy for all people to use – even people with disabilities.

In this course, you'll build a quiz webpage. You'll learn accessibility tools such as keyboard shortcuts, ARIA attributes, and design best practices.



## Effect



## Knowledge

#### *1. Head里面通常写的内容*

- `charset` - specifies the character encoding of the page, and, nowadays, UTF-8 is the only encoding supported by most browsers.
-  `viewport` - tells the browser how to render the page. Including one betters visual accessibility on mobile, and improves *SEO* (search engine optimization).
- `description` - for accessibility and SEO. The value of the content attribute is used by search engines to provide a description of your page.
-  `title` -  is useful for screen readers to understand the content of a page. Furthermore, it is an important part of *SEO*.

```html
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta name="description" content="freeCodeCamp Accessibility Quiz practice project" />
    <title>Accessibility Quiz</title>
    <link rel="stylesheet" href="styles.css" />
</head>
```

#### *2. role="region"* & aria-labelledby

- To increase the page accessibility, the `role` attribute can be used to indicate the purpose behind an element on the page to assistive technologies. The `role` attribute is a part of the *Web Accessibility Initiative* (WAI), and accepts preset values.

- Every `region` role requires a visible label, which should be referenced by the `aria-labelledby` attribute.

```html
<section role="region" aria-labelledby="student-info"></section>
```





## Code

- index.html

```html

```

- styles.css

```css

```

