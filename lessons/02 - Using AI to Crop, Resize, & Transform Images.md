# 02 - Using AI to Crop, Resize, & Transform Images

Images can come from anyhwere, often leaving us stuck with the aspect ratios our content managers provide us.

But there's a better way...

> Next Cloudinary Docs: https://next.cloudinary.dev/

## 01 - Dynamically cropping and resizing images

With Cloudinary, we can dynamically crop and resize our images to any apsect ratio and any size with a few parameters.

```
<CldImage
  ...
  width={940}
  height={940}
  crop="fill"
  ...
/>
```

By default, the CldImage component includes a "gravity" of "auto" that uses AI to determine the most interesting part of the image
and crop to that location.

> Tip: You can see how it differs by defining a `gravity="center"`

## 02 - "Uncropping" images to avoid losing information

The tools we have for cropping are helpful for being able to intelligently crop, but we're still removing part of the image.

We can take advantage of Generative Fill, which uses AI to expand the image without losing any of the original details.

```
<CldImage
  ...
  width={730}
  height={900}
  crop="pad"
  fillBackground
  ...
/>
```

## 03 - Removing unwanted objects from images

But what if the image includes something we don't want?

We can use other Generative AI tools like Remove to simply remove an object from a photo, at scale!

```
<CldImage
  ...
  remove="person"
  ...
/>
```


## 04 - Replacing objects instead of removing

Or if you want something to be shown in the photo, but just not what's there, we can use
Generative Replace to swap it with something else.

```
<CldImage
  ...
  replace={['person', 'cat']}
  ...
/>
```

## Next Up

[03 - Transforming Videos & Optimizing Playback](https://github.com/colbyfayock/cloudinary-ai-travel-workshop/blob/main/lessons/03%20-%20Dynamically%20Cropping%20Videos%20with%20Object%20Detection.md)
