---
title : Lipsum
subtitle : Test
notetype : feed
date : 16-05-2022

---

This is a page used to test various features of the website. Click [here](/assets/txt/Lipsum.txt) to see the raw markdown file which gets rendered into this webpage.

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam commodo lectus eget metus sollicitudin tincidunt.  $$\phi = \sqrt{x_i}$$ [[Inline math. KaTeX is rendered entirely server side and displayed using regular text and SVGs. It ends up being quite fast.::rmn]]Sed blandit velit sit amet viverra condimentum. Donec imperdiet sagittis lectus, dictum convallis **bold text tristique sed**. Praesent *italic text laoreet ornare orci*, lobortis tincidunt odio pretium euismod. [[assets/img/parenting.png::lmn-ibw]]

> Blockquote. sed augue et orci vehicula pharetra vel nec nibh. Proin velit tellus, suscipit sit amet sapien sed, sollicitudin interdum erat. Praesent suscipit porta neque, eu laoreet elit feugiat in. Curabitur tempus metus id urna tincidunt placerat. In hac habi


[[ Expandable sidenotes are done using the vanilla HTML details tag. Notes longer than 500 characters are automatically truncated to a summary with the first 50 words. Because of some issues with the toggle button expandable sidenotes are put inline with the rest of the text on small screens and mobile. Integer sem felis, fringilla sit amet orci vitae, rutrum mollis eros. Mauris odio nisl, aliquam vitae tortor vitae, consectetur rutrum ante. Nullam urna ex. In eget elit eros. Donec porta lorem mi, eu congue velit consectetur ac. Vestibulum egestas velit tempor viverra placerat. Quisque ut condimentum odio, a aliquam ante. Integer posuere aliquet magna. Aliquam laoreet iaculis ante, sed feugiat augue vehicula luctus. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Aliquam velit turpis, vehicula ac lectus vitae, venenatis tristique lorem. Nam a neque non nunc hendrerit commodo. Vivamus mauris enim, condimentum ut posuere faucibus, consectetur non nisl. Sed tristique at leo dictum malesuada. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae; Fusce sodales tempus nisi, a finibus augue. Etiam malesuada ultricies lacus, vitae facilisis magna auctor sit amet. Donec porta lorem mi, eu congue velit consectetur ac. Vestibulum egestas velit tempor viverra placerat. Quisque ut condimentum odio, a aliquam ante. Integer posuere aliquet magna. Aliquam laoreet iaculis ante, sed feugiat augue vehicula luctus. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Aliquam velit turpis, vehicula ac lectus vitae, venenatis tristique lorem. Nam a neque non nunc hendrerit commodo. Vivamus mauris enim, condimentum ut posuere faucibus, consectetur non nisl. Sed tristique at leo dictum malesuada.::rmn]]

[[Sidenotes will rearrange to avoid overlap when a collapsible sidenote is toggled, however the sidenotes on the opposite side are also moved unnecessarily.::rmn]]


## All for One and One for all!
Quisque tristique lectus lacinia dui laoreet, vitae interdum turpis eleifend. Sed sit amet elit porta neque dignissim. Nam ullamcorper nisl a vestibulum sagittis. Quisque enim odio, posuere ut sodales nec, tristique a lacus. Quisque commodo massa turpis, vel consectetur elit ullamcorper non.[[Display math & math within sidenotes::lmn]]

[[$${\hbar {\frac {\partial }{\partial t}}\Psi (x,t)=\left[-{\frac {\hbar ^{2}}{2m}}{\frac {\partial ^{2}}{\partial x^{2}}}+V(x,t)\right]\Psi (x,t).}$$::lmn]]

$$ x=\frac{-b\pm\sqrt{b^2 -4ac}}{2a} $$

