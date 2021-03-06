# Module for BaseX 8.4+ to handle OOXML Workbooks [ECMA-376]
===========================================================

This module help to read data and make simples updates from XML Workbooks files [ECMA-376] for BaseX 8.4+

## Installing this module

1. via command:
    ```REPO INSTALL OOXML-Module-for-BaseXdb.xqm```
    
2. via GUI:
 > * Option
 > * Packages ...
 > * Instal ...
 > * Select the file "OOXML-Module-for-BaseXdb.xqm"

## Use

Use the example below 

```xquery
import module namespace xlsx = 'http://basex.org/modules/ECMA-376/spreadsheetml';

(: Return the cell value of a worksheet :)
xlsx:get-cell-value('Libro1.xlsx','Hoja1','B1')

... 

(: Return the cells of a column :)
xlsx:get-col('Libro1.xlsx','Hoja1','B')

... 

(: Return the cells of a row :)
xlsx:get-row('Libro1.xlsx','Hoja1','13')

... 

(: Update the cell value of a worksheet :)
xlsx:set-cell-value('Libro1.xlsx','Hoja1','B1',23.45)

...

(: Export the content of a worksheet into simple table :)
xlsx:worksheet-to-table('Libro1.xlsx','Hoja1')
```

List of the current functions
-----------------------------

 * get-file: return a binary representation of the workbook file
 * get-sheets: return a element "sheets" containing the name of the workseet of the workbook
 * get-sharedStrings: return the Shared-String element contained in the workbook
 * get-calcChain: Returns the Calc-Chain contained in the workbook
 * get-worksheet-data: Returns the content of the worksheet 
 * get-row: Returns the content of a specified row in the worksheet
 * get-col: Returns the content of a specified column in the worksheet
 * get-cell: Returns the cell element specified in the worksheet
 * get-cell-value: Returns the cell value specified in the worksheet (2017-oct-03: fix the date value representation )
 * set-cell-value: Update the value of the cell (2017-oct-03: a big IF's replace with typeswitch )
 * worksheet-to-table: Export the worksheet data to an html table (2017-oct-03: fix the date value representation)
 * display-cell-value: return the correct format of the value of the cell
 * format-value: return the correct format value based on the excel format-code (0 to 49)
 * get-range: return a range element containing the cell in the specified range
 
 
 
 
