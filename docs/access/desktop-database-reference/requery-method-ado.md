---
title: Requery 方法 (ADO)
TOCTitle: Requery method (ADO)
ms:assetid: 1062d907-979f-020a-b2ed-94e11c0e7d08
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248871(v=office.15)
ms:contentKeyID: 48543292
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 588f99d495716ca3c40376ce323d7c1557da9319
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25925798"
---
# <a name="requery-method-ado"></a><span data-ttu-id="cf5e4-102">Requery 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="cf5e4-102">Requery method (ADO)</span></span>


<span data-ttu-id="cf5e4-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="cf5e4-103">**Applies to**: Access 2013, Office 2013</span></span>



<span data-ttu-id="cf5e4-104">通过重新执行对象所基于的查询，更新 [Recordset](recordset-object-ado.md) 对象中的数据。</span><span class="sxs-lookup"><span data-stu-id="cf5e4-104">Updates the data in a [Recordset](recordset-object-ado.md) object by re-executing the query on which the object is based.</span></span>

## <a name="syntax"></a><span data-ttu-id="cf5e4-105">语法</span><span class="sxs-lookup"><span data-stu-id="cf5e4-105">Syntax</span></span>

<span data-ttu-id="cf5e4-106">*记录集*。Requery*选项*</span><span class="sxs-lookup"><span data-stu-id="cf5e4-106">*recordset*.Requery *Options*</span></span>

## <a name="parameter"></a><span data-ttu-id="cf5e4-107">参数</span><span class="sxs-lookup"><span data-stu-id="cf5e4-107">Parameter</span></span>

  - <span data-ttu-id="cf5e4-108">*Options*</span><span class="sxs-lookup"><span data-stu-id="cf5e4-108">*Options*</span></span>

  - <span data-ttu-id="cf5e4-p101">可选。包含影响此操作的 [ExecuteOptionEnum](executeoptionenum.md) 和 [CommandTypeEnum](commandtypeenum.md) 值的位掩码。</span><span class="sxs-lookup"><span data-stu-id="cf5e4-p101">Optional. A bitmask that contains [ExecuteOptionEnum](executeoptionenum.md) and [CommandTypeEnum](commandtypeenum.md) values affecting this operation.</span></span>


> [!NOTE]
> <P><span data-ttu-id="cf5e4-111">如果<EM>选项</EM>设置为<STRONG>adAsyncExecute</STRONG>，此操作将异步执行，且当它结束时，将发布<A href="willchangerecordset-and-recordsetchangecomplete-events-ado.md">RecordsetChangeComplete</A>事件。</span><span class="sxs-lookup"><span data-stu-id="cf5e4-111">If <EM>Options</EM> is set to <STRONG>adAsyncExecute</STRONG>, this operation will execute asynchronously and a <A href="willchangerecordset-and-recordsetchangecomplete-events-ado.md">RecordsetChangeComplete</A> event will be issued when it concludes.</span></span></P>



<span data-ttu-id="cf5e4-112">**adExecuteNoRecords** 或 **adExecuteStream** 的 **ExecuteOpenEnum** 值不应当与 **Requery** 一起使用。</span><span class="sxs-lookup"><span data-stu-id="cf5e4-112">The **ExecuteOpenEnum** values of **adExecuteNoRecords** or **adExecuteStream** should not be used with **Requery**.</span></span>

## <a name="remarks"></a><span data-ttu-id="cf5e4-113">说明</span><span class="sxs-lookup"><span data-stu-id="cf5e4-113">Remarks</span></span>

<span data-ttu-id="cf5e4-p102">**Requery** 方法用于通过重新发布原始命令和再次检索数据，从数据源刷新 **Recordset** 对象的整个内容。调用此方法的效果相当于依次调用 [Close](close-method-ado.md) 和 [Open](open-method-ado-recordset.md) 方法。如果正在编辑当前记录或添加新记录，那么将发生错误。</span><span class="sxs-lookup"><span data-stu-id="cf5e4-p102">Use the **Requery** method to refresh the entire contents of a **Recordset** object from the data source by reissuing the original command and retrieving the data a second time. Calling this method is equivalent to calling the [Close](close-method-ado.md) and [Open](open-method-ado-recordset.md) methods in succession. If you are editing the current record or adding a new record, an error occurs.</span></span>

<span data-ttu-id="cf5e4-p103">当 **Recordset** 对象打开时，用于定义游标特性的属性（[CursorType](cursortype-property-ado.md)、[LockType](locktype-property-ado.md)、[MaxRecords](maxrecords-property-ado.md) 等）为只读状态。因此，**Requery** 方法只能刷新当前游标。若要更改任意游标属性并查看结果，必须使用 [Close](close-method-ado.md) 方法，以使属性再次变为读/写状态。随后，可以更改属性设置并调用 [Open](open-method-ado-recordset.md) 方法重新打开游标。</span><span class="sxs-lookup"><span data-stu-id="cf5e4-p103">While the **Recordset** object is open, the properties that define the nature of the cursor ([CursorType](cursortype-property-ado.md), [LockType](locktype-property-ado.md), [MaxRecords](maxrecords-property-ado.md), and so forth) are read-only. Thus, the **Requery** method can only refresh the current cursor. To change any of the cursor properties and view the results, you must use the [Close](close-method-ado.md) method so that the properties become read/write again. You can then change the property settings and call the [Open](open-method-ado-recordset.md) method to reopen the cursor.</span></span>

