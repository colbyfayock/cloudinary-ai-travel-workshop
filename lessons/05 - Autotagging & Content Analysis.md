# 05 - Autotagging & Content Analysis

[use case upload images and not being able to search for them]

## 01 - Manually tagging images

We're already tagging our images with `traveler-photo` and `destination-${destination.id}` which helps us programmatically search for the images for each page.

We can update these to whatever we want as long as we update the search request, but it's helpful for organizing when we know what the tag value we want to apply will be.

## 02 - Automatically tagging with AI

Instead, or in addition to, tagging manually, we can use AI to look at what's in the photo and apply those "things" as tags to the image.

To do this, we'll use the Google Auto Tagging Add-on.

Navigate to Settings and then Add-Ons (Puzzle icon), find and select Google Auto Tagging, then select the Free option to add it to your account.

> Reminder: If you want to get a bonus 3 credits and 3 months of free add-on usage which we'll use for this project, submit your new account's cloud name to: https://cld.media/braziljsworkshop

We'll also enable this on our Upload Preset from before, so navigate to Settings, Upload, Upload Control, then when managing your Upload Preset, navigate to Media analysis and AI, then select Google Auto Tagging.

This time if we upload our image, we should be able to look at it inside of our Media Library and see tags applied.

<img width="1726" alt="image" src="https://github.com/colbyfayock/cloudinary-ai-travel-workshop/assets/1045274/a1672590-c270-4c24-beef-9caf642ff653">

But we can also look inside of our Upload network request and see them in our response.

<img width="969" alt="image" src="https://github.com/colbyfayock/cloudinary-ai-travel-workshop/assets/1045274/fc96f4a0-6e70-4b4d-98dc-b6f028da6d7e">

## 03 - Generating Captions with AI

Let's take this analysis another step, where not only can we generate tags, we can generate captions for our images.

We'll use another Add-On for this, the Cloudinary AI Content Analysis Add-on.

Navigate to Settings and then Add-Ons (Puzzle icon), find and select Cloudinary AI Content Analysis, then select the Free option to add it to your account.

To activate it, we're going to update our code, where we're going to state that we want to use a detection of "captioning":

```
<CldUploadButton
  ...
  options={{
    ...
    detection: 'captioning',
  }}
>
  Add a Photo
</CldUploadButton>
```

And if we upload our image, we'll notice that we're missing the caption in the UI.

<img width="1728" alt="image" src="https://github.com/colbyfayock/cloudinary-ai-travel-workshop/assets/1045274/6b8f2750-34f4-4d0a-b632-8748008e7358">

But if we look inside of our Upload request again, we should see the caption!

<img width="1728" alt="image" src="https://github.com/colbyfayock/cloudinary-ai-travel-workshop/assets/1045274/b33b1263-797e-4364-a7be-5f99e39fa590">

So now let's automatically apply it to the image as soon as it's done.

Here we'll update the caption on success, but we'll also add a tag of "autocaption" so we know to review that caption to make sure it's accurate.

```
<CldUploadButton
  ...
  options={{
    ...
    detection: 'captioning',
    on_success: 'current_asset.update({ context: {caption: e.upload_info?.info?.detection?.captioning?.data?.caption} })'
  }}
>
  Add a Photo
</CldUploadButton>
```

And finally, we can apply that to the image by utilizing the image's context which includes a caption:

```
<CldImage
  ...
  alt={photo.context?.caption || ''}
/>
```

## Next Up

[06 - Removing Backgrounds & Stylizing Images](https://github.com/colbyfayock/cloudinary-ai-travel-workshop/blob/main/lessons/06%20-%20Removing%20Backgrounds%20from%20Images.md)
