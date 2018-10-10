---
title: DataMember 属性 (ADO)
TOCTitle: DataMember Property (ADO)
ms:assetid: f89e1d42-7993-764b-4e8a-2f449903f792
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250263(v=office.15)
ms:contentKeyID: 48548787
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3a67864ab135c59f146a27f997d4b0df63865a50
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468912"
---
# <a name="datamember-property-ado"></a><span data-ttu-id="4ca85-102">DataMember 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="4ca85-102">DataMember Property (ADO)</span></span>

<span data-ttu-id="4ca85-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="4ca85-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="4ca85-104">指示将从 [DataSource](datasource-property-ado.md) 属性所引用的对象中检索的数据成员的名称。</span><span class="sxs-lookup"><span data-stu-id="4ca85-104">Indicates the name of the data member that will be retrieved from the object referenced by the [DataSource](datasource-property-ado.md) property.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="4ca85-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="4ca85-105">Settings and Return Values</span></span>

<span data-ttu-id="4ca85-p101">设置或返回一个 **String** 值。该名称不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="4ca85-p101">Sets or returns a **String** value. The name is not case sensitive.</span></span>

## <a name="remarks"></a><span data-ttu-id="4ca85-108">备注</span><span class="sxs-lookup"><span data-stu-id="4ca85-108">Remarks</span></span>

<span data-ttu-id="4ca85-p102">此属性用于使用数据环境创建数据绑定控件。数据环境负责维护数据（数据源）集合，其中包含命名的将用 [Recordset](recordset-object-ado.md) 对象表示的对象（*数据成员*）*。*</span><span class="sxs-lookup"><span data-stu-id="4ca85-p102">This property is used to create data-bound controls with the Data Environment. The Data Environment maintains collections of data (data sources) containing named objects (*data members*) that will be represented as a [Recordset](recordset-object-ado.md) object *.*</span></span>

<span data-ttu-id="4ca85-111">**DataMember** 和 **DataSource** 属性必须一起使用。</span><span class="sxs-lookup"><span data-stu-id="4ca85-111">The **DataMember** and **DataSource** properties must be used in conjunction.</span></span>

<span data-ttu-id="4ca85-p103">**DataMember** 属性确定 **DataSource** 属性指定的哪个对象将用 **Recordset** 对象表示。设置此属性之前，相应的 **Recordset** 对象必须为关闭状态。如果 **DataMember** 属性未在 **DataSource** 属性之前设置，或者如果 **DataSource** 中指定的对象不能识别 **DataMember** 名称，则会生成错误。</span><span class="sxs-lookup"><span data-stu-id="4ca85-p103">The **DataMember** property determines which object specified by the **DataSource** property will be represented as a **Recordset** object. The **Recordset** object must be closed before this property is set. An error is generated if the **DataMember** property isn't set before the **DataSource** property, or if the **DataMember** name isn't recognized by the object specified in the **DataSource** property.</span></span>

<span data-ttu-id="4ca85-115">**用法**</span><span class="sxs-lookup"><span data-stu-id="4ca85-115">**Usage**</span></span>

```vb
    Dim rs as New ADODB.Recordset
    rs.DataMember = "Command"     'Name of the rowset to bind to
    Set rs.DataSource = myDE      'Name of the object containing an IRowset
```
