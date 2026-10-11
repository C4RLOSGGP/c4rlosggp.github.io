# Your website: how to edit it

All the text lives in a few plain files. To change something, open the file on **github.com**, click the pencil ✏️ ("Edit this file"), change the text, and click **Commit changes**. The site rebuilds itself and is updated in about a minute.

| To change… | Open this file |
|---|---|
| Name, line under your name, emails, profile links, "last updated" | `_config.yml` |
| Your bio on the home page | `index.md` |
| Research topics and their figures | `research.md` |
| Papers (with their BibTeX) | `_data/papers.yml` |
| PhD thesis | `_data/thesis.yml` |
| Talks | `_data/talks.yml` |
| CV page (positions, visits, education) | `_data/cv.yml` |
| The CV PDF | upload a new `cv.pdf` (Add file → Upload files) |
| Your photo | upload a new `photo.jpg` (square) |

## Examples

**Add a talk.** At the top of `_data/talks.yml`, paste and edit:

```yaml
- date: "Nov 2026"
  title: "Title of the talk"
  where: "Theory seminar, University, City, Country"
  links:
    - name: "Slides"
      url: "https://..."
```

Leave out the `links:` lines if there are none.

**Add a paper.** At the top of the right year in `_data/papers.yml`, paste and edit:

```yaml
    - title: "Title of the paper"
      authors: "**Pier Giuseppe Catinari**, First Coauthor, and Second Coauthor"
      journal: "Phys. Rev. D 113, 012345 (2027)"
      badge: "PRD"
      arxiv: "2701.01234"
      doi: "10.1103/xxxx"
      inspire: "1234567"
      bibtex: |
        @article{Catinari:2027abc,
            ...
        }
```

The BibTeX is on the paper's INSPIRE page ("cite"). The `inspire` number is the last part of that page's address. For a preprint, leave out `journal`, `doi` and `badge`. For a new year, copy a whole `- year:` block.

**Change your bio.** Open `index.md` and edit the paragraphs below the second `---`. An empty line starts a new paragraph; a link is `[text](https://address)`; bold is `**text**`.

**Add a research topic.** In `research.md`, copy one block from its `## Title` line down to `{: .key}` and edit it. For a figure, upload the image (Add file → Upload files) and put its name in the picture line.

## Three rules that keep it working

1. In the `.yml` files, keep the spaces at the start of each line exactly as they are, and keep the quotes around text.
2. You never need to touch `_layouts/` or `style.css`; they only hold the design.
3. If a change doesn't appear after a few minutes, open the **Actions** tab of your repository. A red ✗ means a file has a typo, usually a missing quote or a wrong indentation: open the file's **History** to see your last change and fix it.

## Publish it on GitHub Pages (first time only)

1. Create a **public** repository named `<your-github-username>.github.io`.
2. Upload everything in this folder, including the `_data` and `_layouts` folders (Add file → Upload files, then drag the folder's contents in), and click **Commit changes**.
3. Open **Settings → Pages**. Under "Build and deployment", choose **Deploy from a branch**, branch `main`, folder `/ (root)`, and save.
4. After a minute or two the site is live at `https://<your-github-username>.github.io`. GitHub builds it from these files automatically; no other setup is needed.
5. Add `cv.pdf` the same way when it's ready.
