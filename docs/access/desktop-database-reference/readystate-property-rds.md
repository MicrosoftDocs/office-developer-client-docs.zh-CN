---
title: ReadyState 属性 (RDS)
TOCTitle: ReadyState property (RDS)
ms:assetid: e7b62205-a604-ef43-2f5d-9b51b46d2b5a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250175(v=office.15)
ms:contentKeyID: 48548412
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 62229a06405c1c7dabc9826b8b03823df5cc1f05
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25996627"
---
# <a name="readystate-property-rds"></a><span data-ttu-id="073a3-102">ReadyState 属性 (RDS)</span><span class="sxs-lookup"><span data-stu-id="073a3-102">ReadyState property (RDS)</span></span>

<span data-ttu-id="073a3-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="073a3-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="073a3-104">指示 [DataControl](datacontrol-object-rds.md) 对象将数据检索进其 [Recordset](recordset-object-ado.md) 对象的进度。</span><span class="sxs-lookup"><span data-stu-id="073a3-104">Indicates the progress of a [DataControl](datacontrol-object-rds.md) object as it retrieves data into its [Recordset](recordset-object-ado.md) object.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="073a3-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="073a3-105">Settings and return values</span></span>

<span data-ttu-id="073a3-106">设置或返回下列值之一。</span><span class="sxs-lookup"><span data-stu-id="073a3-106">Sets or returns one of the following values.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="073a3-107">值</span><span class="sxs-lookup"><span data-stu-id="073a3-107">Value</span></span></p></th>
<th><p><span data-ttu-id="073a3-108">说明</span><span class="sxs-lookup"><span data-stu-id="073a3-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="073a3-109"><strong>adcReadyStateLoaded</strong></span><span class="sxs-lookup"><span data-stu-id="073a3-109"><strong>adcReadyStateLoaded</strong></span></span></p></td>
<td><p><span data-ttu-id="073a3-p101">仍在执行当前查询，尚未获取任何行。<strong>DataControl</strong> 对象的 <strong>Recordset</strong> 不可用。</span><span class="sxs-lookup"><span data-stu-id="073a3-p101">The current query is still executing and no rows have been fetched. The <strong>DataControl</strong> object's <strong>Recordset</strong> is not available for use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="073a3-112"><strong>adcReadyStateInteractive</strong></span><span class="sxs-lookup"><span data-stu-id="073a3-112"><strong>adcReadyStateInteractive</strong></span></span></p></td>
<td><p><span data-ttu-id="073a3-p102">当前查询检索到的初始行集已存储在 <strong>DataControl</strong> 对象的 <strong>Recordset</strong> 中，可以使用。仍在获取其余行。</span><span class="sxs-lookup"><span data-stu-id="073a3-p102">An initial set of rows retrieved by the current query has been stored in the <strong>DataControl</strong> object's <strong>Recordset</strong> and are available for use. The remaining rows are still being fetched.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="073a3-115"><strong>adcReadyStateComplete</strong></span><span class="sxs-lookup"><span data-stu-id="073a3-115"><strong>adcReadyStateComplete</strong></span></span></p></td>
<td><p><span data-ttu-id="073a3-116">当前查询检索到的所有行已存储在 <strong>DataControl</strong> 对象的 <strong>Recordset</strong> 中，可以使用。
</span><span class="sxs-lookup"><span data-stu-id="073a3-116">All rows retrieved by the current query have been stored in the <strong>DataControl</strong> object's <strong>Recordset</strong> and are available for use.</span></span> <span data-ttu-id="073a3-117">如果由于错误或由于未初始化 <strong>Recordset</strong> 对象而中止操作，也会存在此状态。</span><span class="sxs-lookup"><span data-stu-id="073a3-117">This state will also exist if an operation aborted due to an error, or if the <strong>Recordset</strong> object is not initialized.</span></span></p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="073a3-p104">[!注释] 使用这些常量的每个客户端可执行文件必须提供其声明。可从位于 C:\Program Files\Common Files\System\MSADC 文件夹中的 Adcvbs.inc 文件剪切并粘贴所需的常量声明。</span><span class="sxs-lookup"><span data-stu-id="073a3-p104">Each client-side executable file that uses these constants must provide declarations for them. You can cut and paste the constant declarations you want from the file Adcvbs.inc, located in the C:\Program Files\Common Files\System\MSADC folder.</span></span>

## <a name="remarks"></a><span data-ttu-id="073a3-120">备注</span><span class="sxs-lookup"><span data-stu-id="073a3-120">Remarks</span></span>

<span data-ttu-id="073a3-p105">使用 [onReadyStateChange](onreadystatechange-event-rds.md) 事件可在异步查询操作期间监视 **ReadyState** 属性的变化。这比定时检查属性值的效率更高。</span><span class="sxs-lookup"><span data-stu-id="073a3-p105">Use the [onReadyStateChange](onreadystatechange-event-rds.md) event to monitor changes in the **ReadyState** property during an asynchronous query operation. This is more efficient than periodically checking the value of the property.</span></span>

<span data-ttu-id="073a3-123">如果出现错误时发生异步操作， **ReadyState**属性更改为**adcReadyStateComplete**， [State](state-property-ado.md)属性从**adStateExecuting**更改为**adStateClosed**和**记录集**对象的[Value](value-property-ado.md)属性会保持为*Nothing*。</span><span class="sxs-lookup"><span data-stu-id="073a3-123">If an error occurs during an asynchronous operation, the **ReadyState** property changes to **adcReadyStateComplete**, the [State](state-property-ado.md) property changes from **adStateExecuting** to **adStateClosed**, and the **Recordset** object [Value](value-property-ado.md) property remains *Nothing*.</span></span>

