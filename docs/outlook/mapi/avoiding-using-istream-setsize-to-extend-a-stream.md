---
title: 避免使用 IStreamSetSize 扩展流
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b6de594f-e331-4421-956b-86ee0b5518fe
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 614bb3d142b7aaabe89223b6ce3552469edfce27
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331621"
---
# <a name="avoiding-using-istreamsetsize-to-extend-a-stream"></a><span data-ttu-id="2a829-103">避免使用 IStream:: SetSize 扩展流</span><span class="sxs-lookup"><span data-stu-id="2a829-103">Avoiding Using IStream::SetSize to Extend a Stream</span></span>

  
  
<span data-ttu-id="2a829-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2a829-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2a829-105">在写入流时, 有时需要将其放大, 因为它们的初始大小已不再足够。</span><span class="sxs-lookup"><span data-stu-id="2a829-105">When writing to streams, it is sometimes necessary to enlarge them because their initial size is no longer sufficient.</span></span> <span data-ttu-id="2a829-106">使用 OLE 方法**IStream:: Write**实现此目的, 而不是**IStream:: SetSize**。</span><span class="sxs-lookup"><span data-stu-id="2a829-106">Use the OLE method **IStream::Write** to accomplish this rather than **IStream::SetSize**.</span></span> <span data-ttu-id="2a829-107">**IStream:: Write**自动扩展流, 将 \* \* IStream:: SetSize \* \* 设为不必要。</span><span class="sxs-lookup"><span data-stu-id="2a829-107">**IStream::Write** automatically extends the stream, making \*\* IStream::SetSize \*\* unnecessary.</span></span> <span data-ttu-id="2a829-108">调用**IStream::** 不带**IStream:: SetSize**的写入速度可比在**写入**前进行**SetSize**调用的速度快三倍。</span><span class="sxs-lookup"><span data-stu-id="2a829-108">Calling **IStream::Write** without **IStream::SetSize** can be up to three times faster than making the **SetSize** call prior to **Write**.</span></span>
  

