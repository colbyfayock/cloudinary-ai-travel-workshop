# 04 - Moderating Uploads with AI

<Use case about UGC>

## 01 - Setting up Manual moderation with Upload Presets

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

Back inside Upload Preset configuration, under Upload Control and Auto moderation, select Amazon Rekognition.

We'll also need to register the Rekognition Add-On.

Navigate to Settings and then Add-Ons (Puzzle icon), find and select Rekognition AI Moderation, then select the Free option to add it to your account.

> Reminder: If you want to get a bonus 3 credits and 3 months of free add-on usage which we'll use for this project, submit your new account's cloud name to: https://cld.media/braziljsworkshop

If we try to upload a photo that's not permitted, we'll see it automatically gets rejected.

<img width="1110" alt="image" src="https://github.com/colbyfayock/cloudinary-ai-travel-workshop/assets/1045274/94249bcc-8ff4-42b2-a67c-5e0717808a79">
