---
title: Source 属性 (ADO Recordset)
TOCTitle: Source Property (ADO Recordset)
ms:assetid: 523ea81e-d011-8d87-436e-084b6eba0908
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249269(v=office.15)
ms:contentKeyID: 48544843
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: db44459bf3629f6cedfbee023b0be9161ed3bb14
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25605259"
---
# <a name="source-property-ado-recordset"></a><span data-ttu-id="9dd8d-102">Source 属性 (ADO Recordset)</span><span class="sxs-lookup"><span data-stu-id="9dd8d-102">Source Property (ADO Recordset)</span></span>


<span data-ttu-id="9dd8d-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="9dd8d-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="9dd8d-104">指示 [Recordset](recordset-object-ado.md) 对象的数据源。</span><span class="sxs-lookup"><span data-stu-id="9dd8d-104">Indicates the data source for a [Recordset](recordset-object-ado.md) object.</span></span>

<span data-ttu-id="9dd8d-105"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="9dd8d-105"><<<<<<< HEAD</span></span>
## <a name="settings-and-return-values"></a><span data-ttu-id="9dd8d-106">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="9dd8d-106">Settings and Return Values</span></span>
=======
## <a name="settings-and-return-values"></a><span data-ttu-id="9dd8d-107">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="9dd8d-107">Settings and return values</span></span>
>>>>>>> <span data-ttu-id="9dd8d-108">master</span><span class="sxs-lookup"><span data-stu-id="9dd8d-108">master</span></span>

<span data-ttu-id="9dd8d-109">设置一个 **String** 值或 [Command](command-object-ado.md) 对象引用；仅返回一个 **String** 值，该值指示 **Recordset** 的数据源。</span><span class="sxs-lookup"><span data-stu-id="9dd8d-109">Sets a **String** value or [Command](command-object-ado.md) object reference; returns only a **String** value that indicates the source of the **Recordset**.</span></span>

## <a name="remarks"></a><span data-ttu-id="9dd8d-110">备注</span><span class="sxs-lookup"><span data-stu-id="9dd8d-110">Remarks</span></span>

<span data-ttu-id="9dd8d-111">使用 **Source** 属性可指定使用 **Command** 对象变量、SQL 语句、存储过程或表名之一的 **Recordset** 对象的数据源。</span><span class="sxs-lookup"><span data-stu-id="9dd8d-111">Use the **Source** property to specify a data source for a **Recordset** object using one of the following: a **Command** object variable, an SQL statement, a stored procedure, or a table name.</span></span>

<span data-ttu-id="9dd8d-p101">如果将 **Source** 属性设置为 **Command** 对象，则 [Recordset](activeconnection-property-ado.md) 对象的 **ActiveConnection** 属性将继承所指定的 **Command** 对象的 **ActiveConnection** 属性值。然而，读取 **Source** 属性不会返回 **Command** 对象；而会返回 [Source](commandtext-property-ado.md) 属性被设置为的 **Command** 对象的 **CommandText** 属性。</span><span class="sxs-lookup"><span data-stu-id="9dd8d-p101">If you set the **Source** property to a **Command** object, the [ActiveConnection](activeconnection-property-ado.md) property of the **Recordset** object will inherit the value of the **ActiveConnection** property for the specified **Command** object. However, reading the **Source** property does not return a **Command** object; instead, it returns the [CommandText](commandtext-property-ado.md) property of the **Command** object to which you set the **Source** property.</span></span>

<span data-ttu-id="9dd8d-114">如果**Source**属性是 SQL 语句、 存储的过程或表名，您可以通过传递[Open](open-method-ado-recordset.md)方法调用合适的*Options*参数来优化性能。</span><span class="sxs-lookup"><span data-stu-id="9dd8d-114">If the **Source** property is an SQL statement, a stored procedure, or a table name, you can optimize performance by passing the appropriate *Options* argument with the [Open](open-method-ado-recordset.md) method call.</span></span>

<span data-ttu-id="9dd8d-115">对于关闭的 **Recordset** 对象， **Source** 属性为可读/写属性；对于打开的 **Recordset** 对象，则为只读属性。</span><span class="sxs-lookup"><span data-stu-id="9dd8d-115">The **Source** property is read/write for closed **Recordset** objects and read-only for open **Recordset** objects.</span></span>

