---
title: Gridsome's rewriting of file links
components: false
---

It seems that when a hyperlink points to a file, Gridsome usually moves the file to the `/assets/` directory and rewrites the href to point to the file. This page documents what the rules are: what happens and when it happens.

None of the links below were touched by mdfixer, so it's all Gridsome rewriting them.


<div class="compact">

Link Type
---------

How much are the rewriting rules affected by the type of link?

Note: Here, "Rewritten" means the file is moved and the link is rewritten according to the rules [below](#file-type), except the subdirectory links don't seem to work in a VueArticle (throws an error).

### Image

| Type         | Markdown href                                                  | Result    |
|--------------|----------------------------------------------------------------|-----------|
| Absolute     | [/0tests/file-links/button.png](/0tests/file-links/button.png) | Untouched |
| Local        | [./button.png](./button.png)                                   | Rewritten |
| Traversal    | [../file-links/button.png](../file-links/button.png)           | Rewritten |
| Subdirectory | [subdir/button.png](subdir/button.png)                         | Untouched |

### PDF

| Type         | Markdown href                                                        | Result    |
|--------------|----------------------------------------------------------------------|-----------|
| Absolute     | [/0tests/file-links/freebayes.pdf](/0tests/file-links/freebayes.pdf) | Untouched |
| Local        | [./freebayes.pdf](./freebayes.pdf)                                   | Rewritten |
| Traversal    | [../file-links/freebayes.pdf](../file-links/freebayes.pdf)           | Rewritten |
| Subdirectory | [subdir/freebayes.pdf](subdir/freebayes.pdf)                         | Untouched |

</div>


File Type
---------

<div class="no-header compact">

### Images

**Article/Develop**: Placed in `/assets/static/` at the same subdirectory as they are in the build dir. Also appended with data in a query string.

**Article/Build**: Placed in `/assets/static/` directly, with a munged filename. Looks like it's appended with the key + a hash.

**VueArticle**: *The links get broken completely.* The filename is stripped entirely, even the slash preceding it. So the href for these ends up as just `/0tests/file-links`.

#### .png

<div class="float-right">

![./button.png](./button.png)

</div>

[./button.png](./button.png)

|            |         |                                                                           |
|------------|---------|---------------------------------------------------------------------------|
| Article    | Develop | `/assets/static/build/content-md/0tests/file-links/button.png?width=100&key=2ab13f8` |
| Article    | Build   | `/assets/static/button.6f4ef45.ef179782dfbee5a987fdf0dac5aa8fea.png`      |
| VueArticle | Develop | `/0tests/file-links`                                                      |
| VueArticle | Build   | `/0tests/file-links`                                                      |

#### .jpg

<div class="float-right">

![./NabbleN.jpg](./NabbleN.jpg)

</div>

[./NabbleN.jpg](./NabbleN.jpg)

|            |         |                                                                           |
|------------|---------|---------------------------------------------------------------------------|
| Article    | Develop | `/assets/static/build/content-md/0tests/file-links/NabbleN.jpg?width=50&key=04c8b57` |
| Article    | Build   | `/assets/static/NabbleN.0d639c8.5dda6c5998f3bb491c1d7a5cca692cb5.jpg`     |
| VueArticle | Develop | `/0tests/file-links`                                                      |
| VueArticle | Build   | `/0tests/file-links`                                                      |

<br />

### Recognized non-images

**Develop**: Placed in `/assets/files/` at the same subdirectory as they are in the build dir.

**Build**: Placed in `/assets/files/` directly, with a munged filename. Looks like it's appended with a hash.

#### .pdf

[./freebayes.pdf](./freebayes.pdf)

|            |         |                                                                   |
|------------|---------|-------------------------------------------------------------------|
| Article    | Develop | `/assets/files/build/content-md/0tests/file-links/freebayes.pdf`  |
| Article    | Build   | `/assets/files/freebayes.2ec07c2a686fc846a53bb5d81b9c10d9.pdf`    |
| VueArticle | Develop | `/assets/files/build/content-vue/0tests/file-links/freebayes.pdf` |
| VueArticle | Build   | `/assets/files/freebayes.2ec07c2a686fc846a53bb5d81b9c10d9.pdf`    |

#### .sh

[./cp_img.sh](./cp_img.sh)

|            |         |                                                               |
|------------|---------|---------------------------------------------------------------|
| Article    | Develop | `/assets/files/build/content-md/0tests/file-links/cp_img.sh`  |
| Article    | Build   | `/assets/files/cp_img.a4b09fee1d875e621ec3e164e7105337.sh`    |
| VueArticle | Develop | `/assets/files/build/content-vue/0tests/file-links/cp_img.sh` |
| VueArticle | Build   | `/assets/files/cp_img.a4b09fee1d875e621ec3e164e7105337.sh`    |

#### .txt

[./tables.txt](./tables.txt)

|            |         |                                                                |
|------------|---------|----------------------------------------------------------------|
| Article    | Develop | `/assets/files/build/content-md/0tests/file-links/tables.txt`  |
| Article    | Build   | `/assets/files/tables.febc8aa9066f924523c28deacadb1857.txt`    |
| VueArticle | Develop | `/assets/files/build/content-vue/0tests/file-links/tables.txt` |
| VueArticle | Build   | `/assets/files/tables.febc8aa9066f924523c28deacadb1857.txt`    |

<br />

### Unrecognized extensions

**Article**: Ignored - the file and href is left untouched.

**VueArticle**: Rewritten just like a [recognized non-image](#recognized-non-images) during a build.

#### .xcf

[./PoweredByGalaxy.xcf](./PoweredByGalaxy.xcf)

|            |         |                                                                         |
|------------|---------|-------------------------------------------------------------------------|
| Article    | Develop | `./PoweredByGalaxy.xcf`                                                 |
| Article    | Build   | `./PoweredByGalaxy.xcf`                                                 |
| VueArticle | Develop | `/assets/files/build/content-vue/0tests/file-links/PoweredByGalaxy.xcf` |
| VueArticle | Build   | `/assets/files/PoweredByGalaxy.d7536122376b24ddc66657f05d6c7798.xcf`    |

#### .plist

[./data.plist](./data.plist)

|            |         |                                                                |
|------------|---------|----------------------------------------------------------------|
| Article    | Develop | `./data.plist`                                                 |
| Article    | Build   | `./data.plist`                                                 |
| VueArticle | Develop | `/assets/files/build/content-vue/0tests/file-links/data.plist` |
| VueArticle | Build   | `/assets/files/data.59484fc68c1c0040f5fd420cae6c1861.plist`    |

</div>
