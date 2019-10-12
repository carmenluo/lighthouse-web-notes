In web development, we always need to deal with all kinds of data. So what kind of "container" that we want to put all these data into should become something that we need to plan carefully in our application. This is container is what we call data structure in computer science. Basic data structures includes Array, Linked list, Stack, Tree and etc. We are going to focus on tree in this Article.
#### DOM
Open a webpage, what we see in the browser might not be something that we can relate to tree. However, if we open the developer tool we can see the web page written using HTML. Figure 1 shows the tree that corresponds to each of the HTML tags used to generate the page.
```
<html xmlns="http://www.w3.org/1999/xhtml"
      xml:lang="en" lang="en">
<head>
    <meta http-equiv="Content-Type"
          content="text/html; charset=utf-8" />
    <title>simple</title>
</head>
<body>
<h1>A simple web page</h1>
<ul>
    <li>List item one</li>
    <li>List item two</li>
</ul>
<h2><a href="*"></a><h2>
</body>
</html>
```
