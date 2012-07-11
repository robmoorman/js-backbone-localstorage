# Backbone.sync Local Storage

## Requirements
* [Modernizr](http://modernizr.com/)

## Usage

Local Storage is optional for all your collections and models. At instantiation of your collection/model an object under the property `localStorage` should be present with an `id` inherited:

<pre>
var model = Backbone.Model.extend({
    localStorage: {
        id: "UniqueID",
        maxRefresh: 3600000 // optional time before the local storage will be refreshed with new data
    }
});
</pre>

Force your collections/models by setting the property `forceRefresh` to `true` in your options while executing the `fetch` method.