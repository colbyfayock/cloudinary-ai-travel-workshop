# 06 - Removing Backgrounds & Stylizing Images

When showing our photos, we want to maintain consistency and visual appeal. If our images are coming
from different locations, we may not be able to do that so easily.

Cloudinary gives us a Photoshop-like API where we can easily do things like remove the background and
add other stylized effects, to trasnform our images exactly how we'd like.

> Next Cloudinary Docs: https://next.cloudinary.dev/cldimage/examples

## 01 - Removing Backgrounds

Cloudinary makes it easy to remove backgrounds using the [Cloudinary AI Background Removal Add-On](https://cloudinary.com/documentation/cloudinary_ai_background_removal_addon).

Navigate to Settings and then Add-Ons (Puzzle icon), find and select Cloudinary AI Background Removal, then select the Free option to add it to your account.

> Reminder: If you want to get a bonus 3 credits and 3 months of free add-on usage which we'll use for this project, submit your new account's cloud name to: https://cld.media/braziljsworkshop

Once enabled, we can now easily opt in out images to have the background removed by adding:

```
<CldImage
  ...
  removeBackground
/>
```

You'll notice when you first try to load the page with the background removed, you get broken images. When first trying to remove
the background, Cloudinary will return a 423 indicating that it's processing, but once that's complete, it will be served
cached for all following requests.

## 02 - Adding a Background Color

With our background removed, we can now add consistent background colors (or images) really easily.

Let's try adding a nice yellow background to all images:

```
<CldImage
  ...
  background="rgb:FEDD00"
/>
```

And we should see our images starting to look more uniform in appearance.

## 03 - Consistent Cropping & Sizing

Our images unfortunately have different sizes within the image frames, making it look inconsistent.

We can use Cloudinary's AI cropping feature to pick the best crop, making all items take up a good amount
of space, while also looking consistent in the UI.

```
<CldImage
  ...
  crop="auto"
/>
```

## What's Next?

Explore more [Cloudinary AI Features](https://cloudinary.com/documentation/ai_in_action), learn more web dev tech over on my [YouTube channel](https://youtube.com/colbyfayock), and let me know what you thought about the workshop [in this survey](https://forms.gle/32h1grNb8k5F6Z7A8)!
