# ldsn-responsive-images
An approach to using full screen responsive images

## The Goal
Help make your websites and apps faster, by not serving your user bloated images. 

##### Example
You currently have a 1400-px-wide image that you use for both desktop and phone. It looks great in both instances. The problem, is that you're slowing down the mobile user, and making them use more data. Instead of a 230kb image ... maybe the phone user only needs a 70kb image? 

## The fullscreen approach
1. You'll want two divs.
2. An outer wrapper where the position is set to relative.
2. Inside that, a second relative div — this one wraps your fullscreen image. Set your div to **height: 100vh**.
3. For your img CSS, make sure your height is 100%, and you use **object-fit:cover**.

## The normal approach
1. On your image-wrapper div, change your height to auto, and your width to whatever you want it to be (100% is often fine).
2. Remove both height and object-fit from your img CSS. 


## So what's src, srcset and sizes?
##### srcset
* You'll notice there are three, comma-separated items listed under srcset.
* Each item has two parts: The path to the image, and the actual width of that image (ex: 640w)
* The browser takes a look at how wide the container is that's holding your image.
* Say your container is full browser width, and you're on an iPhone 7.
* An iPhone 7's resolution is 750x1334. So the browser is looking for an image that is **at least** 750px wide.
* It goes down the list. It sees the first choice is 640w, so it skips that one. The second item is 1080w, so it goes with that option.

##### sizes
* Essentially, I could have left sizes out of this mix. The default value is 100vw (exactly what I typed in).
* That said, sizes does offer you more control over which image you display, and how wide you display it.
* To learn more, visit https://bitsofco.de/the-srcset-and-sizes-attributes/

##### src
* The traditional **img src** is used just in case you have a browser that doesn't recognize srcset. like maybe an older Windows machine. So then it simply defaults to using the image you declare with src.


![alt tag](https://github.com/bpliske/ldsn-responsive-images/blob/master/images/code-example.png)


![alt tag](https://github.com/bpliske/ldsn-responsive-images/blob/master/images/browser-example.jpg)

###### Photo by Brad Smith
