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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424089"
---
# <a name="fbstatus"></a><span data-ttu-id="b0ee7-103">FBStatus</span><span class="sxs-lookup"><span data-stu-id="b0ee7-103">FBStatus</span></span>

<span data-ttu-id="b0ee7-104">"忙/闲" 块的 "忙/闲" 状态的枚举。</span><span class="sxs-lookup"><span data-stu-id="b0ee7-104">An enumeration for the free/busy status of free/busy blocks.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="b0ee7-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="b0ee7-105">Quick info</span></span>

```cpp
enum  
    { 
      fbFree      = 0, 
      fbTentative = fbFree + 1, 
      fbBusy      = fbTentative + 1, 
      fbOutOfOffice = fbBusy + 1 
    }

```

## <a name="remarks"></a><span data-ttu-id="b0ee7-106">说明</span><span class="sxs-lookup"><span data-stu-id="b0ee7-106">Remarks</span></span>

<span data-ttu-id="b0ee7-107">一段时间的忙/闲状态决定了它在日历中的显示方式:**闲**、**忙**、**暂定**或外出。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b0ee7-107">The free/busy status of a block of time determines how it is displayed on a calendar: **Free**, **Busy**, **Tentative**, or **Out of Office**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b0ee7-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0ee7-108">See also</span></span>

- [<span data-ttu-id="b0ee7-109">FBBlock_1</span><span class="sxs-lookup"><span data-stu-id="b0ee7-109">FBBlock_1</span></span>](fbblock_1.md)
- [<span data-ttu-id="b0ee7-110">IEnumFBBlock::Next</span><span class="sxs-lookup"><span data-stu-id="b0ee7-110">IEnumFBBlock::Next</span></span>](ienumfbblock-next.md)

