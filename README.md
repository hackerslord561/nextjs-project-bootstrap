# Uni Go Transport - Landing Page

A modern, responsive landing page for Uni Go Transport, a Ghanaian transport service company. This project is a complete rebrand and redesign of the original Akwantuo Express website, featuring a yellow and white color palette with smooth animations and modern UI components.

## 🚀 Features

- **Modern Design**: Clean, professional layout with yellow and white color scheme
- **Responsive**: Fully responsive design that works on all devices
- **Smooth Animations**: Powered by Framer Motion for engaging user interactions
- **Accessibility**: Built with accessibility-first Radix UI components
- **Type Safety**: Full TypeScript implementation
- **Performance**: Optimized with Next.js 15+ and Turbopack

## 🛠️ Tech Stack

- **Framework**: Next.js 15.3.2 with App Router
- **Language**: TypeScript
- **Styling**: Tailwind CSS 4.x with custom design system
- **Animations**: Framer Motion
- **UI Components**: Radix UI primitives with shadcn/ui
- **Forms**: React Hook Form with Zod validation
- **Icons**: Emoji-based icons (no external icon libraries)

## 📱 Sections

1. **Header**: Navigation with logo and call-to-action button
2. **Hero**: Eye-catching purple gradient with main messaging
3. **Services**: Five service cards showcasing company offerings
4. **About**: Company information and team showcase
5. **Features**: Detailed booking process explanation
6. **Contact**: Functional contact form with validation
7. **Footer**: Company links and social media

## 🚦 Getting Started

### Prerequisites

- Node.js 18+ 
- npm, yarn, pnpm, or bun

### Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd uni-go-transport
```

2. Install dependencies:
```bash
npm install
# or
yarn install
# or
pnpm install
```

3. Run the development server:
```bash
npm run dev
# or
yarn dev
# or
pnpm dev
```

4. Open [http://localhost:8000](http://localhost:8000) in your browser

## 🎨 Design System

The project uses a custom design system with:

- **Primary Colors**: Yellow (#FFD700) and White (#FFFFFF)
- **Accent Colors**: Purple (#4A148C) for contrast
- **Typography**: Inter font family
- **Components**: Consistent spacing and border radius
- **Animations**: Subtle hover effects and scroll-triggered animations

## 📁 Project Structure

```
src/
├── app/
│   ├── globals.css          # Global styles and CSS variables
│   ├── layout.tsx           # Root layout component
│   └── page.tsx             # Main page component
├── components/
│   ├── LandingPage.tsx      # Main landing page component
│   └── ui/                  # Reusable UI components (shadcn/ui)
├── hooks/                   # Custom React hooks
└── lib/
    └── utils.ts             # Utility functions
```

## 🔧 Customization

### Colors
Update the color palette in `src/app/globals.css`:
```css
:root {
  --uni-yellow: #FFD700;
  --uni-white: #FFFFFF;
  --uni-purple: #4A148C;
}
```

### Content
Modify the content in `src/components/LandingPage.tsx` to update:
- Company information
- Service offerings
- Contact details
- Images and descriptions

## 📦 Build & Deploy

### Build for Production
```bash
npm run build
```

### Start Production Server
```bash
npm start
```

### Deploy on Vercel
The easiest way to deploy is using [Vercel](https://vercel.com/new):

1. Push your code to GitHub
2. Import your repository on Vercel
3. Deploy with zero configuration

## 🚨 Troubleshooting

### Git Push Issues (Large Files)
If you encounter errors about large files when pushing to GitHub:

```bash
# Remove node_modules from Git tracking
git rm -r --cached node_modules/
git rm -r --cached .next/

# Ensure .gitignore is properly named (not gitignore.txt)
mv gitignore.txt .gitignore  # if needed

# Commit and force push
git add .gitignore
git commit -m "Fix: Remove large files and add proper .gitignore"
git push origin master --force
```

See `GIT_FIX_GUIDE.md` for detailed instructions.

### Development Issues
- **Port 8000 in use**: Kill the process with `fuser -k 8000/tcp`
- **Build errors**: Delete `.next` folder and run `npm run build` again
- **TypeScript errors**: Check `tsconfig.json` and ensure all dependencies are installed

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Original design inspiration from Akwantuo Express
- [shadcn/ui](https://ui.shadcn.com/) for the component system
- [Framer Motion](https://www.framer.com/motion/) for animations
- [Radix UI](https://www.radix-ui.com/) for accessible components

## 📞 Support

For support, email support@unigotransport.com or create an issue in this repository.

---

**Built with ❤️ for Uni Go Transport**
