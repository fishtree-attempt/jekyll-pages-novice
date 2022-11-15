---
title: Authoring With Markdown
teaching: 20
exercises: 15
---

## Markdown

::::::::::::::::::::::::::::::::::::::: objectives

- Create simple pages with formatted text

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: questions

- How can I write content for my webpages?
- How do I link to other pages?

::::::::::::::::::::::::::::::::::::::::::::::::::

Markdown is a language used to simplify writing HTML.
Plain text characters like # and \* are used in place of HTML tags.
These characters are then processed by Jekyll (or another script or application)
and transformed into HTML tags.
As the name Markdown suggests,
the language has been trimmed *down* to a minimum.
The most frequently used elements, like
headings,
paragraphs,
lists,
tables
and basic text formatting (i.e. bold, italic)
are part of Markdown.
Markdown's simplified syntax keeps content human-readable.  
This is one reason it is a preferred language for formatted user input on web sites like:

- [Stack Exchange](https://stackexchange.com/)
- [GitHub](https://github.com/)
- [GitLab](https://about.gitlab.com/)

## Where to Start Writing Markdown?

A lot of tools for rendering Markdown source code exist.
Rendering is the process of generating a nice view of the content
using the style information included in the source text.
Chances are high, your editor can do this.
As we are working towards authoring websites using Jekyll and GitHub pages,
we will use GitHub straight away for learning the basics of Markdown.
The GitHub project you created in the last episode contains a file `README.md`.

The image below shows the projects default view.
This view includes a rendered view of the content inside the file `README.md`.
Your project should look quite similar except for the red circle around the pencil symbol.

![](fig/group_website_repo_edit.png){alt='On the homepage of a GitHub repository, the edit button is positioned to the top right of the README preview' .image-with-shadow width="900px" }

Click on that pencil symbol to open an editing interface of your project's `README.md` file.
Once we've clicked the pencil symbol, GitHub will open that file in the editing interface.

![](fig/group_website_readme_edit.png){alt='Editing interface of the group websites README file' .image-with-shadow width="900px" }

We can change the content and have a look at the rendered view by clicking the *Preview changes* tab.

![](fig/group_website_readme_render.png){alt='Preview of the rendered content of the group websites README file' .image-with-shadow width="900px" }

Let's add `Some **bold** font` and see what happens when we preview it using the preview tab.
If you check the "Show diff" box on the upper-right hand side, GitHub will show green vertical bars visually highlighting the new content.
To save the content to the file `README.md`, scroll down a bit and search for a *Commit changes* menu
at the bottom of the page.
After having changed something, the commit menu looks like this:

![](fig/group_website_readme_commit.png){alt='Commit menu for changes done in the GitHub web interface is located at the bottom of the website' .image-with-shadow width="900px" }

:::::::::::::::::::::::::::::::::::::::::  callout

### Writing a Commit Message

A commit message is a short, descriptive, and specific comment that will help us remember later on what we did and why.
When editing in the Github interface, it will suggest a vague message about which file you've updated or added.
It is best practice to change this message to a short but more informative message about what in the file has changed.
This more descriptive message will make it much easier if future you needs to go looking through the history
for which commit made a specific change.
You can find more about writing commit message in [the Software Carpentry *Version Control with Git* lesson](https://swcarpentry.github.io/git-novice/04-changes/index.html).

::::::::::::::::::::::::::::::::::::::::::::::::::

Commit this change to the `main` branch.

## Writing Markdown

Now that we know about the editing interface and preview tab of our projects `README.md`
we can use it as a text editor and investigate selected Markdown features.

Our `README.md` already contains vanilla text and
two formatting features:

- Heading `# group-website`
- Emphasis using `**bold**`.

Let's learn some more Markdown by adding some formatting and
see what happens when we preview it using the preview tab.
Add the following to your `README.md` file.

```markdown 
# group-website
Repo for learning how to make websites with Jekyll and GitHub pages

## Learning Markdown

Vanilla text may contain *italics* and **bold words**.

This paragraph is separated from the previous one by a blank line.
Line breaks
are caused by two trailing spaces at the end of a line.

[Carpentries Webpage](https://carpentries.org/)

### Carpentries Lesson Programs:
- Software Carpentry
- Data Carpentry
- Library Carpentry
```

You can then click the preview tab again to see how the formatting renders.

![](fig/markdown_preview_formatting.png){alt='Preview of the formatting added to the README' .image-with-shadow width="900px" }

If you click the `Show diff` checkbox in the right corner, GitHub will include a preview of differences too -
the green bar indicates added lines, the red bar indicates deleted lines, and yellow - lines that have been modified.

:::::::::::::::::::::::::::::::::::::::::  callout

### Markdown Trailing Spaces Are Meaningful

In the example above there are two spaces at the end of `Line breaks  `.
These introduce what is called a **hard line break**, causing that paragraph to
continue in the next line by adding a `<br/>` to the generated HTML.

If you break the line in a markdown file but don't include the two trailing spaces
the generated HTML will continue in the same line **without** introducing a `<br/>`.
This is called a **soft line break**.

In some cases you may find that **soft line breaks** do introduce a `<br/>`.
This can happen when using different [markdown flavors](#markdown-flavours).

See for instance:

```markdown 
Soft line
break

Hard line
break
```

That produces:

![](fig/soft_hard_markdown_line_break.png){alt='Difference between soft and hard breaks' .image-with-shadow width="200px" }

::::::::::::::::::::::::::::::::::::::::::::::::::

To keep this addition to our `README.md` we need to commit these changes to save them.
Scroll down to the bottom of the page, add a commit message if you wish, and then commit to the `main` branch.

![](fig/committing_formatting_addition_to_readme.png){alt='Committing the formatting added to the README' .image-with-shadow width="800px" }

Let's do an exercise to try out writing more markdown.

::::::::::::::::::::::::::::::::::::::  challenge

### Exercise: Try Out Markdown

Use [this cheatsheet][github-flavored-markdown] to add the following to your `README.md`:

- Another second level heading
- Some text under that second level heading that includes an link and ~~strikethrough~~ text.
- A third level heading
- A numbered list
- Bonus: Add this image [https://raw.githubusercontent.com/carpentries/carpentries.org/main/images/TheCarpentries-opengraph.png](https://raw.githubusercontent.com/carpentries/carpentries.org/main/images/TheCarpentries-opengraph.png)

::::::::::::::  solution

### Example Solution

For example your markdown might look like the following:

```markdown 
## More info on the lesson
You can find this lesson [here](https://carpentries-incubator.github.io/jekyll-pages-novice/).

### Four reasons you should learn Markdown:

1. Less formatting than HTML
2. Easy to read even with formatting
3. Commonly used for websites and software development
4. We ~~don't~~ use it in The Carpentries

![Carpentries Logo](https://github.com/carpentries/carpentries.org/raw/main/images/TheCarpentries-opengraph.png)
```

![](fig/markdown_exercise.png){alt='Rendered solution to the Markdown exercise' .image-with-shadow width="800px" }

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::::  callout

### Reference-Style Links

Up to now, we have used *inline-style* links which have the URL inline with the description text, for example:

```markdown 
[Carpentries Webpage](https://carpentries.org/)
```

If you use a link more than once, consider using so called *reference-style* links instead.
Reference-style links reference the URL via a label.
The label goes into square brackets `[ ]` right after the description text of the link and
then later, usually at the bottom of the page, you can connect that label to the url it references to complete the link.
This looks like:

```markdown 
[Carpentries Webpage][carpentries]

[carpentries]: https://carpentries.org/
```

and helps to follow the [DRY principle][dry-principle], avoiding redundant specification of information.

::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::  callout

### Note about image use and attribution

When using images on your website that you don't own, it's important to reuse the
content responsibly.
This means ensuring that the image owner has given permission for the image to be reused and that the image includes appropriate attribution to the owner.
If you're unsure about the availability of an image you can always contact the owner or check if a license is provided alongside the image which may include conditions for reuse.
Anyone can re-use and edit Public Domain images so searching for images in the public domain can be a good way to find images for your website.
However, it is still good practice to give credit when possible, even for public domain images.


::::::::::::::::::::::::::::::::::::::::::::::::::

We will continue to use Markdown and learn more throughout the rest of the lesson.
Though later we will find we need HTML again for some features.

:::::::::::::::::::::::::::::::::::::::::  callout

### Markdown Cheatsheet

Markdown offers a variety of formatting features.
Have a look at this [cheatsheet][github-flavored-markdown] to get an overview or look things up.


::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::::  callout

### Markdown Flavours

The initial description of Markdown was informal and contained certain ambiguities so over the years [different Markdown
implementations and syntax variations](https://github.com/commonmark/commonmark-spec/wiki/markdown-flavors) (often referred to as "flavours")
appeared to support various syntax features and extensions. As a consequence, the syntax from one variant may not
be interpreted as expected in another - you have to be aware which one is being used by a particular platform. Here are
a few well-known variants:

- [GitHub-flavored Markdown][github-flavored-markdown] (used on this lesson and by GitHub)
- [GitLab-flavored Markdown][gitlab-flavored-markdown] (used by GitLab)
- [Kramdown][kramdown] (a fast, Ruby, open source implementation released under the MIT licence)
  

::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::  challenge

### Optional Exercise: Add Your Repository Details to CodiMD

If your instructors are using *CodiMD* (or *HackMD* or any other Markdown-based shared document platform)
to take notes during this workshop,
use Markdown syntax to add a link in that document to the repository you are using
to follow along with this lesson.
The link text should be your GitHub username, and the target your repository.
Your instructors will direct you towards the appropriate location in the
document to add your link.

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::::  callout

### More Markdown Features

Check out our [Extras page on Markdown](more_markdown/index.html) for a more comprehensive overview of
Markdown, including how to create fenced code blocks
and do syntax highlighting for various languages.


::::::::::::::::::::::::::::::::::::::::::::::::::



:::::::::::::::::::::::::::::::::::::::: keypoints

- Markdown is an relatively easy way to write formatted text

::::::::::::::::::::::::::::::::::::::::::::::::::


