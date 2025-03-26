+++
title = "VCR+/VideoPlus - The Video Timer Thingy"
date = "2025-03-20"
description = "Remember those codes in the paper to program your video recorder? Let's take a look at VideoPlus aka VCR+!"
tags = [
    "retrotech",
    "VCR",
]
+++
![Photograph of a Gemstar VCR+ programming remote control](/images/Gemstar-videoplus-vcrplus-remote.webp)
***

*Remember VideoPlus aka VCR+?* Those codes that you used to find in newspapers and listings magazines to program your video recorder?

---

This is based on [this video](https://youtu.be/EFdd7yDs7hQ?si=iKGft62lfqv9EQZW) which was uploaded to my channel 25 March 2025.


## Is it true VCR+ was invented because a mathematics professor couldn't set his VCR to record a baseball game?

Yes, that's entirely true. You can even [watch Henry Yuen](https://charlierose.com/videos/25649) (the co-inventor) discussing the very matter on the *Charlie Rose* TV programme back in 2002.  

Sources suggest this happened in either **1986 or 1988**, but at some point in that period, the all-round clever chap Mr Yuen came up with the genius idea of *video scheduling codes*.  

---

## Why did VCR+ have different names? Are VideoPlus, ShowView, and G-Code the same?

Yes.  

**VideoPlus** was what we knew it as in the UK, which worked fine here because *video* was both a noun and a verb.  

A VCR would be called a *video*, as would a cassette (*"Stick a video in the video"* makes perfect sense here), and just to really confuse you, *"to video something"* meant to record.  

In **British English**:  
*"Put a video in the video so I can video *Pulp Video* so I don't have to go down the video shop and get the video out, ta."*  
✔ Perfectly cogent to old Brits.  

The term *VCR* was something we mostly heard on American TV shows—if you said *"Put a VHS in the VCR"*, it would have sounded weird in the UK in the '80s and '90s. Honestly, it still sounds clunky to me now.  

More importantly, **Philips owned the trademark "VCR" in Europe** (Video Cassette Recording), so calling it **VCR+** here was a **non-starter**.  

**G-Code** (Gemstar Code) was used in Japan, where *VCR* meant nothing, and also in some other markets. **ShowView** was used exclusively in Europe—though that name must have sounded oddly English in other languages.  

Get in touch—*what did you call yours?*  

---

## Does VCR+ still work?

Absolutely.  

There’s a lot of confusion about how this system worked—many people assume it was **a broadcasted signal**, but it wasn’t.  

VCR+ was **never transmitted over the air**. Instead, the codes were **just a hash** of the start time, channel, and duration.  

GemStar simply **partnered with newspapers and TV listings providers** to print the codes in exchange for licensing their software. *That’s it, in a nutshell.* Naturally, the details were more complicated.  

VCR+ simply became obsolete with the rise of **streaming and hard-disk recorders**. It no longer served a purpose. The [last VCRs were made in July 2016](https://www.bbc.co.uk/news/technology-36857370), so it’s hardly a *thing* anymore, is it?  

That said, you *can* still use it—kind of.  

If you want to get your old snotter of a machine down from the loft, you’ll need to download [this C code](https://www.cs.cmu.edu/~dst/VCRPlus+/) (or the Perl 5 version if you don’t think life is complicated enough) and compile it yourself.  

However, it only seems to have about an **80% success rate in the UK**, and I had to modify it a bit to get it working.  

---

## So, what’s this hash-function stuff?

Well, imagine trying to pee in reverse…  

Peeing "forwards" is, assuming adequate hydration, a fairly straightforward process. However, if you were to attempt to use your bits as a straw to suck it back up from the bowl (please don’t send me evidence of any attempts), you’d find yourself facing an impossible challenge. That’s about the best analogy I can come up with for how a hash function works.  

There are, of course, long and tedious mathematical explanations, but in simple terms, a hash function is a clever set of calculations that can transform key pieces of information—such as start time, duration, and channel number—into a **unique and non-obvious number**.  

If you’re presented with the code but don’t know the formula to work backwards, **decoding it is practically impossible**. This was rather neat for GemStar, as they could **publish codes daily** in TV listings **alongside the necessary details (start time, duration, and channel)**. However, without their proprietary software, you’d have almost **zero chance** of working out how the codes were generated.  

The maths behind this had to be precise to ensure that each unique programme combination (channel, time, and duration) would **always** generate a **single, unique code** within a **month-long period**—**collisions were not allowed**. For example, *Casualty* at **20:00 for 50 minutes on a Saturday** could **never** produce the same code as *Spatz* at **15:50 for 25 minutes the following Friday**.  

All the device—whether it’s a **VCR or a dedicated unit**—has to "know" is **the magic formula** to work backwards. Essentially, it's just **a glorified calculator**. It can take a code like `202403` and decode it, unpacking the necessary details to set your machine to record *The Bill* **tonight at 19:30 for 30 minutes**.  

---

## Shorter Codes for Prime Time  

Prime-time programming (though I haven't found an exact definition of what this means in VCR+) and **more popular channels** were designed to **produce shorter codes**.  

For instance, I’ve seen `3` used as a code for BBC News on BBC One. However, if you wanted to record **a niche overnight broadcast on a lesser-known channel**, you’d likely have to enter a **full 8-digit code** instead.  

---

## Why So Complicated?  

The hashing process had to be **intentionally convoluted** to **prevent the codes from being predictable** without **GemStar’s software**.  

Additionally, the system incorporated **an extra layer of obfuscation**—meaning that the **same programme** could sometimes have **different codes**. This was a deliberate anti-piracy measure, designed so that **one TV listings magazine couldn’t simply copy another**. An **extra hidden factor** was included in the calculations and **unpacked by the decoder**, making it **instantly obvious to GemStar** if someone was **stealing codes** from a competitor.  

So, in summary—**deceptively simple, yet astonishingly complicated!**  

---

**First Uploaded: 20 March 2025 - Written by Andy.**  
**Last Updated: 26 March 2025 - Add Video Link!**

---
