---
title: DataMember 属性 (ADO)
TOCTitle: DataMember property (ADO)
ms:assetid: f89e1d42-7993-764b-4e8a-2f449903f792
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250263(v=office.15)
ms:contentKeyID: 48548787
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 410f11af8daf3912dca9dc78a1cb9216ff8f8dd1
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28719881"
---
# <a name="datamember-property-ado"></a>DataMember 属性 (ADO)

**适用于**： Access 2013、 Office 2013

指示将从 [DataSource](datasource-property-ado.md) 属性所引用的对象中检索的数据成员的名称。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 **String** 值。该名称不区分大小写。

## <a name="remarks"></a>备注

此属性用于使用数据环境创建数据绑定控件。数据环境负责维护数据（数据源）集合，其中包含命名的将用 [Recordset](recordset-object-ado.md) 对象表示的对象（*数据成员*）*。*

**DataMember** 和 **DataSource** 属性必须一起使用。

**DataMember** 属性确定 **DataSource** 属性指定的哪个对象将用 **Recordset** 对象表示。设置此属性之前，相应的 **Recordset** 对象必须为关闭状态。如果 **DataMember** 属性未在 **DataSource** 属性之前设置，或者如果 **DataSource** 中指定的对象不能识别 **DataMember** 名称，则会生成错误。

**用法**

```vb
    Dim rs as New ADODB.Recordset
    rs.DataMember = "Command"     'Name of the rowset to bind to
    Set rs.DataSource = myDE      'Name of the object containing an IRowset
```
