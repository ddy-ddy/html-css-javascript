## Purpose

Accessibility is making your webpage easy for all people to use – even people with disabilities.

In this course, you'll build a quiz webpage. You'll learn accessibility tools such as keyboard shortcuts, ARIA attributes, and design best practices.



## Effect

<img src="https://tva1.sinaimg.cn/large/e6c9d24egy1h4wc4gh8apj20oy11gjt3.jpg" style="zoom:50%;" />

## Knowledge

#### 1. Head里面通常写的内容

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

#### 2. aria-labelledby属性有什么用？

- To increase the page accessibility, the `role` attribute can be used to indicate the purpose behind an element on the page to assistive technologies. The `role` attribute is a part of the *Web Accessibility Initiative* (WAI), and accepts preset values.

- Every `region` role requires a visible label, which should be referenced by the `aria-labelledby` attribute.

```html
<section role="region" aria-labelledby="student-info"></section>
```

#### 3. 如何设置单选？

- 将input的类型设置为radio
- 多个radio类型的type设置value属性为同一个值

```html
<input type="radio" id="q1-a1" name="q1" value="true" />
<input type="radio" id="q1-a2" name="q1" value="false" />
```

#### 4. 如何用CSS定位某个元素前面的pseudo-element？

- To prevent unnecessary repetition, target the `before` pseudo-element of the `p` element

```css
p::before{
	content:"Question #";
}
```

#### 5. 如何设计一个带下拉框的选择器？

- select元素里面嵌套多个option元素
- 每个option元素设置对应的值

```html
<select required>
	<option value="">Select an option</option>
	<option value="yes">Yes</option>
	<option value="no">No</option>
</select>
```

#### 6. 如何设计一个多行多列的文本输入框？

```html
<textarea rows="5" cols="24" placeholder="Who is flexbox..."></textarea>
```

#### 7. 如何设计一个提交按钮？

```html
<form method="post" action="example">
	<button type="submit">Submit</button>
</form>
```



## Code

- index.html

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta name="description" content="freeCodeCamp Accessibility Quiz practice project" />
    <title>Accessibility Quiz</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <header>
      <img id="logo" src="https://cdn.freecodecamp.org/platform/universal/fcc_primary.svg">
      <h1>HTML/CSS Quiz</h1>
      <nav>
        <ul>
          <li><a href="#student-info">INFO</a></li>
          <li><a href="#html-questions">HTML</a></li>
          <li><a href="#css-questions">CSS</a></li>
			  </ul>
      </nav>
    </header>
    <main>
      <form method="post" action="https://freecodecamp.org/practice-project/accessibility-quiz">
        <section role="region" aria-labelledby="student-info">
          <h2 id="student-info">Student Info</h2>
          <div class="info">
            <label for="student-name">Name:</label>
            <input type="text" name="student-name" id="student-name" />
          </div>
          <div class="info">
            <label for="student-email">Email:</label>
            <input type="email" name="student-email" id="student-email" />
          </div>
          <div class="info">
            <label for="birth-date">D.O.B.<span class="sr-only">(Date of Birth)</span></label>
            <input type="date" name="birth-date" id="birth-date" />
          </div>
        </section>
        <section role="region" aria-labelledby="html-questions">
          <h2 id="html-questions">HTML</h2>
          <div class="question-block">
            <p>1</p>
            <fieldset class="question" name="html-question-one">
              <legend>
                The legend element represents a caption for the content of its
                parent fieldset element
              </legend>
              <ul class="answers-list">
                <li>
                  <label for="q1-a1">
                    <input type="radio" id="q1-a1" name="q1" value="true" />
                    True
                  </label>
                </li>
                <li>
                  <label for="q1-a2">
                    <input type="radio" id="q1-a2" name="q1" value="false" />
                    False
                  </label>
                </li>
              </ul>
            </fieldset>
          </div>
          <div class="question-block">
            <p>2</p>
            <fieldset class="question" name="html-question-two">
              <legend>
                A label element nesting an input element is required to have a
                for attribute with the same value as the input's id
              </legend>
              <ul class="answers-list">
                <li>
                  <label for="q2-a1">
                    <input type="radio" id="q2-a1" name="q2" value="true" />
                    True
                  </label>
                </li>
                <li>
                  <label for="q2-a2">
                    <input type="radio" id="q2-a2" name="q2" value="false" />
                    False
                  </label>
                </li>
              </ul>
            </fieldset>
          </div>
        </section>
        <section role="region" aria-labelledby="css-questions">
          <h2 id="css-questions">CSS</h2>
          <div class="formrow">
            <div class="question-block">
              <label for="customer">Are you a frontend developer?</label>
            </div>
            <div class="answer">
              <select name="customer" id="customer" required>
                <option value="">Select an option</option>
                <option value="yes">Yes</option>
                <option value="no">No</option>
              </select>
            </div>
            <div class="question-block">
              <label for="css-questions">Do you have any questions:</label>
            </div>
            <div class="answer">
              <textarea id="css-questions" name="css-questions" rows="5" cols="24" placeholder="Who is flexbox..."></textarea>
            </div>
          </div>
        </section>
        <button type="submit">Submit</button>
      </form>
    </main>
    <footer>
      <address>
        <a href="https://freecodecamp.org">freeCodeCamp</a><br />
        San Francisco<br />
        California<br />
        USA
      </address>
    </footer>
  </body>
