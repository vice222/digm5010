## WEEK 2

###### Here is my first sketch study
<p class="codepen" data-height="446" data-theme-id="dark" data-default-tab="js,result" data-user="zian-liu" data-slug-hash="OJNEXKg" data-preview="true" style="height: 446px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="5010 AS1">
  <span>See the Pen <a href="https://codepen.io/zian-liu/pen/OJNEXKg">
  5010 AS1</a> by Zian Liu (<a href="https://codepen.io/zian-liu">@zian-liu</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

For my first sketch, I have added a few bounce effects. First of all, after detecting the collision event (the new point is out of canvas), the future points will all be calculated to the reverse direction by using `math.abs()` until the next collision. When the bouncing happens, I also add a little variant to the line, so you will see the line begins to vibrate. What is more, to make the animation more attractive, the line will change to various colors by touching different edges. This animation is like a dynamic screensaver, but out of fashion, like from the 90s. D:

I haven't used javascript for over three years. The most time I spent on this sketch is to figure out how to use the array correctly. When I was debugging the yellowtail scripts that Graham provides to us, I found the marks array not only includes a few pair s of dx, dy value, but also the mouse initial position x, y, and a boolean. After a little meditation and researching, I realized the same array in javascript could include different types like numbers, booleans, and strings together. However, most js tutorial websites neither mention that nor give a proper example.


An issue I'm thinking for the whole week is to achieve perfect symmetry. If I draw a specific pattern in the panel, after reflecting from the edge, neither the yellowtail script nor my codes can make the line remain the same as before. The pattern usually will become an irregular curve after the bouncing.

!<>(https://lh3.googleusercontent.com/pw/ACtC-3d6G_Tevzi12wrrPobva75ibK50ck8V9aGKRObVyzTrQ39CYxHZ3xsOpRx2tL9iQzIeM8hdR8_Ap1CaIGdNEJ9L_w2V-fJVAW17qaWbflhN9VcJXoZyDFSmrZufCKnz9ODfB23507lgx5eDdksH7827=w988-h969-no?authuser=0)

The script below is my initial thinking about this problem. Once the new point is out of the edge, the next vector should be exactly the last vector that brought the line to reach the edge but in a different direction. The vector after next should be precisely the vector before last but in a different direction. 

For the array, each time I ought to pop the tail to get and invert the previous vector and unshift the new point to the beginning of the array. Maybe?
Unfortunately, my script doesn't work well, but I think this concept is worth sharing.

```javascript
       //TO achieve a perfect sysmetry,

        
        first = mark.pop();
        //return current (last) point and remove it
        second = mark[mark.length - 2];
        //return the point before last point

        newP = mark[0];
        //assign newP to (any value)

        dx = second.x - first.x;
        dy = second.y - first.y;
        //get the last vector from the array

        newP.x = first.x + dx;
        newP.y = first.y - dy;        
        //turn it over to have the new point

        mark.unshift(newP);
```
