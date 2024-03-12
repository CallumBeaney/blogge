+++
title="Medium-blending and making an ASCII Christmas business card"
date="2024-03-11"
+++


Something I really enjoy, across all forms of human expression, is a novel combination of styles or phenomena belonging to distinct and incongruous domains -- uncynically playful incursions between contexts with well-understood boundaries. The novel thing should be somewhat superficial and be of minimal utility but for as a thing to be seen and enjoyed. Something for _fun_, had cleverly--but the cleverness of the thing should usually only be noted, not explained; something too simple to convincingly analyse without airs; still too refined in concept and design to dismiss as entirely empty.  

<br>  
  
{{ image(src="https://preview.redd.it/htzm54z4fxa61.jpg?auto=webp&s=2ead4d5145d253cd8b901255af004f205ec03f9f", position="left" style="width: 85vh;") }}
  
<br>

A pal recently sent me a good example of this: 15 lines of code for setting up an HTTP client [on the back of a metal business card](https://www.reddit.com/r/tinycode/comments/kvuoqj/wrote_an_http_client_in_python_that_can_fit_on_a/). This gave me an idea.

With the exception of really personal &/ hand-made ones I really dislike birthday and Christmas cards. I'm also quite uncomfortable pitching myself. So I wanted to make something whose novelty would allow me to disseminate my own "fun propaganda" (job market is Bad), which could also function (as intended) as a sincere & friendly mini-gift.  


```
    #  #
   ##  ##
  ###  ###
 ####  ####
```   

Way back in January 2022 I wrote a [C program](https://raw.githubusercontent.com/CallumBeaney/obfuscation/main/tree.c) based on the [CS50 Mario Pset](https://cs50.harvard.edu/x/2024/psets/1/mario/more/), which prints out the above shape at variable height.
    
My program turned that into a christmas tree, with little randomised snowflakes changing position every second:
```
    *  * ## *         
        *||#* *       
 * *   *#||#*  * *    
  **  ###||*##        
     *###||#*##       
    #####||*#### *       
*  *#####||##*### *   
    *    ||   *   *   
_________||_田______
```

I then ported this to Python and cut the linecount right down. It can be made terser but I like this to be _somewhat_ readable to an experienced dev. It needed to be brief enough to copy, obfuscated enough to not be obvious, but have hints enough to give them some ideas of what is happening as they type it out. Let's here recognise that, although Python is generally horrible, being able to do this much this tersely is nice: 

```Python
# iterate over a random subset of indicies that has been sorted numerically
for i in sorted(sample(range(len(var1)),int(var2/randint(0,10)))):
``` 

So, for Winter 2024, I'll be disseminating these.  
The font is a classic - Courier New, and the colour, that's _Bone_.  

{{ image(src="https://raw.githubusercontent.com/CallumBeaney/christmas-tree-card/main/img/mockBack.jpg", position="left" style="width: 65vh;") }}
<br>
{{ image(src="https://raw.githubusercontent.com/CallumBeaney/christmas-tree-card/main/img/mockFront.jpg", position="left" style="width: 65vh;") }}
  
I made up a few of these with some filofax divider paper and handed them out to folks at Tech Fair London in March 2024. They seemed to be received well. One of IBM's staff described me as a "true nerd" which I am choosing to interpret positively. My plan is to have around a hundred made and make it a project to send them to folks in the mail, drop them around places tech people work.  

A few days after, I found [Reuben Son](https://reubenson.com)'s site index, which, if you like what you've seen so far, you will probably also like (_this here below is an iframe and may not display well on a phone_): 
<iframe src="https://reubenson.com" width="600" height="600" frameborder="0"></iframe>

The same night I came across [Sunday Sites](https://sundaysites.cafe), which are HTML/CSS-only projects where folks design a single webpage project in a day. This little seasonal ASCII animation [Four Seasons](https://four-seasons.glitch.me) is likewise quite fun. You should take a look at the source code for that site in the console -- Séan's achieved that in a pretty novel way.  
   
So quickly I've thrown a [web version](https://callumbeaney.github.io/christmas-tree-card/) together too, as this very simple format is very nice. You can peek at the repo [here](https://github.com/CallumBeaney/christmas-tree-card/tree/main).

<iframe src="https://callumbeaney.github.io/christmas-tree-card/" width="600" height="600" frameborder="0"></iframe>

