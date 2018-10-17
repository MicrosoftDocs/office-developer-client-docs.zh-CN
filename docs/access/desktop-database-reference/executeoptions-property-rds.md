---
title: ExecuteOptions 属性 (RDS)
TOCTitle: ExecuteOptions Property (RDS)
ms:assetid: fb244cbd-9a03-9128-1373-694c9061c9da
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250285(v=office.15)
ms:contentKeyID: 48548864
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 641e7942f5336f230d396db7e06b9d0601645cb6
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465995"
---
# <a name="executeoptions-property-rds"></a><span data-ttu-id="d6a66-102">ExecuteOptions 属性 (RDS)</span><span class="sxs-lookup"><span data-stu-id="d6a66-102">ExecuteOptions Property (RDS)</span></span>


<span data-ttu-id="d6a66-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="d6a66-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="d6a66-104">指示是否启用异步执行。</span><span class="sxs-lookup"><span data-stu-id="d6a66-104">Indicates whether asynchronous execution is enabled.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="d6a66-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="d6a66-105">Settings and Return Values</span></span>

<span data-ttu-id="d6a66-106">设置或返回下列值之一。</span><span class="sxs-lookup"><span data-stu-id="d6a66-106">Sets or returns one of the following values.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="d6a66-107">常量</span><span class="sxs-lookup"><span data-stu-id="d6a66-107">Constant</span></span></p></th>
<th><p><span data-ttu-id="d6a66-108">说明</span><span class="sxs-lookup"><span data-stu-id="d6a66-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6a66-109"><strong>adcExecSync</strong></span><span class="sxs-lookup"><span data-stu-id="d6a66-109"><strong>adcExecSync</strong></span></span></p></td>
<td><p><span data-ttu-id="d6a66-110">同步执行 <a href="recordset-object-ado.md">Recordset</a> 的下一个刷新操作。</span><span class="sxs-lookup"><span data-stu-id="d6a66-110">Executes the next refresh of the <a href="recordset-object-ado.md">Recordset</a> synchronously.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6a66-111"><strong>adcExecAsync</strong></span><span class="sxs-lookup"><span data-stu-id="d6a66-111"><strong>adcExecAsync</strong></span></span></p></td>
<td><p><span data-ttu-id="d6a66-p101">该值为默认值。异步执行 <strong>Recordset</strong> 的下一个刷新操作。</span><span class="sxs-lookup"><span data-stu-id="d6a66-p101">Default. Executes the next refresh of the <strong>Recordset</strong> asynchronously.</span></span></p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <P><span data-ttu-id="d6a66-p102">[!注释] 使用这些常量的每个客户端可执行文件必须提供其声明。可从位于 C:\Program Files\Common Files\System\MSADC 文件夹中的 Adcvbs.inc 文件剪切并粘贴所需的常量声明。</span><span class="sxs-lookup"><span data-stu-id="d6a66-p102">Each client-side executable file that uses these constants must provide declarations for them. You can cut and paste the constant declarations that you want from the file Adcvbs.inc, located in the C:\Program Files\Common Files\System\MSADC folder.</span></span></P>



## <a name="remarks"></a><span data-ttu-id="d6a66-116">备注</span><span class="sxs-lookup"><span data-stu-id="d6a66-116">Remarks</span></span>

<span data-ttu-id="d6a66-117">如果 **ExecuteOptions** 设置为 **adcExecAsync** ，则将对 **RDS.DataControl** 对象的 [Recordset](datacontrol-object-rds.md) 异步执行下一个 **Refresh** 调用。</span><span class="sxs-lookup"><span data-stu-id="d6a66-117">If **ExecuteOptions** is set to **adcExecAsync**, then this asynchronously executes the next **Refresh** call on the [RDS.DataControl](datacontrol-object-rds.md) object's **Recordset**.</span></span>

<span data-ttu-id="d6a66-118">当正在执行另一个可能更改 [RDS.DataControl](reset-method-rds.md) 对象的 [Recordset](refresh-method-rds.md) 的异步操作时，如果尝试调用 [Reset](submitchanges-method-rds.md)、[Refresh](cancelupdate-method-ado.md)、[SubmitChanges](recordset-sourcerecordset-properties-rds.md)、[CancelUpdate](datacontrol-object-rds.md) 或 **Recordset**，则将发生错误。</span><span class="sxs-lookup"><span data-stu-id="d6a66-118">If you try to call [Reset](reset-method-rds.md), [Refresh](refresh-method-rds.md), [SubmitChanges](submitchanges-method-rds.md), [CancelUpdate](cancelupdate-method-ado.md), or [Recordset](recordset-sourcerecordset-properties-rds.md) while another asynchronous operation that might change the [RDS.DataControl](datacontrol-object-rds.md) object's **Recordset** is executing, an error occurs.</span></span>

<span data-ttu-id="d6a66-119">如果在异步操作期间发生错误，则 **RDS.DataControl** 对象的 [ReadyState](readystate-property-rds.md) 值将从 **adcReadyStateLoaded** 更改为 **adcReadyStateComplete**，而 **Recordset** 属性值仍为 *Nothing*。</span><span class="sxs-lookup"><span data-stu-id="d6a66-119">If an error occurs during an asynchronous operation, the **RDS.DataControl** object's [ReadyState](readystate-property-rds.md) value changes from **adcReadyStateLoaded** to **adcReadyStateComplete**, and the **Recordset** property value remains *Nothing*.</span></span>
