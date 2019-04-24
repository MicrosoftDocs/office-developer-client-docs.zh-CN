---
title: FBStatus
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: f2d6a11e-847d-6bbe-cd77-e78ee961cb12
description: "\"忙/闲\" 块的 \"忙/闲\" 状态的枚举。"
ms.openlocfilehash: 2a08ef142f9baddd453166c0ebcb989e69a51ceb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319724"
---
# <a name="fbstatus"></a><span data-ttu-id="357d0-103">FBStatus</span><span class="sxs-lookup"><span data-stu-id="357d0-103">FBStatus</span></span>

<span data-ttu-id="357d0-104">"忙/闲" 块的 "忙/闲" 状态的枚举。</span><span class="sxs-lookup"><span data-stu-id="357d0-104">An enumeration for the free/busy status of free/busy blocks.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="357d0-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="357d0-105">Quick info</span></span>

```cpp
enum  
    { 
      fbFree      = 0, 
      fbTentative = fbFree + 1, 
      fbBusy      = fbTentative + 1, 
      fbOutOfOffice = fbBusy + 1 
    }

```

## <a name="remarks"></a><span data-ttu-id="357d0-106">注解</span><span class="sxs-lookup"><span data-stu-id="357d0-106">Remarks</span></span>

<span data-ttu-id="357d0-107">一段时间的忙/闲状态决定了它在日历中的显示方式:**闲**、**忙**、**暂定**或外出。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="357d0-107">The free/busy status of a block of time determines how it is displayed on a calendar: **Free**, **Busy**, **Tentative**, or **Out of Office**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="357d0-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="357d0-108">See also</span></span>

- [<span data-ttu-id="357d0-109">FBBlock_1</span><span class="sxs-lookup"><span data-stu-id="357d0-109">FBBlock_1</span></span>](fbblock_1.md)
- [<span data-ttu-id="357d0-110">IEnumFBBlock::Next</span><span class="sxs-lookup"><span data-stu-id="357d0-110">IEnumFBBlock::Next</span></span>](ienumfbblock-next.md)

