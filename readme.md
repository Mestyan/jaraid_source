---
title: "Readme: Project Jarāʾid source files"
author:
  - Till Grallert
  - Adam Mestyan
date: 2020-05-20
---

Currently all data is kept in a single TEI XML file that mirrors the original source with prose sections for the introduction and glossaries and with two tables that contain information on individual periodicals. Documentation of changes within the source file is not necessary since GitHub commits document the changes.

The data structure for each row in the table is as follows and can be copied in order to add information to the table:

```xml
<row xml:id="t1rxxx" n="xxx" role="data">
  <cell n="1">
     <date when="yyyy or yyyy-mm-dd">date of first publication</date>
  </cell>
  <cell n="2">month/day</cell>
  <cell n="3"><date when="yyyy or yyyy-mm-dd">date of last publication</date></cell>
  <cell n="4">
     <name>title of the periodical</name>
  </cell>
  <cell n="5">
     <placeName>place of publication</placeName>
  </cell>
  <cell n="6">
     <persName>name of publisher etc.</persName>
  </cell>
  <cell n="7">comments</cell>
  <cell n="8">source</cell>
  <cell n="9">holding institutions</cell>
</row>
```

Notes:
- new rows should be added at the bottom of the existing table.
- The `@n` attribute on `<row>` can be omitted and will later be added automatically.
- The `@xml:id` attribute is generated by incrementing the value of the last row of the table, i.e. if the last row has `@xml:id="t1r850"` the new row should be `@xml:id="t1r851"`

# Quick web display using TEI boilerplate

One can quickly view the most current data using `gh-pages` and XSLT 1 transformations in a web browser. To do so click [here](https://ProjectJaraid.github.io/jaraid_source/tei/jaraid_master.TEIP5.xml). If boilerplate does not work, the current data is displayed at projectjaraid.github.io.
