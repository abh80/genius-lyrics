!> Fetching only One Result for fast response.

### Based on `.then`
```js
const Genius = new (require("genius-lyrics"))("your-token-here");

Genius.tracks.search("faded", { limit: 1 })
.then(results => {
    const song = results[0];
    song.lyrics()
    .then(lyrics => {
        console.log(lyrics);
    })
})
.catch(err => console.error(err));
```

### Based on `Async/Await`
```js
const Genius = new (require("genius-lyrics"))("your-token-here");

async function lyrics() {
     try {
          const songs = await Genius.tracks.search("faded", { limit: 1 }); //even tho limit is 1, it will be an array
          const lyrics = await songs[0].lyrics();
          console.log(lyrics);
     } catch(e) {
          console.log(e);
     }
}

lyrics();
```
