---
layout: docs
comments_issue: 25
edit_issue: 26
title: Writing Entries
draft: true
---

To write entries all you need is a GitHub account.
Entries are written in a basic text file with two sections. The first, the **front matter** is between two lines of three consecutive dashes `---` represents datasets in simple `key: value` pairs written in in _YAML_. The second part is the **markdown text**  written in _Markdown Syntax_. An entry can have several components rendered from the data in the front matter and the text in markdown. The elements of an entry page are as follows (hover over the image to remove labels):

{% include other/reveal-image.html visible="/docs/tutorials/AvocadoLab/EntryExampleAnatomy.png" hidden="/docs/tutorials/AvocadoLab/EntryExample.png" %}

It is important to note that the rest of the elements come from the _front matter_.

## Text
The **text** comes directly and only from the second part of the file, the _markdown text_. Markdown is pretty simple, see [this guide](https://learnxinyminutes.com/docs/markdown/) from _Learn X in Y Minutes_. Below is a small snippet:

```markdown
# Heading one
Writing with _italics_ and with **bold** syntax. Create links by enclosing the word in [brackets](http://linksomewhere.com) followed by the link enclosed in parenthesis. Write in `code`.

## Heading two
Write a list:
  - one item
  - two item
    - subitem

```

### Adding images
In case you need to format an image, table, or something else, you can add add `{: .class .another}` after the element. We use the Semantic-UI framework, e.g. for [images](https://semantic-ui.com/elements/image.html):


![](/docs/tutorials/AvocadoLab/image-example.jpg){: .ui .image .fluid}
`![](/docs/tutorials/AvocadoLab/image-example.jpg){: .ui .fluid .image}`


![](/docs/tutorials/AvocadoLab/image-example.jpg){: .ui .small .centered .image}
`![](/docs/tutorials/AvocadoLab/image-example.jpg){: .ui .small .centered .image}`


#### Images with Copyright
{% include cc-image.html position="right floated" size="medium" sourceURL="https://c2.staticflickr.com/8/7275/7770621142_a9d945f825_b.jpg" license="by-nc-nd" workTitle="Up Close and Personal" attributeURL="https://flic.kr/p/cQEsWA" attributeTo="Servando Miramontes" %}

By default, all Content Contributed to the Library is dedicated to the public domain (see our [Terms of Use][terms-of-use]). Contributions that are shared/uploaded should explicitly note their copyright terms if the author(s) do not waive authorship as per our [Contributor Terms][contributor-terms]. Works licensed under the Creative Commons can be included in Contributions as long as the terms of use are met, which in all CC instances it includes attribution.  The `position=` and `size=` properties are CSS classes, use Semantic-UI. You can omit the `workTitle=` property but the rest should be filled.


For `position=` you can specify: _centered_, _fluid_, or _floated right_, or _floated left_).

For `size=` specify: _mini_ (35px), _tiny_ (80px), _small_ (150px), _medium_ (300px), _large_ (450px), _big_ (600px), _huge_ (800px), or _massive_ (960px).




```
{%raw%} {% include cc-image.html position="right floated" size="medium" sourceURL="https://c2.staticflickr.com/8/7275/7770621142_a9d945f825_b.jpg" license="by-nc-nd" workTitle="Up Close and Personal" attributeURL="https://flic.kr/p/cQEsWA" attributeTo="Servando Miramontes" %}{%endraw%}
```







## Title and subtitle
The **title:** should be the name of your entry. It should be short and easy if possible. The **subtitle:** is optional and is a short description of the entry.

## Menu
The menu is set automatically. The only way to add additional items is to edit other entry pages and specify `host-org:` exactly as the  `title:` of this entry. For example, if 'Avocado Lab' wants to list _Projects_, an entry for the Project _Guacamole_ should be created and specify `host-org: Avocado Lab`.

## Header and logo
To display a **header** image at the top of your entry, you can either save an image in the folder of your initiative with the name 'header' in `.png` or `.jpg` format, or add the 'header' key in the front matter with a link to the image, e.g. `header: http://linktoheaderimage.jpg`

The same goes for the **logo**, which is displayed inside the infobox and when clicked links to the entry's website.

You can also add a **thumbnail** image to the folder. Although it is not displayed in the entry, it is meant to be showed in the List of Entries page. The page grabs images in this order: _thumbnail_, _logo_, _header_, a dummy image.

## Infobox
The _infobox_ is the box on the left hand side of the entry. It can show several data, the following table shows the key, description, and an example in order of how they would appear. The green rows represent mandatory keys, while the brown rows are mandatory for some collections.

{% include other/infobox-keys.html %}

## Social Icons
Links to any kind of website, social media, or contact information can be presented here.

## Tags
You are probably familiar with _tags_, they are used as keywords to easily categorize entries. A good rule of thumb is to have maximum 10 tags. In addition, it is good practice to search the current tags used by other entries and reuse them if applicable.

## Promotion boxes
_Promotions_ are boxed items on the left hand side of the entry. Here you can promote whatever you want, you meetups, classes, to join the project, etc. You can add as many as you want, but a good rule of thumb is no more than 3.

To add a promotion you must write in the front matter:

```yaml
promotions:
  - text: #write here your promotion
    button: #text in the button
    URL: #link for the button
    image: #path to the image in the background
  - text: # second promotion starts with another dash
    button:
    URL:
    color: #specify a background color instead of an image. wrap the color in '', e.g. '#43BB7A'
```

The rendered box will first try to grab the `promotions.image` key, then the `promotions.color` key. If these are not specified the background color will be grey.

{% include messages/plus.html title="Get your promotion in the landing page!" text="Entries can have their promotions featured in the landing page carousel if they contain a background image, or if the entry has a header image" %}


## Comments
**Comments** on the entry are rendered from comments of a GitHub Issue. I
