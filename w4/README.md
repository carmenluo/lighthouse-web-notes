#### CSS positioning : relative, absolute:
[tutorial](https://dzone.com/articles/css-position-relative-vs-position-absolute)
1. when we use <b>relative</b>, if we don't specify top, botton, left, right it is not going to have any effect. And it is relative
to itself. 
2. For <b>absolute</b>, if we have parent as relative and child absolute, it is going to absoulte the child based on how the parent look.
3. <b>Fixed</b>, basically similar to absolute, but it is relative the browser viewpoint
4. <b>Z-index</b>: assigning the stack order, let's say z-index:1 and z-index: 2, 2 is going to stack on top of 1

#### CSS Parent and Child
1. In most case, child wil inherit whatever from parent. However, textarea is an exception because textarea default background is white while most other tags are transparent.
2. In html, when we load it a stylesheet, it is going to render the the html, so the last style sheet would rewrite the first one.
3. Each browser has the default user-agent stylesheet. In case to make some standard style, we also have the normalize style for all browser.

#### Event monitor
1. Can use monitorEvent to monitor all the event [example](./goJAx.gif)
