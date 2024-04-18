# 01 - Application Setup & Configuration

## 1. Create a new project

To get started, we'll create a new Next.js application using an existing starter template.

Run the following command in your terminal:

```
npx create-next-app@latest my-travel-ai -e https://github.com/colbyfayock/demo-travel-workshop-starter
```

This will create a new Next.js project, install the dependencies, and even refresh Git history.

Once ready, you can navigate to your new project directory with `cd my-travel-ai` or wherever you chose to install it to!

## 2. Create a new Cloudinary account

For our project, we'll be using Cloudinary to host our images as well as learn how to take advantage of some of the powerful
AI features available, but to do that, we first need a Cloudinary account.

Register for a free Cloudinary account on https://cloudinary.com

> Bonus: If you want to get a bonus 3 credits and 3 months of free add-on usage which we'll use for this project,
submit your new account's cloud name to: https://cld.media/braziljsworkshop

## 3. Configure your Cloudinary account

Now that we have our new account, let's configure our project with our credentials.

Create a new `.env.local` file and add the following:

```
NEXT_PUBLIC_CLOUDINARY_CLOUD_NAME="<Your Cloud Name>"
NEXT_PUBLIC_CLOUDINARY_API_KEY="<Your API Key>"
CLOUDINARY_API_SECRET="<Your API Secret>"
```

> Tip: You could alternatively rename the existing `.env.example` file to `.env.local` and update the values.

The environment variable values should come from your personal Cloudinary account which you can find in your Cloudinary Dashboard.

<img width="1727" alt="image" src="https://github.com/colbyfayock/cloudinary-ai-travel-workshop/assets/1045274/62cdb26f-7145-46d2-8514-8e8caec99b6c">


## 4. Run the setup script

This project assumes that some images and videos exist with specific names. Rather than manually uploading these file by file,
we'll run the setup script that will automatically upload them all for you.

From the root of your project run the following to add the project images and videos to your Cloudinary account:

```
node scripts/setup.js
```

This script will use the credentials you just added to upload a bunch of images and videos to your Cloudinary account.

Once complete, you should be able to see them inside of your Media Library!

![image](https://github.com/colbyfayock/cloudinary-ai-travel-workshop/assets/1045274/7ee80cc9-bbac-4d8c-840d-7d3c80d63ff1)

## 5. Start your development server

Now that the assets are all uploaded, we can get started.

Start your development server by running:

```
npm run dev
```

And the project will be available at http://localhost:3000!

You should now see a basic page with some images representing different countries, with the images being delivered from Cloudinary.

![image](https://github.com/colbyfayock/cloudinary-ai-travel-workshop/assets/1045274/e787f80c-0185-44e3-bdea-689d5a3f76b7)


## 6. Review new project

Before jumping in to the next step, take some time to review the project, including navigating around the web app itself and checking out some of the code.

Some interesting things you can find:
- Using the CldImage component from Next Cloudinary to render optimized images
- Dynamic Next.js page routing to create a new page for each country
- Social media cards for each dynamic page generated using `generateMetadata` and Cloudinary

## Next Up

[02 - Using AI to Crop, Resize, & Transform Images](https://github.com/colbyfayock/cloudinary-ai-travel-workshop/blob/main/lessons/02%20-%20Using%20AI%20to%20Crop%2C%20Resize%2C%20%26%20Transform%20Images.md)
