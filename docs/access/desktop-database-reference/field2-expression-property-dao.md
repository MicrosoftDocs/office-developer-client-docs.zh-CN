---
title: Field2.Expression 属性 (DAO)
TOCTitle: Expression Property
ms:assetid: 8ae9db2c-7460-5bfc-0dc4-3f87e5ab30ff
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197109(v=office.15)
ms:contentKeyID: 48546205
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 603dfaa9a54ddfe769b96a57b790b4657abbeb14
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28720084"
---
# <a name="field2expression-property-dao"></a>Field2.Expression 属性 (DAO)

**适用于**： Access 2013、 Office 2013

获取或设置代表计算字段的公式的表达式。 读/写 **String**。

## <a name="version-information"></a>版本信息

添加的版本： Access 2010

## <a name="syntax"></a>语法

*表达式*。表达式

*表达式*一个代表**Field2**对象的变量。

## <a name="remarks"></a>备注

您可以在 Access 2013 中创建计算值的表字段。 计算可以包括在同一个表以及内置访问函数从字段的值。

计算不能包含其他表或查询中的字段。

计算的结果是只读的。

## <a name="example"></a>示例

下面的示例演示如何创建计算的字段。 CreateField 方法创建一个名为**FullName**字段。 然后表达式属性设置为计算字段的值的表达式。

**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。

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

