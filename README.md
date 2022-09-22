cross-fetch<br>
[![NPM Version](https://img.shields.io/npm/v/cross-fetch.svg?branch=main)](https://www.npmjs.com/package/cross-fetch)
[![Downloads Per Week](https://img.shields.io/npm/dw/cross-fetch.svg?color=blue)](https://www.npmjs.com/package/cross-fetch)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![CI](https://github.com/lquixada/cross-fetch/actions/workflows/ci.yml/badge.svg)](https://github.com/lquixada/cross-fetch/actions/workflows/ci.yml)
[![codecov](https://codecov.io/gh/lquixada/cross-fetch/branch/main/graph/badge.svg)](https://codecov.io/gh/lquixada/cross-fetch)
================

Universal WHATWG Fetch API for Node, Browsers and React Native. The scenario that cross-fetch really shines is when the same JavaScript codebase needs to run on different platforms.

- **Platform agnostic**: browsers, Node or React Native
- **Optional polyfill**: it's up to you if something is going to be added to the global object or not
- **Simple interface**: no instantiation, no configuration and no extra dependency
- **WHATWG compliant**: it works the same way wherever your code runs
- **TypeScript support**: better development experience with types.


* * *

## Table of Contents

-   [Install](#install)
-   [Usage](#usage)
-   [Demo & API](#demo--api)
-   [FAQ](#faq)
-   [Thanks](#thanks)
-   [License](#license)
-   [Author](#author)

* * *

## Install

```sh
npm install --save cross-fetch
```

As a [ponyfill](https://github.com/sindresorhus/ponyfill):

```javascript
// Using ES6 modules with Babel or TypeScript
import fetch from 'cross-fetch';

// Using CommonJS modules
const fetch = require('cross-fetch');
```

As a polyfill:

```javascript
// Using ES6 modules
import 'cross-fetch/polyfill';

// Using CommonJS modules
require('cross-fetch/polyfill');
```


The CDN build is also available on unpkg:

```html
<script src="//unpkg.com/cross-fetch/dist/cross-fetch.js"></script>
```

This adds the fetch function to the window object. Note that this is not UMD compatible.


* * *

## Usage

With [promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise):

```javascript
import fetch from 'cross-fetch';
// Or just: import 'cross-fetch/polyfill';

fetch('//api.github.com/users/lquixada')
  .then(res => {
    if (res.status >= 400) {
      throw new Error("Bad response from server");
    }
    return res.json();
  })
  .then(user => {
    console.log(user);
  })
  .catch(err => {
    console.error(err);
  });
```

With [async/await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function):

```javascript
import fetch from 'cross-fetch';
// Or just: import 'cross-fetch/polyfill';

(async () => {
  try {
    const res = await fetch('//api.github.com/users/lquixada');
    
    if (res.status >= 400) {
      throw new Error("Bad response from server");
    }
    
    const user = await res.json();
  
    console.log(user);
  } catch (err) {
    console.error(err);
  }
})();
```

> ⚠️ **Warning**: If you're in an environment that doesn't support Promises such as Internet Explorer, you must install an ES6 Promise compatible polyfill. [es6-promise](https://github.com/jakearchibald/es6-promise) is suggested.


## Demo & API

You can find a comprehensive doc at [Github's fetch](https://github.github.io/fetch/) page. If you want to play with cross-fetch, check our [**JSFiddle playground**](https://jsfiddle.net/lquixada/3ypqgacp/).

> **Tip**: Run the fiddle on various browsers and with different settings (for instance: cross-domain requests, wrong urls or text requests). Don't forget to open the console in the test suite page and play around.


## FAQ

#### Yet another fetch library?

I did a lot of research in order to find a fetch library that could be simple, cross-platform and provide polyfill as an option. There's a plethora of libs out there but none could match those requirements.


#### Why not isomorphic-fetch?

My preferred library used to be [isomorphic-fetch](https://github.com/matthew-andrews/isomorphic-fetch) but it has this [bug](https://github.com/matthew-andrews/isomorphic-fetch/issues/125) that prevents it from running in a react native environment. It seems unlikely to be fixed since there haven't been any new commits to it since 2016. That means dependencies are outdated as well. 


#### Why polyfill might not be a good idea?

In a word? Risk. If the spec changes in the future, it might be problematic to debug. Read more about it on [sindresorhus's ponyfill](https://github.com/sindresorhus/ponyfill#how-are-ponyfills-better-than-polyfills) page. It's up to you if you're fine with it or not.


#### How does cross-fetch work?

Just like isomorphic-fetch, it is just a proxy. If you're in node, it delivers you the [node-fetch](https://github.com/bitinn/node-fetch/) library, if you're in a browser or React Native, it delivers you the github's [whatwg-fetch](https://github.com/github/fetch/). The same strategy applies whether you're using polyfill or ponyfill.


## Who's Using It?

|[![The New York Times](./docs/images/logo-nytimes.png)](https://www.nytimes.com/)|[![Apollo GraphQL](./docs/images/logo-apollo.png)](https://github.com/apollographql/apollo-client/)|[![Facebook](./docs/images/logo-facebook.png)](https://github.com/facebook/fbjs/)|[![Swagger](./docs/images/logo-swagger.png)](https://swagger.io/)|[![VulcanJS](./docs/images/logo-vulcanjs.png)](http://vulcanjs.org)|[![graphql-request](./docs/images/logo-graphql-request.png)](https://github.com/prisma/graphql-request)|
|:---:|:---:|:---:|:---:|:---:|:---:|
|The New York Times|Apollo GraphQL|Facebook|Swagger|VulcanJS|graphql-request|


## Thanks

Heavily inspired by the works of [matthew-andrews](https://github.com/matthew-andrews). Kudos to him!


## License

cross-fetch is licensed under the [MIT license](https://github.com/lquixada/cross-fetch/blob/main/LICENSE) © [Leonardo Quixadá](https://twitter.com/lquixada/)


## Author

|[![@lquixada](https://avatars0.githubusercontent.com/u/195494?v=4&s=96)](https://github.com/lquixada)|
|:---:|
|[@lquixada](http://www.github.com/lquixada)|
[![OS Ready for review](https://github.com/github/docs/actions/workflows/os-ready-for-review.yml/badge.svg)](https://github.com/github/docs/actions/workflows/os-ready-for-review.yml)

<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<!-- Created with Inkscape (http://www.inkscape.org/) -->

<svg
   xmlns:dc="http://purl.org/dc/elements/1.1/"
   xmlns:cc="http://creativecommons.org/ns#"
   xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
   xmlns:svg="http://www.w3.org/2000/svg"
   xmlns="http://www.w3.org/2000/svg"
   xmlns:sodipodi="http://sodipodi.sourceforge.net/DTD/sodipodi-0.dtd"
   xmlns:inkscape="http://www.inkscape.org/namespaces/inkscape"
   version="1.1"
   id="svg815"
   width="256"
   height="256"
   viewBox="0 0 256 256"
   sodipodi:docname="gcm.svg"
   inkscape:version="0.92.4 (5da689c313, 2019-01-14)">
  <metadata
     id="metadata821">
    <rdf:RDF>
      <cc:Work
         rdf:about="">
        <dc:format>image/svg+xml</dc:format>
        <dc:type
           rdf:resource="http://purl.org/dc/dcmitype/StillImage" />
        <dc:title></dc:title>
      </cc:Work>
    </rdf:RDF>
  </metadata>
  <defs
     id="defs819" />
  <sodipodi:namedview
     pagecolor="#ffffff"
     bordercolor="#666666"
     borderopacity="1"
     objecttolerance="10"
     gridtolerance="10"
     guidetolerance="10"
     inkscape:pageopacity="0"
     inkscape:pageshadow="2"
     inkscape:window-width="3240"
     inkscape:window-height="2035"
     id="namedview817"
     showgrid="false"
     inkscape:zoom="6.75"
     inkscape:cx="123.40741"
     inkscape:cy="127.96376"
     inkscape:window-x="-13"
     inkscape:window-y="-13"
     inkscape:window-maximized="1"
     inkscape:current-layer="svg815" />
  <path
     style="fill:#f05033;fill-opacity:1;stroke-width:2.24708056"
     d="m 127.74219,0 c -4.21881,0 -8.43843,1.6093415 -11.65821,4.828125 L 92.875,28.041016 122.31445,57.482422 c 6.84425,-2.310946 14.68947,-0.761046 20.14258,4.693359 5.48141,5.488392 7.0192,13.400136 4.65039,20.267578 l 28.37696,28.376951 c 6.86492,-2.36579 14.78398,-0.83727 20.26562,4.6543 7.66374,7.66179 7.66374,20.07642 0,27.74023 -7.66486,7.66631 -20.07893,7.66631 -27.74805,0 -5.76254,-5.76724 -7.18821,-14.23373 -4.26953,-21.33398 l -26.46289,-26.464844 -0.002,69.640624 c 1.8684,0.92496 3.63248,2.16064 5.18945,3.71094 7.66148,7.6609 7.66148,20.07236 0,27.74609 -7.66374,7.66066 -20.08459,7.66066 -27.74023,0 -7.66262,-7.67305 -7.66262,-20.08452 0,-27.74609 1.89369,-1.89039 4.08382,-3.32218 6.42187,-4.28125 V 94.199219 c -2.33912,-0.955028 -4.52734,-2.375687 -6.42383,-4.28125 -5.80409,-5.799832 -7.20125,-14.319608 -4.22461,-21.447266 L 81.466797,39.443359 4.8300781,116.08203 c -6.4393305,6.44252 -6.4393305,16.88229 0,23.32031 L 42.5,177.07227 V 162.70508 C 35.078345,157.16403 29.678851,149.02425 27.328125,140.07617 19.76286,115.647 40.902921,87.908596 66.359375,88.345703 76.747705,88.003924 87.132367,91.94485 94.875,98.837891 c 18.78493,15.372969 17.87151,47.496839 -0.888672,62.484379 l -2.566406,1.3457 0.222656,12.46503 -8.160156,8.24395 v 34.67578 l 33.119138,33.11915 c 6.43505,6.43757 16.87041,6.43757 23.31446,0 L 251.17188,139.92969 c 6.43732,-6.4407 6.43732,-16.88336 0,-23.32227 l 0.002,-0.01 L 139.39453,4.828125 C 136.1788,1.6093415 131.96099,0 127.74219,0 Z"
     id="path8"
     inkscape:connector-curvature="0"
     sodipodi:nodetypes="scccccccccccccccccccccccccccccccccccccccs" />
  <path
     style="fill:#4d4d4d;fill-opacity:1;stroke:none;stroke-width:4.12109041;stroke-opacity:1"
     d="M 67.333984 94.333984 A 35.333332 35.333332 0 0 0 32 129.66602 A 35.333332 35.333332 0 0 0 48.5 159.54688 L 48.5 234.5 L 54.5 240 L 67 240 L 79 228 L 79 216.5 L 73 210 L 79 203.5 L 73 197 L 79 191 L 73 185.5 L 85.5 173 L 85.5 159.92188 A 35.333332 35.333332 0 0 0 102.66602 129.66602 A 35.333332 35.333332 0 0 0 67.333984 94.333984 z M 66.777344 109 A 9 9 0 0 1 75.777344 118 A 9 9 0 0 1 66.777344 127 A 9 9 0 0 1 57.777344 118 A 9 9 0 0 1 66.777344 109 z M 54.5 168 L 60.5 173 L 60.5 234.5 L 54.5 228 L 54.5 168 z "
     id="path831" />
</svg>
