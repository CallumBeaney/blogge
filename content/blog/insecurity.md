+++
title="August Sander archive NFTs and naming your files stupidly"
date="2023-10-18"
+++

In 2022 there was some [legal furore](https://www.theartnewspaper.com/2022/05/06/major-court-battle-looms-over-nft-launch-of-august-sander-photographs) over a collection of August Sander's photography being sold as NFTs, with the idea that they would be sold for little more than admin fees, under the below pretext:

>*Each NFT represents ownership of the physical contact print made by Gerd Sander in 1988/89 and depicted by the image as well as access to the August Sander Research Database where the historical legacy of the Sander Family Estate will become publicly available for research. Ownership of the physical contact sheet is determined by the wallet in which the NFT is owned, regardless of wether [sic] the contact print has been redeemed or not.*

This NFT collection was taken down from public viewing some time later, though it looks to now be [back up](https://opensea.io/collection/august-sander-10k-collection) for sale, some at around $100k like this [one](https://opensea.io/assets/ethereum/0x7037843d739d846cdce3a6839a80f7d70b60b99a/1089). At the time, however, the NFTs themselves still pointed to the image and, consequently, its directory on the cloud, which was hosted by the IPFS peer-to-peer filesharing service [Pinata](http://mypinata.cloud). So, if you were to get a look at one of these NFTs, you'd find the url in there.  

You can see similar metadata through this inexplicably publicly-accessible link to the August Sander Foundation website: [https://asrd.augustsander.org/](https://asrd.augustsander.org/)  

<br>

[![image](https://i.seadn.io/gcs/files/433ead1d9a080d24cdc41d59ca15a392.jpg?auto=format&dpr=1&w=3840)](https://opensea.io/assets/ethereum/0x7037843d739d846cdce3a6839a80f7d70b60b99a/6452)  
- An example of one of these lo-res scans: [AS10k+ #9386 (ASA.31.134)](https://opensea.io/assets/ethereum/0x7037843d739d846cdce3a6839a80f7d70b60b99a/6452)

<br>

As you may notice the OpenSea sales platform isn't ideal for viewing the entire collection. Each individual listing does give access to a large-ish JPEG suitable for, say, a mediocre A4 inkjet printing, but it's inconvenient and a bit tedious for people who are interested in, say, looking at the work of August Sander.  The August Sander Foundation provides an interface for viewing 500 (very) low-resolution, [randomly-selected images from the archive](https://augustsander.org/page/sammlung). Pretty neat albeit useless for properly looking at the work of August Sander   (if you ***do*** want to look at August Sander's work check [this book scan](https://archive.org/details/augustsanderphot0000sand/mode/2up?view=theater&ui=embed&wrapper=false) at Internet Archive).   

Perhaps for all these reasons there was less concern over dumb shit like file security, and nobody thought to make these filenames more complicated than an ordinal list. I'm not going to give you the full correct URL but I will tell you that it looks a bit like this:

```
https://theartregister.mypinata.cloud/ipfs/aWholeBunchOfRandomLetters/full/1.jpg
```  
  
<br>
This means that with something as basic as this (written in C to be edgy):
 
```
#include <stdio.h>
#include <stdlib.h>

int main(void)
{
  int lower, upper;
  scanf("%i", &lower);
  scanf("%i", &upper);
  if (upper > 10396 || lower < 1 || lower > upper) return 1;
  
  char buffer[200];
  char *prefix = "the url lol maybe there's a way to find it who knows";
  
  while (lower <= upper) {
    sprintf(buffer, "wget %s%i.jpg", prefix, lower);
    system(buffer);
    printf("%s\nDownloading image #%i", buffer, lower);
    lower++;
  }
}
```

... you can download the entire archive.

<br>

For the ASF's various flaws, I'd like to praise their typography which imo is very nice:

<br>

![](https://augustsander.org/img/name_black.png?1553514393)

<br>
  
Anyway Andrew Molitor [wrote](https://twitter.com/amolitor99/status/1504850168377589760) on Twitter on Mar 18, 2022:
- *gotta say a side note about the Sander NFTs is that a 1500x2000 scan which includes a generous wide border and notes isn't anything I would call a "high resolution" scan. If anything, this suggests even more than nobody gives a shit about the art.*

...and with the exception of anyone who actually cashed in their tokens for the original contact prints, this is the final sentence of this blogpost.
