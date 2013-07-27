As JSON
-------

(with comments)

    # example.json.coffee
    foo:
      a: 1
      b: 2
      c: [
        'one way'
        'another way'
      ]
    lambda: true

Converter:

    #!/usr/bin/env node
    coffeescript = require('coffee-script');
    fs = require('fs');
    fs.writeFileSync(
      'example.json',
      JSON.stringify(
        coffeescript.eval(
          fs.readFileSync(
            'example.json.coffee', 'utf-8'
    ))));
    
As HTML
-------

(with comments)

    # example.html.coffee
    doctype 5
    html ->
      head ->
        title 'Homepage'
      body ->
        h1 'Nobody makes cheesy homepages anymore'
        p ->
          'But I wanted to!'
          
Converter:

    coffeecup example.html.coffee && mv example.html.html example.html
