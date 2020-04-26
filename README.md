# BasicServe

A basic static file http server for development.

No frills, no dependencies, no hassle.

## Usage

```sh
> basicServe -h

Usage: basicServe [options] <directory_to_serve>

Options:

  -h, --help    output usage information
  -p, --port    listen port (default: 8080)
```

## Output

First, logs served directory and server URL.

Then, logs one line per request, with request URL, served file, and content type (if recognized).

Example:

```sh
> basicServe public -p 12345
serving public at http://localhost:12345
/ -> public/index.html (text/html)
/bundle.js -> public/bundle.js (text/javascript)
/favicon.svg -> public/favicon.svg (image/svg+xml)
```

## Path Mappings

The following request paths are mapped:

- `/` -> `/index.html`

## Status Codes

One of two status codes will be returned,
depending on whether a file was found at the requested path:

- `200 OK`
- `404 Not Found`

## Content Types

The extension of the file served is used to determine the content type.

The following extensions are recognized:

- `.apng` -> `image/apng`
- `.bmp` -> `image/bmp`
- `.css` -> `text/css`
- `.cur` -> `image/x-icon`
- `.html` -> `text/html`
- `.gif` -> `image/gif`
- `.gzip` -> `application/gzip`
- `.ico` -> `image/x-icon`
- `.jfif` -> `image/jpeg`
- `.jpeg` -> `image/jpeg`
- `.jpg` -> `image/jpeg`
- `.js` -> `text/javascript`
- `.json` -> `application/json`
- `.otf` -> `font/otf`
- `.pdf` -> `application/pdf`
- `.pjp` -> `image/jpeg`
- `.pjpeg` -> `image/jpeg`
- `.png` -> `image/png`
- `.sfnt` -> `font/sfnt`
- `.svg` -> `image/svg+xml`
- `.tif` -> `image/tiff`
- `.tiff` -> `image/tiff`
- `.ttf` -> `font/ttf`
- `.txt` -> `text/plain`
- `.webp` -> `image/webp`
- `.woff` -> `font/woff`
- `.woff2` -> `font/woff2`
- `.xml` -> `application/xml`
- `.zip` -> `application/zip`

Files with unrecognized extensions will be served without a content type.
