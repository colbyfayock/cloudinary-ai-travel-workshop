# 04 - Moderating Uploads with AI

UGC, or User Generated Content, is a common way to bring engagement from your community.

A common example of this is customer reviews.

But how do you possibly manage all of those photos in a sane way? Making sure to avoid showing
NSFW content or generally enabling quality control.

> Next Cloudinary Docs: https://next.cloudinary.dev/clduploadbutton/examples

## 01 - Setting up Manual moderation with Upload Presets

To start, we can manually moderate any image uploaded to our account.

We'll do this by creating an Upload Preset and activating moderation.

Navigate to:
* Settings
* Upload
* Upload presets

Then click on **Add upload preset**.

Here we'll want to navigate to the Upload Control tab, where we'll select Manual under Auto moderation.

Now we can save, copy the ID of our new preset, and add it to our CldUploadButton:

```
<CldUploadButton
  ...
  uploadPreset="<Upload Preset>"
>
  Add a Photo
</CldUploadButton>
```

## 02 - Moderating with AI using Amazon Rekognition

But the goal here is to use AI to save us time right? Well we can automatically analyze each image upon upload
and determine what kind of content, and if it's determine to be not safe, automatically reject it.

To do this, we'll use the [Amazon Rekognition Add-On](https://cloudinary.com/documentation/aws_rekognition_ai_moderation_addon).

Back inside Upload Preset configuration, under Upload Control and Auto moderation, select Amazon Rekognition.

We'll also need to register the Rekognition Add-On.

Navigate to Settings and then Add-Ons (Puzzle icon), find and select Rekognition AI Moderation, then select the Free option to add it to your account.

> Reminder: If you want to get a bonus 3 credits and 3 months of free add-on usage which we'll use for this project, submit your new account's cloud name to: https://cld.media/braziljsworkshop

If we try to upload a photo that's not permitted, we'll see it automatically gets rejected.

<img width="1110" alt="image" src="https://github.com/colbyfayock/cloudinary-ai-travel-workshop/assets/1045274/94249bcc-8ff4-42b2-a67c-5e0717808a79">

## Next Up

[05 - Autotagging & Content Analysis](https://github.com/colbyfayock/cloudinary-ai-travel-workshop/blob/main/lessons/05%20-%20Autotagging%20%26%20Content%20Analysis.md)
