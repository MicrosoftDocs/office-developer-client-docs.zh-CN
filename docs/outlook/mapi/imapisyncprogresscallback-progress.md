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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 12624ef6212f9113041bf5cf3a82e2b7df6eca9e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775674"
---
# <a name="imapisyncprogresscallbackprogress"></a><span data-ttu-id="2c464-103">IMAPISyncProgressCallback::Progress</span><span class="sxs-lookup"><span data-stu-id="2c464-103">IMAPISyncProgressCallback::Progress</span></span>

  
  
<span data-ttu-id="2c464-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2c464-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2c464-105">更新发送/接收对话框中的状态。</span><span class="sxs-lookup"><span data-stu-id="2c464-105">Updates the status in the Send/Receive dialog.</span></span> <span data-ttu-id="2c464-106">存储提供程序定期调用此函数。</span><span class="sxs-lookup"><span data-stu-id="2c464-106">The store provider periodically calls this function.</span></span>
  
```cpp
HRESULT Progress(
  const WCHAR *pwcszProgress, 
  ULONG ulIndex, 
  ULONG ulIndexMax
);
```

## <a name="parameters"></a><span data-ttu-id="2c464-107">参数</span><span class="sxs-lookup"><span data-stu-id="2c464-107">Parameters</span></span>

 <span data-ttu-id="2c464-108">**pwczsProgress**</span><span class="sxs-lookup"><span data-stu-id="2c464-108">**pwczsProgress**</span></span>
  
> <span data-ttu-id="2c464-109">一个指向一个字符串，显示当前进度步骤。</span><span class="sxs-lookup"><span data-stu-id="2c464-109">A pointer to a string that displays the current progress step.</span></span> <span data-ttu-id="2c464-110">它可以为 NULL，以更新进度。</span><span class="sxs-lookup"><span data-stu-id="2c464-110">It can be NULL to update progress.</span></span>
    
 <span data-ttu-id="2c464-111">**ulIndex**</span><span class="sxs-lookup"><span data-stu-id="2c464-111">**ulIndex**</span></span>
  
> <span data-ttu-id="2c464-112">正在进行中的当前位置。</span><span class="sxs-lookup"><span data-stu-id="2c464-112">The current position in progress.</span></span>
    
 <span data-ttu-id="2c464-113">**ulIndexMax**</span><span class="sxs-lookup"><span data-stu-id="2c464-113">**ulIndexMax**</span></span>
  
> <span data-ttu-id="2c464-114">指示完成进度索引。</span><span class="sxs-lookup"><span data-stu-id="2c464-114">The index indicating complete progress.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="2c464-115">返回值</span><span class="sxs-lookup"><span data-stu-id="2c464-115">Return value</span></span>

<span data-ttu-id="2c464-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="2c464-116">S_OK</span></span> 
  
> <span data-ttu-id="2c464-117">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="2c464-117">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2c464-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c464-118">See also</span></span>



[<span data-ttu-id="2c464-119">IMAPISyncProgressCallback : IUnknown</span><span class="sxs-lookup"><span data-stu-id="2c464-119">IMAPISyncProgressCallback : IUnknown</span></span>](imapisyncprogresscallbackiunknown.md)

