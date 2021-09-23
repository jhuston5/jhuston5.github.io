# Chapter 5: “Images” (pp.94-125)
Design/visuals have never been a strength of mine. I don't think I will love the styling of front end development, but I am happy to learn!

**Images should be**
> Relevant
> Convey Information
> Convey Mood
> Be recognisable
> Fit color palette 
*(Duckett HTML 97)*

**Should organize pictures within the image folder, with various subfolders as needed**

- Pictures should be saved at the size we will be using on the web page
- Photos best saved as JPEGs
- Illustrations or logos with flat colors should be GIFs
*(Duckett HTML 124)*

# Chapter 11: “Color” (pp.246-263)
## Colors
### 3 Main Ways to Specify Colors
1. RGB Values
>Use red green blue to note the color. Format is rgb(100,100,100)
2. Hex Codes
>6 digits that also express the amount of red, green and blue. 
>Preceded by a pound or hash - #ee3e80
3. Color Names
>147 predefined color codes 

- Hue: basically our idea of color
- Saturation: how much grey is in a color
- Brightness: how much black is in a color
- Contrast
>make sure this is set to an appropriate level for the amount of text on a page.
- Opacity
>determines what level you can see through an element. Use RGBA and HSLA.


# Chapter 12: “Text” (pp.264-299)
## Typeface
When choosing a font, remember that it will only display if that font is installed on a user's computer *(Duckett HTML 269)* Font-face can bypass this if fonts are licensed appropriately (277)
1. Serif
2. Sans-Serif
3. Monospace
4. Cursive
5. Fantasy

I had no idea these were different generalized font styles.

PC vs Mac- typefaces can render a bit less smoothly on a PC.

- font-family: select a font
- font-size: specify size of text

text-indent and first-letter seem like they will be useful/fun to play with.

# JPEG vs PNG vs GIF
>Use **JPEG** format for all images that contain a natural scene or photograph where variation in *colour and intensity is smooth*. Use **PNG** format for any image that needs transparency or for images with text & objects with *sharp contrast edges* like logos. Use **GIF** format for images that contain *animations*.
*(https://blog.imagekit.io/jpeg-vs-png-vs-gif-which-image-format-to-use-and-when-c8913ae3e01d)*


## Compression
Lossless vs Lossy
JPEGs are Lossy- lose some of the compression during data transfer
PNGs are Lossless - don't lose compression but do not have a good compression ratio

## Transparency
JPEGs cannot be used when transparency is needed
PNGs can support transparency (another reason they are preferred for logos as they often need to be with different backgrounds.)