</html>

```

- styles.css

```css
@media (prefers-reduced-motion: no-preference) {
  * {
    scroll-behavior: smooth;
  }
}

body {
  background: #f5f6f7;
	color: #1b1b32;
	font-family: Helvetica;
	margin: 0;
}

header {
  width: 100%;
	height: 50px;
	background-color: #1b1b32;
	display: flex;
  justify-content: space-between;
  align-items: center;
  position: fixed;
  top: 0;
}

#logo {
  width: max(100px, 18vw);
	background-color: #0a0a23;
  aspect-ratio: 35 / 4;
	padding: 0.4rem;
}

h1 {
  color: #f1be32;
	font-size: min(5vw, 1.2em);
  text-align: center;
}

nav {
  width: 50%;
	max-width: 300px;
	height: 50px;
}

nav > ul {
  display: flex;
	justify-content: space-evenly;
  flex-wrap: wrap;
	align-items: center;
	padding-inline-start: 0;
	margin-block: 0;
	height: 100%;
}

nav > ul > li {
  color: #dfdfe2;
  margin: 0 0.2rem;
	padding: 0.2rem;
	display: block;
}

nav > ul > li:hover {
  background-color: #dfdfe2;
  color: #1b1b32;
  cursor: pointer;
}

li > a {
  color: inherit;
  text-decoration: none;
}

main {
  padding-top: 50px;
}

section {
  width: 80%;
  margin: 0 auto 10px auto;
  max-width: 600px;
}

h1,
h2 {
  font-family: Verdana, Tahoma;
}

h2 {
  border-bottom: 4px solid #dfdfe2;
  margin-top: 0px;
  padding-top: 60px;
}

.info {
  padding: 10px 0 0 5px;
}

.formrow {
  margin-top: 30px;
	padding: 0px 15px;
}

input {
  font-size: 16px;
}

.info label, .info input {
  display: inline-block;
  text-align: right;
}

.info input {
  width: 50%;
  text-align: left;
}

.info label {
  width: 10%;
  min-width: 55px;
}

.question-block {
  text-align: left;
	display: block;
	width: 100%;
	margin-top: 20px;
	padding-top: 5px;
}

p {
  margin-top: 5px;
  padding-left: 15px;
  font-size: 20px;
}

p::before {
  content: "Question #";
}

.question {
  border: none;
  padding-bottom: 0;
}

.answers-list {
  list-style: none;
  padding: 0;
}

button {
	display: block;
	margin: 40px auto;
	width: 40%;
	padding: 15px;
	font-size: 23px;
	background: #d0d0d5;
	border: 3px solid #3b3b4f;
}

footer {
	background-color: #2a2a40;
	display: flex;
	justify-content: center;
}

footer,
footer a {
  color: #dfdfe2;
}

address {
  text-align: center;
  padding: 0.3em;
}

.sr-only {
  position: absolute;
	width: 1px;
	height: 1px;
	padding: 0;
	margin: -1px;
	overflow: hidden;
	clip: rect(0, 0, 0, 0);
	white-space: nowrap;
	border: 0;
}

```

