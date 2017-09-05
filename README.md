[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/jifalops/geo-query)

# geo-query
A Polymer web component wrapper for GeoFire's GeoQuery.

## Installation

```
bower i -S geo-query        # Polymer 2.0 hybrid (1.x compatible)
bower i -S geo-query#0.3.1  # Polymer 1.x based
```

## Usage
* Set `app-name` and `path` (just like on polymerfire elements) to define the
  geofire instance.
* Set `lat`, `lng`, and `radius` to search for entries in an area.


## Demo
<!--
```
<custom-element-demo>
  <template>
    <script src="../webcomponentsjs/webcomponents-lite.js"></script>
    <link rel="import" href="../paper-checkbox/paper-checkbox.html">
    <link rel="import" href="geo-query.html">
    <firebase-app
      api-key="AIzaSyD0irm8Cxx8qq1Dg7n07COfbA11_0gUsUc"
      auth-domain="geo-fire-demo-b0bdf.firebaseapp.com"
      database-url="https://geo-fire-demo-b0bdf.firebaseio.com">
    </firebase-app>
    <dom-bind>
      <template is="dom-bind">
        <next-code-block></next-code-block>
      </template>
    </dom-bind>
  </template>
</custom-element-demo>
```
-->

```html
<geo-query log
  path="/geofire1"
  data="{{results}}"
  lat="[[lat]]"
  lng="[[lng]]"
  radius="[[rad]]"
  disabled="[[disabled]]">
</geo-query>
<h4>Search</h4>
<input placeholder="latitude" value="{{lat::input}}"/><br />
<input placeholder="longitude" value="{{lng::input}}"/><br />
<input placeholder="radius (km)" value="{{rad::input}}"/><br />
<paper-checkbox checked="{{disabled}}">Disable</paper-checkbox><br />
<p>[[results.length]] results.</p>
<table>
  <dom-repeat items="[[results]]">
    <template>
      <tr><td>[[item.lat]]</td><td>[[item.lng]]</td><td>[[item.distance]] km</td></tr>
    </template>
  </dom-repeat>
</table>
```

Full demo:
[webcomponents.org](https://www.webcomponents.org/element/jifalops/geo-query/demo/demo/index.html)
| [github](https://jifalops.github.io/geo-query/components/geo-query/demo/).

API: [webcomponents.org](https://www.webcomponents.org/element/jifalops/geo-query/geo-query)

## Breaking changes
*0.4 -> 1.0*

* `geo-query` now implements `polymerfire/FirebaseDatabaseBehavior`
* `idle` has been renamed to `disabled`
* `geofire` is now a computed property which depends on `app-name` (optional) and `path`.
* Use `data` (optionally combined with `asObject`) in place of the old `resultsArray` and
  `resultsObject` properties.


## Contributing

1. Fork it on Github.
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request

## License

[MIT](https://opensource.org/licenses/MIT)
