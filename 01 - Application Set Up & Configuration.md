# 01 - Application Set Up & Configuration

## Getting Started

1. Create a new project

```
npx create-next-app@latest my-travel-ai -e https://github.com/colbyfayock/demo-travel-workshop-starter
```

2. Create a new Cloudinary account

Register for a free Cloudinary account on https://cloudinary.com/

If you want to get a bonus 3 credits and 3 months of free add-on usage which we'll use for this project,
submit your new account's cloud name to: https://cld.media/braziljsworkshop

3. Configure your Cloudinary account

Create a new `.env.local` file and add the following:

```
NEXT_PUBLIC_CLOUDINARY_CLOUD_NAME="<Your Cloud Name>"
NEXT_PUBLIC_CLOUDINARY_API_KEY="<Your API Key>"
CLOUDINARY_API_SECRET="<Your API Secret>"
```

These values should be from your personal Cloudinary account which you can find in your Cloudinary Dashboard.

4. Run the setup script

This project assumes that some images and videos exist with specific names. Rather than manually uploading these file by file,
we'll run the setup script that will automatically upload them all for you.

From the root of your project run the following to add the project images and videos to your Cloudinary account:

```
node scripts/setup.js
```

4. Start your development server:

```
npm run dev
```

And the project will be available at http://localhost:3000!

5. Review new project

- Next.js page routing
- Optimization, first AI feature, used for automatically compressing without distorting quality
- Works by adding parameters to the URL