# David Gomez - Marketing & Content Strategy Portfolio

Professional portfolio website for David Gomez, a bilingual marketing and content strategist specializing in English-Spanish localization and multi-channel marketing strategies.

## Tech Stack

- **Astro 5** - Modern web framework
- **Tailwind CSS 4** - Utility-first styling
- **TypeScript** - Type safety

## Features

- 🎨 Modern, professional marketing theme (Blue & Orange)
- 📱 Fully responsive design
- 🌎 Bilingual badges (English/Spanish)
- ⚡ Fast loading with optimized images
- 🎯 SEO-friendly
- 📧 Contact information and social links

## Sections

- **Hero** - Professional photo, tagline, and CTA buttons
- **About** - 7+ years experience overview
- **Services** - 6 core service offerings
- **Experience** - Work history with DG Digital, Campus TV, Costa's Burger
- **Skills** - Creative, marketing, technical skills + certifications
- **Contact** - Email, phone, location, and social links

## Local Development

### Prerequisites

- Node.js 18+ installed
- npm or yarn package manager

### Running Locally

1. Navigate to the project directory:
   ```bash
   cd ~/Documents/personal/gomezdavid.com
   ```

2. Install dependencies (if not already done):
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm run dev
   ```

4. Open your browser to:
   ```
   http://localhost:4321
   ```

The site will automatically reload when you make changes to the code.

### Other Commands

- **Build for production**: `npm run build`
- **Preview production build**: `npm run preview`

## Deployment

### GitHub Setup

1. Initialize git repository:
   ```bash
   cd ~/Documents/personal/gomezdavid.com
   git init
   git add .
   git commit -m "Initial commit: David Gomez portfolio"
   ```

2. Create a new repository on GitHub named `gomezdavid.com`

3. Push to GitHub:
   ```bash
   git remote add origin https://github.com/YOUR_USERNAME/gomezdavid.com.git
   git branch -M main
   git push -u origin main
   ```

### Cloudflare Pages Deployment

1. Log in to [Cloudflare Dashboard](https://dash.cloudflare.com/)
2. Go to **Workers & Pages** → **Create application** → **Pages**
3. Connect your GitHub account and select the `gomezdavid.com` repository
4. Configure build settings:
   - **Build command**: `npm run build`
   - **Build output directory**: `dist`
   - **Framework preset**: Astro
5. Click **Save and Deploy**

Your site will be live at `https://gomezdavid.pages.dev` and will auto-deploy on every push to main.

### Custom Domain (Optional)

1. In Cloudflare Pages, go to your project
2. Click **Custom domains** → **Set up a custom domain**
3. Enter your domain (e.g., `gomezdavid.com`)
4. Follow Cloudflare's instructions to update DNS records

## Content Updates

All content is stored in JSON files in `src/content/`:

- `config.json` - Basic info (name, title, contact)
- `about.md` - About section content
- `services.json` - Service offerings
- `experience.json` - Work history
- `skills.json` - Skills by category
- `certifications.json` - Professional certifications

## Image Optimization

Profile image has been optimized from 4MB to 43KB for fast loading while maintaining quality.

## License

Personal portfolio - All rights reserved.
