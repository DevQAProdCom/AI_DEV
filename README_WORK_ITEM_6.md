# Home Page - Work Item 6

## Description
This implementation creates a HomePage component for the DevQAProdCom application with a header section displaying the text "DevQAProdCom".

## Features
- Angular-based HomePage component located in `src/pages/`
- Header section with DevQAProdCom branding
- Styled header with dark background and centered text
- Responsive design using Flexbox

## File Structure
```
src/
├── pages/
│   ├── home-page.component.ts
│   ├── home-page.component.html
│   └── home-page.component.css
├── app.component.ts
├── app.component.html
├── app.component.css
├── app.module.ts
├── main.ts
└── index.html
```

## Components
- **HomePageComponent**: Main page component with header section
- **AppComponent**: Root component that displays the HomePage

## Styling
The header section features:
- Dark background color (#333)
- White text
- Centered alignment
- Large, bold heading (2.5em)

## Getting Started
Install dependencies:
```bash
npm install
```

Build for production:
```bash
npm run build
```

## Dependencies
- @angular/core
- @angular/common
- @angular/platform-browser
- @angular/platform-browser-dynamic
- @angular/compiler
- @angular/animations
