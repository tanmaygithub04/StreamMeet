# 🚀 Deployment Guide - Zoom Clone App

## Prerequisites
- Make sure you have your environment variables set up locally
- Ensure the app works locally before deploying

## 1. Environment Variables Setup

### Required Environment Variables:
```bash
# Clerk Authentication
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=pk_test_your_publishable_key_here
CLERK_SECRET_KEY=sk_test_your_secret_key_here

# Clerk URL Configuration
NEXT_PUBLIC_CLERK_SIGN_IN_URL=/sign-in
NEXT_PUBLIC_CLERK_SIGN_UP_URL=/sign-up

# Stream Video API
NEXT_PUBLIC_STREAM_API_KEY=your_stream_api_key_here
STREAM_SECRET_KEY=your_stream_secret_key_here

# Base URL for the application (update this to your production URL)
NEXT_PUBLIC_BASE_URL=https://your-app-name.vercel.app
```

### Get Your Credentials:

#### Clerk Credentials:
1. Go to [Clerk Dashboard](https://dashboard.clerk.com/)
2. Create a new application (choose "Next.js")
3. Go to **API Keys** section
4. Copy the **Publishable Key** and **Secret Key**

#### Stream Credentials:
1. Go to [GetStream Dashboard](https://getstream.io/)
2. Create a new application
3. Go to your app dashboard
4. Copy the **API Key** and **Secret Key**

## 2. Deploy to Vercel

### Option A: Deploy via Vercel CLI (Recommended)

1. **Login to Vercel:**
   ```bash
   vercel login
   ```

2. **Deploy the app:**
   ```bash
   vercel
   ```

3. **Follow the prompts:**
   - Set up and deploy? → Yes
   - Which scope? → Choose your account
   - Link to existing project? → No
   - What's your project's name? → zoom-clone (or your preferred name)
   - In which directory is your code located? → ./

4. **Set environment variables:**
   ```bash
   vercel env add NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY
   vercel env add CLERK_SECRET_KEY
   vercel env add NEXT_PUBLIC_STREAM_API_KEY
   vercel env add STREAM_SECRET_KEY
   vercel env add NEXT_PUBLIC_CLERK_SIGN_IN_URL
   vercel env add NEXT_PUBLIC_CLERK_SIGN_UP_URL
   vercel env add NEXT_PUBLIC_BASE_URL
   ```

5. **Deploy to production:**
   ```bash
   vercel --prod
   ```

### Option B: Deploy via GitHub (Alternative)

1. **Push your code to GitHub:**
   ```bash
   git add .
   git commit -m "Ready for deployment"
   git push origin main
   ```

2. **Go to [Vercel Dashboard](https://vercel.com/dashboard)**

3. **Click "New Project"**

4. **Import your GitHub repository**

5. **Configure Environment Variables in Vercel Dashboard:**
   - Go to Project Settings → Environment Variables
   - Add all the required environment variables listed above

6. **Deploy**

## 3. Update Clerk Settings

After deployment, update your Clerk settings:

1. Go to [Clerk Dashboard](https://dashboard.clerk.com/)
2. Go to **Sessions** → **Settings**
3. Update the **Allowed Origins** to include your production URL:
   ```
   https://your-app-name.vercel.app
   ```

## 4. Update Stream Settings

1. Go to [GetStream Dashboard](https://getstream.io/)
2. Go to your app settings
3. Update the **Allowed Origins** to include your production URL

## 5. Test Your Deployment

1. Visit your deployed app URL
2. Test sign-up and sign-in functionality
3. Create a test meeting to ensure video calling works
4. Test all meeting features (screen sharing, recording, etc.)

## 6. Custom Domain (Optional)

If you want to use a custom domain:

1. Go to your Vercel project dashboard
2. Go to **Settings** → **Domains**
3. Add your custom domain
4. Update your environment variables to use the custom domain
5. Update Clerk and Stream settings with the new domain

## Troubleshooting

### Common Issues:

1. **Environment Variables Not Working:**
   - Make sure all environment variables are set in Vercel dashboard
   - Redeploy after adding environment variables

2. **Clerk Authentication Issues:**
   - Check that your Clerk allowed origins include your production URL
   - Verify your Clerk keys are correct

3. **Stream Video Issues:**
   - Ensure Stream API keys are correct
   - Check Stream dashboard for any domain restrictions

4. **Build Errors:**
   - Check the build logs in Vercel dashboard
   - Ensure all dependencies are listed in package.json

### Get Help:
- Vercel Documentation: [https://vercel.com/docs](https://vercel.com/docs)
- Clerk Documentation: [https://clerk.com/docs](https://clerk.com/docs)
- Stream Documentation: [https://getstream.io/video/docs/](https://getstream.io/video/docs/)

## 🎉 Congratulations!

Your Zoom clone app is now deployed and ready to use! Share the URL with others to start hosting video meetings. 