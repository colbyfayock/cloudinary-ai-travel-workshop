# 03 - Transforming Videos & Optimizing Playback

Videos are super impactful for building engaging experiences, but they're a bit more challenging to work with, right?

Nah, Cloudinary can do mose of the same things it can do with images, and more!

> Next Cloudinary: https://next.cloudinary.dev/cldvideoplayer/examples

## 01 - Dynamically cropping and resizing videos

We can use similar cropping and resizing techniques to transform our videos to different aspect ratios on the fly.

If we have a landscape video, but want a social-friendly portrait video, we can easily transform it.

```
<CldVideoPlayer
  ...
  width={900}
  height={1600}
  transformation={{
    width: 900,
    height: 1600,
    crop: 'fill',
    gravity: 'auto'
  }}
  ...
/>
```

## 02 - Adaptive Bitrate Streaming (ABR)

By default, Cloudinary optimizes video playback to make sure you're not wasting bandwidth, but we can take advantage of
more advanced playback techniques like Adaptive Bitrate Streaming which optimizes delivery to the device watching.

```
<CldVideoPlayer
  ...
  transformation={{
    streaming_profile: 'hd',
  }}
  sourceTypes={['hls']}
  ...
/>
```

You might have seen this work similarly in YouTube or Netflix, playing different qualities depending on network conditions.

## 03 - Picture-in-Picture

And while not AI related (neither was ABR), Picture in Picture is a fun browser feature that allows you to easily spin up a floating video
with a simple flag.

```
<CldVideoPlayer
  ...
  pictureInPictureToggle
  ...
/>
```

## Next Up

[04 - Moderating Uploads with AI](https://github.com/colbyfayock/cloudinary-ai-travel-workshop/blob/main/lessons/04%20-%20Moderating%20Uploads%20with%20AI.md)
