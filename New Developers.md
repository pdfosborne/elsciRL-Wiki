![elsciRL_logo|150x150](<./Resources/images/elsciRL_logo.png>)
# elsciRL (pronounced L-SEE)

*Every problem can be automated with Language and Self-Completing Instructions.*

![GitHub watchers](https://img.shields.io/github/watchers/pdfosborne/elsciRL-TextWorldExpress?style=for-the-badge&logo=github&label=Followers&link=https%3A%2F%2Fgithub.com%2Fpdfosborne%2FelsciRL-TextWorldExpress) ![GitHub watchers](https://img.shields.io/github/watchers/pdfosborne/elsciRL-TextWorldExpress?style=for-the-badge&logo=github&label=Followers&link=https%3A%2F%2Fgithub.com%2Fpdfosborne%2FelsciRL-TextWorldExpress) ![GitHub watchers](https://img.shields.io/github/watchers/pdfosborne/elsciRL-TextWorldExpress?style=for-the-badge&logo=github&label=Followers&link=https%3A%2F%2Fgithub.com%2Fpdfosborne%2FelsciRL-TextWorldExpress)  ![Discord](https://img.shields.io/discord/1310579689315893248?style=for-the-badge&logo=discord&label=Discord&link=https%3A%2F%2Fdiscord.com%2Fchannels%2F1184202186469683200%2F1184202186998173878)  

**Quicklinks:** [Homepage](<./README.md>) | [elsciRL in Detail](<./Detailed Introduction to elsciRL.md>) | [Getting Started](<./elsciRL Core/I - Introduction/1 - Getting Started.md>)  | [Introduction to Language RL](<./elsciRL Core/III - Language RL/1 - Introduction to Language RL.md>)

## Getting Started with the Software
If you are ready to begin applying the elsciRL Python library: [Getting Started](<./elsciRL Core/I - Introduction/1 - Getting Started.md>)

## Benchmarking Suite

elsciRL can be used as a benchmarking suite for systematically evaluating new methods. To get started, see [Benchmarking with elsciRL](<./elsciRL Core/V - Benchmarking Suite/1 - Benchmarking with elsciRL.md>).

## Custom Development

You can develop your own agents, analysis and experiment protocols to compare against known methods. To get started with a custom development setup, see [Dev Setup](<./elsciRL Core/VI - Custom Development/1 - Dev Setup.md>).


## Use the Open-Source Documentation for Personal Use

The elsciRL Wiki is written using [Obsidian.md](https://obsidian.md/) and backed-up through GitHub as an open-source documentation site.

If you wish to download the documentation for personal use:
1. Download the [elsciRL-Wiki](https://github.com/pdfosborne/elsciRL-Wiki/tree/main) (click the *Code* button > *Download ZIP*)
2. Unzip the Vault to a local directory (e.g. inside Documents)
3. [Download Obsidian.md](https://obsidian.md/download)
4. Open the Obsidian software
5. Select the *Open folder as Vault* option and then the *elsciRL-Wiki* folder

*You can open the vault in any software that can read markdown files but it is suggested you use Obsidian.md as we use some features and plugins to improve the experience.*


### Obsidian Configuration

By default, not all formatting will work without the correct plugins but they can be setup by:
1. Overriding the configuration folder in *Obsidian>Files and Links settings* to this folder *.obsidian-git* (see image below)
2. Lastly, restart obsidian

![Obsidian settings](<./Resources/images/Obsidian settings.png>)


## Contributing to the Documentation

If you wish to contribute to the project:
1. Clone the vault repository a local directory 
2. Edit the documentation locally with the core changes you wish to implement
3. Open a new *Pull Request* and commit these changes

## Planned Improvements

```dataview
TABLE WITHOUT ID
  min(rows.file.folder) as Folder,
  min(rows.file.link) as File, 
  sum(rows.item.tags) as Tags, 
  map(items, (r) => "[" + r.status + "] " + r.text) as Tasks
FLATTEN file.tasks as item
GROUP BY file.folder + file.name + item.tags
FLATTEN array( filter( rows.item, (r) => r.status != "x" ) ) as items
WHERE items
```
*This is a dynamic table created using the [dataview plugin](https://github.com/blacksmithgu/obsidian-dataview).*