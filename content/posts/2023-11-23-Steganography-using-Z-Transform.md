+++
title = "A Frequency Domain Steganography using Z Transform (FDSZT)"
date = "2023-11-23"
summary = "Data hiding technique using Z transform (ZT) termed as FDSZT"
+++

# An Intro

Transform is applied on 2×2 masks of the source image in row major order to transform original sub image (cover image) block
to its corresponding frequency domain.

# What Does It Do?

So it looks like we can mask an image using Z-Transform and embed an message or even an image....Along with the hidden image , the dimensional values are also embedded into the real part of the host image mask on fourth LSB bit of the transformed coefficient within 2×2 mask

# How does Z-transform work?

The Formula For Z-Transform is:

![](https://cdn.discordapp.com/attachments/1099629557126012940/1210263457300226088/image.png?ex=65e9ecad&is=65d777ad&hm=080e2a00e1f33d4c415390e9c521c652dd46d082403a98b3726bb1ec45e8713b&)

limit is taken 0 to α as pixel value m=0cannot be negative for an image)
In the present implementation the value of r is taken as 1 and
ω varies between 0<= ω <=2π. 

The Schematic Diagram of FDSZT is as follows :
![](https://cdn.discordapp.com/attachments/1099629557126012940/1210264512968527932/image.png?ex=65e9eda9&is=65d778a9&hm=45e85b4499d31e1120a8075fc067940e822ebd8f84a55990b1504c5e51db256f&)

# Algorithm For Insertion

* Step 1: Obtain the size of the hidden image m×n
* Step 2: For each hidden message/image, read source image mask of size 2×2 in row major order. Apply Z-Transform onto the selected cover image mask(2 x 2) to obtain coefficients in transformed domain.
* Step 3:Obtain Median of the four frequency coefficients obtained in step 2 to choose the byte for embedding.
* Step 4:Embed 1 secret bit onto the fourth LSB position towards left of the byte.
* Step 5:Apply adjustmet if necessary so that the coefficient will be the median of the mask after embedding
* Step 5: Apply IZ-Transform to back the mask from Z domain to spatial domain.
* Step 6: Repeat step 2 to 6 for the whole cover image
image.
* Step 7: Stop

Formulas Used :
![](https://cdn.discordapp.com/attachments/1099629557126012940/1210267680695914546/image.png?ex=65e9f09c&is=65d77b9c&hm=d7ca0acbd54bd1324cd9017b68c1b523dd1a1807e418dacda7533369897858c8&)

# Algorithm For Extraction

The hidden image is received in spatial domain. The
embedded image is taken as the input and the hidden
message/ image size, content are extracted from it in
transform domain. 

Input: Embedded image of size p×q.
Output: Host image of size p×q, hidden image of
size m×n.

Method: ```Extract bits of hidden image from embedded image```

* Step 1: Read embedded image mask( of size 2×2) in
row major order. Apply Z-Transform onto
the embedded image mask to transform the
embedded sub image from spatial to
frequency domain so that four frequency
components are regenerated.
* Step 2:Obtain Median of four frequency
components to choose the embedded byte
from 2×2 mask.
* Step 3: Extract the secret bit from the byte
embedded in fourth LSB position. Replace
hidden message/ image bit position in the
block by '1'. For each eight extracted bits
construct one image pixel of authenticating
image.
* Step 4: Repeat step 1 to 3 to regenerate hidden
image as per size of the hidden image.
* Step 5: Stop

![](https://cdn.discordapp.com/attachments/1099629557126012940/1210277405818884177/image.png?ex=65e9f9ab&is=65d784ab&hm=9add397d16d5ad95a4d84c543b0eaa1d9e7da84b0912d93c901ff7cd2a7ceeba&)