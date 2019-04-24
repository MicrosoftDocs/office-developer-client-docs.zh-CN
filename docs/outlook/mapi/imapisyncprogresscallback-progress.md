---
title: IMAPISyncProgressCallbackProgress
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISyncProgressCallback.Progress
api_type:
- COM
ms.assetid: 6797cd1c-8a0b-4f42-ba56-6162d8e7b058
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9b44337a4bc9615558ac6337e99ea206ba063b1a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341256"
---
# <a name="imapisyncprogresscallbackprogress"></a><span data-ttu-id="61a64-103">IMAPISyncProgressCallback::Progress</span><span class="sxs-lookup"><span data-stu-id="61a64-103">IMAPISyncProgressCallback::Progress</span></span>

  
  
<span data-ttu-id="61a64-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="61a64-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="61a64-105">更新 "发送/接收" 对话框中的状态。</span><span class="sxs-lookup"><span data-stu-id="61a64-105">Updates the status in the Send/Receive dialog.</span></span> <span data-ttu-id="61a64-106">存储提供程序定期调用此函数。</span><span class="sxs-lookup"><span data-stu-id="61a64-106">The store provider periodically calls this function.</span></span>
  
```cpp
HRESULT Progress(
  const WCHAR *pwcszProgress, 
  ULONG ulIndex, 
  ULONG ulIndexMax
);
```

## <a name="parameters"></a><span data-ttu-id="61a64-107">参数</span><span class="sxs-lookup"><span data-stu-id="61a64-107">Parameters</span></span>

 <span data-ttu-id="61a64-108">**pwczsProgress**</span><span class="sxs-lookup"><span data-stu-id="61a64-108">**pwczsProgress**</span></span>
  
> <span data-ttu-id="61a64-109">指向显示当前进度步骤的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="61a64-109">A pointer to a string that displays the current progress step.</span></span> <span data-ttu-id="61a64-110">它可以是 NULL 以更新进度。</span><span class="sxs-lookup"><span data-stu-id="61a64-110">It can be NULL to update progress.</span></span>
    
 <span data-ttu-id="61a64-111">**ulIndex**</span><span class="sxs-lookup"><span data-stu-id="61a64-111">**ulIndex**</span></span>
  
> <span data-ttu-id="61a64-112">当前正在进行的位置。</span><span class="sxs-lookup"><span data-stu-id="61a64-112">The current position in progress.</span></span>
    
 <span data-ttu-id="61a64-113">**ulIndexMax**</span><span class="sxs-lookup"><span data-stu-id="61a64-113">**ulIndexMax**</span></span>
  
> <span data-ttu-id="61a64-114">指示完整进度的索引。</span><span class="sxs-lookup"><span data-stu-id="61a64-114">The index indicating complete progress.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="61a64-115">返回值</span><span class="sxs-lookup"><span data-stu-id="61a64-115">Return value</span></span>

<span data-ttu-id="61a64-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="61a64-116">S_OK</span></span> 
  
> <span data-ttu-id="61a64-117">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="61a64-117">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="61a64-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61a64-118">See also</span></span>



[<span data-ttu-id="61a64-119">IMAPISyncProgressCallback : IUnknown</span><span class="sxs-lookup"><span data-stu-id="61a64-119">IMAPISyncProgressCallback : IUnknown</span></span>](imapisyncprogresscallbackiunknown.md)

