# About     

Baleen is a tool for ingesting _formal_ natural language data from the discourse of professional and amateur writers: e.g. bloggers and news outlets. Rather than performing web scraping, Baleen focuses on data ingestion through the use of RSS feeds. It performs as much raw data collection as it can, saving data into a Mongo document store.

## Contributing

Baleen is open source, and I'd love your help. If you would like to contribute, you can do so in the following ways:

1. Add issues or bugs to the bug tracker: [https://github.com/bbengfort/baleen/issues](https://github.com/bbengfort/baleen/issues)
2. Work on a card on the dev board: [https://waffle.io/bbengfort/baleen](https://waffle.io/bbengfort/baleen)
3. Create a pull request in Github: [https://github.com/bbengfort/baleen/pulls](https://github.com/bbengfort/baleen/pulls)

Note that labels in the Github issues are defined in the blog post: [How we use labels on GitHub Issues at Mediocre Laboratories](https://mediocre.com/forum/topics/how-we-use-labels-on-github-issues-at-mediocre-laboratories).

If you are a member of the District Data Labs Faculty group, you have direct access to the repository, which is set up in a typical production/release/development cycle as described in _[A Successful Git Branching Model](http://nvie.com/posts/a-successful-git-branching-model/)_. A typical workflow is as follows:

1. Select a card from the [dev board](https://waffle.io/bbengfort/baleen) - preferably one that is "ready" then move it to "in-progress".

2. Create a branch off of develop called "feature-[feature name]", work and commit into that branch.

        ~$ git checkout -b feature-myfeature develop

3. Once you are done working (and everything is tested) merge your feature into develop.

        ~$ git checkout develop
        ~$ git merge --no-ff feature-myfeature
        ~$ git branch -d feature-myfeature
        ~$ git push origin develop

4. Repeat. Releases will be routinely pushed into master via release branches, then deployed to the server.

## Contributors

Thank you for all your help contributing to make Baleen a great project!

### Maintainers

- Benjamin Bengfort: [@bbengfort](https://github.com/bbengfort/)

### Contributors

- Your name welcome here!

## Changelog

The release versions that are sent to the Python package index (PyPI) are also tagged in Github. You can see the tags through the Github web application and download the tarball of the version you'd like. Additionally PyPI will host the various releases of Baleen (eventually).

The versioning uses a three part version system, "a.b.c" - "a" represents a major release that may not be backwards compatible. "b" is incremented on minor releases that may contain extra features, but are backwards compatible. "c" releases are bug fixes or other micro changes that developers should feel free to immediately update to.

### Version 0.1

* **tag**: [v0.1](https://github.com/bbengfort/baleen/releases/tag/v0.1)
* **release**: Tuesday, September 23, 2014
* **deployment**: Thursday, February 18, 2016
* **commit**: [f5f15dd](https://github.com/bbengfort/baleen/commit/f5f15dda6da9c0fb680d7af43bb941c5086845a1)

This was the initial version of Baleen before the revamp occurred thanks to the PyCon tutorial. Baleen in this form was a command line utility that fetched RSS feeds on demand and stored them in a Mongo database. The input to Baleen is an OPML file that contains an RSS feed listing as well as their topics.

Baleen was originally used to produce a corpus for the [District Data Labs](https://www.districtdatalabs.com) _NLP with NLTK_ course. The corpus was then adapted for use in the [Statistics.com](http://www.statistics.com/) online course of the same name. The problem is that because Baleen had to be ran manually, it was difficult to get a high quality corpus on demand.