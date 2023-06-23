# Tailwind + Postcss #

Installing Tailwind CSS as a PostCSS plugin is the most seamless way to integrate it with build tools like webpack, Rollup, Vite, and Parcel.

eun below command to install all the dependances

```
npm install
```

Here below steps shoild be done if you are not using our project file.

## Step 1 ##

Create your web project.

```
npm init
```

## Step 2 ##

Install tailwindcss and its peer dependencies via npm.

```
npm install -D tailwindcss postcss postcss-cli autoprefixer cross-env
```

## Step 3 ##

Create your tailwind.config.js file.

```
npx tailwindcss init
```

## Step 4 ##

Add tailwindcss and autoprefixer to your postcss.config.js file, or wherever PostCSS is configured in your project.

```
touch postcss.config.js
```

content of the `postcss.config.js` file.

```
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  }
}
```

## Step 5 ##

Add the paths to all of your template files in your tailwind.config.js file.

```
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./src/**/*.{html,js}"],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

## Step 6 ##

Add the @tailwind directives for each of Tailwind’s layers to your main CSS file inside the main folder as `tailwind.css` or any name.

```
@tailwind base;
@tailwind components;
@tailwind utilities;
```

## Step 7 ##

inside the `package.json` file, edit the script value as,

```
"scripts": {
    "dev": "postcss tailwind.css -o ./src/css/styles.css --watch"
  },
```

## Step 8 ##

craete a `src` folder and inside it put the below html code.

Make sure your compiled CSS is included in the <head> (your framework might handle this for you), then start using Tailwind’s utility classes to style your content.

```
<!doctype html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href="/dist/main.css" rel="stylesheet">
</head>
<body>
  <h1 class="text-3xl font-bold underline">
    Hello world!
  </h1>
</body>
</html>
```

## Step 9 ##

Build the website

```
npm run dev
```