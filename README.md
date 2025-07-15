# CopilotKit Self-Hosted with Google Gemini

A modern Next.js application that demonstrates how to integrate CopilotKit with Google Gemini AI for a self-hosted AI assistant experience. This project provides a complete setup for running CopilotKit with Google's Gemini 2.5 Pro model as the underlying language model.

## 🚀 Features

- **Self-Hosted AI Assistant**: Run your own AI assistant without relying on external services
- **Google Gemini Integration**: Powered by Google's Gemini 2.5 Pro model
- **Modern UI**: Built with Next.js 15, React 19, and Tailwind CSS 4
- **CopilotKit Integration**: Features an interactive popup assistant
- **TypeScript Support**: Fully typed for better development experience
- **Hot Reload**: Instant updates during development with Turbopack

## 🛠️ Tech Stack

- **Framework**: Next.js 15.3.3 with App Router
- **Runtime**: React 19
- **AI Platform**: CopilotKit with Google Generative AI
- **Language Model**: Google Gemini 2.5 Pro
- **Styling**: Tailwind CSS 4
- **Language**: TypeScript 5
- **Package Manager**: pnpm

## 📋 Prerequisites

Before running this project, ensure you have:

1. **Node.js** (version 18 or higher)
2. **pnpm** package manager
3. **Google AI API Key** - Get one from [Google AI Studio](https://makersuite.google.com/app/apikey)

## 🔧 Installation

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd copilotkit-self-hosted-google
   ```

2. **Install dependencies**:
   ```bash
   pnpm install
   ```

3. **Set up environment variables**:
   Create a `.env.local` file in the root directory and add your Google API key:
   ```env
   GOOGLE_API_KEY=your_google_api_key_here
   
   # Optional: For Copilot Cloud integration
   NEXT_PUBLIC_COPILOT_API_KEY=your_copilot_api_key
   NEXT_PUBLIC_COPILOTKIT_RUNTIME_URL=your_runtime_url
   ```

## 🚀 Getting Started

1. **Start the development server**:
   ```bash
   pnpm dev
   ```

2. **Open your browser**:
   Navigate to [http://localhost:3000](http://localhost:3000) (or the port shown in your terminal)

3. **Try the AI Assistant**:
   - Click on the "Need any help?" popup in the bottom right corner
   - Start chatting with your AI assistant powered by Google Gemini

## 📁 Project Structure

```
copilotkit-self-hosted-google/
├── src/
│   └── app/
│       ├── api/
│       │   └── copilotkit/
│       │       └── route.ts          # CopilotKit API endpoint
│       ├── layout.tsx                # App layout with CopilotKit provider
│       ├── page.tsx                  # Main page with assistant popup
│       └── globals.css               # Global styles
├── public/                           # Static assets
├── package.json                      # Dependencies and scripts
├── next.config.ts                    # Next.js configuration
├── tailwind.config.js               # Tailwind CSS configuration
└── tsconfig.json                    # TypeScript configuration
```

## 🔌 API Integration

The project uses a custom API route (`/api/copilotkit`) that:

- Initializes the CopilotKit runtime
- Configures Google Gemini 2.5 Pro as the service adapter
- Handles all AI assistant requests through the CopilotKit framework

Key components:
- **GoogleGenerativeAIAdapter**: Connects to Google's Gemini API
- **CopilotRuntime**: Manages the AI assistant functionality
- **CopilotPopup**: Provides the user interface for the assistant

## 🎨 Customization

### Modify Assistant Behavior
Edit the instructions in `src/app/page.tsx`:
```tsx
<CopilotPopup
  instructions={"Your custom instructions here"}
  labels={{
    title: "Your Assistant Name",
    initial: "Your greeting message",
  }}
/>
```

### Change AI Model
Update the model in `src/app/api/copilotkit/route.ts`:
```typescript
const serviceAdapter = new GoogleGenerativeAIAdapter({
  apiKey: process.env["GOOGLE_API_KEY"] || "",
  model: "gemini-2.5-pro", // Change to your preferred model
});
```

### Styling
The project uses Tailwind CSS 4. Customize styles in:
- `src/app/globals.css` for global styles
- Individual components for component-specific styling

## 📝 Available Scripts

- `pnpm dev` - Start development server with Turbopack
- `pnpm build` - Build the application for production
- `pnpm start` - Start the production server
- `pnpm lint` - Run ESLint for code quality

## 🔒 Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `GOOGLE_API_KEY` | Google AI API key for Gemini access | Yes |
| `NEXT_PUBLIC_COPILOT_API_KEY` | CopilotKit public API key | No* |
| `NEXT_PUBLIC_COPILOTKIT_RUNTIME_URL` | CopilotKit runtime URL | No* |

*Required only when using Copilot Cloud instead of self-hosted setup

## 🚀 Deployment

### Deploy on Vercel
1. Push your code to a Git repository
2. Connect your repository to [Vercel](https://vercel.com)
3. Add your environment variables in the Vercel dashboard
4. Deploy!

### Other Platforms
This Next.js application can be deployed on any platform that supports Node.js applications.

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🔗 Links

- [CopilotKit Documentation](https://docs.copilotkit.ai/)
- [Google Gemini API](https://ai.google.dev/)
- [Next.js Documentation](https://nextjs.org/docs)
- [Tailwind CSS](https://tailwindcss.com/)

## 🆘 Support

If you encounter any issues:

1. Check the [CopilotKit documentation](https://docs.copilotkit.ai/)
2. Verify your Google API key is valid and has sufficient quota
3. Check the browser console for any error messages
4. Open an issue in this repository

---

Built with ❤️ using CopilotKit and Google Gemini AI