---
title: Close 方法的 ActiveX 数据对象 (ADO)
TOCTitle: Close Method (ADO)
ms:assetid: 26a7cced-ebeb-70be-f5de-96a35711bc37
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249029(v=office.15)
ms:contentKeyID: 48543818
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6623af069ddbf74dc94fa173160003711779cc8a
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466699"
---
# <a name="close-method-ado"></a><span data-ttu-id="cc975-102">Close 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="cc975-102">Close Method (ADO)</span></span>


<span data-ttu-id="cc975-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="cc975-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="cc975-104">用于关闭打开的对象和任何相关的对象。</span><span class="sxs-lookup"><span data-stu-id="cc975-104">Closes an open object and any dependent objects.</span></span>

## <a name="syntax"></a><span data-ttu-id="cc975-105">语法</span><span class="sxs-lookup"><span data-stu-id="cc975-105">Syntax</span></span>

<span data-ttu-id="cc975-106">*object*.Close</span><span class="sxs-lookup"><span data-stu-id="cc975-106">*object*.Close</span></span>

## <a name="remarks"></a><span data-ttu-id="cc975-107">说明</span><span class="sxs-lookup"><span data-stu-id="cc975-107">Remarks</span></span>

<span data-ttu-id="cc975-108">使用 **Close** 方法可以关闭 [Connection](connection-object-ado.md)、[Record](record-object-ado.md)、[Recordset](recordset-object-ado.md) 或 [Stream](stream-object-ado.md) 对象，以释放任何关联的系统资源。</span><span class="sxs-lookup"><span data-stu-id="cc975-108">Use the **Close** method to close a [Connection](connection-object-ado.md), a [Record](record-object-ado.md), a [Recordset](recordset-object-ado.md), or a [Stream](stream-object-ado.md) object to free any associated system resources.</span></span> <span data-ttu-id="cc975-109">关闭对象不会将它从内存中删除，您仍然可以更改它的属性设置，并在以后再次打开它。</span><span class="sxs-lookup"><span data-stu-id="cc975-109">Closing an object does not remove it from memory; you can change its property settings and open it again later.</span></span> <span data-ttu-id="cc975-110">若要完全消除内存中的对象，请关闭对象后设置为*Nothing* （在 Visual Basic) 的对象变量。</span><span class="sxs-lookup"><span data-stu-id="cc975-110">To completely eliminate an object from memory, set the object variable to *Nothing* (in Visual Basic) after closing the object.</span></span>

<span data-ttu-id="cc975-111">**Connection**</span><span class="sxs-lookup"><span data-stu-id="cc975-111">**Connection**</span></span>

<span data-ttu-id="cc975-p102">如果使用 **Close** 方法关闭 **Connection** 对象，则同时也会关闭与连接关联的任何活动的 **Recordset** 对象。与要关闭的 [Connection](command-object-ado.md) 对象关联的 **Command** 对象不会关闭，但它不再与 **Connection** 对象关联，即其 [ActiveConnection](activeconnection-property-ado.md) 属性将设置为 **Nothing** 。此外， **Command** 对象的 [Parameters](parameters-collection-ado.md) 集合中的任何提供程序定义的参数都将被清除。</span><span class="sxs-lookup"><span data-stu-id="cc975-p102">Using the **Close** method to close a **Connection** object also closes any active **Recordset** objects associated with the connection. A [Command](command-object-ado.md) object associated with the **Connection** object you are closing will persist, but it will no longer be associated with a **Connection** object; that is, its [ActiveConnection](activeconnection-property-ado.md) property will be set to **Nothing**. Also, the **Command** object's [Parameters](parameters-collection-ado.md) collection will be cleared of any provider-defined parameters.</span></span>

<span data-ttu-id="cc975-p103">稍后可以调用 [Open](open-method-ado-connection.md) 方法重新建立与相同数据源或其他数据源的连接。当 **Connection** 对象关闭时，调用任何需要与数据源建立打开连接的方法都会产生错误。</span><span class="sxs-lookup"><span data-stu-id="cc975-p103">You can later call the [Open](open-method-ado-connection.md) method to re-establish the connection to the same, or another, data source. While the **Connection** object is closed, calling any methods that require an open connection to the data source generates an error.</span></span>

<span data-ttu-id="cc975-p104">如果连接上有打开的 **Recordset** 对象，此时关闭 **Connection** 对象将回滚所有 **Recordset** 对象中的任何挂起更改。如果在进行事务处理时显式关闭 **Connection** 对象（调用 **Close** 方法），则将产生错误。如果在进行事务处理时 **Connection** 对象超出范围，ADO 将自动回滚事务。</span><span class="sxs-lookup"><span data-stu-id="cc975-p104">Closing a **Connection** object while there are open **Recordset** objects on the connection rolls back any pending changes in all of the **Recordset** objects. Explicitly closing a **Connection** object (calling the **Close** method) while a transaction is in progress generates an error. If a **Connection** object falls out of scope while a transaction is in progress, ADO automatically rolls back the transaction.</span></span>

<span data-ttu-id="cc975-120">**Recordset、Record、Stream**</span><span class="sxs-lookup"><span data-stu-id="cc975-120">**Recordset, Record, Stream**</span></span>

<span data-ttu-id="cc975-p105">使用 **Close** 方法关闭 **Recordset** 、 **Record** 或 **Stream** 对象会释放关联的数据以及通过该特定对象访问数据所需的任何独占访问。稍后可以调用 [Open](open-method-ado-recordset.md) 方法重新打开具有相同属性或已修改属性的对象。</span><span class="sxs-lookup"><span data-stu-id="cc975-p105">Using the **Close** method to close a **Recordset**, **Record**, or **Stream** object releases the associated data and any exclusive access you may have had to the data through this particular object. You can later call the [Open](open-method-ado-recordset.md) method to reopen the object with the same, or modified, attributes.</span></span>

<span data-ttu-id="cc975-123">在 **Recordset** 对象处于关闭状态时，调用任何需要实时游标的方法都将产生错误。</span><span class="sxs-lookup"><span data-stu-id="cc975-123">While a **Recordset** object is closed, calling any methods that require a live cursor generates an error.</span></span>

<span data-ttu-id="cc975-p106">如果正处于即时更新模式下且正在进行编辑，则调用 **Close** 方法将产生错误。相反，应当首先调用 [Update](update-method-ado.md) 或 [CancelUpdate](cancelupdate-method-ado.md) 方法。如果在批更新模式下关闭 **Recordset** 对象，那么自上次调用 [UpdateBatch](updatebatch-method-ado.md) 以来所做的所有更改都将丢失。</span><span class="sxs-lookup"><span data-stu-id="cc975-p106">If an edit is in progress while in immediate update mode, calling the **Close** method generates an error; instead, call the [Update](update-method-ado.md) or [CancelUpdate](cancelupdate-method-ado.md) method first. If you close the **Recordset** object while in batch update mode, all changes since the last [UpdateBatch](updatebatch-method-ado.md) call are lost.</span></span>

<span data-ttu-id="cc975-126">如果使用 [Clone](clone-method-ado.md) 方法创建打开的 **Recordset** 对象的副本，则关闭原始对象或克隆不会影响其他任何副本。</span><span class="sxs-lookup"><span data-stu-id="cc975-126">If you use the [Clone](clone-method-ado.md) method to create copies of an open **Recordset** object, closing the original or a clone does not affect any of the other copies.</span></span>

