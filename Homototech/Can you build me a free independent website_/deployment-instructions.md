# Deployment Instructions for HOMO TECH Survey Website

This document provides step-by-step instructions for deploying your HOMO TECH survey website to GitHub and Netlify, and configuring your custom domain.

## 1. GitHub Repository Setup

1. Create a new GitHub repository:
   - Go to [GitHub](https://github.com)
   - Click the "+" icon in the top right and select "New repository"
   - Name your repository (e.g., "homototech-survey")
   - Choose "Public" or "Private" visibility
   - Click "Create repository"

2. Push your code to GitHub:
   ```bash
   # Initialize Git in your project folder (if not already done)
   git init
   
   # Add all files to Git
   git add .
   
   # Commit the files
   git commit -m "Initial commit"
   
   # Add your GitHub repository as remote
   git remote add origin https://github.com/YOUR_USERNAME/homototech-survey.git
   
   # Push to GitHub
   git push -u origin main
   ```

## 2. Supabase Setup

1. Create a Supabase account:
   - Go to [Supabase](https://supabase.com)
   - Sign up for a free account
   - Create a new project

2. Set up your database:
   - Go to the SQL Editor in your Supabase dashboard
   - Create a new query
   - Copy and paste the SQL from your `migrations/0001_initial.sql` file
   - Run the query to create your tables

3. Get your API credentials:
   - Go to Project Settings > API
   - Copy your "URL" and "anon key"
   - You'll need these for the next step

## 3. Netlify Deployment

1. Create a Netlify account:
   - Go to [Netlify](https://netlify.com)
   - Sign up for a free account

2. Connect to GitHub:
   - Click "New site from Git"
   - Choose GitHub as your Git provider
   - Authorize Netlify to access your GitHub account
   - Select your repository

3. Configure build settings:
   - Build command: `npm run build`
   - Publish directory: `.next`
   - Click "Show advanced" and add environment variables:
     - `NEXT_PUBLIC_SUPABASE_URL`: Your Supabase URL
     - `NEXT_PUBLIC_SUPABASE_ANON_KEY`: Your Supabase anon key
     - `ADMIN_EMAIL`: Your admin email for accessing the dashboard
     - `ADMIN_PASSWORD`: Your admin password for accessing the dashboard

4. Deploy your site:
   - Click "Deploy site"
   - Wait for the build and deployment to complete

## 4. Custom Domain Setup

1. Add your custom domain to Netlify:
   - Go to your Netlify site dashboard
   - Click "Domain settings"
   - Click "Add custom domain"
   - Enter your domain name (homototech.com)
   - Follow the verification steps

2. Configure DNS settings:
   - If you purchased your domain through a domain registrar:
     - Go to your domain registrar's DNS settings
     - Add the Netlify DNS records provided in the Netlify dashboard
   - If you want to use Netlify DNS:
     - Click "Set up Netlify DNS" in the domain settings
     - Follow the instructions to point your domain's nameservers to Netlify

3. Enable HTTPS:
   - Netlify automatically provisions a free SSL certificate
   - This may take a few minutes to a few hours to complete

## 5. Testing Your Deployed Website

1. Test all functionality:
   - Visit your website at your custom domain
   - Test the survey form submission
   - Test the admin dashboard login
   - Verify that all pages load correctly

2. Admin Access:
   - Go to yourdomain.com/admin
   - Log in with the admin credentials you set in the environment variables

## 6. Maintenance and Updates

1. Making updates to your website:
   - Make changes to your local code
   - Commit and push to GitHub
   - Netlify will automatically rebuild and deploy your site

2. Monitoring:
   - Use the Netlify dashboard to monitor your site's performance
   - Check Supabase to monitor your database usage

## 7. Monetization Strategies

As discussed, here are potential ways to monetize your survey website:

1. Research partnerships with institutions interested in AI-human integration data
2. Premium insights for organizations wanting detailed analysis
3. Sponsored content from tech companies
4. Consulting services based on your expertise and data
5. Educational resources about AI's impact

## Need Help?

If you encounter any issues during deployment, please refer to:
- [Netlify Documentation](https://docs.netlify.com/)
- [Supabase Documentation](https://supabase.com/docs)
- [Next.js Deployment Documentation](https://nextjs.org/docs/deployment)
