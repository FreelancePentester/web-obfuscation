
# Chapter 1 Introduction #
## Page 7 - Regular Expressions ##
This was reported as [Issue 5](https://code.google.com/p/web-obfuscation/issues/detail?id=5).

There was an error somewhere after final edition and printing. And an extra "A" slipped in to a code block:
```
A^\t+    Matches one or more Tab characters at the start of a string
```

should be

```
^\t+    Matches one or more Tab characters at the start of a string
```

# Chapter 2 HTML #
## Page 19 - History and overview ##
This was reported as [Issue 1](https://code.google.com/p/web-obfuscation/issues/detail?id=1).

A closing square bracket was mistakenly deleted during review:
```html

<![CDATA[
Here you can ...
]>
```

Should be
```html

<![CDATA[
Here you can ...
]]>
```

## Page 51 - Advanced markup obfuscation ##
This was reported as [Issue 2](https://code.google.com/p/web-obfuscation/issues/detail?id=2).

This is not an error by itself, but some people may have problem reproducing this.

```html

<![if IE 8.0]>
<script>alert(1)

Unknown end tag for &lt;/script&gt;

  // works on IE8
<![endif]>
```

This code is supposed to work on Internet Explorer 8 mode. Depending on the doctype of the page, it could load your browser in other mode.

## Page 51 - Advanced markup obfuscation ##
This was reported as [Issue 3](https://code.google.com/p/web-obfuscation/issues/detail?id=3).

During edition some dashes were missed:

```html

<!-[if<img src=x onerror=alert(1)//]--> works!
<b>000

Unknown end tag for &lt;/b&gt;


<!--[endif]->
```

should be

```html

<!--[if<img src=x onerror=alert(1)//]--> works!
<b>000

Unknown end tag for &lt;/b&gt;


<!--[endif]-->
```

## Page 52 - Advanced markup obfuscation ##
This was reported as [Issue 4](https://code.google.com/p/web-obfuscation/issues/detail?id=4).

A closing angle bracket got lost during editing.

```html

<!--[if true && ><script>alert(1)</script]->
000
<!--[endif]->
```

should be

```html

<!--[if true && ><script>alert(1)

Unknown end tag for &lt;/script&gt;

]->
000
<!--[endif]->
```