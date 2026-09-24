# Responsive Website Layout

A 12-card food menu grid that shows three, two or one columns depending on the screen width, built with CSS Grid and two media queries.

**Live site:** <https://shayan-abrar.github.io/Responsive-Website-Layout/>

<p align="center">
  <a href="screenshots/preview.jpg"><img src="screenshots/preview.jpg" width="800" alt="The same menu page at three widths: three columns on desktop, two columns on a tablet and one column on a phone"></a>
</p>

Most page layouts need to change their number of columns as the screen gets narrower. This page shows the smallest version of that pattern: one CSS Grid container whose column count is changed by two media queries, with no framework and no JavaScript. It works as a quick reference for breakpoint and grid syntax.

## Quick Start

```bash
git clone https://github.com/SHAYAN-ABRAR/Responsive-Website-Layout.git
cd Responsive-Website-Layout
python3 -m http.server 8000
```

Open <http://localhost:8000> and make the browser window narrower, or use your browser's responsive design mode, to watch the columns change. On Windows, use `python` instead of `python3`. Opening `index.html` directly in a browser works too, and nothing is loaded from the internet.

## Features

- **Twelve menu cards:** each has a photo, a name, a price ($100 to $1,200) and a short description inside a red rounded border.
- **Three layouts:**

  | Screen width | Columns |
  | --- | --- |
  | 993px and wider | 3 |
  | 576px to 992px | 2 |
  | 575px and narrower | 1 |

- **Fluid images:** `width: 100%` makes each photo scale with its card.
- **One file:** all the styles are in a `<style>` block in `index.html`.

## Usage Example

The layout comes down to these rules in `index.html`. To change a breakpoint, edit the widths in the media queries. To change the desktop column count, edit `repeat(3,1fr)`.

```css
.container{
    display: grid;
    grid-template-columns: repeat(3,1fr);
    gap: 20px;
}
@media screen and (max-width:576px){
    .container{
        grid-template-columns: repeat(1,1fr);
    }
}
@media screen and (min-width:576px) and (max-width:992px){
    .container{
        grid-template-columns: repeat(2,1fr);
    }
}
```

## Limitations

- At exactly 576px wide, both media queries match. The second one comes later in the file, so that width shows two columns, not one.
- All 12 cards use the same photo and placeholder text, and the page has no header, navigation or footer.
- No font is set, so the text uses the browser's default font, and the images have empty alt text.

## Tech Stack

- HTML5
- CSS3: Grid and media queries, inline in `index.html`
- Hosted on GitHub Pages

## Contributing

Suggestions and bug reports are welcome. Please [open an issue](https://github.com/SHAYAN-ABRAR/Responsive-Website-Layout/issues). Please read the license note below before reusing any code or images.

## License

This repository doesn't have a license yet, so it doesn't grant anyone permission to reuse or redistribute its code or images. Please ask before reusing any part of it.

---

Built by **Shayan Abrar** · [GitHub](https://github.com/SHAYAN-ABRAR) · [LinkedIn](https://www.linkedin.com/in/shayan-abrar/)
