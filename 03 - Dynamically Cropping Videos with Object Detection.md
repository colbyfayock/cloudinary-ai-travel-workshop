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
