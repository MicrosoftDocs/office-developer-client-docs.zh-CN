---
title: Source 属性（ADO 记录集）
TOCTitle: Source property (ADO Recordset)
ms:assetid: 523ea81e-d011-8d87-436e-084b6eba0908
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249269(v=office.15)
ms:contentKeyID: 48544843
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a58ac3c5315daef040ba6a999753a19f76504087
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25947566"
---
# <a name="source-property-ado-recordset"></a><span data-ttu-id="74b58-102">Source 属性（ADO 记录集）</span><span class="sxs-lookup"><span data-stu-id="74b58-102">Source property (ADO Recordset)</span></span>


<span data-ttu-id="74b58-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="74b58-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="74b58-104">指示 [Recordset](recordset-object-ado.md) 对象的数据源。</span><span class="sxs-lookup"><span data-stu-id="74b58-104">Indicates the data source for a [Recordset](recordset-object-ado.md) object.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="74b58-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="74b58-105">Settings and return values</span></span>

<span data-ttu-id="74b58-106">设置一个 **String** 值或 [Command](command-object-ado.md) 对象引用；仅返回一个 **String** 值，该值指示 **Recordset** 的数据源。</span><span class="sxs-lookup"><span data-stu-id="74b58-106">Sets a **String** value or [Command](command-object-ado.md) object reference; returns only a **String** value that indicates the source of the **Recordset**.</span></span>

## <a name="remarks"></a><span data-ttu-id="74b58-107">备注</span><span class="sxs-lookup"><span data-stu-id="74b58-107">Remarks</span></span>

<span data-ttu-id="74b58-108">使用 **Source** 属性可指定使用 **Command** 对象变量、SQL 语句、存储过程或表名之一的 **Recordset** 对象的数据源。</span><span class="sxs-lookup"><span data-stu-id="74b58-108">Use the **Source** property to specify a data source for a **Recordset** object using one of the following: a **Command** object variable, an SQL statement, a stored procedure, or a table name.</span></span>

<span data-ttu-id="74b58-p101">如果将 **Source** 属性设置为 **Command** 对象，则 [Recordset](activeconnection-property-ado.md) 对象的 **ActiveConnection** 属性将继承所指定的 **Command** 对象的 **ActiveConnection** 属性值。然而，读取 **Source** 属性不会返回 **Command** 对象；而会返回 [Source](commandtext-property-ado.md) 属性被设置为的 **Command** 对象的 **CommandText** 属性。</span><span class="sxs-lookup"><span data-stu-id="74b58-p101">If you set the **Source** property to a **Command** object, the [ActiveConnection](activeconnection-property-ado.md) property of the **Recordset** object will inherit the value of the **ActiveConnection** property for the specified **Command** object. However, reading the **Source** property does not return a **Command** object; instead, it returns the [CommandText](commandtext-property-ado.md) property of the **Command** object to which you set the **Source** property.</span></span>

<span data-ttu-id="74b58-111">如果**Source**属性是 SQL 语句、 存储的过程或表名，您可以通过传递[Open](open-method-ado-recordset.md)方法调用合适的*Options*参数来优化性能。</span><span class="sxs-lookup"><span data-stu-id="74b58-111">If the **Source** property is an SQL statement, a stored procedure, or a table name, you can optimize performance by passing the appropriate *Options* argument with the [Open](open-method-ado-recordset.md) method call.</span></span>

<span data-ttu-id="74b58-112">对于关闭的 **Recordset** 对象， **Source** 属性为可读/写属性；对于打开的 **Recordset** 对象，则为只读属性。</span><span class="sxs-lookup"><span data-stu-id="74b58-112">The **Source** property is read/write for closed **Recordset** objects and read-only for open **Recordset** objects.</span></span>

