# Plugins for adminer

Repository contains some useful plugins for [Adminer](http://adminer.cz/) to ease up your workflow.

## Plugins for PHPUnit

A central concept of PHPUnit's Database Extension are [DataSets and DataTables](http://phpunit.de/manual/current/en/database.html#database.available-implementations). Here can be found two Adminer plugins to export database structure and data to PHPUnit's File-Based DataSets and DataTables.

- [Flat XML DataSet](#flat-xml-dataset)
- [XML DataSet](#xml-dataset)
 

### Flat XML DataSet {#flat-xml-dataset}
Exports database to dataset, where each node of `<dataset />` has structure `<table col='value' ... />`.
```
<?xml version="1.0" ?>
<dataset>
    <guestbook id="1" content="Hello buddy!" user="joe" created="2010-04-24 17:15:23" />
    <guestbook id="2" content="I like it!" user="nancy" created="2010-04-26 12:14:20" />
</dataset>
```

### XML DataSet {#xml-dataset}
Exports database to dataset, where each node of `<dataset />` has structure `<table><column>columnName</column> ... <row><value>value</value> ... </row></table>`.
```
<?xml version="1.0" ?>
<dataset>
    <table name="guestbook">
        <column>id</column>
        <column>content</column>
        <column>user</column>
        <column>created</column>
        <row>
            <value>1</value>
            <value>Hello buddy!</value>
            <value>joe</value>
            <value>2010-04-24 17:15:23</value>
        </row>
        <row>
            <value>2</value>
            <value>I like it!</value>
            <null />
            <value>2010-04-26 12:14:20</value>
        </row>
    </table>
</dataset>
```