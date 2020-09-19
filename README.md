# digm5010


# WEEK 2

<p class="codepen" data-height="446" data-theme-id="dark" data-default-tab="js,result" data-user="zian-liu" data-slug-hash="OJNEXKg" data-preview="true" style="height: 446px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="5010 AS1">
  <span>See the Pen <a href="https://codepen.io/zian-liu/pen/OJNEXKg">
  5010 AS1</a> by Zian Liu (<a href="https://codepen.io/zian-liu">@zian-liu</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>





```javascript
       //TO achieve a perfect reflection,
       //get and rotate the previous vector 
        //from end to beginning
        
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