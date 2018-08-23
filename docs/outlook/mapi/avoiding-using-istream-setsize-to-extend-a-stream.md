---
title: 避免使用 IStreamSetSize 扩展流
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b6de594f-e331-4421-956b-86ee0b5518fe
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9245d4913c2832b8c942093e65cf088643a1947c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592078"
---
# <a name="avoiding-using-istreamsetsize-to-extend-a-stream"></a><span data-ttu-id="cf32d-103">避免使用 IStream::SetSize 来扩展流</span><span class="sxs-lookup"><span data-stu-id="cf32d-103">Avoiding Using IStream::SetSize to Extend a Stream</span></span>

  
  
<span data-ttu-id="cf32d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cf32d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cf32d-105">写入流，时，有时不必放大它们，因为其初始大小不再足够。</span><span class="sxs-lookup"><span data-stu-id="cf32d-105">When writing to streams, it is sometimes necessary to enlarge them because their initial size is no longer sufficient.</span></span> <span data-ttu-id="cf32d-106">使用**IStream::Write**的 OLE 方法实现这一点而不是**IStream::SetSize**。</span><span class="sxs-lookup"><span data-stu-id="cf32d-106">Use the OLE method **IStream::Write** to accomplish this rather than **IStream::SetSize**.</span></span> <span data-ttu-id="cf32d-107">**IStream::Write**自动扩展流，使 * * IStream::SetSize * * 不必要。</span><span class="sxs-lookup"><span data-stu-id="cf32d-107">**IStream::Write** automatically extends the stream, making ** IStream::SetSize ** unnecessary.</span></span> <span data-ttu-id="cf32d-108">调用不带**IStream::SetSize** **IStream::Write**可以比进行**写入**之前调用**SetSize**速度更快是三倍。</span><span class="sxs-lookup"><span data-stu-id="cf32d-108">Calling **IStream::Write** without **IStream::SetSize** can be up to three times faster than making the **SetSize** call prior to **Write**.</span></span>
  

