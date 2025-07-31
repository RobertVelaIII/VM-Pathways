# VM Pathways

VM Pathways is an iOS application that helps users find medicinal products by analyzing their symptoms, conditions, and preferences. The app uses OpenAI's Assistant API to provide personalized product recommendations from Valley Medicinals' inventory.

## Features

- User-friendly welcome and onboarding flow
- Multi-step user intake process to collect health information
- AI-powered product recommendations using OpenAI Assistant API
- Modern, clean UI with proper sign-up and login screens

## Requirements

- Xcode 15.0+
- iOS 17.0+
- Swift 5.9+

## Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/RobertVelaIII/VM-Pathways.git
cd VM-Pathways
```

### 2. OpenAI API Configuration

This app requires an OpenAI API key and Assistant ID to function properly. These credentials are not included in the repository for security reasons.

You'll need to set up the following:

1. Create an OpenAI account at [https://platform.openai.com/](https://platform.openai.com/)
2. Generate an API key in your OpenAI dashboard
3. Create an Assistant with access to the Valley Medicinals product map JSON file
4. Configure your Xcode scheme with the following environment variables:

   - `OPENAI_API_KEY`: Your OpenAI API key
   - `OPENAI_ASSISTANT_ID`: Your OpenAI Assistant ID

To set environment variables in Xcode:
1. Open the project in Xcode
2. Select the VM Pathways scheme
3. Click "Edit Scheme..."
4. Select "Run" from the left sidebar
5. Go to the "Arguments" tab
6. Add the environment variables in the "Environment Variables" section

### 3. Assistant Configuration

The OpenAI Assistant should be configured with the following system instructions:

```
You are Bud, a product recommendation assistant for Valley Medicinals. Your purpose is to analyze customer needs and recommend the SINGLE most suitable product from Valley Medicinals' inventory. 

Carefully check the Valley Medicinals product map JSON file before responding. Match the customer's symptoms, health context, goals, experience, and preferences to the product map to select only ONE best-fit product, using ONLY information from the JSON file. 

When responding:
- Briefly acknowledge their needs.
- State the best matching product.
- Include the product URL in the format: https://valleymedicinals.com/products/product-name-with-hyphens
- Focus on clarity and helpfulness.
- If there is not a perfect match, recommend the closest option and explain why.
```

### 4. Build and Run

Open the project in Xcode and build/run on your preferred iOS simulator or device.

## Project Structure

The project follows a modular, feature-based architecture:

- **App**: Core app files and entry point
- **Core**: Shared components and utilities
- **Features**: Feature-specific modules
  - Welcome
  - Authentication
  - IntakeFlow
  - Recommendation
- **Resources**: Assets, fonts, and other resources
- **Utils**: Utility classes including OpenAI integration

## Notes for Contributors

- The OpenAI API key and Assistant ID are stored in environment variables and should never be committed to the repository
- The VM Pathways.xcscheme file is excluded from git to protect sensitive information
- Make sure to test the AI recommendation flow thoroughly before submitting changes

## License

[Include license information here]
