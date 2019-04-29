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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 74c307fca27f1adec18d236792f8a58d97e33ec5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406148"
---
# <a name="imapitableabort"></a><span data-ttu-id="d7e0d-103">IMAPITable::Abort</span><span class="sxs-lookup"><span data-stu-id="d7e0d-103">IMAPITable::Abort</span></span>

  
  
<span data-ttu-id="d7e0d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d7e0d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d7e0d-105">停止当前对表进行的所有异步操作。</span><span class="sxs-lookup"><span data-stu-id="d7e0d-105">Stops any asynchronous operations currently in progress for the table.</span></span>
  
```cpp
HRESULT Abort( void );
```

## <a name="parameters"></a><span data-ttu-id="d7e0d-106">参数</span><span class="sxs-lookup"><span data-stu-id="d7e0d-106">Parameters</span></span>

<span data-ttu-id="d7e0d-107">无</span><span class="sxs-lookup"><span data-stu-id="d7e0d-107">None</span></span>
  
## <a name="return-value"></a><span data-ttu-id="d7e0d-108">返回值</span><span class="sxs-lookup"><span data-stu-id="d7e0d-108">Return value</span></span>

<span data-ttu-id="d7e0d-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="d7e0d-109">S_OK</span></span> 
  
> <span data-ttu-id="d7e0d-110">一个或多个异步操作已停止。</span><span class="sxs-lookup"><span data-stu-id="d7e0d-110">One or more asynchronous operations have been stopped.</span></span>
    
<span data-ttu-id="d7e0d-111">MAPI_E_UNABLE_TO_ABORT</span><span class="sxs-lookup"><span data-stu-id="d7e0d-111">MAPI_E_UNABLE_TO_ABORT</span></span> 
  
> <span data-ttu-id="d7e0d-112">正在进行异步操作, 无法停止或已完成。</span><span class="sxs-lookup"><span data-stu-id="d7e0d-112">An asynchronous operation is in progress and cannot be stopped or it has already completed.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d7e0d-113">说明</span><span class="sxs-lookup"><span data-stu-id="d7e0d-113">Remarks</span></span>

<span data-ttu-id="d7e0d-114">**IMAPITable:: Abort**方法会停止当前正在进行的任何异步操作。</span><span class="sxs-lookup"><span data-stu-id="d7e0d-114">The **IMAPITable::Abort** method stops any asynchronous operation that is currently in progress.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="d7e0d-115">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="d7e0d-115">Notes to callers</span></span>

<span data-ttu-id="d7e0d-116">若要了解是否正在进行异步操作, 请调用[IMAPITable:: GetStatus](imapitable-getstatus.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d7e0d-116">To find out if an asynchronous operation is in progress, call the [IMAPITable::GetStatus](imapitable-getstatus.md) method.</span></span> 
  
<span data-ttu-id="d7e0d-117">如果**Abort 中止**对[IMAPITable:: Restrict](imapitable-restrict.md)方法的调用的处理, 则表的状态将与处理**中止**调用时的状态相同。</span><span class="sxs-lookup"><span data-stu-id="d7e0d-117">If **Abort** halts the processing of a call to the [IMAPITable::Restrict](imapitable-restrict.md) method, the state of the table will be as it was at the time the **Abort** call is processed.</span></span> 
  
<span data-ttu-id="d7e0d-118">如果**Abort 中止**对[IMAPITable:: SortTable](imapitable-sorttable.md)方法的调用的处理, 则表的排序顺序不受影响, 并保持在**SortTable**调用之前。</span><span class="sxs-lookup"><span data-stu-id="d7e0d-118">If **Abort** halts the processing of a call to the [IMAPITable::SortTable](imapitable-sorttable.md) method, the table's sort order is unaffected and remains as it was before the **SortTable** call.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d7e0d-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7e0d-119">See also</span></span>



[<span data-ttu-id="d7e0d-120">IMAPITable::GetStatus</span><span class="sxs-lookup"><span data-stu-id="d7e0d-120">IMAPITable::GetStatus</span></span>](imapitable-getstatus.md)
  
[<span data-ttu-id="d7e0d-121">IMAPITable::Restrict</span><span class="sxs-lookup"><span data-stu-id="d7e0d-121">IMAPITable::Restrict</span></span>](imapitable-restrict.md)
  
[<span data-ttu-id="d7e0d-122">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="d7e0d-122">IMAPITable::SortTable</span></span>](imapitable-sorttable.md)
  
[<span data-ttu-id="d7e0d-123">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d7e0d-123">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

