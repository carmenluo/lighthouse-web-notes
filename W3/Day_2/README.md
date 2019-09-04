#### || and && in a function ####
```
let a = 6 || 0 return 6
let b = "" || null return null
```
for ||, if the first operand is truthy, it is going to return the first one without evaluating the second one, otherwise it
will return the second one anway.<br/>
for &&, if the first operand is falsey, it is going to return the first one otherwise the second one.<br/>

## Today: CRUD Functions and Cookies ##
<ol>
  1. Database
  <ul>
    <li>Even if we declare fnction in our logic, if we don't pass it into render as params, the views can't use it</li>
  </ul>
  2. Post
  <ul>
    <li>Use put, we will have something call url encoded. you will see all the submit info in the url</li>
    <li>express.urlencoded({extended:false}) to tell the route that we need to use the data in the body, after taht we can
    see the req.body, otherwise it will see undefined. Basically before we use badyParser, but right now it is built in 
    express<br/>
    (in order to read HTTP POST data , we have to use "body-parser" node module. body-parser is a piece of express 
      middleware that reads a form's input and stores it as a javascript object accessible through **req.body**)</li>
  </ul>
  3. Form
  <ul>
    <li>In the form that we want to submit, if we don't submit it with the name, basically we are telling the browser
    that you don't need to submit</li>
  </ul>
</ol>

## COOKIES ##
<ol>
  <li>Third party cookie: Website store the real cookie for each client in server but only the id of client in client pc</li>
  <li><b>Tracking Pixels for Retargeting:</b> One website can actually contains bit for other website in cookie. With the bits enabled, the other website embeded these bits can access the cookie they save to our computer earlier.
  </li>
  <li><b>If statement in EJS</b>
    typeof username == 'undefined'. this is tricky, I thought if I didn't pass username as parameter, username would be
    "undefined'. But I get error. It turned out that we need to check type
  </li>
</ol>
```
<%if (typeof username == 'undefined') { %>
<% } else{ %>  
<% } %>
```
