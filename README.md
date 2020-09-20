## WEEK 2

###### Here is my first sketch study
<p class="codepen" data-height="446" data-theme-id="dark" data-default-tab="js,result" data-user="zian-liu" data-slug-hash="OJNEXKg" data-preview="true" style="height: 446px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="5010 AS1">
  <span>See the Pen <a href="https://codepen.io/zian-liu/pen/OJNEXKg">
  5010 AS1</a> by Zian Liu (<a href="https://codepen.io/zian-liu">@zian-liu</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

For my first sketch, I've added a few bounce effects. First of all, after detecting the collision event (new point is out of canvas), the future points will all be calculated to the reverse direction by using `math.abs()` until next collision. When the bouncing happens I also add little variant to the line, so you will see the line begins to vibrate. What's more, to make the animation more attractive, the line is going to change to various colors by touching different edges. This is like a dynamic screensaver, but out of fashion, like from 90s. D:

I haven't used javascript over 3 years. I thought it should be easy-to-use for me this time after I learned so many languages but I was wrong. The most time I spent on this sketch is to figure out how to use the array correctly. When I debugging the yellowtail scripts that Graham provides to us, I found the marks array not only includes a few pair s of dx, dy value, but also the mouse initial position x, y and a boolean. After a little meditaion and researching I realized the same array in javascript can include different types like numbers, booleans and strings together. However, most js tutorial websites neither mention that nor give a proper example.


An issue I'm thinking for the whole week is to achieve a perfect symmetry. If I draw a specific pattern in the panel, after reflecting from the edge, neither the yellowtail script nor my codes are able to make the line to remain the same as before. The pattern usally will become a irregular curve after the bouncing.

The script below is my initial thinking about this problem. Once the new point is out of the edge, the next vector should be excatly the last vector that brought the line to reach the edge but with different direction. The vector after next should be excatly the vector before last but with different direction. 

For the array, each time I have to pop the tail to get and invert the previous vector and unshift the new point to the beginning of the array. Maybe?
Unfortunatley my script dosne't work well but I think this concept is worth to share.


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
