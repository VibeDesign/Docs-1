---
title: "xPDOManager.createObjectContainer"
_old_id: "1279"
_old_uri: "2.x/class-reference/xpdomanager/xpdomanager.createobjectcontainer"
---

## xPDOManager::createObjectContainer()

Creates the container for a persistent data object. In this implementation, a source container is a synonym for a MySQL database table. The table name will be generated by the schema; related tables will **not** be created, however.

## Syntax

API Docs: [createObjectContainer](http://api.modxcms.com/xpdo/om-mysql/xPDOManager_mysql.html#createObjectContainer)

``` php
void createObjectContainer (string $className)
```

## Examples

Create the table for the class 'Person':

``` php
$manager = $xpdo->getManager();
$manager->createObjectContainer('Person');
```

If you need to do this in a MODX Snippet, you'd use the $modx object, and you'd have to make sure you added your package (and its model classes) first:

``` php
$modx->addPackage('yourpkg',MODX_CORE_PATH.'components/yourpkg/model/','prefix_');
$manager = $modx->getManager();
$manager->createObjectContainer('Myobject');
```

Note that the database prefix here is independent of the MODX prefix. You may have `modx_` for your MODX prefix and `mypkg_` for your package's tables.
