To dig into Data Structure - Tree In web development, we always need to deal with all kinds of data. What kind of "container" that we want to put all these data into should become something that we need to plan carefully in our application. This container what we call a data structure in computer science. Basic data structures includes Array, Linked list, Stack, Tree, etc. We are going to focus on tree in this article.

#### DOM
Open a webpage, what we see in the browser might not be something that we can relate to the tree. However, if we open the developer tool we can see the web page written using HTML. Figure 1 shows the tree that corresponds to each of the HTML tags used to generate the page.
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
![Figure1](https://github.com/carmenluo/lighthouse-web-notes/blob/master/W8/htmltree.png) <br>
Figure 1: Tree representation of HTML<br>
The `<html>` element is the parent, the `<body>` is a child, and the `<h1>` element is a child of the `<body>` element. All these nested tags would become much more clear when we represent them in these hierarchy style.
#### DATABASE
Tree is also commonly seen in DATABASE design.
Let's take another look at the official Durian org chart:
![chart](https://github.com/carmenluo/lighthouse-web-notes/blob/master/W8/boaN2Sy.png) <br>
What if I want to know the total number of employees in all departments under Craig? That's when tree comes in handy. We can represent every person as a node.<br>

##### Node
<ul>
 <li> data stores a value
 <li> parent point to a node's parent
 <li> children point to the next node in the list
</ul>

##### Tree
<ul>
 <li> root: the top-level node of a tree
 <li> search: find the specific node in the tree
 <li> add: insert another node in the tree
 <li> remove: delete the node from the tree
</ul>
We can imagine that our app might need to deal with a lot of BST operations (e.g., search, max, min, insert, delete.. etc). It takes O(h) time where h is the height fo the BST. It makes sense when the structures are kinda balanced so that we don't need to worry too much about the worst case. But what if we have an extremely large dataset with one branch is way larger than the others? 
That's why we have Balanced BST like Red-Black Trees that ensure we have a better performance for these operations of O(logN) time.

#### Red-Black Tree
<strong> Rules </strong>
<ul>
 <li> Each node is either red or black
 <li> Root node is always black
 <li> if a node is red, then its child node must be black
 <li> There are no two adjacent red nodes (A red node cannot have a red parent or red child).
</ul>
<strong> How does Red-Black Tree remains balance</strong>
A simple example to understand balancing is, a chain of 3 nodes is not possible in the Red-Black tree. We can try any combination of colors and see all of them violate Red-Black tree property.

![example](https://github.com/carmenluo/lighthouse-web-notes/blob/master/W8/Screenshot%20from%202019-10-12%2012-33-29.png) <br>

##### Conclusion 
Trees simulate hierarchical data. Whenever you think you need this type of hierarchy, such as web development or company structure, consider using a tree!
