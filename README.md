# bettah-media

Makes programmatically transcoding media easier

`npm install --save bettah-media`

```js
const Bettah = require('bettah-media');
const fs = require('fs');

const bettah = new Bettah();

const transcoder = bettah.transcode({
  type: 'ffmpeg',
  media: './test/test.mp3',
  ffmpegArguments: [
    '-analyzeduration', '0',
    '-loglevel', '0',
    '-f', 's16le',
    '-ar', '48000',
    '-ac', '2',
  ],
});

transcoder.output.pipe(fs.createWriteStream('./test/test.pcm'));
```
