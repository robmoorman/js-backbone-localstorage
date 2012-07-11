# Backbone.sync Local Storage

**Note:** this utility only applies for read methods in Backbone.sync

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

### Version number

Since stored data is outdated when a new version is deployed, you probably want to clear the current cache. By setting your version number before any server-activity takes place, the Local Storage will be cleared when different version is detected. This can be done by calling the static `BackboneLocalStorage.setVersion` method.