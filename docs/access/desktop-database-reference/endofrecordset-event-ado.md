---
title: EndOfRecordset 事件 (ADO)
TOCTitle: EndOfRecordset Event (ADO)
ms:assetid: 8995b851-dff6-2525-1d62-a2cfb4f95393
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249603(v=office.15)
ms:contentKeyID: 48546167
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a95ae75eb71ea50e08952418058f87bf54a40e45
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25888123"
---
# <a name="endofrecordset-event-ado"></a><span data-ttu-id="3150b-102">EndOfRecordset 事件 (ADO)</span><span class="sxs-lookup"><span data-stu-id="3150b-102">EndOfRecordset Event (ADO)</span></span>


<span data-ttu-id="3150b-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="3150b-103">**Applies to**: Access 2013, Office 2013</span></span>



<span data-ttu-id="3150b-104">当尝试移动到 **Recordset** 末尾之后的某一行时，调用 [EndOfRecordset](recordset-object-ado.md) 事件。</span><span class="sxs-lookup"><span data-stu-id="3150b-104">The **EndOfRecordset** event is called when there is an attempt to move to a row past the end of the [Recordset](recordset-object-ado.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="3150b-105">语法</span><span class="sxs-lookup"><span data-stu-id="3150b-105">Syntax</span></span>

<span data-ttu-id="3150b-106">EndOfRecordset*fMoreData*， *adStatus* *pRecordset*</span><span class="sxs-lookup"><span data-stu-id="3150b-106">EndOfRecordset*fMoreData*, *adStatus*, *pRecordset*</span></span>

## <a name="parameters"></a><span data-ttu-id="3150b-107">参数</span><span class="sxs-lookup"><span data-stu-id="3150b-107">Parameters</span></span>

  - <span data-ttu-id="3150b-108">*fMoreData*</span><span class="sxs-lookup"><span data-stu-id="3150b-108">*fMoreData*</span></span>

  - <span data-ttu-id="3150b-109">A **VARIANT\_BOOL**值，如果设置为 VARIANT\_值为 TRUE，指示已向**Recordset**添加更多行。</span><span class="sxs-lookup"><span data-stu-id="3150b-109">A **VARIANT\_BOOL** value that, if set to VARIANT\_TRUE, indicates more rows have been added to the **Recordset**.</span></span>

  - <span data-ttu-id="3150b-110">*adStatus*</span><span class="sxs-lookup"><span data-stu-id="3150b-110">*adStatus*</span></span>

  - [<span data-ttu-id="3150b-111">EventStatusEnum</span><span class="sxs-lookup"><span data-stu-id="3150b-111">EventStatusEnum</span></span>](eventstatusenum.md)
    
    <span data-ttu-id="3150b-p101">调用 **EndOfRecordset** 时，如果导致事件的操作成功，则该参数设置为 **adStatusOK** ；如果此事件无法请求取消导致此事件的操作，则该参数设置为 **adStatusCantDeny** 。</span><span class="sxs-lookup"><span data-stu-id="3150b-p101">When **EndOfRecordset** is called, this parameter is set to **adStatusOK** if the operation that caused the event was successful. It is set to **adStatusCantDeny** if this event cannot request cancellation of the operation that caused this event.</span></span>
    
    <span data-ttu-id="3150b-114">在 **EndOfRecordset** 返回之前，将该参数设置为 **adStatusUnwantedEvent** 可以阻止随后进行通知。</span><span class="sxs-lookup"><span data-stu-id="3150b-114">Before **EndOfRecordset** returns, set this parameter to **adStatusUnwantedEvent** to prevent subsequent notifications.</span></span>

  - <span data-ttu-id="3150b-115">*pRecordset*</span><span class="sxs-lookup"><span data-stu-id="3150b-115">*pRecordset*</span></span>

  - <span data-ttu-id="3150b-p102">**Recordset** 对象。发生此事件的 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="3150b-p102">A **Recordset** object. The **Recordset** for which this event occurred.</span></span>

## <a name="remarks"></a><span data-ttu-id="3150b-118">备注</span><span class="sxs-lookup"><span data-stu-id="3150b-118">Remarks</span></span>

<span data-ttu-id="3150b-119">如果 **MoveNext** 操作失败，可能会发生 [EndOfRecordset](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) 事件。</span><span class="sxs-lookup"><span data-stu-id="3150b-119">An **EndOfRecordset** event may occur if the [MoveNext](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) operation fails.</span></span>

<span data-ttu-id="3150b-120">当尝试移动到 **Recordset** 对象末尾之后的位置时（可能是作为调用 **MoveNext** 的结果），调用该事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="3150b-120">This event handler is called when an attempt is made to move past the end of the **Recordset** object, perhaps as a result of calling **MoveNext**.</span></span> <span data-ttu-id="3150b-121">但是，在该事件中，您可以从数据库中检索更多记录并将它们追加到 **Recordset** 的末尾。</span><span class="sxs-lookup"><span data-stu-id="3150b-121">However, while in this event, you could retrieve more records from a database and append them to the end of the **Recordset**.</span></span> <span data-ttu-id="3150b-122">在这种情况下，将*fMoreData*设置为 VARIANT\_为 TRUE，并从**EndOfRecordset**返回。</span><span class="sxs-lookup"><span data-stu-id="3150b-122">In that case, set *fMoreData* to VARIANT\_TRUE, and return from **EndOfRecordset**.</span></span> <span data-ttu-id="3150b-123">然后再次调用 **MoveNext** 以访问最新检索到的记录。</span><span class="sxs-lookup"><span data-stu-id="3150b-123">Then call **MoveNext** again to access the newly retrieved records.</span></span>

