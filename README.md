#### This is an updated version of [save-pixels](https://github.com/scijs/save-pixels) which patches the [CVE-2020-8175](https://github.com/advisories/GHSA-w7q9-p3jq-fmhm) security issue. At the time of creation, every file is the same as the ones from the original repository, excluding the package.json.

# save-pixels-updated
##### The following is from the [save-pixels](https://github.com/scijs/save-pixels) GitHub page. As mentioned before, this repository has no breaking changes and is nearly the exact same as the original repository.
Saves an ndarray to an image.

Example
=======
```javascript
var zeros = require("zeros")
var savePixels = require("save-pixels-updated")

//Create an image
var x = zeros([32, 32])
x.set(16, 16, 255)

//Save to a file
savePixels(x, "png").pipe(process.stdout)
```

This writes the following image to stdout:

<img src=https://raw.github.com/mikolalysenko/save-pixels/master/example/example.png>

Install
=======

    npm install save-pixels-updated

### `require("save-pixels-updated")(array, type[, options])`
Saves an ndarray as an image with the given format

* `array` is an `ndarray` of pixels.  Assumes that shape is `[width, height, channels]`
* `type` is the type of the image to save.  Currently supported formats:

  + `"jpeg"`, `"jpg"` - Joint Photographic Experts Group format
  + `"gif"` - Graphics Interchange Format
  + `"png"` - Portable Network Graphics format
  + `"canvas"` - A canvas element

* `options` is an object that alters saving behavior

  + `quality` is the `Number` to use for saved image quality

    + This can only be used with a `"jpeg"` image
    + It range between 1 (low quality) and 100 (high quality) inclusively

**Returns** A stream that you can pipe to serialize the result, or a canvas element if the `type` is `"canvas"`.

Credits
=======
Original code from [save-pixels](https://github.com/scijs/save-pixels), updated by [sysollie](https://github.com/sysollie) to fix the [CVE-2020-8175](https://github.com/advisories/GHSA-w7q9-p3jq-fmhm) security issue. Code used and relicensed under and in accordance with the MIT license ([original](https://github.com/scijs/save-pixels/blob/master/LICENSE) | [new](https://github.com/sysollie/save-pixels-updated/blob/main/LICENSE)).
