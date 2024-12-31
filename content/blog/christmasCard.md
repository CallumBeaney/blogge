+++
title="Making an ASCII Christmas/Business-Card & other decorations"
date="2024-12-12"
+++

{{ image(src="https://raw.githubusercontent.com/CallumBeaney/christmas-tree-card/main/img/christmas_card_1.jpg", position="left" style="width: 100vh;") }}


This documents a bit of creative process making the above, very little of which is truly original.  
To see the raw files, code etc just go to [the repo](https://github.com/CallumBeaney/christmas-tree-card/).

## Index

- [Interesting Business Cards](#interesting-business-cards)
- [My Business Card](#my-business-card)
- [Other Peoples' Code Greetings Cards](#making-a-christmas-card)
- [My Christmas Card](#my-christmas-card)
- [Other Christmas Decorations](#other-decorations)
- [Relevant Sites](#websites)
- [Rolling updates](#rolling-updates)

<br>

## Interesting business cards

A pal recently forwarded this post my way: 15 lines of code for setting up an HTTP client [on the back of a metal business card](https://www.reddit.com/r/tinycode/comments/kvuoqj/wrote_an_http_client_in_python_that_can_fit_on_a/).  

<br>  
{{ image(src="https://preview.redd.it/htzm54z4fxa61.jpg?auto=webp&s=2ead4d5145d253cd8b901255af004f205ec03f9f", position="left" style="width: 85vh;") }}
<br>
  
A small part of the joke in American Psycho's [business card scene](https://www.youtube.com/watch?v=aZVkW9p-cCU) is that the cards are poorly designed (odd spacing, typos, OTT textures etc), yet they care about them so much. Most business cards I pick up are perfunctory, discardable things, but I'd not forget someone who gave me a code card.  

I decided to try at making a little business card that could be as much a fun self-advertisement as a nice piece of paper ephemera.  

<br>
{{ image(src="https://external-preview.redd.it/mk8leSSX4tYcql92G51e8K1cwnKsgqqPPHQsmNu8cn0.jpg?auto=webp&s=4e7cd63c8fdffeb459a1b12cf50483911b6b93f9", position="left" style="width: 100vh;") }}
<br>

Way back in January 2022 I wrote a [program](https://raw.githubusercontent.com/CallumBeaney/obfuscation/main/tree.c) based on the [CS50 Mario Pset](https://cs50.harvard.edu/x/2024/psets/1/mario/more/), in which you must generate the below shape at variable height.  

```
    #  #
   ##  ##
  ###  ###
 ####  ####
```   

My program turned that into a christmas tree, with little randomised snowflakes changing position every second:  


```
    *  * ## *         
        *||#* *       
 * *   *#||#*  * *    
  **  ###||*##        
     *###||#*##      
    #####||*#### *         
    *    ||   *   *   
_________||________
```  
  

So for this I ported it from C to Python and cut the linecount right down. It needed to be brief enough to copy out if wanted, obfuscated enough to not be obvious how it works, but have hints enough to give them some ideas of what is happening:  

```python
import os,time;from random import randint as rnd,sample as smp
seed=rnd(12,20); present='\u7530'; s,n,o,w,y=' ','_','|','#','*'

def bud(len, chr): return chr*len  

def snow(branch):
  for i in sorted(smp(range(len(branch)),int(seed/rnd(3,6)))):
    if branch[i]==present or branch[i]==n:continue
    else: branch=branch[:i]+y+branch[i+1:]
  return branch

def grow(rows): 
  time.sleep(1.0);os.system('cls'if os.name=='nt'else'clear')
  for row in range(rows):
    if row>=rows-2:twig=bud(rows,s if row==rows-2 else n)+o
    else:twig=bud(rows-row,s)+bud(row,w)+(o if row!=0 else w)
    print(snow(twig+(twig[::-1][:3]+present+twig[::-1][5:]\
      if row==rows-1 else twig[::-1])))

while True: grow(seed)
```

It can be made terser but I like this to be somewhat readable to an experienced dev.   

The easiest way to get what is going on here is to bear in mind that for each row of the tree, I'm building the left half of it, and then building the right half by appending the string with a reversed copy of it. Then it's just a matter of replacing some of the characters with asterisks.    


<br>
<br>


## My Business Card

Just stanning the (much better) HTTP client code card above I first mocked up a business card like this, and handed it out at a few events/fun people at the pub. The main purpose it fills in the end is generating intrigue; despite the little `# comment` I don't recommend trying to type it out:  

<br>
{{ image(src="https://raw.githubusercontent.com/CallumBeaney/christmas-tree-card/main/img/mockFront.jpg", position="left" style="width: 65vh;") }}
{{ image(src="https://raw.githubusercontent.com/CallumBeaney/christmas-tree-card/main/img/mockBack.jpg", position="left" style="width: 65vh;") }}  


<br>
<br>


## Making a Christmas Card

Excepting those handmade or properly filled with handwriting, the scrawled To and From of gift-card giving culture is both too expensive and too impersonable for me. I love written correspondence and given that the best way to do it is to start it, I thought I'd forego phone Christmas messages and tried adapting the above into something cute I could write a proper end-of-year update into.

##### Inspiration

I was expecting to find more software-related greetings cards online, however most I've come across - particularly those on Etsy - are like those `if (thirsty) { drinkCoffee(); }` mugs.  

The best designed are the sadly no-longer-made 2011-made letterpress [Code Cards](https://www.etsy.com/shop/codecards) by  [Matt Raw](http://mattraw.com/) (see some more pics [here](https://coolhunting.com/design/code-cards/)):

{{ image(src="http://www.logobird.com/wp-content/uploads/2011/11/javascript-code-cards_thumb.jpg", position="left" style="width: 65vh;") }}
{{ image(src="https://150102931.v2.pressablecdn.com/wp-content/uploads/2011/11/code-cards5-thumb-499x414-33940.jpg", position="left" style="width: 65vh;") }}

<br>

Other than those, [codingstrawberry](https://www.instagram.com/codingstrawberry/)'s [binary tree christmas card](https://www.etsy.com/uk/listing/1824917095/binary-tree-christmas-card-tech) is pretty neat:

{{ image(src="https://i.etsystatic.com/50413664/r/il/446900/6473015999/il_1588xN.6473015999_g4pv.jpg", position="left" style="width: 65vh;") }}


<br>
<br>


##### My Christmas Card

As my card's tree motif fills the card's center-front, I decided to keep the back's empty, and bracket with a similar colophon top and bottom. I wanted a fairly firm, off-white paper stock, slightly more _office card_ than _letterpress artwork_, and, being in China at the time, went with 荷兰白卡300克, got 40 made for 15 quid and sent them out Christmas 2024.  

So here's my card:

<br>
{{ image(src="https://raw.githubusercontent.com/CallumBeaney/christmas-tree-card/main/img/christmas_card_1.jpg", position="left" style="width: 100vh;") }}
{{ image(src="https://raw.githubusercontent.com/CallumBeaney/christmas-tree-card/main/img/christmas_card_2.jpg", position="left" style="width: 100vh;") }}
{{ image(src="https://raw.githubusercontent.com/CallumBeaney/christmas-tree-card/main/img/christmas_card_3.jpg", position="left" style="width: 100vh;") }}


<br>
<br>


## Other Decorations

These are less good but were fun to try.  

##### Medieval botanical paper bauble

On PlantIllustrations I found scans of the old manuscript [_Grandes Heures Anne de Bretagne_](http://www.plantillustrations.org/illustration.php?id_illustration=343953&id_taxon=1070&mobile=0&SID=e3et3jslh6gjkr4tfq8v6iue38&language=English&thumbnails_selectable=0&selected_thumbnail=0&query_type=species&query_broad_or_restricted=broad&group=0&lay_out=0&uhd=0) (1503-1508). Though a little lo-res I managed to find within snowdrops, Ilex holly, and rose hips and adapted an old-fashioned top-threaded paper baubel design  purchased from the [East Anglian Food Museum's printing press](https://www.facebook.com/FoodMuseumUK/posts/pfbid02spctbg3yUqi2uGimcKbkJerLzFdHeYyjDdSbaHogYU5YkkTGeJaMVnPNgBTtbccrl) team in GIMP and made a demo printout:


{{ image(src="https://github.com/CallumBeaney/christmas-tree-card/blob/main/printouts/bauble.png?raw=true", position="left" style="width: 100vh;") }}
<br>
{{ image(src="https://github.com/CallumBeaney/christmas-tree-card/blob/main/img/bauble_1.jpg?raw=true", position="left" style="width: 65vh;") }}  

If you'd like to print your own, go [here](https://github.com/CallumBeaney/christmas-tree-card/tree/main/printouts).  

<br>
<br>


##### Unicode emoji winter tree decoration

Kirsty Baynham of [PrismOfStarlings](https://www.etsy.com/uk/listing/881024488/wolf-in-the-forest-miniature-kit?ref=user_profile)' designed these really beautiful "Wolf in the Forest" triange-shaped wolf + trees paper cutout decoration, which you should buy because they're wonderful.  
  
I bought a few and thought "you could do a really kitsch internet-art designer style version of this with the deer and tree emoji". It's not really meant to be much visually nice, it's just something cute to be sent to a friend or two:  

{{ image(src="https://github.com/CallumBeaney/christmas-tree-card/blob/main/printouts/emojiDecoration.png?raw=true", position="left" style="width: 100vh;") }}

<br>

{{ image(src="https://github.com/CallumBeaney/christmas-tree-card/blob/main/img/deer_1.jpg?raw=true", position="left" style="width: 65vh;") }}
{{ image(src="https://github.com/CallumBeaney/christmas-tree-card/blob/main/img/deer_2.jpg?raw=true", position="left" style="width: 65vh;") }}

If you'd like to print your own, go [here](https://github.com/CallumBeaney/christmas-tree-card/tree/main/printouts).


<br>
<br>


## Websites

A few days after seeing the HTML Client card, I found [Reuben Son](https://reubenson.com)'s site index, which, if you like what you've seen so far, you will probably agree is really excellent (_this here below is an iframe and may not display well on a phone_): 

{{ image(src="/images/reubenson.png", position="center" style="width: 85vh;") }}

The same night I came across Son's site, I also found [Sunday Sites](https://sundaysites.cafe), which are HTML/CSS-only projects where folks design a single webpage project in a day. This little seasonal ASCII animation [Four Seasons](https://four-seasons.glitch.me) is likewise quite fun. You should take a look at the source code for that site in the console -- Séan's achieved that in a pretty novel way.  
   
So quickly inspired by that Four Seasons layout, I've thrown a [web version](https://callumbeaney.github.io/christmas-tree-card/) together too, as this very simple format is very nice.  

<iframe src="https://callumbeaney.github.io/christmas-tree-card/" width="650" height="600" frameborder="0" style=""></iframe>


<br>
<br>


### Rolling updates 
(last updated: 2024/04/13)

Hereon, I'm going to keep a little log of interesting/techy business cards:
  
- [Brian D Carlton's PCB business card](https://github.com/bdc0/businesscard) and also Anthony Kouttron's [implementation](https://github.com/anthonykouttron/pcb-business-card-qr-nfc/tree/master)
- [Lee Byron](https://leebyron.com)'s site, which adds a bit of embodiment.  
- [Micah R Ledbetter](https://me.micahrl.com/business-card/) has this little randomised business card content page.
- [Tony Richards](https://fourtoes.co.uk/iblog/the-auto-phrame/) found the `Auto Phrame`, an old businesscard-sized metal photo frame that holds a stack of prints.


<br>
<br>

{{ image(src="https://raw.githubusercontent.com/CallumBeaney/christmas-tree-card/main/img/bale.jpg", position="left" style="width: 100vh;") }}
