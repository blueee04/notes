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

