<img style="width: 200px; height: 200px;" src="https://raw.githubusercontent.com/cytoscape/cytoscape.js/unstable/documentation/img/cytoscape-logo.png" width="200" height="200"></img>

[![GitHub repo](https://img.shields.io/badge/Repo-GitHub-yellow.svg)](https://github.com/cytoscape/cytoscape.js)
[![Twitter updates](https://img.shields.io/badge/Updates-Twitter-yellow.svg)](https://twitter.com/cytoscapejs)
[![News and tutorials](https://img.shields.io/badge/News%20and%20tutorials-Blog-yellow.svg)](https://blog.js.cytoscape.org)
[![Questions at StackOverflow](https://img.shields.io/badge/Questions-StackOverflow-yellow.svg)](https://stackoverflow.com/questions/tagged/cytoscape.js)
[![Ask a question at StackOverflow](https://img.shields.io/badge/Ask%20a%20question-StackOverflow-yellow.svg)](https://stackoverflow.com/questions/ask?tags=cytoscape.js,javascript)
[![GitHub license](https://img.shields.io/badge/License-MIT-blue.svg)](https://raw.githubusercontent.com/cytoscape/cytoscape.js/master/LICENSE)
[![DOI](https://zenodo.org/badge/2255947.svg)](https://zenodo.org/badge/latestdoi/2255947)
[![Cite](https://img.shields.io/badge/Cite-Oxford%20Bioinformatics%20Article-blue.svg)](https://js.cytoscape.org/#introduction/citation)
[![npm](https://img.shields.io/npm/v/cytoscape.svg)](https://www.npmjs.com/package/cytoscape)
[![Download](https://img.shields.io/npm/v/cytoscape.svg?label=Download)](https://github.com/cytoscape/cytoscape.js/tree/master/dist)
[![Extensions](https://img.shields.io/badge/Extensions-52-blue.svg)](https://js.cytoscape.org/#extensions)
[![npm installs](https://img.shields.io/npm/dm/cytoscape.svg?label=npm%20installs)](https://www.npmjs.com/package/cytoscape)
[![master branch tests](https://img.shields.io/travis/cytoscape/cytoscape.js/master.svg?label=master%20branch)](https://travis-ci.org/cytoscape/cytoscape.js)
[![unstable branch tests](https://img.shields.io/travis/cytoscape/cytoscape.js/unstable.svg?label=unstable%20branch)](https://travis-ci.org/cytoscape/cytoscape.js)
[![Greenkeeper badge](https://badges.greenkeeper.io/cytoscape/cytoscape.js.svg)](https://greenkeeper.io/)

# Cytoscape.js

Graph theory (network) library for visualisation and analysis : [https://js.cytoscape.org](https://js.cytoscape.org)

## Description

Cytoscape.js is a fully featured [graph theory](https://en.wikipedia.org/wiki/Graph_theory) library.  Do you need to model and/or visualise relational data, like biological data or social networks?  If so, Cytoscape.js is just what you need.

Cytoscape.js contains a graph theory model and an optional renderer to display interactive graphs.  This library was designed to make it as easy as possible for programmers and scientists to use graph theory in their apps, whether it's for server-side analysis in a Node.js app or for a rich user interface.

You can get started with Cytoscape.js with one line:

```js
var cy = cytoscape({ elements: myElements, container: myDiv });
```

Learn more about the features of Cytoscape.js by reading [its documentation](https://js.cytoscape.org).





## Documentation

You can find the documentation and downloads on the [project website](https://js.cytoscape.org).



## Roadmap

Future versions of Cytoscape.js are planned in the [milestones of the Github issue tracker](https://github.com/cytoscape/cytoscape.js/milestones).  You can use the milestones to see what's currently planned for future releases.




## Contributing to Cytoscape.js

Please refer to [CONTRIBUTING.md](.github/CONTRIBUTING.md).

Feature releases are made at the start of each month, while patch releases are made at the start of each week.  This allows for rapid releases of first- and third-party contributions.



## Citation

To cite Cytoscape.js in a paper, please cite the Oxford Bioinformatics issue:

*Cytoscape.js: a graph theory library for visualisation and analysis*

Franz M, Lopes CT, Huck G, Dong Y, Sumer O, Bader GD

[Bioinformatics (2016) 32 (2): 309-311 first published online September 28, 2015 doi:10.1093/bioinformatics/btv557 (PDF)](https://bioinformatics.oxfordjournals.org/content/32/2/309)

[PubMed Abstract](https://www.ncbi.nlm.nih.gov/pubmed/26415722)




## Build dependencies

Install `node` and `npm`.  Run `npm install` before using `npm run`.




## Build instructions

Run `npm run <target>` in the console.  The main targets are:

**Building:**

 * `build`: do all builds of the library (unmin, min, umd)
 * `build:unmin` : do the unminified build with bundled dependencies (for simple html pages, good for novices)
 * `build:min` : do the unminified build with bundled dependencies (for simple html pages, good for novices)
 * `build:umd` : do the umd (cjs/amd/globals) build
 * `clean` : clean the `build` directory
 * `docs` : build the docs into `documentation`
 * `release` : build all release artifacts
 * `watch` : automatically build lib for debugging (with sourcemap, no babel, very quick)
   * good for general testing on `debug/index.html`
   * served on `http://localhost:8080` or the first available port thereafter, with livereload on `debug/index.html`
 * `watch:babel` : automatically build lib for debugging (with sourcemap, with babel, a bit slower)
   * good for testing performance or for testing out of date browsers
   * served on `http://localhost:8080` or the first available port thereafter, with livereload on `debug/index.html`
 * `watch:umd` : automatically build prod umd bundle (no sourcemap, with babel)
   * good for testing cytoscape in another project (with a `"cytoscape": "file:./path/to/cytoscape"` reference in your project's `package.json`)
   * no http server
 * `dist` : update the distribution js for npm etc.

**Testing:**

If the `TRAVIS` or `TEST_BUILD` environment variables are defined, then `mocha` or `npm test` will test `build/cytoscape.umd.js`.  Otherwise, the unbundled, unbabelified, raw source is tested.  This keeps local tests very quick to run on modern versions of node while ensuring we can test old versions of node as well.  The library can be built on `node>=6`, but it can be tested on `node>=0.10`.

 * `test` : run the Mocha unit tests
 * `test:build` : run the Mocha unit tests (on a built bundle)
 * `lint` : lint the js sources via eslint
 * `ci` : run tests and linting
 * `ci:build` : run tests and linting (on a built bundle)
 * `benchmark` : run all benchmarks
 * `benchmark:single` : run benchmarks only for the suite specified in `benchmark/single`
 * `sniper` : runs a biojs sniper server that hosts demos



## Release instructions

 1. Do each backport patch release before the corresponding current release.  This ensures that npm lists the current version as the latest one.
 1. Make sure the docs are updated with the list of releases in `documentation/md/intro.md`
 1. Update the `VERSION` environment variable, e.g. `export VERSION=1.2.3`
 1. Confirm all the tests are passing: `npm run test` (see also `test/index.html` for browser testing)
 1. Confirm all the tests are passing in IE9:
     1. `npm run watch:umd`
     1. Open an [IE9 VM](https://developer.microsoft.com/en-us/microsoft-edge/tools/vms/)
     1. Open `http://yourip:8081/test/ie.html` in IE
 1. Prepare a release: `npm run release`
 1. Review the files that were just built in the previous step.  Try out the newly-built docs and demos.
 1. Add the the release to git: `git add . && git commit -m "Build $VERSION"`
 1. Update the package version: `npm version $VERSION`
 1. Push the release changes: `git push && git push --tags`
 1. Publish the release to npm: `npm publish .`
 1. [Create a release](https://github.com/cytoscape/cytoscape.js/releases/new) for Zenodo from the latest tag
 1. For feature releases:  Create a release announcement on the [blog](https://github.com/cytoscape/cytoscape.js-blog).  Share the announcement on mailing lists and social media.



## Tests

Mocha tests are found in the [test directory](https://github.com/cytoscape/cytoscape.js/tree/master/test).  The tests can be run in the browser or they can be run via Node.js (`npm test` or `mocha`).
