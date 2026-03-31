# Seatwork #2 - Getting to know CSS Position and z-index.
### This seatwork will ask you to implement the different CSS position on a given code.
### short link to this .md file is: https://bit.ly/4c61P9K
#### Resources (also found in Khub week 5)
- [4 Minute Youtube Video on CSS Position](https://www.youtube.com/watch?v=YEmdHbQBCSQ)
- [CSS Position Tutorial](https://roycan.github.io/CssPositioningZIndexLab/)



```html
<!DOCTYPE html>
<html>
<head>
  <meta name="author" content="<your names>" />
  <meta name="revised" content="<date today>" />
  <style>
    body { font-family: Arial, sans-serif; }
    .header, .footer {
      background: lightblue;
      padding: 10px;
    }
    .footer {
       opacity: 0.5;
    }
    .sidebar {
      background: lightgreen;
      width: 150px;
      height: 200px;
    }
    .content {
      background: lightyellow;
      width: 300px;
      height: 200px;
    }    
  </style>
</head>
<body>
  <div class="header">Header</div>
  <div class="sidebar">Sidebar</div>
  <div class="content">Main Content</div>
  <div class="footer">Footer</div>
</body>
</html>
```
### Step 1 (Static vs Relative):

- Add in css ```position: relative; top: 20px; left: 20px;``` to .sidebar.

- Guided Question: What changed compared to the default static positioning? Try to give different values to top and left or you can change it to bottom, right. 
- Answer: Using position: relative took the sidebar out of static/default positioning. Now, we can use properties like top, bottom, left, right, to adjust it relative to its default position.

### Step 2 (Fixed):

- Add in css ```position: fixed; bottom: 0; width: 100%;``` to .footer.

- Guided Question: What happens when you scroll the page? Why does the footer behave differently from position relative?
- Answer: When the footer has a fixed position, it will always stay in the same location on the screen, regardless of where you scroll. This is good for footers, nav bars, etc. 

### Step 3 (Absolute):

- Add in css ```position: absolute; top: 66px; left: 200px;``` to .content.

- Guided Question: What is the effect of position: absolute on an element? How is it different from fixed?
- Answer: Absolute position takes out the element of usual static positioning, liked fixed. However, the reference point is the nearest "ancestor", which is just the first parent element not static in position.


### Step 4 : (Absolute)

- Add in html ```<div class="notice">Notice!</div>``` and include the css below:

```css
.notice {
    position: absolute;
    top: 60px;
    left: 400px;
    background: orange;
    padding: 10px;
    z-index: 2;
}
```

- Give .content a z-index: 1.

- Guided Question: Why does the notice appear on top of the content? What happens if you swap the z‑index values?
- Answer: Z-index affects the stacking order of elements occupying the same space in viewport. Higher z-index stacks the element higher. In this case, swapping z-index values would put notice "below" the content. 

- Challenge: 
    * What changes that you have to do on the code that will position .notice box on the top right corner of the .content box? Please write the code on paper as well (both html and css on the part of .notice and .content).
    - The div of notice box must be wrapped in the div of the main content, which acts of the parents container. Next, apply ```top: 0px; right: 0px;``` in css of notice box.
    * Try to change the position of .content to relative then to fixed. What do you observed each time?
    * What do you observe on about the effect of z-index on .notice and .content boxes?

3. Please answer the following reflection questions (15 minutes)

    a. Could you summarize the differences between the CSS position values (static, relative, absolute, fixed)? 
    - Static position is the default position of elements based on normal document flow. Relative position is similar to static, which uses the default location as the reference point, but has the ability to move relative to it.
    - Absolute position places the element out of normal document flow and has the ability to position relative to nearest positioned ancestor. 
    - Finally, fixed positioning "stamps" the element at a certain location on the screen.

    b. How does absolute positioning depend on its parent element?
    - When we say "nearest positioned ancestor", it is just a term for the element's container or parent element. The positioning checks for the immediate parent element that is not static and takes it as reference. 

    c. How do you differentiate sticky from fixed (you can research on sticky)?
    - Sticky positioning is a mix of relative and fixed positioning. It behaves as relative up to a threshold, staying in normal document flow. Once a scroll/position threshold is surpassed, it sticks to the edge of viewport or ancestor, like fixed. 

    d. If you were designing a webpage for a school event, how might you use positioning to highlight important information? Please give concrete examples.
    - Example 1: Keep a navigation bar fixed at top of screen for easy traversal of webpage.
    - Example 2: Important elements (like essential info or announcements) prominently showing in screen via z-index manipulation.
    - Example 3: A registration button stays fixed in scrolling, always being in frame of users' sight. 
