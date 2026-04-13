---
{"dg-publish":true,"permalink":"/dendron-is-an-open-source-local-first-markdown-based-note-taking-tool/","dg-note-properties":{}}
---

> Minha opinião sobre o Dendron: funciona, é bom, se você pode usar o VSCode para desktop. Eu não posso: não instala no Fórum e é incompatível com apps expansores de textos (snippets) (a versão para Windows também era). A importação do Obsidian é precária, salva-se o texto mas perdem-se os links (só rodam para files com nomes sem acentos) e as tags (tem de ser recriadas manualmente)
> 
> q.v. [[programas que andei testando para substituir o evernote e o sublimeless\|programas que andei testando para substituir o evernote e o sublimeless]]

Dendron is an **open-source, local-first, markdown-based, note-taking tool**. It's a personal knowledge management solution (PKM) built specifically for developers and integrates natively with IDEs like [VSCode](https://code.visualstudio.com/ "https://code.visualstudio.com/").

## Why

Most PKM tools help you create notes but slam into a wall retrieving them once your knowledge base reaches a certain size threshold. That threshold varies with the tool, but virtually everything stops working past 10k notes unless the user was extremely diligent about organizing their knowledge. Past this threshold, entropy wins and every query becomes a keyword search and scrolling through pages of results.

> Dendron's mission is to help **humans organize, find, and work with any amount of knowledge**.

It not only helps you create notes but also retrieve them - retrieval works as well with ten notes as it does with ten thousand.

## How

Dendron builds on top of the past five decades of programming languages and developer tooling. We apply the key lessons from software to the management of general knowledge. We make managing general knowledge like managing code and your PKM like an IDE.

## Design Principles

### Developer Centric

Dendron aims to create a world class developer experience for managing knowledge.

Our goal is to provide a tool with the efficiency of Vim, the extensibility of Emacs, and the approachability of VS Code.

What this means:

- dendron features are text centric and composables
    
- dendron provides the lowest friction interface for working with your knowledge base
    
- dendron optimizes for efficiency, speed, and keyboard focused ux
    
- dendron comes with sane defaults and the ability to customize to your liking
    
- dendron can be extended along any dimension
    

### Gradual Structure

Dendron extends markdown with structural primitives to make it easier to manage at scale and tooling on top to work with this structure.

Different knowledge bases require different levels of structure - a PKM used for keeping daily journals is different than a company wide knowledge base used by thousands of developers.

Dendron works with any level of structure, meaning you can take free form notes when starting out and gradually layer on more structure as your knowledge base grows more.

### Flexible and Consistent

Dendron is both flexible and consistent. It provides a consistent structure for all your notes and gives you the flexibility to change that structure.

In Dendron, you can refactor notes and Dendron will make sure that your PKM is consistent throughout. This means that you have the best of both worlds: a basic structure for the organization but the flexibility to change it.

## Features

Dendron has hundreds of features. The following is a list of highlights.

### It's just Plaintext

- manage using git
    
- use git blame to see individual edits
    
- edit in anything that works on text files (eg. Vim)
    

