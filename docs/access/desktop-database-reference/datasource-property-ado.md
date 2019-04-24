---
title: DataSource 属性 (ADO)
TOCTitle: DataSource property (ADO)
ms:assetid: 5c5d6c9b-b7d4-45a5-0f6a-a5580a74361e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249325(v=office.15)
ms:contentKeyID: 48545087
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0dec30715d1eb4e31d7490db4cedd015ecf3c040
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294468"
---
# <a name="datasource-property-ado"></a>DataSource 属性 (ADO)


**适用于**：Access 2013、Office 2013

指示一个对象，其中包含要表示为 [Recordset](recordset-object-ado.md) 对象的数据。

## <a name="remarks"></a>注解

此属性用于使用数据环境创建数据绑定控件。数据环境负责维护数据（数据源）集合，其中包含命名的将用 **Recordset** 对象表示的对象（*数据成员*）*。*

[DataMember](datamember-property-ado.md) 和 **DataSource** 属性必须一起使用。

所引用的对象必须实现 **IDataSource** 接口，且必须包含 **IRowset** 接口。

**用法**

```vb
    Dim rs as New ADODB.Recordset
    rs.DataMember = "Command"     'Name of the rowset to bind to
    Set rs.DataSource = myDE      'Name of the object containing an IRowset
```
