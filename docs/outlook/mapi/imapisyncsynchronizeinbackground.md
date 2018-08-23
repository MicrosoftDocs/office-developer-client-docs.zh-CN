---
title: IMAPISync SynchronizeInBackground
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISync.SynchronizeInBackground
api_type:
- COM
ms.assetid: c4aaca65-d553-476c-8c6d-5f880b6efdc1
description: 上次修改时间： 2012 年 6 月 26 日
ms.openlocfilehash: ee6fe07df894213331ab51f9abaa4008247dac07
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568775"
---
# <a name="imapisync--synchronizeinbackground"></a><span data-ttu-id="1229d-103">IMAPISync : SynchronizeInBackground</span><span class="sxs-lookup"><span data-stu-id="1229d-103">IMAPISync : SynchronizeInBackground</span></span>

 
  
<span data-ttu-id="1229d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1229d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="1229d-105">启动同步。</span><span class="sxs-lookup"><span data-stu-id="1229d-105">Initiates a synchronization.</span></span> <span data-ttu-id="1229d-106">此方法是通过 Microsoft Outlook 2010 和 Microsoft Outlook 2013 调用，并由消息存储提供程序实现。</span><span class="sxs-lookup"><span data-stu-id="1229d-106">This method is called by Microsoft Outlook 2010 and Microsoft Outlook 2013 and implemented by message store providers.</span></span> 
  
```cpp
HRESULT SynchronizeInBackground (
  PMAPISIB psibpb
);
```

## <a name="parameters"></a><span data-ttu-id="1229d-107">参数</span><span class="sxs-lookup"><span data-stu-id="1229d-107">Parameters</span></span>

 <span data-ttu-id="1229d-108">_psibpb_</span><span class="sxs-lookup"><span data-stu-id="1229d-108">_psibpb_</span></span>
  
> <span data-ttu-id="1229d-109">通知的内容将同步的提供程序和访问提供可在同步过程中使用的接口。</span><span class="sxs-lookup"><span data-stu-id="1229d-109">Informs the provider of what will be synchronized and gives access to interfaces that can be used during the synchronization.</span></span> <span data-ttu-id="1229d-110">它是[MAPISIB](mapisib.md)结构。</span><span class="sxs-lookup"><span data-stu-id="1229d-110">It is a [MAPISIB](mapisib.md) structure.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="1229d-111">返回值</span><span class="sxs-lookup"><span data-stu-id="1229d-111">Return value</span></span>

<span data-ttu-id="1229d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="1229d-112">S_OK</span></span> 
  
> <span data-ttu-id="1229d-113">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="1229d-113">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1229d-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1229d-114">See also</span></span>



[<span data-ttu-id="1229d-115">IMAPISync : IUnknown</span><span class="sxs-lookup"><span data-stu-id="1229d-115">IMAPISync : IUnknown</span></span>](imapisynciunknown.md)
  
[<span data-ttu-id="1229d-116">MAPISIB</span><span class="sxs-lookup"><span data-stu-id="1229d-116">MAPISIB</span></span>](mapisib.md)

