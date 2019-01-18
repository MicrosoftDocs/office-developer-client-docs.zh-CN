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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28700029"
---
# <a name="datasource-property-ado"></a><span data-ttu-id="10683-102">DataSource 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="10683-102">DataSource property (ADO)</span></span>


<span data-ttu-id="10683-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="10683-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="10683-104">指示一个对象，其中包含要表示为 [Recordset](recordset-object-ado.md) 对象的数据。</span><span class="sxs-lookup"><span data-stu-id="10683-104">Indicates an object that contains data to be represented as a [Recordset](recordset-object-ado.md) object.</span></span>

## <a name="remarks"></a><span data-ttu-id="10683-105">备注</span><span class="sxs-lookup"><span data-stu-id="10683-105">Remarks</span></span>

<span data-ttu-id="10683-p101">此属性用于使用数据环境创建数据绑定控件。数据环境负责维护数据（数据源）集合，其中包含命名的将用 **Recordset** 对象表示的对象（*数据成员*）*。*</span><span class="sxs-lookup"><span data-stu-id="10683-p101">This property is used to create data-bound controls with the Data Environment. The Data Environment maintains collections of data (data sources) containing named objects (*data members*) that will be represented as a **Recordset** object *.*</span></span>

<span data-ttu-id="10683-108">[DataMember](datamember-property-ado.md) 和 **DataSource** 属性必须一起使用。</span><span class="sxs-lookup"><span data-stu-id="10683-108">The [DataMember](datamember-property-ado.md) and **DataSource** properties must be used in conjunction.</span></span>

<span data-ttu-id="10683-109">所引用的对象必须实现 **IDataSource** 接口，且必须包含 **IRowset** 接口。</span><span class="sxs-lookup"><span data-stu-id="10683-109">The object referenced must implement the **IDataSource** interface and must contain an **IRowset** interface.</span></span>

<span data-ttu-id="10683-110">**用法**</span><span class="sxs-lookup"><span data-stu-id="10683-110">**Usage**</span></span>

```vb
    Dim rs as New ADODB.Recordset
    rs.DataMember = "Command"     'Name of the rowset to bind to
    Set rs.DataSource = myDE      'Name of the object containing an IRowset
```
