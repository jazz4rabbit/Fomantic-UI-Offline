# Fomantic-UI-Offline
Fomantic-UI with offline fonts

## Pre-requirements

### install fomantic using nodejs
```bash
npm install fomantic-ui
```

### Downalod needed fonts (Lato, Nanum Gothic ...)
- Lato(https://google-webfonts-helper.herokuapp.com/fonts/lato?subsets=latin,latin-ext)
  - Styles: regular, italic, 700, 700italic
  - CSS: Modern Broswer
- Nanum Gothic(https://google-webfonts-helper.herokuapp.com/fonts/nanum-gothic?subsets=korean)
  - Styles: regular, 700
  - CSS: Modern Browser

## Configure fonts in Fomantic-UI
`semantic/src/site/global/site.variables`
```diff
 /*******************************
      User Global Variables
 *******************************/
+ 
+ @importGoogleFonts: false;
+ @fontName: 'Lato', 'Nanum Gothic';
```

`semantic/src/site/global/site.overrides`
```diff
 /*******************************
          Site Overrides
 *******************************/
+ 
+ /* lato-regular - latin-ext_latin */
+ @font-face {
+   font-family: 'Lato';
+   font-style: normal;
+   font-weight: 400;
+   src: local('Lato Regular'), local('Lato-Regular'),
+        url('../fonts/lato-v16-latin-ext_latin-regular.woff2') format('woff2'), /* Chrome 26+, Opera 23+, Firefox 39+ */
+        url('../fonts/lato-v16-latin-ext_latin-regular.woff') format('woff'); /* Chrome 6+, Firefox 3.6+, IE 9+, Safari 5.1+ */
+ }
+ /* lato-italic - latin-ext_latin */
+ @font-face {
+   font-family: 'Lato';
+   font-style: italic;
+   font-weight: 400;
+   src: local('Lato Italic'), local('Lato-Italic'),
+        url('../fonts/lato-v16-latin-ext_latin-italic.woff2') format('woff2'), /* Chrome 26+, Opera 23+, Firefox 39+ */
+        url('../fonts/lato-v16-latin-ext_latin-italic.woff') format('woff'); /* Chrome 6+, Firefox 3.6+, IE 9+, Safari 5.1+ */
+ }
+ /* lato-700italic - latin-ext_latin */
+ @font-face {
+   font-family: 'Lato';
+   font-style: italic;
+   font-weight: 700;
+   src: local('Lato Bold Italic'), local('Lato-BoldItalic'),
+        url('../fonts/lato-v16-latin-ext_latin-700italic.woff2') format('woff2'), /* Chrome 26+, Opera 23+, Firefox 39+ */
+        url('../fonts/lato-v16-latin-ext_latin-700italic.woff') format('woff'); /* Chrome 6+, Firefox 3.6+, IE 9+, Safari 5.1+ */
+ }
+ /* lato-700 - latin-ext_latin */
+ @font-face {
+   font-family: 'Lato';
+   font-style: normal;
+   font-weight: 700;
+   src: local('Lato Bold'), local('Lato-Bold'),
+        url('../fonts/lato-v16-latin-ext_latin-700.woff2') format('woff2'), /* Chrome 26+, Opera 23+, Firefox 39+ */
+        url('../fonts/lato-v16-latin-ext_latin-700.woff') format('woff'); /* Chrome 6+, Firefox 3.6+, IE 9+, Safari 5.1+ */
+ }
+ 
+ 
+ /* nanum-gothic-regular - korean */
+ @font-face {
+   font-family: 'Nanum Gothic';
+   font-style: normal;
+   font-weight: 400;
+   src: local('NanumGothic'),
+        url('../fonts/nanum-gothic-v17-korean-regular.woff2') format('woff2'), /* Chrome 26+, Opera 23+, Firefox 39+ */
+        url('../fonts/nanum-gothic-v17-korean-regular.woff') format('woff'); /* Chrome 6+, Firefox 3.6+, IE 9+, Safari 5.1+ */
+   unicode-range: U+ac00-d7af;
+ }
+ /* nanum-gothic-700 - korean */
+ @font-face {
+   font-family: 'Nanum Gothic';
+   font-style: normal;
+   font-weight: 700;
+   src: local('NanumGothic Bold'), local('NanumGothic-Bold'),
+        url('../fonts/nanum-gothic-v17-korean-700.woff2') format('woff2'), /* Chrome 26+, Opera 23+, Firefox 39+ */
+        url('../fonts/nanum-gothic-v17-korean-700.woff') format('woff'); /* Chrome 6+, Firefox 3.6+, IE 9+, Safari 5.1+ */
+   unicode-range: U+ac00-d7af
}
```

## Build Fomantic-UI
```bash
cd semantic
npx glup build

# move download fonts
mkdir dist/fonts
mv /path/to/download/fonts dist/fonts/
```