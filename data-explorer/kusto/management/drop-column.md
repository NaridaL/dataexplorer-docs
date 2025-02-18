---
title: drop column - Azure Data Explorer
description: This article describes drop column in Azure Data Explorer.
ms.reviewer: orspodek
ms.topic: reference
ms.date: 02/21/2023
---
# .drop column

Removes a column from a table.

To drop multiple columns from a table, see [drop multiple table columns](#drop-multiple-table-columns).

> [!NOTE]
> This command does not physically delete the data, and does not reduce the cost of storage
> for data that was already ingested.

> [!WARNING]
> This command is irreversible. All data in the column that is removed will no longer by queryable.
> Future commands to add that column back will not be able to restore the data.

## Permissions

You must have at least [Table Admin](access-control/role-based-access-control.md) permissions to run this command.

## Syntax

`.drop` `column` *TableName* `.` *ColumnName* [`ifexists`]

* `ifexists`: If specified, modifies the behavior so that the command won't fail on a non-existent column.

## Drop multiple table columns

Removes multiple columns from a table.

> [!NOTE]
> This command does not physically delete the data, and does not reduce the cost of storage
> for data that was already ingested.

> [!WARNING]
> This command is irreversible. All data in the column that is removed will no longer by queryable.
> Future commands to add those columns back will not be able to restore the data.

### Syntax

`.drop` `table` *TableName* `columns` `(` *Col1* [`,` *Col2*]... `)`
