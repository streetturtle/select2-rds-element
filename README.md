# select2-rds-element

Polymer based element which represents select2 functionality with loading data from a remote data source.

This project is created just to show how to implement such component. Since some customization should be done I think publishing this component would be useless.

## Demo

To see how it works locally clone this repo and run the project:

```
git clone https://github.com/streetturtle/select2-rds-element.git
cd ./select2-rds-element
npm install
bower install
gulp serve
```  

## Custom select2

First you'll need to change the `url` parameter and `templateResult` and `templateSelection` methods in **select2-rds-element.html** according to your needs.

Then I would recommend to use wrappers around this element, so you'd have element specific to your needs, like in the example:

```
<link rel="import" href="./select2-rds-element.html">

<dom-module id="city-selector">

  <template>
    <p><h4>Selected city:</h4>
    {{selectedCity}}</p>
    <select2-rds-element placeholder="Select city..." selected-city={{selectedCity}}></select2-rdf-element>
  </template>

</dom-module>

<script>
  Polymer({
        is: 'city-selector',
        properties: {
          selectedCity: {
            type: String
          }
        }
      });
</script>
```
