# elsciRL-Wiki
## Language Guidance for Reinforcement Learning

<a href="https://elsci.org"><img src="https://raw.githubusercontent.com/pdfosborne/elsciRL-Wiki/refs/heads/main/Resources/images/elsciRL_logo_owl_cropped.png" align="left" height="250" width="250" ></a>

<div align="center">

<br>
<b>Open-source Python Software for Academic and Industry Applications</b>

Visit our <a href="https://elsci.org">website</a> to get started, explore our <a href="https://github.com/pdfosborne/elsciRL-Wiki">open source Wiki</a> to learn more or join our <a href="https://discord.gg/GgaqcrYCxt">Discord server</a> to connect with the community.
<br>
<i>In pre-alpha development.</i>
<p> </p>
</div>

<div align="center">

<a href="https://github.com/pdfosborne/elsciRL">![elsciRL GitHub](https://img.shields.io/github/stars/pdfosborne/elsciRL?style=for-the-badge&logo=github&label=elsciRL&link=https%3A%2F%2Fgithub.com%2Fpdfosborne%2FelsciRL)</a> <a href="https://github.com/pdfosborne/elsciRL-Wiki">![Wiki GitHub](https://img.shields.io/github/stars/pdfosborne/elsciRL-Wiki?style=for-the-badge&logo=github&label=elsciRL-Wiki&link=https%3A%2F%2Fgithub.com%2Fpdfosborne%2FelsciRL-Wiki)</a> <a href="https://discord.gg/GgaqcrYCxt">![Discord](https://img.shields.io/discord/1310579689315893248?style=for-the-badge&logo=discord&label=Discord&link=https%3A%2F%2Fdiscord.com%2Fchannels%2F1184202186469683200%2F1184202186998173878)</a>

<b>Quicklinks:</b> [Website](https://elsci.org) | [About Us](<./About us.md>) | [FAQs](<./FAQs.md>) | [Developer Guide](<./Developer Guide.md>) | [Contributing Guide](<./Become a Contributor.md>) | [App Interface Guide](<./App Interface Guide.md>)
<br>
<br>
</div>

## What is elsciRL?

**elsciRL** offers a general purpose framework and infrastructure for accelerating the development of language based Reinforcement Learning (RL) solutions.

This has also been known as *AI agents* but we notably do not require the problem to already contain language.

### Features
1. **Accelerates Research** by seperating Reinforcement Learning development into distinct components and providing an [Open-Source Wiki](https://github.com/pdfosborne/elsciRL-Wiki) and [Discord Server](https://discord.gg/GgaqcrYCxt) to share knowledge
2. **Improve Reproducability** by designing generally applicable alogorithms & applications including configurations to re-create prior experiments
3. **Extract Domain Expert Knowledge** by using our App Interface to let non-technical users provide instructions
4. **Enchance New Applications** by making it easier to setup new problems and reduce the amount of data required testing

<div width="75%" align="center">
	<img src="https://github.com/pdfosborne/elsciRL-Wiki/blob/main/Resources/images/Agent-Performance-2.gif?raw=true" />
</div>

## What Makes the Wiki Open Source? 

The primary aim of elsciRL is to accelerate research in the Language and Reinforcement Learning domain. 

In many cases research can be fragmented by short-term paper submissions. 

Therefore, we believe it to be a fundamental requirement to improve how we collectively share knowledge as a global network of researchers. 

We encourage academics who are new to the domain to freely use the knowledge contained in this Wiki for their projects by making it accessible to all. 

In turn, we ask that once projects are completed and publicly available the research notes used to complete new developments is contributed to the community. 

**Specifically, the Wiki provides:**

1. Beginner guides for new users
2. Information to academics new to the space on how they can contribute
3. A centralized set of applications that can be searched and filtered
4. Complete documentation for using the elsciRL software
5. Literature studies on a range of topics
6. References with summaries and ready to copy citations
7. A list of notable researchers to follow and their contributions to the domain

Lastly, the [documentation website](https://elsci.org/) is a direct display of the notes contained in this repository so as to streamline the contribution to the community.

## Download the Wiki

The elsciRL Wiki is written using [Obsidian.md](https://obsidian.md/) and backed-up through GitHub as an open-source documentation site. 

If you wish to download the documentation for personal use:

8. Download the [elsciRL-Wiki](https://github.com/pdfosborne/elsciRL-Wiki/tree/main) (click the *Code* button > *Download ZIP*)
9. Unzip the Vault to a local directory (e.g. inside Documents)
10. [Download Obsidian.md](https://obsidian.md/download)
11. Open the Obsidian software
12. Select the *Open folder as Vault* option and then the *elsciRL-Wiki* folder 

See [New Contributors Guide](https://elsci.org/Become+a+Contributor) for more information on contributing to the open-source development of this project.

### Obsidian Configuration

By default, not all formatting will work without the correct plugins but they can be setup by:
13. Overriding the configuration folder in *Obsidian>Files and Links settings* to this folder *.obsidian-git* (see image below)
14. Lastly, restart obsidian

We also use a set of custom css snippets that you can enable in settings > appearance > CSS snippets at the bottom.

![osbsidian\_settings](https://raw.githubusercontent.com/pdfosborne/elsciRL-Wiki/refs/heads/main/Documentation/0%20-%20Prerequisites/attachments/Obsidian%20settings.png)

## LaTeX Export

We use the [Latex-Exporter](https://github.com/mscott99/latex-exporter?tab=readme-ov-file) plugin.

You can simply open Obsidian's command pallete (ctrl+p) on any note and run the `Latex Exporter: Export Current Note`. 

This will produce a folder in the **LatexExports** directory of the vault containing the `.tex` file and the Bibliography for you to copy.

All notes in the **Publications** directory and all equations in the **Studies** directory are designed to be exported directly to LaTeX. This means we cannot use Obsidian's linking but provides a smoother experience for academic publications.

### Copying Notes from Studies

If you copy blocks from the **Studies** you will need to update references (labelled with {[[]]}) by removing the Obsidian link and replace with the Latex Exporter tag. e.g. 

```{[[suttonReinforcementLearningIntroduction2018|sutton2018]]}```

into 

```@suttonReinforcementLearningIntroduction2018```

References to other notes (labelled with [[]]) will simply need to be removed and then you can add text from linked notes manually.

### Adding New References

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


--- 

Please use the following to cite this work

```bibtex
  title        = {Improving Real-World Reinforcement Learning by Self Completing Human Instructions on Rule Defined Language},  
  author       = {Philip Osborne},  
  year         = 2024,  
  month        = {August},  
  address      = {Manchester, UK},  
  note         = {Available at \url{https://research.manchester.ac.uk/en/studentTheses/improving-real-world-reinforcement-learning-by-self-completing-hu}},  
  school       = {Department of Computer Science},  
  type         = {PhD thesis}
```
