# vue-directive-image-previewer

> A Vue.js project for tag img, click img to zoom out to full screen.

## Build Setup

``` bash
# install vue-directive-image-previewer
npm install vue-directive-image-previewer -D

# main.js
import VueDirectiveImagePreviewer from 'vue-directive-image-previewer'
import 'vue-directive-image-previewer/dist/assets/style.css'
Vue.use(VueDirectiveImagePreviewer)	
or
Vue.use(VueDirectiveImagePreviewer, {
  background: {     // or : background: '#000'
    color: '#000' // or rgba or rgb     // or image: 'url(xxx)'
  },
  // transition
  animate: {
    duration: 600,
    delay: 500
  },
  // loading (not supported)
  loading: {
    image: ''
  },
  // cursor(css)
  cursor: 'pointer',
  clickMethod: 'doubleClick'   // click or doubleClick(not supported)
})

# use this directive
<img v-image-preview src="some-pic-url"/>
or 
<img v-image-preview="some-pic-url or another-pic-url" src="some-pic-url"/>
or
<img v-image-preview="{src: 'some-pic-url or another-pic-url'}" src="some-pic-url"/>
```

## Github
[github](https://github.com/wszxdhr/vue-directive-image-previewer.git)   Why not Star? Why? Come on!

> Welcome to give me some advise or help me to make the code stronger, thanks!

## Demo

http://demo.image-previewer.anymelon.com

## Api    (updated at 2018-07-04)

### options(in Vue.use())

| API                          | TYPE          | EXAMPLE                                  | DEFAULT           | DESCRIBE                                 |
| ---------------------------- | ------------- | ---------------------------------------- | ----------------- | ---------------------------------------- |
| background                   | String / JSON | "#000000" or "rgba(0, 0, 0, 0.5)" or {backgroundColor: "#000000"} | {backgroundColor:"#000000"} | Background css of wrapper                |
| animate     | JSON          | {duration: 500, delay: 300, func: "linear"} | {duration: 500}   | Transition css of image(field "duration" must be Number) |
| loading（not support yet）     | JSON          | {pictureUrl: "http://somePicUrl"}        | undefined         | Settings of image when it is loading     |
| cursor      | String        | (whatever of css cursor)                 | "pointer"         | Cursor css of image which has directive "v-image-preview" |
| clickMethod（not support yet） | String        | "click" / "doubleClick"                  | "click"           | Method of opening image, **not for closing** |

### options(in directive)

| API        | TYPE   | EXAMPLE               | DEFAULT      | DESCRIBE                                 |
| ---------- | ------ | --------------------- | ------------ | ---------------------------------------- |
| ALL        | String | "http://some-pic-url" | src of <img> | This is for only set in a String, like v-image-preview="some-pic-url". |
| background                   | String / JSON | "#000000" or {backgroundColor: "#000000"} | {backgroundColor:"#000000"} | Background css of wrapper                |
| src | String | "http://some-pic-url" | src of <img> | When you want to set another optioins of directive, use this. |

