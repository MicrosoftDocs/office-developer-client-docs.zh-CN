---
title: Field2 属性 (DAO)
TOCTitle: Expression Property
ms:assetid: 8ae9db2c-7460-5bfc-0dc4-3f87e5ab30ff
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197109(v=office.15)
ms:contentKeyID: 48546205
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 603dfaa9a54ddfe769b96a57b790b4657abbeb14
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292816"
---
# <a name="field2expression-property-dao"></a>Field2 属性 (DAO)

**适用于**：Access 2013、Office 2013

获取或设置一个表达式, 该表达式代表计算字段的公式。 读/写 **String**。

## <a name="version-information"></a>版本信息

添加的版本: Access 2010

## <a name="syntax"></a>语法

*表达式*。表达式

*表达式*一个代表**Field2**对象的变量。

## <a name="remarks"></a>注解

在 Access 2013 中, 可以创建用于计算值的表字段。 计算可以包含来自同一个表中的字段以及内置的 Access 函数的值。

计算不能包含其他表或查询中的字段。

计算结果为只读。

## <a name="example"></a>示例

以下示例显示了如何创建计算字段。 CreateField 方法将创建名为 **FullName** 的字段。 Expression 属性随后将被设为用于计算字段值的表达式。

**示例代码提供方：**[Microsoft Access 2010 程序员参考](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。

```vb
    Sub CreateCalculatedField()
        Dim dbs As DAO.Database
        Dim tdf As DAO.TableDef
        Dim fld As DAO.Field2
        
        ' get the database
        Set dbs = CurrentDb()
        
        ' create the table
        Set tdf = dbs.CreateTableDef("tblContactsCalcField")
        
        ' create the fields: first name, last name
        tdf.Fields.Append tdf.CreateField("FirstName", dbText, 20)
        tdf.Fields.Append tdf.CreateField("LastName", dbText, 20)
        
        ' create the calculated field: full name
        Set fld = tdf.CreateField("FullName", dbText, 50)
        fld.Expression = "[FirstName] & "" "" & [LastName]"
        tdf.Fields.Append fld
        
        ' append the table and cleanup
        dbs.TableDefs.Append tdf
        
    Cleanup:
        Set fld = Nothing
        Set tdf = Nothing
        Set dbs = Nothing
    End Sub
```

