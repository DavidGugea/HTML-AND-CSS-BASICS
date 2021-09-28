## The most important tags

### 1. \<dl>\<dt>\<dd>

Write a description list with terms & the definition for each term

dl = Description list
dt = Description term
dd = Definition Description

Example:

```HTML
<dl>
    <dt>4U</dt>
    <dd>For you</dd>

    <dt>ASAP</dt>
    <dd>As soon as possible</dd>

    <dt>FYI</dt>
    <dd>For your information</dd>
</dl>
```

### 2. \<details>

Provide a \<details> section for something ( it can be closed or opened by clicking on it). You can also provide a short summary about the details:

```HTML
<h3>Book </h3>
<details>
    <summary>See more</summary>
    <dl>
        <dt>Term 1</dt>
        <dd>Data 1</dd>

        <dt>Term 2</dt>
        <dd>Data 2</dd>

        <dt>Term 3</dt>
        <dd>Data 3</dd>

        <dt>Term 4</dt>
        <dd>Data 4</dd>

        <dt>Term 5</dt>
        <dd>Data 5</dd>
    </dl>
</details>
```

### 3. \<pre>\<code>\<kbd>\<samp>

\<code> is for souce code.
\<kbf> keyboard input
\<sampe> terminal output

\<pre> is for multiline output

```HTML
<section>
    <p>Source code here</p>
    <pre>
        <code>
#include &lt;stdio.h&gt;
int main(void){
    puts("Hello "World!);
    return 0;
}
        </code>
    </pre>
    </section>

<section>
    <p>You can select everything with <kbd>Ctrl</kbd> + <kbd>A</kbd>.</p>
    <pre>
        term#1&gt; <kbd>gcc-o Wall hello hello.c</kbd>
        term#1&gt; <kbd>./hello</kbd>
        <samp>Hello World!</samp>
        term#1&gt;
    </pre>
</section>
```