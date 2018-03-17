asciidoctor.js-pug
==================

Override asciidoctor.js html5 output with pug templates.


[![Build Status](https://travis-ci.org/s-leroux/asciidoctor.js-pug.png?branch=master)](https://travis-ci.org/s-leroux/asciidoctor.js-pug)

## Installation

    npm install --save asciidoctor.js-pug


## Usage

    // load asciidoctor.js
    const asciidoctor = require('asciidoctor.js')();

    // load asciidoctor.js-pug.
    // This will register a new TemplateConverter with AsciiDoctor.
    require('asciidoctor.js-pug');

    // At this point, to convert a node, AsciiDoctor will try first to find
    // a corresponding pug template in the directory passed in the
    // `template_dirs` option. Then it will fallback
    // to the default backend behavior if there is no specific template for
    // that node.

    const doc = asciidoctor.load("Hello world",
                     { template_dirs: './path/to/template/directory' });

    console.log(doc.convert());


The template directory should contain one template per type of node. The
template name is made of the node_name + the `.pug` extension.

See the test/templates folder for some examples.

## Node version
Require NodeJS >= v7.0
Tested with v7.0, v7.6 and v8.9

## License

(The MIT License)

Copyright (c) 2018 [Sylvain Leroux](mailto:sylvain@chicoree.fr)

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
