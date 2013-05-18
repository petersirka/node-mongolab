Simple node.js MongoDB REST client for MongoLab.com
===================================================

- [MongoLab](http://www.mongolab.com) MongoDB-as-a-Service
- [partial.js / Web application framework for node.js](http://partialjs.com)
- [node.js NoSQL embedded database](https://github.com/petersirka/nosql)

***

## NPM mongolab

- create on your desktop empty directory with name: website
- open terminal and find this directory: cd /Desktop/website/
- write and run on terminal:

```text
$ npm install mongolab
```

## Methods

```js
/*
    MongoDB constructor
    @database {String}
    @key {String} :: get your key from https://mongolab.com/user?username=[username]
*/
MongoDB(database, key);
 
/*
    Usage / Constructor
    @database {String}
    @key {String} :: get your key from https://mongolab.com/user?username=[username]
    return {MongoDB};
*/
require('mongolab').init(database, key);
 
/*
    All collection in database
    @cb {Function} :: function(error, object)
    return {MongoDB}
*/
mongodb.collections(cb);
 
/*
    Get all documents
    @collection {String}
    @params {Object}
    @cb {Function} :: function(error, object)
    return {MongoDB}
*/
mongodb.documents(collection, params, cb);
 
 
// Params options
// REST API www.mongolab.com documentation: https://support.mongolab.com/entries/20433053-rest-api-for-mongodb
 
// q<query> :: restrict results by the specified JSON query
// q = {} :: object
// where = {} :: object
// query = {} :: object
 
// s<sort> :: specify the order in which to sort each specified field (1- ascending; -1 - descending)
// s = {} :: object
// sort = {} :: object
// asc = ['name', 'age'] :: array
// desc = ['name', 'age'] :: array
 
// f<set of fields> :: specify the set of fields to include or exclude in each document (1 - include; 0 - exclude)
// f = {} :: object
// include = ['name', 'age'] :: array
// exclude = ['name', 'age'] :: array
 
// c<boolean> :: return the result count for this query
// c = true :: boolean
// count = true :: boolean
 
// fo<boolean> :: return a single document from the result set (same as findOne() using the mongo shell
// fo = true :: boolean
// first = true :: boolean
 
// sk<num results to skip> :: specify the number of results to skip in the result set; useful for paging
// sk = 10 :: number
// skip = 10 :: number
 
// l<limit> :: specify the limit for the number of results (default is 1000)
// l = 10 :: number
// take = 10 :: number
// max = 10 :: number
// top = 10 :: number
// limit = 10 :: number
 
// --------
// UPDATING
// --------
 
// m<boolean> :: update all documents
// m = true :: boolean
// all = true :: boolean
// update-all = true :: boolean
 
// u<boolean> :: insert the document defined in the request body if none match the specified query
// u = true :: boolean
// upsert = true :: boolean
 
var params = { where: { age: 28 }, asc: ['age'] };
 
mongodb.documents('users', params, function(err, data) {
     
});
 
/*
    Insert document / documents
    @collection {String}
    @documents {Object or Object array}
    @cb {Function} :: function(error, object)
    return {MongoDB}
*/
mongodb.insert(collection, documents, cb);
 
/*
    Update document / documents
    @collection {String}
    @condition {Object or Object array}
    @params {Object}
    @cb {Function} :: function(error, object)
    return {MongoDB}
*/
mongodb.update(collection, condition, params, cb);
 
/*
    Find document by Id
    @collection {String}
    @id {String or Number}
    @cb {Function} :: function(error, object)
    return {MongoDB}
*/
mongodb.findId(collection, id, cb);
 
/*
    Update document by Id
    @collection {String}
    @id {String or Number}
    @document {Object}
    @cb {Function} :: function(error, object)
    return {MongoDB}
*/
mongodb.updateId(collection, id, document, cb);
 
/*
    Delete document by Id
    @collection {String}
    @id {String or Number}
    @cb {Function} :: function(error, object)
    return {MongoDB}
*/
mongodb.deleteId(collection, id, cb);
 
/*
    Run command
    @command {Object}
    @cb {Function} :: function(error, object)
    return {MongoDB}
*/
mongodb.command(command, cb);
```

***

## The MIT License

Copyright (c) 2012-2013 Peter Širka <petersirka@gmail.com>

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the 'Software'), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

## Contact

[www.petersirka.sk](http://www.petersirka.sk)
