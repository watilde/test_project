# GitHub Flavored Markdown

## Basic writing and formatting syntax

<div id="article-platform-nav">

*   [mac](#platform-mac)
*   [windows](#platform-windows)
*   [linux](#platform-linux)
*   [all](#platform-all)

</div>

<div class="article-body content-body wikistyle markdown-format">

<div class="intro">

Create sophisticated formatting for your prose and code on GitHub with simple syntax.

</div>

In this article:

*   [Headings](#headings)
*   [Styling text](#styling-text)
*   [Quoting text](#quoting-text)
*   [Quoting code](#quoting-code)
*   [Links](#links)
*   [Section links](#section-links)
*   [Relative links](#relative-links)
*   [Lists](#lists)
*   [Task lists](#task-lists)
*   [Mentioning users and teams](#mentioning-users-and-teams)
*   [Referencing issues and pull requests](#referencing-issues-and-pull-requests)
*   [Using emoji](#using-emoji)
*   [Paragraphs and line breaks](#paragraphs-and-line-breaks)
*   [Ignoring Markdown formatting](#ignoring-markdown-formatting)

### [<span aria-hidden="true" class="octicon octicon-link"></span>](#headings)Headings

To create a heading, add one to six `#` symbols before your heading text. The number of `#` you use will determine the size of the heading.

    # The largest heading
    ## The second largest heading
    ###### The smallest heading

![Rendered H1, H2, and H6 headings](/assets/images/help/writing/headings-rendered.png)

### [<span aria-hidden="true" class="octicon octicon-link"></span>](#styling-text)Styling text

You can indicate emphasis with bold, italic, or strikethrough text.

<table>

<thead>

<tr>

<th>Style</th>

<th>Syntax</th>

<th>Keyboard shortcut</th>

<th>Example</th>

<th>Output</th>

</tr>

</thead>

<tbody>

<tr>

<td>Bold</td>

<td>`** **` or `__ __`</td>

<td>command/control + b</td>

<td>`**This is bold text**`</td>

<td>**This is bold text**</td>

</tr>

<tr>

<td>Italic</td>

<td>`* *` or `_ _`</td>

<td>command/control + i</td>

<td>`*This text is italicized*`</td>

<td>_This text is italicized_</td>

</tr>

<tr>

<td>Strikethrough</td>

<td>`~~ ~~`</td>

<td>`~~This was mistaken text~~`</td>

<td><del>This was mistaken text</del></td>

</tr>

<tr>

<td>Bold and italic</td>

<td>`** **` and `_ _`</td>

<td>`**This text is _extremely_ important**`</td>

<td>**This text is _extremely_ important**</td>

</tr>

</tbody>

</table>

### [<span aria-hidden="true" class="octicon octicon-link"></span>](#quoting-text)Quoting text

You can quote text with a `>`.

    In the words of Abraham Lincoln:

    > Pardon my French

![Rendered quoted text](/assets/images/help/writing/quoted-text-rendered.png)

<div class="alert tip">

**Tip:** When viewing an issue or pull request, you can automatically quote text in a reply by highlighting the text, then typing `r`. For more information, see "[Using keyboard shortcuts](/articles/using-keyboard-shortcuts/)."

</div>

### [<span aria-hidden="true" class="octicon octicon-link"></span>](#quoting-code)Quoting code

You can call out code or a command within a sentence with single backticks. The text within the backticks will not be formatted.

`Use `git status` to list all new or modified files that haven't yet been committed.`

![Rendered inline code block](/assets/images/help/writing/inline-code-rendered.png)

To format code or text into its own distinct block, use triple backticks.

<pre>Some basic Git commands are:
```
git status
git add
git commit
```
</pre>

![Rendered code block](/assets/images/help/writing/code-block-rendered.png)

For more information, see "[Creating and highlighting code blocks](/articles/creating-and-highlighting-code-blocks)."

### [<span aria-hidden="true" class="octicon octicon-link"></span>](#links)Links

You can create an inline link by wrapping link text in brackets `[ ]`, and then wrapping the URL in parentheses `( )`. You can also use the keyboard shortcut `command + k` to create a link.

`This site was built using [GitHub Pages](https://pages.github.com/).`

![Rendered link](/assets/images/help/writing/link-rendered.png)

<div class="alert tip">

**Tip:** GitHub automatically creates links when valid URLs are written in a comment. For more information, see "[Autolinked references and URLS](/articles/autolinked-references-and-urls)."

</div>

### [<span aria-hidden="true" class="octicon octicon-link"></span>](#section-links)Section links

You can link directly to a section in a rendered file by hovering over the section heading to expose the link:

![Section link within the README file for the github/scientist repository](/assets/images/help/repository/readme-links.png)

### [<span aria-hidden="true" class="octicon octicon-link"></span>](#relative-links)Relative links

You can define relative links and image paths in your rendered files to help readers navigate to other files in your repository.

A relative link is a link that is relative to the current file. For example, if you have a README file in root of your repository, and you have another file in _docs/CONTRIBUTING.md_, the relative link to _CONTRIBUTING.md_ in your README might look like this:

    [Contribution guidelines for this project](docs/CONTRIBUTING.md)

GitHub will automatically transform your relative link or image path based on whatever branch you're currently on, so that the link or path always works. You can use all relative link operands, such as `./` and `../`.

Relative links are easier for users who clone your repository. Absolute links may not work in clones of your repository - we recommend using relative links to refer to other files within your repository.

### [<span aria-hidden="true" class="octicon octicon-link"></span>](#lists)Lists

You can make a list by preceding one or more lines of text with `-` or `*`.

    - George Washington
    - John Adams
    - Thomas Jefferson

![Rendered unordered list](/assets/images/help/writing/unordered-list-rendered.png)

To order your list, precede each line with a number.

    1\. James Madison
    2\. James Monroe
    3\. John Quincy Adams

![Rendered ordered list](/assets/images/help/writing/ordered-list-rendered.png)

**Nested Lists**

You can also create nested lists.

If you're writing in the web editor on GitHub or in a text editor that uses a monospaced font, like [Atom](https://atom.io/), you can create a nested list by aligning your list visually with the list above it.

For example, you can type space characters until the list marker character (`-` or `*`) lies directly below the first character of the text in the list item above it.

    1\. First list item in first line.
       - First nested list item
         - Second nested list item

![Nested list with alignment highlighted](/assets/images/help/writing/nested-list-alignment.png)

![Nested list example 1](/assets/images/help/writing/nested-list-example-1.png)

If you're writing a comment on an issue or pull request, you can create a nested list by counting the space characters before the content of the list above your nested list. Then in your nested list, you must indent by the number of space characters before the content of the list above your nested list.

In this example, to add a nested list under the first line, you must indent a minimum of five spaces because there are five spaces (`100.`) before "First line item in first line." Because the first nested list item has seven spaces (`␣␣␣␣␣-␣`) before the nested list content `First nested list item`, the second nested list must indent seven spaces.

    100\. First list item in first line.
         - First nested list item
          - Second nested list item.

![Nested list example 2](/assets/images/help/writing/nested-list-example-2.png)

In this unordered list example, the number of spaces before "New List" is two spaces (`-`), so we indented by two spaces.

    - New List
      - New idea
      - Another new idea

In this ordered list example, the number of spaces before "Ordered list" is 6 spaces (`1000.`), so we indented by 6 spaces.

    1000\. Ordered list
          i. Nested list item
          ii. Another nested list item

For more examples, see the [GitHub Flavored Markdown Spec](https://github.github.com/gfm/#example-264).

### [<span aria-hidden="true" class="octicon octicon-link"></span>](#task-lists)Task lists

To create a task list, preface list items with `[ ]`. To mark a task as complete, use `[x]`.

    - [x] Finish my changes
    - [ ] Push my commits to GitHub
    - [ ] Open a pull request

![Rendered task list](/assets/images/help/writing/task-list-rendered.png)

If a task list item description begins with a parenthesis, you'll need to escape it with `\`:

`- [ ] \(Optional) Open a followup issue`

For more information, see "[About task lists](/articles/about-task-lists)."

### [<span aria-hidden="true" class="octicon octicon-link"></span>](#mentioning-users-and-teams)Mentioning users and teams

You can mention a user or [team](/articles/setting-up-teams/) on GitHub by typing `@` plus their username or team name to trigger a [notification](/articles/about-notifications) and bring their attention to an issue or pull request. People will also receive a notification if you edit a comment to mention their username or team name.

`@github/support What do you think about these updates?`

![Rendered @mention](/assets/images/help/writing/mention-rendered.png)

When you mention a parent team, members of its child teams also receive notifications, simplifying communication with multiple groups of people. For more information, see "[About teams](/articles/about-teams)."

Typing an `@` symbol will bring up a list of people or teams on a project. The list filters as you type, so once you find the name of the person or team you are looking for, you can use the arrow keys to select it and hit either tab or enter to complete the name. For teams, just enter the @organization/team-name and all members of that team will get subscribed to the issue.

The autocomplete results are restricted to repository collaborators and any other participants on the thread.

### [<span aria-hidden="true" class="octicon octicon-link"></span>](#referencing-issues-and-pull-requests)Referencing issues and pull requests

You can bring up a list of suggested Issues and Pull Requests within the repository by typing `#`. Type the issue or PR number or title to filter the list, then hit either tab or enter to complete the highlighted result.

For more information, see "[Autolinked references and URLs](/articles/autolinked-references-and-urls)."

### [<span aria-hidden="true" class="octicon octicon-link"></span>](#using-emoji)Using emoji

You can add emoji to your writing by typing `:EMOJICODE:`.

`@octocat :+1: This PR looks great - it's ready to merge! :shipit:`

![Rendered emoji](/assets/images/help/writing/emoji-rendered.png)

Typing `:` will bring up a list of suggested emoji. The list will filter as you type, so once you find the emoji you're looking for, press **Tab** or **Enter** to complete the highlighted result.

For a full list of available emoji and codes, check out [emoji-cheat-sheet.com](http://emoji-cheat-sheet.com).

### [<span aria-hidden="true" class="octicon octicon-link"></span>](#paragraphs-and-line-breaks)Paragraphs and line breaks

You can create a new paragraph by leaving a blank line between lines of text.

### [<span aria-hidden="true" class="octicon octicon-link"></span>](#ignoring-markdown-formatting)Ignoring Markdown formatting

You can tell GitHub to ignore (or escape) Markdown formatting by using `\` before the Markdown character.

`Let's rename \*our-new-project\* to \*our-old-project\*.`

![Rendered escaped character](/assets/images/help/writing/escaped-character-rendered.png)

For more information, see Daring Fireball's "[Markdown Syntax](https://daringfireball.net/projects/markdown/syntax#backslash)."

### [<span aria-hidden="true" class="octicon octicon-link"></span>](#further-reading)Further reading

*   "[About writing and formatting on GitHub](/articles/about-writing-and-formatting-on-github)"
*   "[Working with advanced formatting](/articles/working-with-advanced-formatting)"
*   "[Mastering Markdown](https://guides.github.com/features/mastering-markdown/)"

*   [<span class="octicon octicon-comment-discussion"></span>Contact a human](https://github.com/contact)

</div>

</div>
