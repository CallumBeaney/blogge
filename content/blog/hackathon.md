+++
title="Prototying at ＜HANDS: On＞ Cambridge University Hackathon"
date="2024-08-31"
+++


<!-- STYLE BEGINS -->
<style>
  .image-container {
      position: relative;
      width: 50vw; 
      height: 80vw;
      margin: 20px auto; 
      max-width: 100%;
  }

@media (max-width: 600px) {
    .image-container {
      position: relative;
      width: 80vw; 
      height: 110vw;
    }
      .flex-container {
      flex-direction: column!important;
    }
    .flex-container img {
      width: 100%!important;
      height: auto!important;
    }
  }

  .image-container img {
      position: absolute;
      width: 100%;
      height: 100%;
      transition: opacity 2s ease;
  }

  .image-container img.top-image {
      opacity: 1;
  }

  .image-container:hover img.top-image {
      opacity: 0;
  }

  .flex-container {
  display: flex;
  flex-direction: row;
}

.flex-container img {
  width: 50%; 
  object-fit: cover;  
  height: auto;
  padding: 2px;
}

.youtube-video-container {
  position: relative;
  overflow: hidden;
  width: 100%;
}

.youtube-video-container::after {
  display: block;
  content: "";
  padding-top: 56.25%;
}

.youtube-video-container iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

.center-container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh; 
}
</style>

I was invited to participate as a developer at Cambridge University Library's week-long [_Hackathon_](https://projects.history.qmul.ac.uk/handson/hackathon-2024/), where ~30 postgraduates made educational app prototypes, giving researchers of the [Hidden In Plain Sight](https://projects.history.qmul.ac.uk/inplainsight/) project ideas for educational software.  

