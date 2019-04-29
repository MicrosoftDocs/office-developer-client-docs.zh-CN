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
description: 上次修改时间：2012 年 6 月 26 日
ms.openlocfilehash: 108073f5e4833d9641e67065eb642320352fffe4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426854"
---
# <a name="imapisync--synchronizeinbackground"></a><span data-ttu-id="5e3c9-103">IMAPISync : SynchronizeInBackground</span><span class="sxs-lookup"><span data-stu-id="5e3c9-103">IMAPISync : SynchronizeInBackground</span></span>

 
  
<span data-ttu-id="5e3c9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5e3c9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="5e3c9-105">启动同步。</span><span class="sxs-lookup"><span data-stu-id="5e3c9-105">Initiates a synchronization.</span></span> <span data-ttu-id="5e3c9-106">此方法由 microsoft outlook 2010 和 microsoft outlook 2013 调用, 并由邮件存储提供程序实现。</span><span class="sxs-lookup"><span data-stu-id="5e3c9-106">This method is called by Microsoft Outlook 2010 and Microsoft Outlook 2013 and implemented by message store providers.</span></span> 
  
```cpp
HRESULT SynchronizeInBackground (
  PMAPISIB psibpb
);
```

## <a name="parameters"></a><span data-ttu-id="5e3c9-107">参数</span><span class="sxs-lookup"><span data-stu-id="5e3c9-107">Parameters</span></span>

 <span data-ttu-id="5e3c9-108">_psibpb_</span><span class="sxs-lookup"><span data-stu-id="5e3c9-108">_psibpb_</span></span>
  
> <span data-ttu-id="5e3c9-109">通知提供程序将进行同步, 并提供对可在同步过程中使用的接口的访问权限。</span><span class="sxs-lookup"><span data-stu-id="5e3c9-109">Informs the provider of what will be synchronized and gives access to interfaces that can be used during the synchronization.</span></span> <span data-ttu-id="5e3c9-110">它是一个[MAPISIB](mapisib.md)结构。</span><span class="sxs-lookup"><span data-stu-id="5e3c9-110">It is a [MAPISIB](mapisib.md) structure.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="5e3c9-111">返回值</span><span class="sxs-lookup"><span data-stu-id="5e3c9-111">Return value</span></span>

<span data-ttu-id="5e3c9-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="5e3c9-112">S_OK</span></span> 
  
> <span data-ttu-id="5e3c9-113">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="5e3c9-113">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5e3c9-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e3c9-114">See also</span></span>



[<span data-ttu-id="5e3c9-115">IMAPISync : IUnknown</span><span class="sxs-lookup"><span data-stu-id="5e3c9-115">IMAPISync : IUnknown</span></span>](imapisynciunknown.md)
  
[<span data-ttu-id="5e3c9-116">MAPISIB</span><span class="sxs-lookup"><span data-stu-id="5e3c9-116">MAPISIB</span></span>](mapisib.md)

