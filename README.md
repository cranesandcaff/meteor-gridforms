### meteor-gridforms

Based on Kumail Hunaids »[gridforms](https://github.com/kumailht/gridforms) front-end library« this package brings his beautiful gridforms to your meteor application project in no time. Currently working with the following html input elements:   **text**, **email**, **number**, **date**, **submit** and **textarea**.


### basic usage

Add to your project with: ```meteor add herrhelms:meteor-gridforms```.


### architecture

In your templates build your gridforms like this:

```
  {{#gridForm "custom-css-class"}} 
    {{#gridSet label="A form header"}}
      {{#gridRow span="4"}} <!--'span' of rows+elements is for layout, -->
        {{#gridElement span="3" type="text" label="A Text"}}Some additional help text.{{/gridElement}}
        {{#gridElement span="1" type="date" label="A Date"}}Can also host a <a href="#">link</a>.{{/gridElement}}
      {{/gridRow}}  
      {{#gridRow}} <!-- without 'span' it defaults to 'span="1"' -->
        {{#gridElement type="submit" value="Submit this form"}}{{/gridElement}}
      {{/gridRow}}  
    {{/gridSet}}
  {{/gridForm}}
```

Any content inbetween `{{#gridElement}}` and `{{/gridElement}}` will serve as help text and is wrapped in a `<span class"grid-form-help"></span>`. **You can add any additional HTML anywhere**, but keep in mind that this might mess up the plain and simple form layout. 

To wrap your gridRows and gridElements in a `{{#gridSet label="A form header"}}{{/gridSet}}` is optional. It will render as a fieldset element. Very useful if you like to layout your form into separated sections containing lots of form fields below.  use the `label=""` to add a heading to these sections. You might want to take a look at Kumails [›Bank Application Form‹ ](http://kumailht.com/gridforms/example.html) example for more details.

### available settings:

For any `{{#gridElement}}{{/gridElement}}`:

  `type`          text|number|date|email|submit|textarea - if none is given 'text' will be used.
  
  `'id'`          uniqueIDs for field elements (you might want to access fields later w/ jQuery)
  
  `'label'`       a label (shown above the element)
  
  `'classes'`     class names without separators (i.E. 'btn btn-lg btn-success')
  
  `'placeholder'` placeholder text (shown inside the element)  

  `'value'`       prefill element with a certain value

For 'date' and 'number' types:

  `'min'`         minimum value
  
  `'max'`         maximum value  

  `'step'`        offset

For 'date' only

  `'format'`      the date output format (i.E. 'yyyy-mm-dd')

For 'submit' only

  `'value'`       will be the text on the button. (defaults to 'Submit')


  
### form validation?

This package will auto-check any element based on it's type upon onBlur/onFocusOut event. Any error will be made visually by coloring the field with the missing or wrong input with a `.grid-form-error` class. Any other validation is up to you in your `Template.YOURTEMPLATENAME.events();` function. **Do not forget** to use the `id="YOURID"` at the specific `{{#gridElement}}` you want to extend or validate. This is helpful if not mandatory once you like to add some date picker, auto-complete typeahead or any other fun jQuery addition. There are lots of packages already available for those things so save yourself some time and do a `meteor search WHATEVERYOULIKE`.

### now what?

This is my first public meteor package, so please feel free to [contact me](https://twitter.com/herrhelms) for comments, suggestions and critique, or **contribute to the code and extend this package** and don't forget to give kudos and/or a star to [Kumail](https://github.com/kumailht). Happy grid-forming...

