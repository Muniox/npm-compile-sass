# npm-compile-sass


```
{
  "name": "npm-compile-sass",
  "version": "1.0.0",
  "description": "SASS compile|autoprefix|minimize and live-reload dev server using Browsersync for static HTML",
  "main": "public/index.html",
  "author": "Muniox",
  "scripts": {
    "build:sass": "sass  --no-source-map src/sass:public/css",
    "copy:assets": "copyfiles -u 1 ./src/assets/**/* public",
    "copy:html": "copyfiles -u 1 ./src/*.html public",
    "copy": "npm-run-all --parallel copy:*",
    "watch:assets": "onchange \"/src/assets/**/*\" -- npm run copy:assets",
    "watch:html": "onchange \"src/*.html\" -- npm run copy:html",
    "watch:sass": "sass  --no-source-map --watch src/sass:public/css",
    "watch": "npm-run-all --parallel watch:*",
    "serve": "browser-sync start --server public --files public",
    "start": "npm-run-all copy --parallel watch serve",
    "build": "npm-run-all copy:html build:*",
    "postbuild": "postcss public/css/*.css -u autoprefixer cssnano -r --no-map"
  },
  "dependencies": {
    "autoprefixer": "^10.4.2",
    "browser-sync": "^2.27.7",
    "copyfiles": "^2.4.1",
    "cssnano": "^5.0.17",
    "npm-run-all": "^4.1.5",
    "onchange": "^7.1.0",
    "postcss-cli": "^9.1.0",
    "sass": "^1.49.8"
  }
}
```
