# OpenSSF SBOM Everywhere Contributing Guide

If you are interested in adding entries to the catalog or wiki, or modifying functionality of the catalog, please review this guide.

The top portion of this guide is to provide guidance on the basics of using git for anyone unfamiliar. You can jump to the [SBOM Catalog Contributing Guide](#sbom-catalog-contributing-guide) or [SBOM Wiki Contributing Guide](#sbom-wiki-contributing-guide) sections.

## Who can contribute
Everyone is welcome to contribute to the catalog and wiki. If you work for a company that makes SBOM tools or products, we would love to see them listed here.

Both open source and commercial offerings should be included.

## About the projects

The SBOM Catalog and SBOM Wiki projects use an open source development model. Whoever does the work gets to make the decisions. While the SBOM Everywhere group has meetings, those meetings are not where work on these projects happen.

## Contributing
It can be a terrifying prospect to submit a PR or open an issue for an open source project, and it's not always clear what to do. We understand that many contributions to this project will come from people who are not necessarily regular open source contributors. We can't wait for you to contribute! If you have any questions, no matter how silly you think they could be, please hop in Slack or open an issue in this repo and ask, we'd be happy to help with anything.

## Opening an issue

By far the easiest way to contribute is to open an issue in our [GitHub repository](https://github.com/ossf/sbom-everywhere/). Don't worry about getting all the details right, we'll be nice and ask any questions that we might have.

You need a GitHub account to open an issue. If you don't have one, anyone can create an account.

Click on the "Issues" link at the top left, then the "New issue" button on the right

![](documentation-images/new-issue.png?raw=true)

Please fill out the title and description as best as you can. Don't worry about getting all the detials correct, we'll help you out with that part.

Once you're happy with the description just hit "Submit new issue" and you should hear from someone in a few days.

## Opening a Pull Request

The instructions below are meant to be everything anyone could need to contribute. You don't even have to leave your web browser. The instructions below are focused on creating a PR in GitHub using only the browser.

The code and data is stored in this git repository which is hosted on GitHub. Knowing how Git works is useful, but not necessary. You should find enough instructions in this section to get you started to edit in the web browser.

To set expectations, it's very likely there will be discussion and several iterations of your modifications. This is how the process works, you're not doing anything wrong, all of us are smarter than one of us.

### The repository
The Git repository for this project is located at [https://github.com/ossf/sbom-everywhere](https://github.com/ossf/sbom-everywhere). This document is located in that repository, so it's extremely likely you've already found it if you're reading this.

The Catalog is located in the `SBOM-Catalog` directory. The Wiki is in the `SBOM-wiki` directory.

### Adding your contribution
In order to contribute to the project, you will need to create something called a Pull Request, or PR. Some of the below steps will seem a bit odd, but it's how GitHub works, and generally speaking it's a pretty great process.

You need a GitHub account to submit a PR. If you don't have one, anyone can create an account.

#### Fork the project
We first have to fork the project. This will create a personal instance of the SBOM Everywhere repository we can make changes to. There is a button labeled `Fork` in the upper right of the GitHub project page

![](documentation-images/contributing-fork.png?raw=true)

When you click `Fork`, you will find the URL has changed from ossf/sbom-everywhere, to *yourusername*/sbom-everywhere

#### Enable signoff
You need to enable the signoff with web commits feature to have your PR accepted. This is done to pass the [Developer Certificate of Origin](https://en.wikipedia.org/wiki/Developer_Certificate_of_Origin), or DCO check that is requires by the OpenSSF.

First click Settings, then check the box labeled *Require contributors to sign off on web-based commits*

You only have to check that box once. If you ever have to re-fork the repo, you will have to click the box again (it's common to break a fork so bad it's easier to just delete it and start over, don't feel bad if this happens).

![](documentation-images/contributing-signoff.png?raw=true)

#### Editing a file
In the web interface, you can edit or add files.

To add a file click the `+` icon

![](documentation-images/contributing-add-file.png?raw=true)

To edit a file, there is an edit button when viewing an individual file

![](documentation-images/contributing-edit-button.png?raw=true)

Each project has specific instructions and expectations, you should review those sections in this document.
- [Catalog Editing](#sbom-catalog-contributing-guide)
- [Wiki Editing](#sbom-wiki-contributing-guide)

Make the changes you need to make to a given file, then hit the `Commit Changes` button

![](documentation-images/contributing-make-changes.png?raw=true)

You will be presented with a screen asking you to add a commit message.

![](documentation-images/contributing-commit-message.png?raw=true)

If the button at the bottom doesn't say `Sign off and commit changes` you probably forgot the sign off step above. Add a description and commit your change. Your change is not stored in your fork of the sbom-everywhere repository.

#### Testing your changes
It was sort of a lie that you could do all of this using only a web browser. Testing is easiest to do locally. Each tool has documentation about how to run a local copy and check things are working as expected.

- [Catalog Editing](#sbom-catalog-contributing-guide)
- [Wiki Editing](#sbom-wiki-contributing-guide)

If you're not able to do this, feel free to ask in Slack, someone will be willing to help out.

#### Opening the PR
Assuming all the editing and testing went as expected, it's time to submit a PR.

You might see a button labeled `Compare & pull request` for the branch you're working on. If not you can use the `Contribute` button to open a PR

![](documentation-images/contributing-open-pr.png?raw=true)

You should then see a screen that looks like this

![](documentation-images/contributing-create-pr.png?raw=true)

Make sure the Title and Description make sense. The click the `Create pull request` button. That's it, you've submitted a PR to the project. Congrats!

It's possible it will take time for us to get to your changes. Feel free to ping the Slack channel if it's more than a week without any activity. We're all volunteers, so patience is appreciated.

---
---

# SBOM Catalog Contributing Guide

If you wish to contribute to the SBOM Catalog, first you might want to review the above [Contributing](#contributing) guidance.

## How to run the tool locally

If you plan to run the tool locally, you will need to "pull" the git repository. This could be the sbom-everywhere repository, or your fork.

You will also need a functional Node.js installed. Getting the repo pulled and Node.js installed are larger than we wish to include in this guide, feel free to ask on Slack if you need some help.

Assuming you have Node.js and the repo cloned, run these comamnds
```
cd SBOM-Catalog
npm install
npm run dev
```

There will be much printed to the screen, but eventually you should see

```bash
  VITE v5.3.2  ready in 416 ms

  ➜  Local:   http://localhost:5173/catalog/
  ➜  Network: use --host to expose
  ➜  press h + enter to show help

```

Visiting the URL specified in the output will show you the current version of the Catalog.

## How to add your tool
If you know of a tool or project that should be listed here, please open a pull request. There are three things to consider while adding a new tool:

### 1. Add a new entry
The public/data.yaml contains all the information a user can search on the page. Add a new entry to the list of tools. Please follow the following convention regarding the values. Please also refer to the tool's source, where the features are documented.

##### Name
The name of the tool. This should be distinct in the list and is used as an identifier.

##### Publisher
The publisher refers to the company or institution maintaining the tool. It should be spelled similarly each time so users can find all tools from the same publisher.

#### License
The general class of license the tool is released under.
Use either *OpenSource* or *Proprietary*.

##### Standards
A list of Standards a tool can produce. Currently, the three standards which are recognized by the [NTIA](https://www.ntia.gov/sites/default/files/publications/sbom_formats_survey-version-2021_0.pdf) are supported:
- SPDX
- CycloneDx
- SWID

##### Abilities
Abilities describe the capabilities of the tool. In what part of the software development lifecycle can the tool be used? The following abilities are supported:
- **Compare**   - *Can compare two SBOMs*
- **Consume**   - *Can use a provided SBOM in some form*
- **Convert**   - *Can Convert between formats (SPDX, CycloneDX), versions or file-formats (json, xml)*
- **Edit**      - *Can somehow edit the contents of a SBOM*
- **Generate**  - *Can automatically generate a SBOM*
- **Merge**     - *Can merge several SBOMs*
- **Validate**  - *Can validate a SBOM against the file schema or requirements like defined by the NTIA*

##### Type
SBOMs may contain different forms of the minimum information sourced from different
product artifacts. The following types are supported as published by the [NTIA](https://www.cisa.gov/resources-tools/resources/types-software-bill-materials-sbom). Because many tools specifically support the scanning of container images, the category **Container** is added additionally. Even if container scans can be considered *Analyzed*:
- Design
- Source
- Build
- Analyzed
- Deployed
- Runtime
- Container

### 2. Add a description
You can add a detailed description to the /public/descriptions folder. The description should be written in markdown and named after the tool (the Same name as in the data.yaml). It should contain detailed information about the tools and features claimed in the data section. Feel free to add links to the GitHub repository or supplier.

### 3. Add a logo
You can add a logo to the /public/logos folder. The logo should be named after the tool (the Same name as in the data.yaml). It should be a PNG file with a transparent background and 200px x 200px.

The logo will be displayed on the page in the Map View, the List View, and the details section. You can add Logos for all categories and also for the Publisher.

If you add a Logo, we assume your project and/or company are OK with that. The logo should be used under the fair use policy. If you want to remove your logo, please open an issue, and we will remove it.

# SBOM Wiki Contributing Guide

Add things here

---

## Shoutout

A shoutout goes to D3JS for providing such a great library to visualize and interact with data. I stand on the shoulders of giants with this tooling. Also, thanks go to the people from vue.js, who just provide a great JavaScript framework.

Special thanks to [Mike Bostock](https://observablehq.com/@d3/zoomable-circle-packing?intent=fork) for sharing their examples and snippets used under the [ISC License](https://choosealicense.com/licenses/isc/) to provide the different views in the landscape.

<details><summary>ISC License</summary>
Permission to use, copy, modify, and/or distribute this software for any
purpose with or without fee is hereby granted, provided that the above
copyright notice and this permission notice appear in all copies.

THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES
WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF
MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR
ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES
WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN
ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF
OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.
</details>
