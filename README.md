# Accessible-Lanyon

Accessible-Lanyon is an opinionated, accessible theme based on [Neo-Lanyon][1]
and [Lanyon](https://lanyon.getpoole.com). Lanyon is an unassuming
[Jekyll](https://jekyllrb.com) theme that places content first by tucking away
navigation in a hidden drawer. It's based on [Poole](https://getpoole.com), the
Jekyll butler. Neo-Lanyon by @zwotzie. Lanyon and Poole are by @mdo.

## Contents

- [Accessible-Lanyon](#accessible-lanyon)
  - [Contents](#contents)
  - [Differences](#differences)
  - [Usage](#usage)
    - [1. Install Dependencies](#1-install-dependencies)
      - [Windows Installation](#windows-installation)
    - [2. Install Jekyll and Theme](#2-install-jekyll-and-theme)
    - [3. Running Locally](#3-running-locally)
  - [Options](#options)
    - [Sidebar Menu](#sidebar-menu)
    - [Sidebar Open On Page Load](#sidebar-open-on-page-load)
  - [Development](#development)
  - [Author](#author)
  - [License](#license)

## Differences

There are differences between this theme and the original Lanyon theme:

- Opinionated: This theme is created for a single purpose to serve a single
  person, but that does not mean others can modify this theme.
- Mostly Accessible: This site tries to follow WCAG 2.1, but the needs be more
  testing.
- No JavaScript: All JavaScript required code has been removed.
- Latent Semantic Indexer: Provides better related post creation.
- MathML Support: Uses KaTeX to add math support.
- Self-Hosted: This theme contains all thee assets it needs without requiring
  the use of other cdns like Google Fonts or Font Awesome.
- Dark Mode: This theme uses Poole as the base which includes a dark theme.
- More Plugins: Additional plugins are added to make blogging easier.
- Github Actions: Includes an example workflow to deploy site to Github Pages.

## Usage

### 1. Install Dependencies

To start using Accessible-Lanyon and create a blog with Jekyll, you will need
to install:

- Ruby: The programming language that Jekyll was created on.
- Bundler: A dependency manager for Ruby gems.
- GCC or Clang: Required to compile gems and plugins with C-extensions.
- Node.js: Required to render math using KaTeX and minify the site.
- ImageMagick: Required to generate favicon.
- LAPACKE and OpenBLAS: Required to speed up LSI.

To install these dependencies on Fedora:

```bash
sudo dnf install ruby ruby-devel rubygem-bundler @c-development nodejs ImageMagick lapack-devel openblas-devel
```

On Arch:

```bash
sudo pacman -S ruby ruby-bundler base-devel nodejs npm imagemagick blas-openblas
```

For other distributions please consult your package manager and distribution
documentations.

#### Windows Installation

Ruby+Devkit from RubyInstaller is sufficient to provide a C development
environment with GCC via MSYS2. To install it:

```powershell
# Replace Major and Minor with Ruby version
# Bundler is included in RubyInstaller
winget install RubyInstallerTeam.RubyWithDevKit.Major.Minor
```

But it's recommended to install Ruby and MSYS2 separably if you are using
different ruby versions, as different versions of Ruby can use the same MSYS2
environment.

```powershell
# Installing MSYS2 and Ruby, Replace Major and Minor with Ruby version
winget install MSYS2.MSYS2 RubyInstallerTeam.Ruby.Major.Minor
# Tell Ruby to use the local installed MSYS2 setup development environment
ridk install
# Enable the MSYS2 environment in current shell
ridk enable
```

Now you can install rest of the dependencies.

```powershell
# In the shell with MSYS2 environment enabled
winget install OpenJS.NodeJS.LTS ImageMagick.ImageMagick
# Installing LAPACKE and OpenBLAS in MSYS2
pacman -S mingw-w64-ucrt-x86_64-lapacke mingw-w64-ucrt-x86_64-openblas
```

### 2. Install Jekyll and Theme

Once you have all dependencies installed, download Accessible-Lanyon, extract
and open a shell in the extracted folder. Now install Jekyll and required
plugins using Bundler:

```bash
bundler install
```

### 3. Running Locally

To see the site running with Accessible-Lanyon applied, run:

```bash
bundler exec jekyll serve
```

Now you can modify the theme and site to your liking, be sure to modify
`_config.yml` before hosting your site. If you host your code on Github, you can
use Github Pages to host your site using the provide workflow.

## Options

Accessible-Lanyon only has two customizable options from the original, but you
can readd them back if you wish.

### Sidebar Menu

Create a list of nav links in the sidebar by assigning each Jekyll page the
correct layout in the page's [front-matter][2].

```yaml
---
layout: page
title: About
---
```

**Why require a specific layout?** Jekyll will return *all* pages and with an
alphabetical sort order. To ensure the first link is *Home*, we exclude the
`pages/index.html` page from this list by specifying the `default` layout.

### Sidebar Open On Page Load

Show an open sidebar on page load by modifying the `<input>` tag within the
`sidebar.html` layout to add the `checked` boolean attribute:

```html
<input type="checkbox" class="sidebar-checkbox" id="sidebar-checkbox" checked>
```

Using Liquid you can also conditionally show the sidebar open on a per-page
basis. For example, here's how you could have it open on the homepage only:

```html
<input type="checkbox" class="sidebar-checkbox" id="sidebar-checkbox"
  {% if page.title =="Home" %}checked{% endif %}>
```

## Development

Accessible-Lanyon has two branches, but only one is used for active development.

- `main` for development and releases.
  **All pull requests should be to submitted against `main`.**
- `gh-pages` for project site, a github action is ran to build the site.
  **Please avoid using this branch as is a difference between the branches.**

## Author

- Mark Otto @mdo
- Nichts Besonderes @zwotzie
- Samuel Wu @TwoPizza9621536

## License

The theme is available as open source under the terms of the
[MIT License](LICENSE).

This project uses some content from Mozilla Developer Network which are licensed
under the Mozilla Public License 2.0. Below is a list of those files:

- `_layouts/mozilla.html`
- `_sass/mozilla.scss`

Check other HTML and CSS files for additional content that comes from other
websites:

- [botleg](https://botleg.com/stories/line-numbers-in-jekyll-code-blocks/)
- [m-cat](https://www.bytedude.com/jekyll-syntax-highlighting-and-line-numbers)
- [jreel](https://jreel.github.io/social-media-icons-on-jekyll/)

Some icons are from Font Awesome, they are located in `assets/svg` and are under
the CC-BY 4.0 License.

Fonts in `assets/fonts` are under the Open Font License 1.1 and KaTeX fonts in
`assets/fonts/KaTeX` are under the MIT License.

Classifier-reborn is under the LGPL 2.1 or later.

These licenses can be found in the `LICENSES` folder.

[1]: https://github.com/zwotzie/neo-lanyon
[2]: https://jekyllrb.com/docs/frontmatter/
