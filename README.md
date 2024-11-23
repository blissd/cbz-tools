# CBZ Tools

Command-line tools for processing comic archive (CBZ) files.

* _cbz-repack_ Convert file formats and resize images.
* _pdf-to-cbz_ Convert PDF documents to CBZ archives. Useful when [Humble Bundles](https://www.humblebundle.com/) of comics only come in a PDF format.

## cbz-repack

Reformat and resize images in CBZ files. Converted CBZ files will have the same name as the source CBZ file but with a `-{format}` in their name. Convert all pages to avif format:

```shell
cbz-repack my-comic.cbz
```

Convert to avif and also scale all pages to be 75% of the original size:

```shell
cbz-repack -r 75 my-comic.cbz
```

Convert to JXL (note: scaling with `-r` not support for JXL right now):

```shell
cbz-repack -f jxl my-comic.cbz
```

## pdf-to-cbz

Extracts pages from a PDF document and converts those pages to JPEG images and then packages the pages in a ZIP archives with a `.cbz` suffix.

Example usage:

```shell
pdf-to-cbz my-comic.pdf
```

Encode to a different file format (jxl, webp, and avif supported):

```shell
pdf-to-cbz -f jxl my-comic.pdf
```

Encode with a different resolution (default 400 dpi):

```shell
pdf-to-cbz -d 300 my-comic.pdf
```

By default the CBZ file will be produced next to the PDF document but with a `.cbz` suffix Override the output file path:

```shell
pdf-to-cbz -o some/other/path.cbz my-comic.pdf
```
