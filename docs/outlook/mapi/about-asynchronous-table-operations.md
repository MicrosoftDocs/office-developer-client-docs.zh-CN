---
title: 有关异步表操作
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 57219d96-bd9e-4e9a-b34a-dd3aad97bfd9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 99bff153d4ce4bac3f85e0ed0feeaffafa6bf3f6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774464"
---
# <a name="about-asynchronous-table-operations"></a><span data-ttu-id="7009c-103">有关异步表操作</span><span class="sxs-lookup"><span data-stu-id="7009c-103">About asynchronous table operations</span></span>
 
<span data-ttu-id="7009c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="7009c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="7009c-105">**IMAPITable**界面包括异步操作的三种方法和用于控制异步操作的三种方法。</span><span class="sxs-lookup"><span data-stu-id="7009c-105">The **IMAPITable** interface includes three methods that operate asynchronously and three methods for controlling an asynchronous operation.</span></span> <span data-ttu-id="7009c-106">下表列出了这些方法：</span><span class="sxs-lookup"><span data-stu-id="7009c-106">The following table lists these methods:</span></span> 
  
|<span data-ttu-id="7009c-107">**异步操作**</span><span class="sxs-lookup"><span data-stu-id="7009c-107">**Asynchronous operation**</span></span>|<span data-ttu-id="7009c-108">**异步控制方法**</span><span class="sxs-lookup"><span data-stu-id="7009c-108">**Asynchronous control method**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="7009c-109">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="7009c-109">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md) <br/> |[<span data-ttu-id="7009c-110">IMAPITable::GetStatus</span><span class="sxs-lookup"><span data-stu-id="7009c-110">IMAPITable::GetStatus</span></span>](imapitable-getstatus.md) <br/> |
|[<span data-ttu-id="7009c-111">IMAPITable::Restrict</span><span class="sxs-lookup"><span data-stu-id="7009c-111">IMAPITable::Restrict</span></span>](imapitable-restrict.md) <br/> |[<span data-ttu-id="7009c-112">IMAPITable::Abort</span><span class="sxs-lookup"><span data-stu-id="7009c-112">IMAPITable::Abort</span></span>](imapitable-abort.md) <br/> |
|[<span data-ttu-id="7009c-113">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="7009c-113">IMAPITable::SortTable</span></span>](imapitable-sorttable.md) <br/> |[<span data-ttu-id="7009c-114">IMAPITable::WaitForCompletion</span><span class="sxs-lookup"><span data-stu-id="7009c-114">IMAPITable::WaitForCompletion</span></span>](imapitable-waitforcompletion.md) <br/> |
   
<span data-ttu-id="7009c-115">**若要检索有关表的类型和当前操作的状态信息**</span><span class="sxs-lookup"><span data-stu-id="7009c-115">**To retrieve status information about a table's type and current operation**</span></span>
  
- <span data-ttu-id="7009c-116">调用[IMAPITable::GetStatus](imapitable-getstatus.md)。</span><span class="sxs-lookup"><span data-stu-id="7009c-116">Call [IMAPITable::GetStatus](imapitable-getstatus.md).</span></span> <span data-ttu-id="7009c-117">使用**GetStatus**，表用户可以确定是否表是静态或动态，如果操作正在进行或完成后，而如果出现错误从已完成的操作。</span><span class="sxs-lookup"><span data-stu-id="7009c-117">With **GetStatus**, a table user can determine whether the table is static or dynamic, if an operation is in progress or has completed, and if an error has occurred from a completed operation.</span></span> <span data-ttu-id="7009c-118">例如，如果客户端需要取消排序操作，因为时间太长时间，客户端可以先调用**GetStatus**以确定是否，实际上，排序操作目前处理。</span><span class="sxs-lookup"><span data-stu-id="7009c-118">For example, if a client needs to cancel a sort operation because it is taking too much time, the client can first call **GetStatus** to determine whether, in fact, a sort operation is presently processing.</span></span> <span data-ttu-id="7009c-119">然后，客户端可以调用[IMAPITable::Abort](imapitable-abort.md)以将其停止。</span><span class="sxs-lookup"><span data-stu-id="7009c-119">Then the client can call [IMAPITable::Abort](imapitable-abort.md) to stop it.</span></span> 
    
<span data-ttu-id="7009c-120">**挂起活动，直到异步任务已完成**</span><span class="sxs-lookup"><span data-stu-id="7009c-120">**To suspend activity until an asynchronous task has completed**</span></span>
  
- <span data-ttu-id="7009c-121">调用[IMAPITable::WaitForCompletion](imapitable-waitforcompletion.md)。</span><span class="sxs-lookup"><span data-stu-id="7009c-121">Call [IMAPITable::WaitForCompletion](imapitable-waitforcompletion.md).</span></span> <span data-ttu-id="7009c-122">调用**WaitForCompletion**允许任务完成不会中断。</span><span class="sxs-lookup"><span data-stu-id="7009c-122">Calling **WaitForCompletion** allows the task to complete without interruption.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="7009c-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7009c-123">See also</span></span>

- [<span data-ttu-id="7009c-124">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="7009c-124">MAPI Tables</span></span>](mapi-tables.md)

