# 02 - Using AI to Crop, Resize, & Transform Images


## 01 - Dynamically cropping and resizing images

```
<CldImage
  ...
  width={940}
  height={940}
  crop="fill"
  ...
/>
```

## 02 - "Uncropping" images to avoid losing informatoin

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

```
<CldImage
  ...
  remove="person"
  ...
/>
```


## 04 - Replacing objects instead of removing

```
<CldImage
  ...
  replace={['person', 'cat']}
  ...
/>
```

## Next Up

[03 - Transforming Videos & Optimizing Playback](https://github.com/colbyfayock/cloudinary-ai-travel-workshop/blob/main/03%20-%20Dynamically%20Cropping%20Videos%20with%20Object%20Detection.md)
