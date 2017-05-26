# xls-parser #

###Description###
Parses xls, xslx and csv into json

### Install ###
````
npm install xls-parser
````

### Use node ###

````
'use strict';
var xlsParser = require('xls-parser');

function uploadFile(file) {
	
	var data = xlsParser.onFileSelection(file);
	console.log(data); //output xls json data
}

````

#### Example ####

Im using ng-file-upload in this example

To run example, navigate to the example folder

````
npm install
npm start
````

# html #
````
 <input type="file" ngf-select="vm.uploadFile($file)" ng-disabled="vm.disableUpload" accept=".csv, application/vnd.openxmlformats-officedocument.spreadsheetml.sheet, application/vnd.ms-excel"  />
 <pre>{{vm.data | json}}</pre>
````

# javascript #
````
var xlsParser = require('xls-parser');

function uploadFile(file) {
	
	vm.data = xlsParser.onFileSelection(file);
	
}
````
# input file #
````
Name	| Lastname	| Age
-------------------------
test1	| node		| 4
test2	| node		|
test3	| node		| 9
test4	| node		|

````

# output sample #
````
[
  {
    "Name": "test1",
    "Lastname": "node",
    "Age": 4
  },
  {
    "Name": "test2",
    "Lastname": "node"
  },
  {
    "Name": "test3",
    "Lastname": "node",
    "Age": 9
  },
  {
    "Name": "test4",
    "Lastname": "node"
  }
]
````