![](en-cache://tokenKey%3D%22AuthToken%3AUser%3A124106736%22+0870c6be-053a-c0e6-d514-7ba6ce1b6731+66fb0cad32b3d8687f602901ce7cba54+https%3A%2F%2Fpublic.www.evernote.com%2Fresources%2Fs672%2F5ec5ce73-1370-bad7-6392-559be1684de1)

### Markdown and More

- create diagrams using mermaid
    
- write math using katex
    
- embed notes (and parts of notes) in multiple places using note references
    

![](en-cache://tokenKey%3D%22AuthToken%3AUser%3A124106736%22+0870c6be-053a-c0e6-d514-7ba6ce1b6731+d3d0da05f81e81c9ff565f33725a83e8+https%3A%2F%2Fpublic.www.evernote.com%2Fresources%2Fs672%2F2329fdf3-6b54-5d12-71e5-1277aefe605c)

### Lookup

- one unified way to find and create notes
    
- quickly traverse and create new hierarchies
    

![](en-cache://tokenKey%3D%22AuthToken%3AUser%3A124106736%22+0870c6be-053a-c0e6-d514-7ba6ce1b6731+0549541d64f28aa42f12c3858fa1e6b6+https%3A%2F%2Fpublic.www.evernote.com%2Fresources%2Fs672%2F60b15951-e5b0-8a50-bb73-51db7a2adf1a)

### Schema

- ensure consistency for your knowledge base
    
- get autocomplete hints when creating new notes
    
- automatically apply common templates to notes on creation
    

![](en-cache://tokenKey%3D%22AuthToken%3AUser%3A124106736%22+0870c6be-053a-c0e6-d514-7ba6ce1b6731+b606dc283b29f39cfb7470899e86f662+https%3A%2F%2Fpublic.www.evernote.com%2Fresources%2Fs672%2Fe3e69bb3-fd8a-27db-a2f4-cc565333a73c)

### Navigation

- explore relationships using backlinks
    
- navigate to notes, headers and arbitrary blocks
    
- visualize your knowledge base using the graph view
    

![](en-cache://tokenKey%3D%22AuthToken%3AUser%3A124106736%22+0870c6be-053a-c0e6-d514-7ba6ce1b6731+2cdf3b8547a29c14593b0be47f2f4df3+https%3A%2F%2Fpublic.www.evernote.com%2Fresources%2Fs672%2Fdfa7ec02-bbe2-06c9-2cc7-23c81cea318a)

### Refactor

- restructure your knowledge base without breaking links
    
- rename a single note or refactor using arbitrary regex
    
- rename and move individual sections within notes
    

![](en-cache://tokenKey%3D%22AuthToken%3AUser%3A124106736%22+0870c6be-053a-c0e6-d514-7ba6ce1b6731+8f587d5d70b6081568f0925e9580f7ac+https%3A%2F%2Fpublic.www.evernote.com%2Fresources%2Fs672%2F70499160-312e-0be8-2d65-fcd5c4f73ccd)

### Vaults

- mix and match knowledge using vaults, a git backed folder for your notes
    
- use vaults to separate concerns, like personal notes and work notes
    
- publish vaults on git to collaborate and share knowledge with others
    

![](en-cache://tokenKey%3D%22AuthToken%3AUser%3A124106736%22+0870c6be-053a-c0e6-d514-7ba6ce1b6731+62cefd9c9458d793e65f9dd38ce1de21+https%3A%2F%2Fpublic.www.evernote.com%2Fresources%2Fs672%2F517e0cf9-11a8-bc44-8879-7d554311cc99)

### Publish

- export your knowledge base as a static (nextjs) site
    
- lookup locally and share globally with generated links
    
- manage what you publish using fine grained permissions on a per vault, per hierarchy and per note basis
    

![](en-cache://tokenKey%3D%22AuthToken%3AUser%3A124106736%22+0870c6be-053a-c0e6-d514-7ba6ce1b6731+10e61a1df2107df52a1ecee85ffc17b1+https%3A%2F%2Fpublic.www.evernote.com%2Fresources%2Fs672%2F0e56467b-e9b7-c99f-26fa-d31f7469c012)

## Use Cases

- personal knowledge management (PKM)
    
- documentation
    
- meeting notes
    
- tasks and todos
    
- blogging
    
- customer relationship management
    

## Getting Started

Interested in trying out Dendron? Jump right in with the [Getting Started Guide](https://wiki.dendron.so/notes/678c77d9-ef2c-4537-97b5-64556d6337f1/ "https://wiki.dendron.so/notes/678c77d9-ef2c-4537-97b5-64556d6337f1/")!

## Join Us

Dendron wouldn't be what it is today without our wonderful set of members and supporters.

### Community Calendar

We have a bunch of community events that we host throughout the week. You can stay up to date on whats happening by taking a look at our community calendar!

- View and register for upcoming [Dendron Community Events on Luma](https://link.dendron.so/luma "https://link.dendron.so/luma")
    

### Dendron Newsletter

- [Subscribe to the Dendron Newsletter](https://link.dendron.so/newsletter "https://link.dendron.so/newsletter")
    

Dendron sends out a weekly newsletter highlighting:

- Latest release features
    
- Latest [Dendron blog](https://blog.dendron.so/ "https://blog.dendron.so") posts
    
- Insights from the [Dendron Discord](https://link.dendron.so/discord "https://link.dendron.so/discord") community
    
- RFC updates and [GitHub discussions](https://link.dendron.so/6WvK "https://link.dendron.so/6WvK")
    
- and more!
    

### Join other Dendrologists

There are a variety of ways to connect with Dendron devs, contributors, and other members of the Dendron community:

- Join the [Dendron on Discord](https://link.dendron.so/discord "https://link.dendron.so/discord")
    
- Follow [Dendron on Twitter (](https://link.dendron.so/twitter "https://link.dendron.so/twitter")`@dendronhq`)
    
- Checkout [Dendron on GitHub](https://link.dendron.so/github "https://link.dendron.so/github")
    
- Read the [Dendron Blog](https://blog.dendron.so/ "https://blog.dendron.so/")
    
- Subscribe to the [Dendron Newsletter](https://link.dendron.so/newsletter "https://link.dendron.so/newsletter")