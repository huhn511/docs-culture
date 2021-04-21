# Tools
This is a list of tools, which you can use to support your documentation workflows.

## GitHub Actions

GitHub actions is a nice tool for automate things.

With [this workflow](https://github.com/huhn511/git-submodules-mdbook/blob/main/.github/workflows/deploy_to_gh-pages.yml) running on GitHub Action, the documentation automaticly builds and deploy itself.

## GitHub Pages
GitHub Pages allows you to host static content, like a website - and it's free!

## mdBook

[mdBook](https://github.com/rust-lang/mdBook) is a command line tool and Rust crate to create books using Markdown
(as by the [CommonMark](https://commonmark.org/) specification) files. It's very similar to Gitbook but written in [Rust](http://www.rust-lang.org).

### Why mdBook?
- Easy to use
- Flexible and powerful
- Developed by Rust Core 🦀 ❤️ 

### Run rust Code
Click on the `play`button on the right corner of the code example.
```rust
fn main() {
    println!("Hello World, this is awesome!");
}
```

### incluce files
Perfect tool for the `DRY`principle.
With the following syntax, you can include files into your book:

```
{{#include file.rs}}
```


Example (book.toml):
```toml
{{#include ../book.toml}}
```

## mdBook multiverse
Where each project has a own documentation page build with mdbook, it's very distributed and hard to find all the pages of your project. If you want to combine multiple projects to one documentation, you also can use mdBook! 

See [this example](https://docs.einfachiota.de/) and [the code repository](https://github.com/huhn511/git-submodules-mdbook), which loads all projects with gitsubmodules. [Here is a Github Action](https://github.com/huhn511/git-submodules-mdbook/blob/main/.github/workflows/deploy_to_gh-pages.yml) for auto deployment.

If you sidebar grows, you may need to use [this css and javascript code](https://github.com/huhn511/git-submodules-mdbook/tree/main/theme/custom) to add a collapse feature to your sidebar.


This is an example, how it could work in the future. At the moment you need to add this manual, if the project strucutre changes.

**SUMMARY.md**
```
# Summary
<!-- IDEA By: https://github.com/rust-lang/mdBook/issues/1347#issuecomment-703202921 -->
- [Welcome](./docs/welcome.md)
- [Networks](./docs/networks.md)
    - {{#import "Chrysalis" "./networks/chrysalis-docs/docs/introduction/SUMMERY.md"}}
- [Libraries](./docs/README.md)
    - {{#import "client-lib" "./libraries/client-lib/docs/SUMMERY.md"}}
- [Node Software](./docs/node-software.md)
    - {{#import "HORNET" "./node-software/hornet/docs/SUMMERY.md"}}
    - {{#import "Bee" "./node-software/bee/docs/SUMMERY.md"}}
```
