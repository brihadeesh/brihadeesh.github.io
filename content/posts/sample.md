+++
date = '2025-07-07T13:02:38+05:30'
draft = false
title = 'Markdown Guide'
section = "posts"

author = "reverist dark moth"
summary = "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam eu turpis urna."
description = "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam eu turpis urna."
+++

## Introduction

### Epigraphs

{{<epigraph author="Anonymous" cite="Some book or article">}}
*This is an epigraph or quote at the beginning of a section. Remember
to use the asterisk before and after the text otherwise it wont appear
in italics.*
{{</epigraph>}}

{{<epigraph author="Anonymous" cite="Some book or article">}}
*Neque porro quisquam est qui dolorem ipsum quia dolor sit amet,
consectetur, adipisci velit...*
{{</epigraph>}}

{{<epigraph author="Anonymous" cite="Some book or article">}}
*There is no one who loves pain itself, who seeks after it and wants to
have it, simply because it is pain...*
{{</epigraph>}}

### Regular paragraphs

{{<newthought>}}Start the sentence with small caps,{{</newthought>}}
and if you want to create other emphasis types, there is **Bold** and
*italic*.

### Links

[the text that will be visible](https://the-link.com/)


### Blockquotes

{{<blockquote author="Anonymous" cite="Some book or article">}}
Blah blah blah blah
{{</blockquote>}}

## Let me know if you have doubts.

## Images are below Only the `src` attribute is necessary.

{{<figure
  src="https://github.com/edwardtufte/tufte-css/raw/gh-pages/img/exports-imports.png"
>}}



Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam eu
turpis urna. roin arcu sem, imperdiet et tempus a, suscipit et
felis.{{<marginnote>}}This is a marginnote. It will appear on the
right of the text{{</marginnote>}} Ut commodo gravida turpis non
rutrum. Sed lacus ipsum, porttitor in interdum a, pellentesque nec
nisi. Suspendisse potenti. Nulla facilisi.{{<sidenote>}}This is a
sidenote. It has a number and you can use it like you would use
footnotes or to show something you referred to.{{</sidenote>}}
Phasellus sodales lobortis elit dictum porta. Nam molestie ante vel
mauris varius blandit. Ut laoreet odio vel tortor placerat, eget
condimentum sem aliquet. Etiam quis pulvinar magna. Morbi fringilla
neque non consequat varius. Cras quis aliquam felis. Cras egestas
sodales pretium. Praesent vitae metus id mauris elementum
fermentum. ({{<cite>}}Someone & Someone else,
2025{{</cite>}}{{<marginnote>}}This can be the details of the
citation{{</marginnote>}})

## The same image with `title` and `caption`

{{<figure
  src="https://github.com/edwardtufte/tufte-css/raw/gh-pages/img/exports-imports.png"
  title="The image title"
  label="mn-export-import"
  caption="This is the image caption. [Image attribution](#)"
  link="link"
>}}

Donec at felis non urna pellentesque imperdiet. Duis at dignissim
tellus, sed laoreet mi. Mauris ac interdum lorem. Suspendisse ut diam
a libero feugiat pellentesque. Nulla eros enim, pretium ut mi sed,
dictum posuere lacus. Nulla facilisi. Donec sit amet enim vehicula,
tempus leo id, dignissim mi. Duis sem libero, posuere et vulputate eu,
pharetra vitae nibh.{{<sidenote>}}This is a sidenote! It has
a little number.{{</sidenote>}}

## Use second and third level headings only

### For poetry

Make stanzas and at the end of each line except the last one on the
stanza add two spaces.


{{<blockquote author="William Wordsworth" cite="Daffodils">}}
I wandered lonely as a Cloud  
That floats on high o’er Vales and Hills,  
When all at once I saw a crowd,  
A host of golden Daffodils;  
Beside the Lake, beneath the trees,  
Fluttering and dancing in the breeze.


Continuous as the stars that shine  
And twinkle on the milky way,  
They stretched in never-ending line  
Along the margin of a bay:  
Ten thousand saw I at a glance,  
Tossing their heads in sprightly dance.


The waves beside them danced, but they  
Out-did the sparkling waves in glee:—  
A Poet could not but be gay  
In such a jocund company:  
I gazed—and gazed—but little thought  
What wealth the shew to me had brought:  


For oft when on my couch I lie  
In vacant or in pensive mood,  
They flash upon that inward eye  
Which is the bliss of solitude,  
And then my heart with pleasure fills,  
And dances with the Daffodils.
{{</blockquote>}}



Vestibulum ante ipsum primis in faucibus orci luctus et ultrices
posuere cubilia curae; Praesent gravida, mi et aliquet pulvinar, lacus
lectus pellentesque mi, sed porttitor nibh nisi eget dui. Cras
convallis, ipsum vel congue interdum, diam libero molestie mauris, at
tempor quam mi ut magna. Cras molestie ligula feugiat ipsum
vestibulum, ac pharetra mauris ullamcorper. Mauris euismod lectus
tellus. In hac habitasse platea dictumst. In a sollicitudin ligula, a
fermentum est. Donec ullamcorper libero ligula, eu tempor eros
lobortis at. Mauris et turpis sit amet turpis mollis faucibus quis non
purus. Nulla finibus odio quis mauris interdum, eu rutrum diam
rutrum. Sed eget mi nec magna ornare egestas id ac justo. Sed iaculis
magna ut quam vulputate congue.{{<sidenote>}}This is a sidenote! It has
a little number.{{</sidenote>}}

### This is a third level heading

**Full-width figure:**

{{<figure
  src="https://github.com/edwardtufte/tufte-css/raw/gh-pages/img/napoleons-march.png"
  type="full"
  label="mn-napoleonic-wars"
  title="Napoleonic wars"
  caption="This the image caption. [Image attribution](#)"
  alt="Napoleonic wars"
  link="#"
>}}

**Margin figure:**

Margin figures appear on the margin. Highly logical.
{{<figure
  src="https://github.com/edwardtufte/tufte-css/raw/gh-pages/img/rhino.png"
  type="margin"
  label="mn-rhino"
  title="The image title"
  caption="This is the image caption. [Image attribution](https://edwardtufte.github.io/tufte-css)"
  alt="alt"
  link="#"
>}}

In hac habitasse platea dictumst. Suspendisse consectetur, tortor ut
feugiat porttitor, est tortor elementum ante, sit amet auctor nisi
sapien in risus. Lorem ipsum dolor sit amet, consectetur adipiscing
elit. Sed vitae orci mi. Pellentesque eget orci fermentum,
pellentesque orci eu, aliquet est. Nunc rhoncus ante ac diam mattis,
sed euismod augue scelerisque. In id felis nec erat suscipit molestie
sit amet at elit. Etiam in dictum nisi. Integer consectetur eros
tempor, pharetra tortor iaculis, elementum metus. Pellentesque
habitant morbi tristique senectus et netus et malesuada fames ac
turpis egestas. Pellentesque dictum, lacus eu tincidunt ultricies,
purus sapien vulputate neque, et fringilla eros elit at
quam. Phasellus eu mi ut massa pulvinar viverra. Nulla rutrum urna non
pellentesque iaculis. Suspendisse a pretium urna. Suspendisse
pulvinar, mi nec egestas molestie, sapien arcu tempor tellus, sit amet
consequat nulla arcu eu dui. Phasellus at augue tristique, rhoncus mi
in, posuere lorem.

Suspendisse vitae nibh et magna ullamcorper feugiat. Vivamus porta,
leo et euismod commodo, purus est malesuada lorem, ac scelerisque dui
felis ac mi. Fusce ut metus metus. Ut a mattis tortor, ut gravida
nisi. In porttitor mattis dui eu ultricies. Proin mattis molestie
tellus consequat tincidunt. Nam aliquam, nisl at condimentum
facilisis, orci nisi rhoncus purus, eu fermentum lorem eros eu
velit. Aliquam gravida justo felis, nec lacinia erat lobortis in.
