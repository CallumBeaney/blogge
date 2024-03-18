+++
title="Medium-blending and making an ASCII Christmas business card"
date="2024-03-11"
+++

Something I really enjoy, across all forms of human expression, is a novel combination of styles or phenomena belonging to distinct and incongruous contexts or domains -- clever, uncynically playful incursions between well-known boundaries. The sort of thing where cleverness of the novel thing is usually best left only noted, not explained, because it's too simple to analyse without coming off as pretentious, but still is refined enough in concept and design to be seen as an aesthetic object.  

<br>  
{{ image(src="https://preview.redd.it/htzm54z4fxa61.jpg?auto=webp&s=2ead4d5145d253cd8b901255af004f205ec03f9f", position="left" style="width: 85vh;") }}
<br>

A pal recently sent me a good example of this: 15 lines of code for setting up an HTTP client [on the back of a metal business card](https://www.reddit.com/r/tinycode/comments/kvuoqj/wrote_an_http_client_in_python_that_can_fit_on_a/).  
  
I guess a small part of the joke in American Psycho's [business card scene](https://www.youtube.com/watch?v=aZVkW9p-cCU) is that the cards themselves have bad design (poor spacing, typos, distracting textures etc), yet they care about them so much. Most business cards I pick up at trade fairs are contrariwise the most perfunctory things, totally discardable. A good execution of the below genre of card isn't _bad_, but wouldn't it be better to receive something more like the above card, a curio to keep for its own merit?   

<br>
{{ image(src="https://external-preview.redd.it/mk8leSSX4tYcql92G51e8K1cwnKsgqqPPHQsmNu8cn0.jpg?auto=webp&s=4e7cd63c8fdffeb459a1b12cf50483911b6b93f9", position="left" style="width: 100vh;") }}
<br>

With the exception of hand-made ones, I really dislike most birthday and Christmas cards. Sending someone an overpriced piece of card stock with a bad joke printed on it having written their name at the top of the template and one's own at the bottom, is exactly the sort of impersonal behaviour American Psycho mocks yuppies for.  

I wanted to make something whose novelty would work in both these contexts, functioning as "fun propaganda" in tech (job market is Bad), but also able to function (as intended) as a sincere & friendly mini-gift to friends, even ones not much into coding.   

```
    #  #
   ##  ##
  ###  ###
 ####  ####
```   

Way back in January 2022 I wrote a [program](https://raw.githubusercontent.com/CallumBeaney/obfuscation/main/tree.c) based on the [CS50 Mario Pset](https://cs50.harvard.edu/x/2024/psets/1/mario/more/), in which you must generate the above shape at variable height.
    
My program turned that into a christmas tree, with little randomised snowflakes changing position every second:

```
    *  * ## *         
        *||#* *       
 * *   *#||#*  * *    
  **  ###||*##        
     *###||#*##      
    #####||*#### *         
    *    ||   *   *   
_________||_田______
```

So for this I ported it to Python and cut the linecount right down. It can be made terser but I like this to be _somewhat_ readable to an experienced dev. It needed to be brief enough to copy out if wanted, obfuscated enough to not be obvious how it works, but have hints enough to give them some ideas of what is happening if they type it out.  
  
Let's here recognise that, although Python is generally horrible, being able to do this much this terse is nice: 

```Python
# iterate over a random subset of numerically-sorted indicies
for i in sorted(sample(range(len(var1)),int(var2/randint(0,10)))):
``` 

<br>

So, for Winter 2024, I'll be disseminating something like this:

<br>
{{ image(src="https://raw.githubusercontent.com/CallumBeaney/christmas-tree-card/main/img/mockFront.jpg", position="left" style="width: 65vh;") }}
<br>
{{ image(src="https://raw.githubusercontent.com/CallumBeaney/christmas-tree-card/main/img/mockBack.jpg", position="left" style="width: 65vh;") }}
  
I made up a few of these with some filofax divider paper and handed them out to folks at Tech Fair London in March 2024. They seemed to be received well. One of IBM's staff described me as a "true nerd" which I am guessing was positive. My plan is to have around a hundred made and make it a project to send them to folks in the mail, drop them around places tech people work. You can peek at the repo [here](https://github.com/CallumBeaney/christmas-tree-card/tree/main).


<br>

### Sites

A few days after, I found [Reuben Son](https://reubenson.com)'s site index, which, if you like what you've seen so far, you will probably agree is really excellent (_this here below is an iframe and may not display well on a phone_): 

<iframe src="https://reubenson.com" width="650" height="600" frameborder="0"></iframe>

The same night I came across Son's site, I also found [Sunday Sites](https://sundaysites.cafe), which are HTML/CSS-only projects where folks design a single webpage project in a day. This little seasonal ASCII animation [Four Seasons](https://four-seasons.glitch.me) is likewise quite fun. You should take a look at the source code for that site in the console -- Séan's achieved that in a pretty novel way.  
   
So quickly inspired by that Four Seasons layout, I've thrown a [web version](https://callumbeaney.github.io/christmas-tree-card/) together too, as this very simple format is very nice.  

<iframe src="https://callumbeaney.github.io/christmas-tree-card/" width="650" height="600" frameborder="0"></iframe>


<br>

### Rolling updates

Hereon, I'm going to keep a little log of interesting/techy business cards:
  
- [Brian D Carlton's PCB business card](https://github.com/bdc0/businesscard) and also Anthony Kouttron's [implementation](https://github.com/anthonykouttron/pcb-business-card-qr-nfc/tree/master)
- [Lee Byron](https://leebyron.com)'s site, which adds a bit of embodiment to this little incursion. 