# Maria Carranza — professional bio site

A one-page professional bio and virtual resume for **Maria Carranza, MT, SH(ASCP)**,
Clinical Laboratory Consultant in St. Petersburg, Florida.

**Live at:** <https://mariacarranza394.github.io/>

---

## What's in here

| File or folder | What it is |
|---|---|
| `index.html` | The whole website — all the words, the layout, the colours |
| `images/` | The photos the website shows, in the modern AVIF format |
| `images/fallback/` | The same photos as JPEGs, for older web browsers |
| `images/originals/` | Your full-size original photos, kept safe. The website doesn't use these |
| `.nojekyll` | A technical marker that tells GitHub to publish the folder exactly as-is |

## Changing the words

Open `index.html`. It looks like a lot, but the actual text is near the bottom half —
look for the sentences you recognise and type over them. Everything between angle
brackets like `<p>` is formatting; leave those alone and only change the plain words
between them.

## Changing your phone number

In `index.html`, search for `813`. You'll find it twice and **both** need changing:

```html
<a class="contact-phone" href="tel:+18135631923">(813) 563-1923</a>
```

- The one after `tel:` is what your phone dials. It has no brackets or dashes, and starts
  with `+1`.
- The one between `>` and `<` is what visitors see, so it can be formatted however you like.

## Changing a photo

1. Put your new photo in `images/originals/`.
2. Make the two web-sized versions:
   ```
   magick images/originals/NEW-PHOTO.jpg -auto-orient -strip -resize "900x900>" -quality 55 images/NEW-PHOTO.avif
   magick images/originals/NEW-PHOTO.jpg -auto-orient -strip -resize "900x900>" -quality 82 images/fallback/NEW-PHOTO.jpg
   ```
3. In `index.html`, find the old photo's name and swap in the new one.

## Publishing your changes

From this folder:

```
git add -A
git commit -m "describe what you changed"
git push
```

The live site updates itself about a minute later.

## Why the photos look the way they do

The original photos totalled about 3.9 MB, which is slow to load on a phone. They're now
about 320 KB in total — roughly 92% smaller — with no visible difference at the sizes
they're displayed. Your untouched originals are still in `images/originals/`.