Vestibulum dapibus, elit id rutrum porttitor, turpis diam convallis leo, in congue orci turpis in justo. Aenean a feugiat libero. Interdum et malesuada fames ac ante ipsum primis in faucibus. Nulla id sem diam. Integer iaculis egestas nisi non luctus. Donec non gravida libero. Etiam auctor iaculis scelerisque. [[Aliquam erat volutpat. Integer sem felis, fringilla sit amet orci vitae, rutrum mollis eros. Mauris odio nisl, [Xanadu](/notes/Xanadu).::rmn]]
# Heading 1
## Heading 2
Duis nisl risus, semper eu ullamcorper eu, cursus at augue. Sed cursus odio neque, a vestibulum dolor pellentesque at. 
### Heading 3
lectus lacinia dui laoreet, vitae interdum. Duis orci nibh, egestas nec dictum  semper, congue a justo.
#### Heading 4
Nulla pretium justo in sapien auctor vehicula. Donec ac leo eu lectus sollicitudin vulputate ac id ligula.

[[Normally sidenotes are written using a simple markdown notation, but for external side images it's necessary to write HTML directly.::rmn]]

<label for="rmn-A" class="margin-toggle  ">⊕</label><input type="checkbox" id="rmn-A" class="margin-toggle"><span class="mn-right" style="text-align: center;"> ![Portrait of Lincoln](https://upload.wikimedia.org/wikipedia/commons/a/ab/Abraham_Lincoln_O-77_matte_collodion_print.jpg)*Lincoln in 1863*</span>

[[\<mark\> tag renders red::lmn]]<mark>Duis nisl risus, semper eu ullamcorper eu, cursus at augue. Sed cursus odio neque, a vestibulum dolor pellentesque at. Nulla pretium justo in sapien auctor vehicula. Donec ac leo eu lectus sollicitudin vulputate ac id ligula.</mark> Aliquam ut sagittis orci. Maecenas non maximus magna. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae; Nunc accumsan eget erat vel egestas. Maecenas tempus, elit a venenatis condimentum, augue lacus vestibulum velit, id lacinia justo ipsum quis ipsum. Mauris molestie tristique ipsum eget lacinia.


[[Image colors can be preserved in dark mode using a hue rotation. The brightness is lowered slightly::rmn]]
[[assets/img/Lipsum.svg::ibw]]
[[Try switching from dark mode to light mode (The ◑ button)::lmn]]
[[I can load external images and adjust them to match the theme. This picture is from XKCD.com and without any editing it inverts in dark mode to the correct off black. This wouldn't work for all images, for example the lincoln pic above would look odd inverted, so I add ?b&w to the end of an image URL to indicate that it's invertible.::rmn]]`![XKCD 600, Android Boyfriend](https://imgs.xkcd.com/comics/android_boyfriend.png?b&w)` renders to ![XKCD 600, Android Boyfriend](https://imgs.xkcd.com/comics/android_boyfriend.png?b&w)


<figcaption><a href="https://xkcd.com/600/">via XKCD</a></figcaption>
Integer ornare orci ut augue convallis efficitur. Integer vestibulum mi et eros tincidunt, ut euismod turpis dapibus. Nullam mauris nisl, laoreet ac lectus vitae, dapibus volutpat felis. Nulla sollicitudin, mi id mattis fringilla, ligula nisi mollis urna, a suscipit augue quam ut enim. Vestibulum id justo ut nulla rutrum vehicula. Cras aliquet lorem id enim sagittis 

| Event          | Date       |
| -------------- | ---------- |
| Tuition Due    | March 31   |
| Quarter Begins | April 10    |
| Final Exams    | June 20 |
| Quarter Ends   | June 31    |

Vivamus velit sem, aliquam hendrerit fringilla ut, tincidunt non dui. Aenean dignissim scelerisque eros vel sollicitudin. Phasellus sollicitudin sed massa vitae rhoncus. 

- [ ]   Pay tuition
- [X]  Finish essay
- [ ]  Call John


mollis. Aliquam erat volutpat. Duis finibus diam eu tempus lacinia. Cras ac placerat ante. Etiam molestie tristique tellus, in ornare felis malesuada euismod. Curabitur interdum libero eget lorem lacinia dictum. Vestibulum a sem sem. Donec leo nulla, posuere sit amet iaculis auctor, posuere id eros. Nullam iaculis, purus non viverra iaculis, quam ante consectetur massa, eget aliquet arcu mi quis nunc. Ut malesuada luctus mi, nec fringilla est tincidunt vel. 
