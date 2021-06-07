---
title: Markdown explanation
publicationDate: '11:40 PM - June 6, 2021'
---

There's plenty of explanation on how to write markdown on the internet. This is a reference
that you can use to check out the main elements and learn how to use them.
<!--more-->

By the way, if you want to use the first part of the post as the description, instead of
copy pasting you can use the ```html <!--more-->``` tag (checkout this post source). That will
set the content before the comment as the excerpt, and if there's no description, the excerpt will
take its place.

## Table of contents

<ul class="table-of-contents">
  <li><a href="#header">Headers</a></li>
  <li><a href="#images">Images</a></li>
  <li><a href="#links">Links</a></li>
  <li><a href="#code">Code</a></li>
  <li><a href="#quotes">Quotes</a></li>
</ul>


First, lets check out the headers


# Header
## Header
### Header
#### Header
##### Header
###### Header

You can write headers using the # sign

    # Header
    ## Header
    ### Header
    ...

and you can write blocks like that 👆 by identing the lines 4 spaces

       ...
       This is written inside of a block
       ...


## Images

![a dog](/dog.jpg)

## Links 
[Source](https://unsplash.com/photos/Zn5chZcnFRA) of the previous image

## Code

```py
arr = ["Person 1", "Person 2"]
arr.push("Person 3")
print(len(arr))
```

## Quotes

> This is a quote from a very wise person. 
> It takes this style by default but you can change 
> it on assets/css/global.css.
> Anyway, that's all for today.