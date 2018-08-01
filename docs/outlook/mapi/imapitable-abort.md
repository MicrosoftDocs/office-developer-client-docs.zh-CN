---
title: IMAPITableAbort
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.Abort
api_type:
- COM
ms.assetid: 73291a5b-b626-494c-b5d9-f7709e34bac2
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 4b578f287a532475b53fb69cc4499662b6c4b6d7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775689"
---
# <a name="imapitableabort"></a><span data-ttu-id="01a5f-103">IMAPITable::Abort</span><span class="sxs-lookup"><span data-stu-id="01a5f-103">IMAPITable::Abort</span></span>

  
  
<span data-ttu-id="01a5f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="01a5f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="01a5f-105">停止当前正在进行任何异步操作表。</span><span class="sxs-lookup"><span data-stu-id="01a5f-105">Stops any asynchronous operations currently in progress for the table.</span></span>
  
```cpp
HRESULT Abort( void );
```

## <a name="parameters"></a><span data-ttu-id="01a5f-106">参数</span><span class="sxs-lookup"><span data-stu-id="01a5f-106">Parameters</span></span>

<span data-ttu-id="01a5f-107">无</span><span class="sxs-lookup"><span data-stu-id="01a5f-107">None</span></span>
  
## <a name="return-value"></a><span data-ttu-id="01a5f-108">返回值</span><span class="sxs-lookup"><span data-stu-id="01a5f-108">Return value</span></span>

<span data-ttu-id="01a5f-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="01a5f-109">S_OK</span></span> 
  
> <span data-ttu-id="01a5f-110">一个或多个异步操作已停止。</span><span class="sxs-lookup"><span data-stu-id="01a5f-110">One or more asynchronous operations have been stopped.</span></span>
    
<span data-ttu-id="01a5f-111">MAPI_E_UNABLE_TO_ABORT</span><span class="sxs-lookup"><span data-stu-id="01a5f-111">MAPI_E_UNABLE_TO_ABORT</span></span> 
  
> <span data-ttu-id="01a5f-112">异步操作正在编写中，无法停止或已完成。</span><span class="sxs-lookup"><span data-stu-id="01a5f-112">An asynchronous operation is in progress and cannot be stopped or it has already completed.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="01a5f-113">说明</span><span class="sxs-lookup"><span data-stu-id="01a5f-113">Remarks</span></span>

<span data-ttu-id="01a5f-114">**IMAPITable::Abort**方法停止当前正在进行的任何异步操作。</span><span class="sxs-lookup"><span data-stu-id="01a5f-114">The **IMAPITable::Abort** method stops any asynchronous operation that is currently in progress.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="01a5f-115">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="01a5f-115">Notes to callers</span></span>

<span data-ttu-id="01a5f-116">若要找出异步操作是否正在进行，请调用[IMAPITable::GetStatus](imapitable-getstatus.md)方法。</span><span class="sxs-lookup"><span data-stu-id="01a5f-116">To find out if an asynchronous operation is in progress, call the [IMAPITable::GetStatus](imapitable-getstatus.md) method.</span></span> 
  
<span data-ttu-id="01a5f-117">如果**中止**暂停处理[IMAPITable::Restrict](imapitable-restrict.md)方法的调用，表的状态将时处理**中止**的呼叫的时间。</span><span class="sxs-lookup"><span data-stu-id="01a5f-117">If **Abort** halts the processing of a call to the [IMAPITable::Restrict](imapitable-restrict.md) method, the state of the table will be as it was at the time the **Abort** call is processed.</span></span> 
  
<span data-ttu-id="01a5f-118">如果**中止**暂停处理[IMAPITable::SortTable](imapitable-sorttable.md)方法的调用，表的排序顺序不会受到影响，并保持前**SortTable**呼叫。</span><span class="sxs-lookup"><span data-stu-id="01a5f-118">If **Abort** halts the processing of a call to the [IMAPITable::SortTable](imapitable-sorttable.md) method, the table's sort order is unaffected and remains as it was before the **SortTable** call.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="01a5f-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01a5f-119">See also</span></span>



[<span data-ttu-id="01a5f-120">IMAPITable::GetStatus</span><span class="sxs-lookup"><span data-stu-id="01a5f-120">IMAPITable::GetStatus</span></span>](imapitable-getstatus.md)
  
[<span data-ttu-id="01a5f-121">IMAPITable::Restrict</span><span class="sxs-lookup"><span data-stu-id="01a5f-121">IMAPITable::Restrict</span></span>](imapitable-restrict.md)
  
[<span data-ttu-id="01a5f-122">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="01a5f-122">IMAPITable::SortTable</span></span>](imapitable-sorttable.md)
  
[<span data-ttu-id="01a5f-123">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="01a5f-123">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

