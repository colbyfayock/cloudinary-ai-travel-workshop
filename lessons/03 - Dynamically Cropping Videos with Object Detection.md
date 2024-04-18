# 03 - Transforming Videos & Optimizing Playback

## 01 - Dynamically cropping and resizing videos

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

## 03 - Picture-in-Picture

```
<CldVideoPlayer
  ...
  pictureInPictureToggle
  ...
/>
```

## Next Up

[04 - Moderating Uploads with AI](https://github.com/colbyfayock/cloudinary-ai-travel-workshop/blob/main/04%20-%20Moderating%20Uploads%20with%20AI.md)
