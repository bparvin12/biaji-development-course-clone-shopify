# Repository Description
This is a shopify reposity that was initially cloned from https://github.com/polidario/Elizabeth_Clean.

The repository is used for learning how to create shopify themes. Most of my notes will be found in `./shopifyNotes.md`

## Lessons covered from the course

Status | Lectures
------------ | -------------
:heavy_check_mark: | Installing Development Tools
:heavy_check_mark: | Navigational Bar
:heavy_check_mark: | 404 Page
:heavy_check_mark: | Article Page
:heavy_check_mark: | Blog Page
:heavy_check_mark: | Cart Page
:heavy_check_mark: | Product Collection Page
:heavy_check_mark: | Collections Page
:heavy_check_mark: | Homepage (Index)
:heavy_check_mark: | Pages (About & Contact)
:heavy_check_mark: | Advanced Product Page
:heavy_check_mark: | Search Page
:hourglass: | More lessons coming

## Steps to get the course up and running
Simultaneously run the following commands in separate terminals
### Start the Shopify Store Locally
```
shopify theme dev
```

Or, if the store is not configure yet:
```
shopify theme dev --store
```

### Start Tailwind CSS build --watch
```
npx tailwindcss -i ./src/tailwind.css -o ./assets/application.css --watch
```