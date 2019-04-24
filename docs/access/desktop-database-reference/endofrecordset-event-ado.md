---
title: EndOfRecordset 事件 (ADO)
TOCTitle: EndOfRecordset event (ADO)
ms:assetid: 8995b851-dff6-2525-1d62-a2cfb4f95393
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249603(v=office.15)
ms:contentKeyID: 48546167
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 48e0eb25b443175013a144fafaa433df12c2cc9c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293558"
---
# <a name="endofrecordset-event-ado"></a><span data-ttu-id="243f2-102">EndOfRecordset 事件 (ADO)</span><span class="sxs-lookup"><span data-stu-id="243f2-102">EndOfRecordset event (ADO)</span></span>

<span data-ttu-id="243f2-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="243f2-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="243f2-104">当尝试移动到 [Recordset](recordset-object-ado.md) 末尾之后的某一行时，调用 **EndOfRecordset** 事件。</span><span class="sxs-lookup"><span data-stu-id="243f2-104">The **EndOfRecordset** event is called when there is an attempt to move to a row past the end of the [Recordset](recordset-object-ado.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="243f2-105">语法</span><span class="sxs-lookup"><span data-stu-id="243f2-105">Syntax</span></span>

<span data-ttu-id="243f2-106">EndOfRecordset*fMoreData*、 *adStatus*、 *pRecordset*</span><span class="sxs-lookup"><span data-stu-id="243f2-106">EndOfRecordset*fMoreData*, *adStatus*, *pRecordset*</span></span>

## <a name="parameters"></a><span data-ttu-id="243f2-107">参数</span><span class="sxs-lookup"><span data-stu-id="243f2-107">Parameters</span></span>

|<span data-ttu-id="243f2-108">参数</span><span class="sxs-lookup"><span data-stu-id="243f2-108">Parameter</span></span>|<span data-ttu-id="243f2-109">描述</span><span class="sxs-lookup"><span data-stu-id="243f2-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="243f2-110">*fMoreData*</span><span class="sxs-lookup"><span data-stu-id="243f2-110">*fMoreData*</span></span> |<span data-ttu-id="243f2-111">**\_variant BOOL**值, 如果设置为 VARIANT\_TRUE, 则表示已向**Recordset**添加了更多的行。</span><span class="sxs-lookup"><span data-stu-id="243f2-111">A **VARIANT\_BOOL** value that, if set to VARIANT\_TRUE, indicates more rows have been added to the **Recordset**.</span></span>|
|<span data-ttu-id="243f2-112">*adStatus*</span><span class="sxs-lookup"><span data-stu-id="243f2-112">*adStatus*</span></span> |<span data-ttu-id="243f2-113">[EventStatusEnum](eventstatusenum.md)。</span><span class="sxs-lookup"><span data-stu-id="243f2-113">[EventStatusEnum](eventstatusenum.md).</span></span> <span data-ttu-id="243f2-114">当调用**EndOfRecordset**时, 如果导致事件的操作成功, 则将此参数设置为**adstatusok;** 。</span><span class="sxs-lookup"><span data-stu-id="243f2-114">When **EndOfRecordset** is called, this parameter is set to **adStatusOK** if the operation that caused the event was successful.</span></span> <span data-ttu-id="243f2-115">如果此事件不能请求取消导致该事件的操作, 则将其设置为**adStatusCantDeny** 。</span><span class="sxs-lookup"><span data-stu-id="243f2-115">It is set to **adStatusCantDeny** if this event cannot request cancellation of the operation that caused this event.</span></span><br/><br/><span data-ttu-id="243f2-116">在 **EndOfRecordset** 返回之前，将该参数设置为 **adStatusUnwantedEvent** 可以阻止随后进行通知。</span><span class="sxs-lookup"><span data-stu-id="243f2-116">Before **EndOfRecordset** returns, set this parameter to **adStatusUnwantedEvent** to prevent subsequent notifications.</span></span>|
|<span data-ttu-id="243f2-117">*pRecordset*</span><span class="sxs-lookup"><span data-stu-id="243f2-117">*pRecordset*</span></span> | <span data-ttu-id="243f2-p102">**Recordset** 对象。发生此事件的 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="243f2-p102">A **Recordset** object. The **Recordset** for which this event occurred.</span></span>|

## <a name="remarks"></a><span data-ttu-id="243f2-120">注解</span><span class="sxs-lookup"><span data-stu-id="243f2-120">Remarks</span></span>

<span data-ttu-id="243f2-121">如果 **MoveNext** 操作失败，可能会发生 [EndOfRecordset](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) 事件。</span><span class="sxs-lookup"><span data-stu-id="243f2-121">An **EndOfRecordset** event may occur if the [MoveNext](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) operation fails.</span></span>

<span data-ttu-id="243f2-122">当尝试移动到 **Recordset** 对象末尾之后的位置时（可能是作为调用 **MoveNext** 的结果），调用该事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="243f2-122">This event handler is called when an attempt is made to move past the end of the **Recordset** object, perhaps as a result of calling **MoveNext**.</span></span> <span data-ttu-id="243f2-123">但是，在该事件中，您可以从数据库中检索更多记录并将它们追加到 **Recordset** 的末尾。</span><span class="sxs-lookup"><span data-stu-id="243f2-123">However, while in this event, you could retrieve more records from a database and append them to the end of the **Recordset**.</span></span> <span data-ttu-id="243f2-124">在这种情况下\*\* , 将 fMoreData\_设置为 VARIANT TRUE, 然后从**EndOfRecordset**返回。</span><span class="sxs-lookup"><span data-stu-id="243f2-124">In that case, set *fMoreData* to VARIANT\_TRUE, and return from **EndOfRecordset**.</span></span> <span data-ttu-id="243f2-125">然后再次调用 **MoveNext** 以访问最新检索到的记录。</span><span class="sxs-lookup"><span data-stu-id="243f2-125">Then call **MoveNext** again to access the newly retrieved records.</span></span>

