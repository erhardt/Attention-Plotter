Attention Plotter
=================

This is a d3.js-based tool for graphing and comparing volumes of content 
from multiple media sources and word frequencies within that content over 
a range of dates. It's part of the [Controversy Mapper](http://civic.mit.edu/controversy-mapper) project at the
[MIT Center for Civic Media](http://civic.mit.edu).

It's based on Mike Bostocks's ["Grouped Bar Chart"](http://bl.ocks.org/mbostock/3887051) and ["Multi-Series Line Chart"](http://bl.ocks.org/mbostock/3884955) 
d3.js examples, as well as Jim Vallandingham's 
["How to Animate Transitions Between Multiple Charts"](http://flowingdata.com/2013/01/17/how-to-animate-transitions-between-multiple-charts/) tutorial. It uses the [Bootstrap](http://twitter.github.io/bootstrap/), [jQuery](jquery.com), and [jQuery.popover](https://github.com/klaas4/jQuery.popover) libaries.

Live demo of the code: [http://erhardtgraeff.com/demo/aplotter/aplotter.html](http://erhardtgraeff.com/demo/aplotter/aplotter.html)

Installation and Use
--------------------

Copy the whole directory structure to a server folder. A running server 
instance is necessary to allow javascript to access the data files. You 
can either use a hosted server or start a local server in the directory, 
e.g. `python -m SimpleHTTPServer 8888 &`.

You should change the title and description of the graph in the 
`aplotter.html` file:
```
      <h1 id="title">Title of the Attention Plot</h1>
      <div id="description">
        <p>Description of the graph.</p>
```

You should add your own data to the `data/media.csv` and `data/words.csv`
files. It's recommended you use the example data files as templates. You 
can also add your own data files to the folder and then change the paths
in the `aplotter.js` file.

Here's the parameters you can change in the `aplotter.js` file:
```
// Path to csv file containing volumes of media by day
// Column headers should be: date, [media source 1], [media source 2], ...
// Make sure data is already normalized
// Recommended date format: mmm d
var mediacsv = '../data/media.csv';

// Path to csv file containing word frequencies by day
// Column headers should be: date, word, magnitude
// Dates should be formatted identically to those in media.csv
// Recommended metric for magnitude: tf-idf
var wordscsv = '../data/words.csv';

// Dimensions of the graph
var graphwidth = 2000;
var graphheight = 400;
```

Files
-----

Files unique to this project are all named aplotter.*:
* `aplotter.html`
* `css/aplotter.js`
* `js/aplotter.js`

Required libraries are in the `css/libs` and `js/libs` folders.