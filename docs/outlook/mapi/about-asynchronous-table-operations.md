---
title: 关于异步表操作
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 57219d96-bd9e-4e9a-b34a-dd3aad97bfd9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: eebc04e2263b4a2037e167bd464a31d298b84664
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329015"
---
# <a name="about-asynchronous-table-operations"></a><span data-ttu-id="06c08-103">关于异步表操作</span><span class="sxs-lookup"><span data-stu-id="06c08-103">About asynchronous table operations</span></span>
 
<span data-ttu-id="06c08-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="06c08-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="06c08-105">**IMAPITable**接口包括三种异步操作方法, 以及用于控制异步操作的三种方法。</span><span class="sxs-lookup"><span data-stu-id="06c08-105">The **IMAPITable** interface includes three methods that operate asynchronously and three methods for controlling an asynchronous operation.</span></span> <span data-ttu-id="06c08-106">下表列出了这些方法:</span><span class="sxs-lookup"><span data-stu-id="06c08-106">The following table lists these methods:</span></span> 
  
|<span data-ttu-id="06c08-107">**异步操作**</span><span class="sxs-lookup"><span data-stu-id="06c08-107">**Asynchronous operation**</span></span>|<span data-ttu-id="06c08-108">**异步控制方法**</span><span class="sxs-lookup"><span data-stu-id="06c08-108">**Asynchronous control method**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="06c08-109">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="06c08-109">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md) <br/> |[<span data-ttu-id="06c08-110">IMAPITable::GetStatus</span><span class="sxs-lookup"><span data-stu-id="06c08-110">IMAPITable::GetStatus</span></span>](imapitable-getstatus.md) <br/> |
|[<span data-ttu-id="06c08-111">IMAPITable::Restrict</span><span class="sxs-lookup"><span data-stu-id="06c08-111">IMAPITable::Restrict</span></span>](imapitable-restrict.md) <br/> |[<span data-ttu-id="06c08-112">IMAPITable::Abort</span><span class="sxs-lookup"><span data-stu-id="06c08-112">IMAPITable::Abort</span></span>](imapitable-abort.md) <br/> |
|[<span data-ttu-id="06c08-113">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="06c08-113">IMAPITable::SortTable</span></span>](imapitable-sorttable.md) <br/> |[<span data-ttu-id="06c08-114">IMAPITable::WaitForCompletion</span><span class="sxs-lookup"><span data-stu-id="06c08-114">IMAPITable::WaitForCompletion</span></span>](imapitable-waitforcompletion.md) <br/> |
   
<span data-ttu-id="06c08-115">**检索有关表的类型和当前操作的状态信息**</span><span class="sxs-lookup"><span data-stu-id="06c08-115">**To retrieve status information about a table's type and current operation**</span></span>
  
- <span data-ttu-id="06c08-116">调用[IMAPITable:: GetStatus](imapitable-getstatus.md)。</span><span class="sxs-lookup"><span data-stu-id="06c08-116">Call [IMAPITable::GetStatus](imapitable-getstatus.md).</span></span> <span data-ttu-id="06c08-117">通过**GetStatus**, 表用户可以确定表是静态的还是动态的, 如果某个操作正在进行中或已完成, 以及在已完成的操作中是否发生了错误。</span><span class="sxs-lookup"><span data-stu-id="06c08-117">With **GetStatus**, a table user can determine whether the table is static or dynamic, if an operation is in progress or has completed, and if an error has occurred from a completed operation.</span></span> <span data-ttu-id="06c08-118">例如, 如果客户端需要取消某个排序操作, 因为它花费的时间太长, 则客户端可以先调用**GetStatus** , 以确定当前是否正在处理排序操作。</span><span class="sxs-lookup"><span data-stu-id="06c08-118">For example, if a client needs to cancel a sort operation because it is taking too much time, the client can first call **GetStatus** to determine whether, in fact, a sort operation is presently processing.</span></span> <span data-ttu-id="06c08-119">然后, 客户端可以调用[IMAPITable:: Abort](imapitable-abort.md)停止它。</span><span class="sxs-lookup"><span data-stu-id="06c08-119">Then the client can call [IMAPITable::Abort](imapitable-abort.md) to stop it.</span></span> 
    
<span data-ttu-id="06c08-120">**挂起活动直到异步任务完成**</span><span class="sxs-lookup"><span data-stu-id="06c08-120">**To suspend activity until an asynchronous task has completed**</span></span>
  
- <span data-ttu-id="06c08-121">调用[IMAPITable:: WaitForCompletion](imapitable-waitforcompletion.md)。</span><span class="sxs-lookup"><span data-stu-id="06c08-121">Call [IMAPITable::WaitForCompletion](imapitable-waitforcompletion.md).</span></span> <span data-ttu-id="06c08-122">通过调用**WaitForCompletion** , 可以在不中断的情况下完成任务。</span><span class="sxs-lookup"><span data-stu-id="06c08-122">Calling **WaitForCompletion** allows the task to complete without interruption.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="06c08-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="06c08-123">See also</span></span>

- [<span data-ttu-id="06c08-124">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="06c08-124">MAPI Tables</span></span>](mapi-tables.md)

