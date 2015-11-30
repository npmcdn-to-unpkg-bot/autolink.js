# autolink.js [![Build Status](https://img.shields.io/circleci/project/egoist/autolink.js/master.svg?style=flat-square)](https://circleci.com/gh/egoist/autolink.js/tree/master)

Auto-link url and images, email, video, music, `<br/>` in text.

## Installation

CDN: https://npmcdn.com/autolink.js/autolink.min.js

```bash
npm install --save autolink.js
```

## Example

```javascript
import autoLink from 'autolink.js'
// link URL and Images/Emails
// `https?://` is optional
// normal link is transformed to <a>
// image address(png|gif|jpe?g) is transformed to <img>
autoLink(text, {
  // default options:
  email: true,
  image: true,
  // \n to <br/>
  br: true
})
// link URL only
// then it would regard image address as normal link using <a>
// instead of using <img> tag
autoLink(text, {image: false})
// link-ify and add DOM attributes
autoLink(text, {
  // add attributes for image only
  imageAttr: {
    'data-image': true
  },
  // add attributes for link only
  linkAttr: {
    'data-link': true
  },
  // add attributes for both
  sharedAttr: {
    'data-shared': true
  }
})
// show URL path only for normal links
// eg: 'http://github.com' is transformed to
// '<a href="http://github.com">github.com</a>'
// wow, without `http://` in the text
autoLink(text, {removeHTTP: true})
// enable to transform all embedable url
// eg: youtube/kickstarter/cloudmusic
autoLink(text, {embed: true})
```

## Embed

Feel free to make a request for supporting a embed-able link

Now we supports:

- Youtube, eg `https://www.youtube.com/watch?v=5vOAxP-u5KA`
- Kickstarter, eg: `https://www.kickstarter.com/projects/1546683916/treasures-of-the-universe-unique-astrophotography?ref=home_popular`
- Cloudmusic, eg: `http://music.163.com/#/song?id=36103237`

## License

MIT &copy; [EGOIST](https://github.com/egoist)
