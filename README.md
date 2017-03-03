[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/jifalops/geo-query)

# geo-query
A Polymer web component wrapper for GeoFire's GeoQuery.

## Installation

```
bower install --save geo-query
```

## Usage
* Pass it a GeoFire instance that references your database.
* Specify the center point and search radius.
* Either use the `resultsArray`, `resultsObject`, or listen for events.

## Demo
<!--
```
<custom-element-demo>
  <template is="dom-bind" id="scope">
    <script src="../webcomponentsjs/webcomponents-lite.js"></script>    
    <link rel="import" href="geo-query.html">
    <script src="../../firebase/firebase.js"></script>
    <script>
      firebase.initializeApp({
        apiKey: "AIzaSyD0irm8Cxx8qq1Dg7n07COfbA11_0gUsUc",
        authDomain: "geo-fire-demo-b0bdf.firebaseapp.com",
        databaseURL: "https://geo-fire-demo-b0bdf.firebaseio.com"
      });
      var geofireDbRef = firebase.app().database().ref('geofire1');
      function resultToString(result) {
        return '[' + result.location + '] (' + Math.round(result.distance) + ' km)';
      }
    </script>
    <next-code-block></next-code-block>
  </template>
</custom-element-demo>
```
-->

```html
<input placeholder="latitude" value="{{lat::input}}"/><br />
<input placeholder="longitude" value="{{lng::input}}"/><br />
<input placeholder="radius (km)" value="{{rad::input}}"/><br />
<geo-query   
  geofire="[[geofire]]"
  lat="[[lat]]"
  lng="[[lng]]"
  radius="[[rad]]"
  results-array="{{resultsArray}}">
</geo-query>
<div>[[resultsArray.length]] results.</div>
<template is="dom-repeat" items="[[resultsArray]]">
  <div>[[_resultToString(item)]]</div>
</template>
<script>
  var scope = document.getElementById('scope');
  scope.geofire = new GeoFire(geofireDbRef);
  scope._resultToString = function(result) { return resultToString(result); };
</script>
```

Full demo:
[webcomponents.org](https://www.webcomponents.org/element/jifalops/geo-query/demo/demo/index.html)
| [github](https://jifalops.github.io/geo-query/components/geo-query/demo/).

API: [webcomponents.org](https://www.webcomponents.org/element/jifalops/geo-query/geo-query)
| [github](https://jifalops.github.io/geo-query).


## Contributing

1. Fork it on Github.
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request

## License

[MIT](https://opensource.org/licenses/MIT)
