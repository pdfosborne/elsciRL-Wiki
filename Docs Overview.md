# How to use the Wiki

<div align="center">

<a href="https://github.com/pdfosborne/elsciRL">![elsciRL GitHub](https://img.shields.io/github/stars/pdfosborne/elsciRL?style=for-the-badge&logo=github&label=elsciRL&link=https%3A%2F%2Fgithub.com%2Fpdfosborne%2FelsciRL)</a> <a href="https://github.com/pdfosborne/elsciRL-Wiki">![Wiki GitHub](https://img.shields.io/github/stars/pdfosborne/elsciRL-Wiki?style=for-the-badge&logo=github&label=elsciRL-Wiki&link=https%3A%2F%2Fgithub.com%2Fpdfosborne%2FelsciRL-Wiki)</a> <a href="https://discord.gg/GgaqcrYCxt">![Discord](https://img.shields.io/discord/1310579689315893248?style=for-the-badge&logo=discord&label=Discord&link=https%3A%2F%2Fdiscord.com%2Fchannels%2F1184202186469683200%2F1184202186998173878)</a>

</div>

**Quicklinks:** [Homepage](https://elsci.org) | [About Us](https://elsci.org/About+us) | [FAQs](https://elsci.org/FAQs) | [New Developers](https://elsci.org/Developer+Guide)  | [App Interface Guide](https://elsci.org/App+Interface+Guide) | [Contributing Guide](https://elsci.org/Become+a+Contributor)

## Basics

The Wiki contains a complete set of notes in a hierarchy.

```
Topics & Publications
 |--Studies
	 |--Definitions
		|--References
```

**1. Topics & Publications** combine studies into a more complete narrative structure that are ready to publish. These include: sections of academic papers, online articles or summary studies.

**2. Studies** summarize subjects into digestible parts. These are designed to be objective descriptions of prior work and could be used as they are for sections in a literature review.

**3. Definitions** provide specification of individual components needed to produce studies.

**4. References** include the citation for any work used in the other notes as well as notes on individual resources.

## How to use these notes for your own work

As the Wiki is Open-Source we actively encourage individual researches to use this vault and add their own studies. 

Simply add new notes in any of the directories that best match the intended use. 

### LaTeX Export Format

We use the [Latex-Exporter](https://github.com/mscott99/latex-exporter?tab=readme-ov-file) plugin.

You can simply open Obsidian's command pallete (ctrl+p) on any note and run the `Latex Exporter: Export Current Note`. 

This will produce a folder in the **LatexExports** directory of the vault containing the `.tex` file and the Bibliography for you to copy.

All notes in the **Definitions** and all equations in the **Studies** directory are designed to be exported directly to LaTeX. This means we cannot use Obsidian's linking but provides a smoother experience for academic publications.

#### Exporting Notes from Studies

If you copy blocks from the **Studies** you will need to update references (labelled with {[[]]}) by removing the Obsidian link and replace with the Latex Exporter tag. e.g. 

```{[[suttonReinforcementLearningIntroduction2018|sutton2018]]}```

into 

```@suttonReinforcementLearningIntroduction2018```

References to other notes (labelled with [[]]) will simply need to be removed and then you can add text from linked notes manually.

#### Adding New References

You will need to add any BibTeX citations into the ```References/Library.bib``` file which is not viewable inside Obsidian so will need to access from your computer's file manager.


When writing your own notes, you can do the following:
- Citations are wikilinks
	- Reference in text using `@...`
	- The `...` is replaced by the cite key in the Biblography
	- Add references to the [Bibliography](https://github.com/pdfosborne/elsciRL-Wiki/blob/main/References/Bibliography/Bibliography.bib) file
- Equations are labelled with the quarto syntax 
	- Specified by `$$...$${#eq-my_label}`
	- Required format is `{#eq-...}`
	- Referenced with `@eq-my_label`

*The following image shows an example with a citation and equation reference.*

<div width="50%" align="center">
	<img src="https://github.com/pdfosborne/elsciRL-Wiki/blob/main/References/_images/Latex-Exporter-Example.png?raw=true" />
</div>

## How to reference notes

 As notes are added with their intended usage to be in academic work, it is expected that you reference these appropriately.

Authors should provide the BibTeX for any note they provide so that future research can correctly cite their work.

Definitions should only include the citations that are used within the note.