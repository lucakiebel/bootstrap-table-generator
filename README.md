## Bootstrap 3 Table generator

This package is a dynamic table generator for Bootstrap 3 written in Php.
This package is fully tested and ready for use.

###Installation 

Begin by installing this package through Composer. Edit your project's `composer.json` file to require `"jacopo/bootstrap3tablegenerator": "dev-master"`.

	"require": {
		"jacopo/bootstrap3tablegenerator": "dev-master"
	},
	"minimum-stability" : "dev"

Next, update Composer from the Terminal:

    composer update

That's it. You successfully installed Bootstrap 3 table generator!

###Usage

To use te package you need to require `Jacopo\Bootstrap3Table\BootstrapTable`.
Here is an example for a quick usage of the tool:

```PHP
use Jacopo\Bootstrap3Table\BootstrapTable;

// create the generator class
$table = new BootstrapTable();
// set the configuration
$table->setConfig(array("table-hover"=>false,"table-condensed"=>true));
// Set header content
$table->setHeader(array("firstCol") );
// Add table rows
$table->addRows(array("cell1","cell2" ), array("custom-class1"));
// print the table
$table->setTableExtraClasses(array("extra-table"));

```

###Methods overview

The methods available are:

`setConfig`: set the base configuration of the table. Accepts an array of options. The option available are:

 `table-striped`: Adds zebra-striping to any table row .
 `table-bordered`: Add borders and rounded corners to the table.
 `table-hover`: Enable a hover state on table rows.
 `table-condensed`: Makes tables more compact by cutting cell padding in half.
 `table-responsive`: Makes table responsive.
 `id`: Set the id of the table.

You can also add extra css classes to the `<table>`tag. To do that you need to set the
`setTableExtraClasses()`method.

Example:

```PHP
$table = new BootstrapTable();
$table->setTableExtraClasses(array("extra-custom-class") );
``` 

`setHeader`: this method setup the header of the file, his only parameter is an array that contains the data of each `<th>`.

Example:

```PHP
$table = new BootstrapTable();
$table->setHeader(array("First header column data") );
```

`addRows`: add a row of data to the table. Accepts two params: the fist is the array of data, the second is an array of custom css classes to add to the `<tr>` tag.

Example:
```PHP
$table = new BootstrapTable();
$table->addRows(array("First data column data"), array("custom-class1") );
```

When you're done setting up you table you can just do `echo $table` and you'll see the table as html.
If you prefer you can get the html string of the table instead with `table->getHtml()` method.
