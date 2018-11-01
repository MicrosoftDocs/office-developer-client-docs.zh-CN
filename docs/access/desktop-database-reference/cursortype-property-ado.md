---
title: CursorType 属性 (ADO)
TOCTitle: CursorType property (ADO)
ms:assetid: f42ded8f-9f92-ef03-a198-ffb892324611
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250239(v=office.15)
ms:contentKeyID: 48548682
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1d9560ad975d545015a02bb0e594777ced3cc8d3
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25886653"
---
# <a name="cursortype-property-ado"></a><span data-ttu-id="e6405-102">CursorType 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="e6405-102">CursorType property (ADO)</span></span>


<span data-ttu-id="e6405-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="e6405-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e6405-104">指示在 [Recordset](recordset-object-ado.md) 对象中使用的游标类型。</span><span class="sxs-lookup"><span data-stu-id="e6405-104">Indicates the type of cursor used in a [Recordset](recordset-object-ado.md) object.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="e6405-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="e6405-105">Settings and return values</span></span>

<span data-ttu-id="e6405-p101">设置或返回 [CursorTypeEnum](cursortypeenum.md) 值。默认值为 **adOpenForwardOnly** 。</span><span class="sxs-lookup"><span data-stu-id="e6405-p101">Sets or returns a [CursorTypeEnum](cursortypeenum.md) value. The default value is **adOpenForwardOnly**.</span></span>

## <a name="remarks"></a><span data-ttu-id="e6405-108">备注</span><span class="sxs-lookup"><span data-stu-id="e6405-108">Remarks</span></span>

<span data-ttu-id="e6405-109">使用 **CursorType** 属性可以指定打开 **Recordset** 对象时应使用的游标类型。</span><span class="sxs-lookup"><span data-stu-id="e6405-109">Use the **CursorType** property to specify the type of cursor that should be used when opening the **Recordset** object.</span></span>

<span data-ttu-id="e6405-p102">如果 **CursorLocation** 属性设置为 [adUseClient](cursorlocation-property-ado.md) ，则仅支持 **adOpenStatic** 设置。如果设置了不受支持的值，则不会导致出错；因此应改用最接近的受支持的 **CursorType** 。</span><span class="sxs-lookup"><span data-stu-id="e6405-p102">Only a setting of **adOpenStatic** is supported if the [CursorLocation](cursorlocation-property-ado.md) property is set to **adUseClient**. If an unsupported value is set, then no error will result; the closest supported **CursorType** will be used instead.</span></span>

<span data-ttu-id="e6405-p103">如果提供程序不支持所请求的游标类型，它可能会返回另一个游标类型。打开 **Recordset** 对象时， [CursorType](recordset-object-ado.md) 属性将更改为与实际使用的游标类型相匹配的值。若要验证返回的游标的特定功能，请使用 [Supports](supports-method-ado.md) 方法。关闭 **Recordset** 后， **CursorType** 属性将恢复为其原始设置。</span><span class="sxs-lookup"><span data-stu-id="e6405-p103">If a provider does not support the requested cursor type, it may return another cursor type. The **CursorType** property will change to match the actual cursor type in use when the [Recordset](recordset-object-ado.md) object is open. To verify specific functionality of the returned cursor, use the [Supports](supports-method-ado.md) method. After you close the **Recordset**, the **CursorType** property reverts to its original setting.</span></span>

<span data-ttu-id="e6405-116">下面的图表显示了每种游标类型所需要的提供程序功能（由 **Supports** 方法常量进行标识）。</span><span class="sxs-lookup"><span data-stu-id="e6405-116">The following chart shows the provider functionality (identified by **Supports** method constants) required for each cursor type.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e6405-117">对于使用此 CursorType 的 Recordset</span><span class="sxs-lookup"><span data-stu-id="e6405-117">For a Recordset of this CursorType</span></span></p></th>
<th><p><span data-ttu-id="e6405-118">Supports 方法必须为以下所有常量返回 True</span><span class="sxs-lookup"><span data-stu-id="e6405-118">The Supports method must return True for all of these constants</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e6405-119"><strong>adOpenForwardOnly</strong></span><span class="sxs-lookup"><span data-stu-id="e6405-119"><strong>adOpenForwardOnly</strong></span></span></p></td>
<td><p><span data-ttu-id="e6405-120">无</span><span class="sxs-lookup"><span data-stu-id="e6405-120">none</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6405-121"><strong>adOpenKeyset</strong></span><span class="sxs-lookup"><span data-stu-id="e6405-121"><strong>adOpenKeyset</strong></span></span></p></td>
<td><p><span data-ttu-id="e6405-122"><strong>adBookmark</strong> <strong>adHoldRecords</strong>、 <strong>adMovePrevious</strong>、 <strong>adResync</strong></span><span class="sxs-lookup"><span data-stu-id="e6405-122"><strong>adBookmark</strong>, <strong>adHoldRecords</strong>, <strong>adMovePrevious</strong>, <strong>adResync</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6405-123"><strong>adOpenDynamic</strong></span><span class="sxs-lookup"><span data-stu-id="e6405-123"><strong>adOpenDynamic</strong></span></span></p></td>
<td><p><span data-ttu-id="e6405-124"><strong>adMovePrevious</strong></span><span class="sxs-lookup"><span data-stu-id="e6405-124"><strong>adMovePrevious</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6405-125"><strong>为 adOpenStatic</strong></span><span class="sxs-lookup"><span data-stu-id="e6405-125"><strong>adOpenStatic</strong></span></span></p></td>
<td><p><span data-ttu-id="e6405-126"><strong>adBookmark</strong> <strong>adHoldRecords</strong>、 <strong>adMovePrevious</strong>、 <strong>adResync</strong></span><span class="sxs-lookup"><span data-stu-id="e6405-126"><strong>adBookmark</strong>, <strong>adHoldRecords</strong>, <strong>adMovePrevious</strong>, <strong>adResync</strong></span></span></p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> <span data-ttu-id="e6405-p104">虽然 **Supports**(**adUpdateBatch**) 对于动态游标和只进游标为 true，但对于批更新，应使用键集游标或静态游标。请将 [LockType](locktype-property-ado.md) 属性设置为 **adLockBatchOptimistic**，并将 **CursorLocation** 属性设置为 **adUseClient**，以启用批更新所必需的 Cursor Service for OLE DB。</span><span class="sxs-lookup"><span data-stu-id="e6405-p104">Although **Supports**(**adUpdateBatch**) may be true for dynamic and forward-only cursors, for batch updates you should use either a keyset or static cursor. Set the [LockType](locktype-property-ado.md) property to **adLockBatchOptimistic** and the **CursorLocation** property to **adUseClient** to enable the Cursor Service for OLE DB, which is required for batch updates.</span></span>

<span data-ttu-id="e6405-129">当 **Recordset** 关闭时， **CursorType** 属性为可读/写属性，而当其打开时为只读属性。</span><span class="sxs-lookup"><span data-stu-id="e6405-129">The **CursorType** property is read/write when the **Recordset** is closed and read-only when it is open.</span></span>

<span data-ttu-id="e6405-130">**远程数据服务用法**当客户端 Recordset 对象上使用时， **CursorType**属性可以设置仅为**adOpenStatic**。</span><span class="sxs-lookup"><span data-stu-id="e6405-130">**Remote Data Service Usage**When used on a client-side Recordset object, the **CursorType** property can be set only to **adOpenStatic**.</span></span>

