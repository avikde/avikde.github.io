
## Installation

- Use package manager to install Hugo. For example,
```sh
winget install Hugo.Hugo.Extended
```

In the root directory, 
```sh
hugo new site site --force
cd site
git submodule add https://github.com/kaiiiz/hugo-theme-monochrome.git themes/hugo-theme-monochrome
```

## Build and Deploy

From the `site/` directory:

- Build site for testing
```sh
hugo serve -D
```

- Build for production
```sh
hugo --environment production --minify
```
