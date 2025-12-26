# Grande Theme! ☕️

A [JSON Resume](https://jsonresume.org/) theme based on [jsonresume-theme-macchiato](https://github.com/biosan/jsonresume-theme-macchiato) with improved visual styles for better readability.

## Changes from Original Macchiato Theme

### New Features

- **Certifications Section** - Added support for the `certificates` field from JSON Resume schema, displayed as "Certifications"
- **Notable Projects Section** - Full-width layout for better visibility of project details

### Visual Improvements

- Increased font sizes for better readability
  - Paragraphs and list items: 11px → 14px
  - Headings (h3-h6) proportionally increased
- Maintained proper typographic hierarchy
- Enhanced visual comfort for extended reading
- Full-width layout for Projects, Certifications, and Education sections to prevent content cutoff


## Usage

> **Note:** The official `resume-cli` is no longer actively maintained. We recommend using [resumed](https://github.com/rbardini/resumed) instead, which is a modern, actively maintained alternative.

### Using resumed (Recommended)

1. Create a new project directory and initialize it
  ```bash
  mkdir my-resume
  cd my-resume
  npm init -y
  ```

2. Install [resumed](https://github.com/rbardini/resumed) and the theme
  ```bash
  npm install resumed jsonresume-theme-grande
  ```

3. Create your `resume.json` file in the project directory (see [JSON Resume Schema](https://jsonresume.org/schema/))

4. Use resumed to build your resume
  ```bash
  npx resumed render --theme grande
  ```

### Alternative: Using the legacy resume-cli

If you prefer to use the legacy [JSON Resume CLI](https://jsonresume.org/):

```
npm install -g resume-cli
npm install -g jsonresume-theme-grande
resume export resume.html --theme grande
```

### PDF output

Probably you want a PDF version of your resume...

JSONResume CLI should be able to make a PDF out of your JSON but I always struggled to get it to work,
so I switched to a more direct and effective approach.

I use Puppeteer-CLI to make a PDF from my HTML resume.

```
npm install -g puppeteer-cli
puppeteer --wait-until networkidle0 --margin-top 0 --margin-right 0 --margin-bottom 0 --margin-left 0 --format A4 print resume.html resume.pdf
```

Obviously you could write a very simple Node script to use the real Puppeteer and the `render` function to make a PDF without first exporting the HTML version.


## License

Available under the [MIT license](http://mths.be/mit).

