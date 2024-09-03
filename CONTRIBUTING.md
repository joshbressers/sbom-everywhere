# OpenSSF SBOM Everywhere Contributing Guide

If you are interested in adding entries to the catalog or wiki, or modifying functionality of the catalog, please review this guide.

The top portion of this guide is to provide guidance on the basics of using git for anyone unfamiliar. You can jump to the [Catalog](#sbom-catalog) or [Wiki](#sbom-wiki) sections.

## About the projects

The SBOM Catalog and SBOM Wiki projects use an open source development model. Whoever does the work gets to make the decisions. While the SBOM Everywhere group has meetings, those meetings are not where work on these projects happen.

## Contributing
It can be a terrifying prospect to submit a PR to an open source project, and it's not always clear what to do. We understand that many contributions to this project will come from people who are not necessarily regular open source contributors. We can't wait for your contribution. If you have any questions, no matter how silly you think they could be, please hop in Slack and ask, we'd be happy to help with anything below.

If you're more adventerous, the instructions below are meant to be everything anyone could need to contribute. You don't ever have to leave your web browser!

The code and data is stored in this git repository which is hosted on GitHub. Knowing how Git works is useful, but not necessary. You should find enough instructions here to get you started to edit in the web browser.

To set expectations, it's very likely there will be discussion and several iterations of your modifications. This is how the process works, you're not doing anything wrong, all of us are smarter than one of us.

### The repository
The Git repository for this project is located at [https://github.com/ossf/sbom-everywhere](https://github.com/ossf/sbom-everywhere). This document is located in that repository, so it's extremely likely you've already found it.

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

You only have to check that box once. If you have to re-fork the repo, you will have to click the box again (it's common to break a fork so bad it's easier to just delete it and start over, don't feel bad if this happens).

![](documentation-images/contributing-signoff.png?raw=true)

- Editing
  - Edit files in the web

- Link to instructions for the specific project you want to edit
  - Catalog
  - Wiki

- Pushing your changes
- Opening a PR
  - Please be patient
  - You can ping us in the slack channel if we're taking too long


# SBOM Catalog

## How to run the tool locally

Run the comamnds
```
npm install
npm run dev
```

Visiting the URL specified in the output will show you the current version of the site.

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

# SBOM Wiki

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