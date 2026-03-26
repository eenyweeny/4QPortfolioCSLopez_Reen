# Seatwork #2 - Getting to know CSS Position and z-index.
### This seatwork will ask you to implement the different CSS position on a given code.
### short link to this .md file is: https://bit.ly/4c61P9K
#### Resources (also found in Khub week 5)
- [4 Minute Youtube Video on CSS Position](https://www.youtube.com/watch?v=YEmdHbQBCSQ)
- [CSS Position Tutorial](https://roycan.github.io/CssPositioningZIndexLab/)

### Instructions: 
1. This is individual submission in khub, but you can work with a partner.  When you submit in khub please place both your names in the submission bin.
2. Guided Activity (30 minutes), please follow what is being required.  

    - Make a copy of this .md file to your Q4 repository and name it as **SectionLNseatwork2.md** example **9LiCruzSeatwork2.md**. Place it in your q4 repository vscode local computer. Committing frequently to your Github repository.  
    - Copy the code below and paste it inside a new file (name it as SectionLNseatwork2.html). Place this file in the same location where the .md file is saved. 
    - Change the content values of the meta tags to your names for author/s and the date today for revised.
    - Please do the following tasks that will ask you to reposition HTML elements then answer the guided question for each task on the .md file. Commit changes to the .md file and to the .html file as well.
    **- This seatwork is worth 20pts and should be submitted by the end of the period** The link to [KHub submission bin](https://khub.mc.pshs.edu.ph/mod/assign/view.php?id=15481).
      - Submit the links to your .md file and .html file.

```html
<!DOCTYPE html>
<html>
<head>
  <meta name="author" content="Reen Debbie S. Lopez" />
  <meta name="revised" content="March 27, 2026" />
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
    # When the sidebar's position is changed from static to relative, the element translates from its original position based on the values of top and left. For example, setting top: 20px and left: 20px moves the sidebar 20 pixels down and 20 pixels to the right. Unlike static positioning, the element still occupies its original space in the layout, so other elements are not affected. Changing the numbers/values of top, left, bottom, or right simply moves the element in different directions relative to its original position.

### Step 2 (Fixed):

- Add in css ```position: fixed; bottom: 0; width: 100%;``` to .footer.

- Guided Question: What happens when you scroll the page? Why does the footer behave differently from position relative?
    # When the footer is set to position fixed, it stays at the bottom of the screen even when the page is scrolled. This happens because fixed positioning relies on the viewport rather than the document flow. Unlike relative positioning, the footer is removed from the normal layout and does not move along with the rest of the page content.

### Step 3 (Absolute):

- Add in css ```position: absolute; top: 66px; left: 200px;``` to .content.

- Guided Question: What is the effect of position: absolute on an element? How is it different from fixed?
    # When an element is set to position absolute, it is eradicated from the normal document flow and positioned using top and left numbers/values. Its position relies on the nearest parent element that has a position value other than static. If no such parent element exists, it is positioned based on the entire page. Unlike fixed positioning, an absolutely positioned element moves when the page is scrolled because it is still tied to the document rather than the viewport.

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
    # The notice appears on top of the content because it has a larger z-index value. The z-index determines the elements' stacking order, where a larger value places the element in front. If the z-index values are swapped, the content will appear above the notice, possibly hiding it. This shows that z-index controls which elements are visible on top when they overlap.

- Challenge: 
    * What changes that you have to do on the code that will position .notice box on the top right corner of the .content box? Please write the code on paper as well (both html and css on the part of .notice and .content).
    * Try to change the position of .content to relative then to fixed. What do you observed each time?
    * What do you observe on about the effect of z-index on .notice and .content boxes?
        # To position the notice at the top right corner of the content box, the content element must be transformed to position relative, while the notice is set to position absolute with top set to 0 and right set to 0. This allows the notice to align itself within the boundaries of the screen/content.

        # When the position of the content is transformed to relative, the notice stays properly aligned inside it. However, when the content is transformed to fixed, it becomes attached to the screen, and the notice moves together with it since it is inside the content element.

        # The z-index affects which element overlaps. Elements with higher z-index values are displayed above those with lower values, as long as they are positioned elements.

3. Please answer the following reflection questions (15 minutes)

    a. Could you summarize the differences between the CSS position values (static, relative, absolute, fixed)?
      # The static position is the default position and does not allow movement using top or left. Relative position allows an element to move from its original position while still keeping its original space in the layout. Absolute positioning eradicates the element from the normal flow and positions it relative to its nearest positioned parent element. Fixed positioning also removes the element from the flow but keeps it fixed on the screen regardless of scrolling. 

    b. How does absolute positioning depend on its parent element?
      # Absolute positioning relies on the nearest parent element that has a position value such as relative, absolute, or fixed. If no parent has a defined position, the element is positioned relative to the entire screen/page. This is why setting a parent to position relative is important when controlling declared child elements.

    c. How do you differentiate sticky from fixed (you can research on sticky)?
      # Sticky positioning is akin to relative positioning at first, allowing the element to scroll normally. However, once it reaches a specific point, such as the top of the screen, it becomes fixed in that position. In contrast, fixed positioning keeps the element in the same place on the screen at all times regardless of scrolling.

    d. If you were designing a webpage for a school event, how might you use positioning to highlight important information? Please give concrete examples.
      # If I were to design a webpage for a school event, a fixed navigation bar on top of the screen can be used so that users can easily access different sections while navigating/scrolling. An absolute position can be used to place a “Register Now” button or any other important button at the corner of a banner image to make it more noticeable. Sticky positioning can be applied to section headers so they remain seen as users scroll through schedules. Relative positioning can be used to adjust spacing and alignment for better layout design.
