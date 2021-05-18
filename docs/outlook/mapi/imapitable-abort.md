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
# <a name="imapitableabort"></a><span data-ttu-id="79fcc-103">IMAPITable::Abort</span><span class="sxs-lookup"><span data-stu-id="79fcc-103">IMAPITable::Abort</span></span>

  
  
<span data-ttu-id="79fcc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="79fcc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="79fcc-105">停止表当前正在执行的任何异步操作。</span><span class="sxs-lookup"><span data-stu-id="79fcc-105">Stops any asynchronous operations currently in progress for the table.</span></span>
  
```cpp
HRESULT Abort( void );
```

## <a name="parameters"></a><span data-ttu-id="79fcc-106">参数</span><span class="sxs-lookup"><span data-stu-id="79fcc-106">Parameters</span></span>

<span data-ttu-id="79fcc-107">无</span><span class="sxs-lookup"><span data-stu-id="79fcc-107">None</span></span>
  
## <a name="return-value"></a><span data-ttu-id="79fcc-108">返回值</span><span class="sxs-lookup"><span data-stu-id="79fcc-108">Return value</span></span>

<span data-ttu-id="79fcc-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="79fcc-109">S_OK</span></span> 
  
> <span data-ttu-id="79fcc-110">一个或多个异步操作已停止。</span><span class="sxs-lookup"><span data-stu-id="79fcc-110">One or more asynchronous operations have been stopped.</span></span>
    
<span data-ttu-id="79fcc-111">MAPI_E_UNABLE_TO_ABORT</span><span class="sxs-lookup"><span data-stu-id="79fcc-111">MAPI_E_UNABLE_TO_ABORT</span></span> 
  
> <span data-ttu-id="79fcc-112">异步操作正在进行中，无法停止或已完成。</span><span class="sxs-lookup"><span data-stu-id="79fcc-112">An asynchronous operation is in progress and cannot be stopped or it has already completed.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="79fcc-113">备注</span><span class="sxs-lookup"><span data-stu-id="79fcc-113">Remarks</span></span>

<span data-ttu-id="79fcc-114">**IMAPITable：：Abort** 方法将停止当前进行的任何异步操作。</span><span class="sxs-lookup"><span data-stu-id="79fcc-114">The **IMAPITable::Abort** method stops any asynchronous operation that is currently in progress.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="79fcc-115">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="79fcc-115">Notes to callers</span></span>

<span data-ttu-id="79fcc-116">若要了解异步操作是否正在进行，请调用 [IMAPITable：：GetStatus](imapitable-getstatus.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="79fcc-116">To find out if an asynchronous operation is in progress, call the [IMAPITable::GetStatus](imapitable-getstatus.md) method.</span></span> 
  
<span data-ttu-id="79fcc-117">如果 **Abort** 停止处理对 [IMAPITable：：Restrict](imapitable-restrict.md) 方法的调用，则表的状态将和 **处理 Abort** 调用时的状态一样。</span><span class="sxs-lookup"><span data-stu-id="79fcc-117">If **Abort** halts the processing of a call to the [IMAPITable::Restrict](imapitable-restrict.md) method, the state of the table will be as it was at the time the **Abort** call is processed.</span></span> 
  
<span data-ttu-id="79fcc-118">如果 **Abort** 停止处理对 [IMAPITable：：SortTable](imapitable-sorttable.md) 方法的调用，则表的排序顺序不受影响，并且保持与 **SortTable** 调用之前一样。</span><span class="sxs-lookup"><span data-stu-id="79fcc-118">If **Abort** halts the processing of a call to the [IMAPITable::SortTable](imapitable-sorttable.md) method, the table's sort order is unaffected and remains as it was before the **SortTable** call.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="79fcc-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79fcc-119">See also</span></span>



[<span data-ttu-id="79fcc-120">IMAPITable::GetStatus</span><span class="sxs-lookup"><span data-stu-id="79fcc-120">IMAPITable::GetStatus</span></span>](imapitable-getstatus.md)
  
[<span data-ttu-id="79fcc-121">IMAPITable::Restrict</span><span class="sxs-lookup"><span data-stu-id="79fcc-121">IMAPITable::Restrict</span></span>](imapitable-restrict.md)
  
[<span data-ttu-id="79fcc-122">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="79fcc-122">IMAPITable::SortTable</span></span>](imapitable-sorttable.md)
  
[<span data-ttu-id="79fcc-123">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="79fcc-123">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