__INDEX__  
　[The week](#the-week)  
　[The historical context](#the-historical-context)  
　[Imaging techniques & materials analysis](#imaging-techniques-and-materials-analysis)  
　[Prototyping](#prototyping)  
　[Teamwork & academia](#teamwork-and-academia)  
　[Final thoughts](#final-thoughts)  
　[Recommended reading](#recommended-reading)  

<br>


## The week  

- __Monday__: Introductions, presentations & demonstrations on heritage-oriented scientific imaging techniques, design thinking for app development, meeting curators, etc.
- __Tuesday__: "Speed dating" for to form groups of 5, pitching project ideas, paper prototyping.
- __Wednesday__: Prototyping all day, an update at the end of the day.
- __Thursday__: Prototype app testing with brought-in testers who matched user personas, feedback meetings, more prototyping.
- __Friday__: Cleanup and presentation to university & project members.


<br>

{{ image(src="https://images.theconversation.com/files/351276/original/file-20200805-22-y3voc3.JPG",  position="center" style="width: 80vh;") }}

<br>


# The historical context

The _Bible_'s first authorized English-language printing, _The Great Bible_ (1539) was distributed to every English parish during the Reformation, for to legitimise Henry VIII's divorce from the Catholic church and self-imposition as the head of the local Church of England.  
   
Thomas Cromwell (_above_) commissioned an illuminated variant for the king with his own portrait pasted over the figure to the king's right on the book's title page (_below_). That seam below his chin was discovered by illuminating the page with a raking light during microscope inspection.
  
Both versions are riddled with brazen heresy and propaganda, most comically the shunting of the word of the Lord to a narrow sliver above the enormous figure of the now-Godlike Henry VIII distributing these books to the populace below. You can read more about the illuminated copy's many political alterations [__here__](https://theconversation.com/how-thomas-cromwell-used-cut-and-paste-to-insert-himself-into-henry-viiis-great-bible-143765).  

<br>
{{ image(src="/images/hackathon_colour.jpg",  position="center" style="width: 80vh;") }}
<br>
{{ image(src="/images/hackathon_print.jpg",  position="center" style="width: 80vh;") }}
<br>
<br>

# Imaging techniques and materials analysis
Having worked in the past in heritage digitzation, I was familiar with the purely photographic stuff like photogrammetry, MSI, panoramic stitching tools etc. The newer materials-specific techniques introduced to us in the labs around the [Cultural Heritage Imaging Laboratory](https://www.lib.cam.ac.uk/collections/departments/chil) in the library included e.g. Fibre-Optic Reflectance Spectrography (FORS), and [X-Ray Flouresence Spectroscopy](https://physicsopenlab.org/2016/02/24/diy-xrf-spectrometry/) (XRF - below). 
  
Each technique has its own pitfalls: XRF isn't good with organics; some pigment identification processes are highly influenced by the pigment's substrate, and so on. Analysis of output data & graphs is consequently, in the researchers' own words, highly interpretive.   

<br>

{{ image(src="https://physicsopenlab.org/wp-content/uploads/2016/02/xrf.jpg", alt="XRF", position="center" style="width: 75vh;") }}
{{ image(src="/images/hackathon_macroXRF.jpg", alt="Macro XRF", position="center" style="width: 75vh;") }}
<p style="padding:0% 12%; font-style:italic">Macro-XRF Analysis of the Great Bible by Nathan Daly at the Hamilton Kerr Institute</p>


<br>

Application of machine learning to these technologies has been discussed ([__1__](https://www.nature.com/articles/s41598-024-53988-z), [__2__](https://opg.optica.org/optica/fulltext.cfm?uri=optica-11-2-146&id=545855)), and surveys have identified that there is more general uptake of ML in a cultural heritage context ([__2020__](https://www.sciencedirect.com/science/article/pii/S0167865520300532#sec0016), [__2022__](https://ceur-ws.org/Vol-3234/paper2.pdf)), but even in larger institutions this can be either highly localised to a specific project, be owing to financial or quality requirements slow to develop, or be otherwise tailored insufficiently.  

The prototypes we made at the hackathon focused on public edification rather than on e.g. internal tools for researchers; I'd love to be involved in designing and building massive data & training sets for specialised open source tooling.  

<br>

{{ image(src="/images/hackathon_dcu.jpg",  position="center" style="width: 60vh;") }}
<p style="padding:0% 15%; font-style:italic; text-align:center;">The MSI unit in the CUL Digital Lab.</p>


{{ image(src="/images/hackathon_bone.jpg",  position="center" style="width: 60vh;") }}
<p style="padding:0% 15%; font-style:italic; text-align:center;">A 3D print of a Chinese oracle bone, digitised via photogrammetry</p>

<br>


## Prototyping

The goal was to make an educational app providing extra insight into this book and/or the analysis methods used to study it. 

With four software developers and around 25 students, four groups were formed. In past years app prototyping was done with a generic JS stack; the last two, the hosts moved to simulating a user experience by building UIs with basic conditional logic in [Figma](https://www.figma.com/), owing to developers having to stay up late in previous years programming in the features, and due to their role in the collaborative process being both less integrated and less accessible to non-technical participants.  

<br>
{{ image(src="/images/hackathon_workflow_board.jpg",  position="center" style="width: 75vh;") }}
<br>
{{ image(src="/images/hackathon_workflow_figma.jpg",  position="center" style="width: 75vh;") }}
<p style="padding:0% 15%; font-style:italic; text-align:center;">Workflows from board to screen</p><br>


By doing this however the scope of the app prototypes expanded and so this year also we developers stayed up late. This really was OK, but is humorously microcosmic of automation in industry.  
  
With stylised history-themed mystery-puzzle games like `Return of the Obrah Dinn` and `Pentiment` in mind, teammates envisaged a "find the clue" investigation game in which the player - cosplaying as a researcher-out-of-time tasked by the King to find out why his special copy of the Bible is so suspicious - would inspect and 'colour in' the print version with the illuminated colour version by applying these research tools to it, in a click+paint manner. For the final product itself, TTS and adaptive animation tools like Facebook's [Animated Drawings](https://github.com/facebookresearch/AnimatedDrawings) might be utilised.  

Achieving this with Figma being difficult, we opted for a simpler _click here to see how it'd look_ button to trigger a fading painting-in-effect animation.  

<br>

{{ image(src="/images/hackathon_screens_1.jpg",  position="center" style="width: 85vh;padding-bottom:5px") }}
{{ image(src="/images/hackathon_screens_2.jpg",  position="center" style="width: 85vh;padding-bottom:5px") }}
{{ image(src="/images/hackathon_screens_3.jpg",  position="center" style="width: 85vh;padding-bottom:5px") }}
{{ image(src="/images/hackathon_screens_4.jpg",  position="center" style="width: 85vh;") }}
<p style="font-style:italic; text-align:center;">Screenshots from our Figma project.</p><br>

Without a proper toolchain prototyping for a minigame like this involves "telling" over "showing" for the testers brought in; we imagined a GUI showing many different tools to use on the manuscript; we were advised to instead simulate the experience of one or two features, well. As such we hard-coded a fixed path, rather than the "open map" we wanted, where the user would zoom in & out and inspect the pertinent elements of the title page in whatever order they desired.  

Whereas many project ideas take time to develop naturally, the basic shape of our project was already partly formed at the group-forming stage. Interested in a younger persona (a schoolkid) seeking an entertaining but edifying resource for a school report, our team began walking through how a user would experience the first stages of the game. We were quickly advised to slow down and take a step back; we tried, but despite reaching a roadblock on the 2nd day, we all shared roughly the same vision for the project.  

<br>

# Teamwork and academia

Working with these academics was vitalizing. A couple of teammates were especially adept at prototyping & making workflows/basic storyboards. Another was a natural manager. Others had great intution for concisely communicating (and cataloguing) relevant factual & technical information.  

Though using Figma with only a little practice was a challenge, the most difficult thing was managing the enthusiasm and frequent ideas from my fellow groupmates, and occasionally steering them back on track; I wanted to follow every tangent brought up. Also difficult was appropriately involving myself creatively; I was expected to do so, but not so much as to take over. In the end, I changed to more of an organiser-type role, prompting focus when others tangented on details, and advising on feasability of new feature ideas.  

<br>

<!-- <div class="center-container"> -->
  <blockquote class="twitter-tweet" data-dnt="true" data-theme="dark"><p lang="en" dir="ltr">Done! The prototype is ready for tomorrow&#39;s presentation and you can be the first to see it. A big thank you to the team, it was amazing working with you on this prototype!<br><br>Can you think of website like this for your research? <a href="https://t.co/uMbTBYntU4">pic.twitter.com/uMbTBYntU4</a></p>&mdash; Martin Rocek (@Silencesys) <a href="https://twitter.com/Silencesys/status/1803914759097495595?ref_src=twsrc%5Etfw">June 20, 2024</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
<!-- </div> -->

<br>

One of the developers, Martin Rocek, was experienced with Figma and previous Hackathons both, and kindly offered technical support to we other developers. His group's contribution was the most polished, and was for its more conservative design and refined architecture, likely the ideal reference choice for the Hidden In Plain Sight project. Martin has made a lot of interesting digital humanities things - [have a look here](https://dh-humanities-tools-j2eicc6qe-martin-rocek.vercel.app/cs?collection=E-13-46-47-3C-45-22-24-19&name=Martin%20Rocek%27s%20projects).  

Other groups were more experimental in their presentation. Inspired by floral marginalia, _R's_ group's UI was busy and digital-scrapbookish, with a stack-like architecture wherein the user would look closer, learning progressively finer detail of the book before gradually zooming back out.  

_J_'s group designed a linear progression of 3-column page layouts in which each main layout page had sub-pages or elements (like nodes) which could be interacted with before progressing onto the next main page. On each page the centre column contained article text, with comparison images either side. This more explorative and preference-driven user experience over a fixed path is suitable for museum tablets and displays.  

<br>
{{ image(src="/images/hackathon_fail.jpg",  position="left" style="width: 60vh;") }}
<br>
  
Outside of work, all we different groups met for breakfasts and dinners. All parties involved enjoyed a lovely meal on a green outside the host's residence on the Wednesday eve.  
  
Most of the time, being around other humans and being on my own feel to me very similar. People who bring the particular quality of having substantial knowledge interests, unabashed idiosyncracies, comfort prodding convential ideas and enthusiasm for new ones, are in the real world rare.  
  
Younger, less jaded researchers' casual discourse, free of the oily pretention of too many career academics and of the simplistic platitudes and moralities of daily life's conversants, allows for description-oriented discussion about and calm evaluation of  usually sensitive political and cultural topics, without the typical encumbering verbal asterisks, and it is missed.  

Here's a video walkthrough going over most of what we did:  

<br>

<div class="youtube-video-container">
  <iframe width="560" height="315" src="https://www.youtube.com/embed/J1c6-XGmnDQ?si=U-fB9v0xQ2eOYQEP" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>

<br>
<br>
  
# Final thoughts

This prototype was a youth-oriented homework aid. For myself, I would rather than a game prefer to make a comprehensive visual comparison tool designed to use these two front pages as a single point of reference through which the entirety of the Reformation could be filtered to an engaged, even specialist audience - a sort of historiographical fulcrum.  
  
I feel somewhat conflicted about our contribution - the game idea was good and I would really like for my teammates to see it realised, however the final Hidden In Plain Sight app will be developed by a single member of the project team who has some webdev experience working in a developer-adjacent role. Given time/budget constraints typical to heritage sector projects, I don't expect building a game is feasible compared with less architecturally complex and asset-light prototypes. I could be and hope I am wrong.  
 
I encourage those reading this, be they developers or academics, to consider participating in this or like events.  

<br>

## Recommended reading
- [The Fitzwilliam Museum Illuminated Manuscripts Lab](https://www.fitzmuseum.cam.ac.uk/illuminated/lab/lab)
- [_How Thomas Cromwell used cut and paste to insert himself into Henry VIII’s Great Bible_ - Ian McKee](https://theconversation.com/how-thomas-cromwell-used-cut-and-paste-to-insert-himself-into-henry-viiis-great-bible-143765). 
- _A Material History of the Bible, England 1200 –1553_, [Eyal Poleg](https://uk.linkedin.com/in/eyal-poleg-2b51338a)
- _Science of the Book::Analytical Methods for the Study of Illuminated Manuscripts_ - Paola Ricciardi and Catherine Schmidt Patterson
- [Martin Rocek's digital humanities tools](https://dh-humanities-tools-j2eicc6qe-martin-rocek.vercel.app/cs?collection=E-13-46-47-3C-45-22-24-19&name=Martin%20Rocek%27s%20projects) 
- Here's a [short video](https://www.youtube.com/watch?v=81iYAtfONdo) of a previous iteration of this Hackathon.
- [A prototype tool from a previous Hackathon](https://dlukes.github.io/demm-cambridge/#/0/0/0) for learning how to inspect medieval manuscripts.  

