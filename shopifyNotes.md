# Shopify Notes

## Shopify Online Store 2.0

- It allows custom content components to be added everywhere not just on the homepage
- App Blocks
- Metafields
- Developer tooling (shopify cli and theme development)

## Shopify Liquid

Template language used for creating or modify shopify themes, but it is very limited.

- static content
- dymanic content

Categorized by three features
- **objects**: wrapped in curly braces {{ }}
- **tags**: tells template what to do -- {% %} {% end %}

  - control flow: create conditions
    ```
    {% if %} {% endif %}
    ```
  - iteration: tags that can be used to repeat blocks of code
    ```
    {% for product in collection.products %}
      <h1>{{ product.title }}
    {% endfor %}
    ```
  - theme: used to generate
    - template-specific HTML codes
    - dividing arrays into multiple pages
    - to make shopify themes use custom layouts/snippets
  - variable: tags that you can use to create liquid variables

    ```
    {% assign variable_name = shop.name %}

    {{ variable_name }}
    ```
- **filters**: they are methods thats modifies the value or output of an object
  ```
  {{ product.title | SPECIFIC_FILTER }}
  {{ product.title | upcase }}
  ```

## Creating Development Store
In shopify.dev, create new store: 
 - add business name
 - select the "for development mode" (not the transfer site option)
 - select latest build options
 - select create from scratch

**store created:** https://admin.shopify.com/store/biaji-development-online-store/

## Shopify CLI
### Install
- need to install homebrew first
- then shopify
```
brew tap shopify/shopify
brew install shopify-cli
```
- git
- node

### Create new theme using Shopify CLI
Couple ways
```
shopify theme init (this clones from the dawn template from shopify)

shopify theme init --clone-url=urlhere (this will clone from git url template)
```
### Log into development store
```
shopify theme dev --store
```
**Preview Url**: http://127.0.0.1:9292

## Init NPM and package.json
```
npm init -y
```

## Install Tailwind CSS
https://tailwindcss.com/

```
npm install -D tailwindcss
npx tailwindcss init
```

Installs tailwind CSS into project, as well as creates the initial `tailwind.config.js`

### Modify tailwind.config.js
Modified so that the content the config reaches is inside the layout folder
```
module.exports = {
  content: [
    './layout/*.liquid'
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

### Add Tailwind Directives
```
@tailwind base;
@tailwind components;
@tailwind utilities;
```

### Tailwind build prrocess
We modifed the command from the docs a bit, because our input and ouput paths are a bit different
Need to run this everytime new styles from tailwind or added
```
npx tailwindcss -i ./src/tailwind.css -o ./assets/application.css
```
Or, you can keep it running to change automatically using
```
npx tailwindcss -i ./src/tailwind.css -o ./assets/application.css --watch
```




