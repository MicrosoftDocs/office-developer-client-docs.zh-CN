---
title: FBStatus
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: f2d6a11e-847d-6bbe-cd77-e78ee961cb12
description: 忙/闲状态的忙/闲块枚举。
ms.openlocfilehash: 67d710f82856dc8ff4839c926018eef88d355f73
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "19774185"
---
# <a name="fbstatus"></a><span data-ttu-id="eac12-103">FBStatus</span><span class="sxs-lookup"><span data-stu-id="eac12-103">FBStatus</span></span>

<span data-ttu-id="eac12-104">忙/闲状态的忙/闲块枚举。</span><span class="sxs-lookup"><span data-stu-id="eac12-104">An enumeration for the free/busy status of free/busy blocks.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="eac12-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="eac12-105">Quick info</span></span>

```cpp
enum  
    { 
      fbFree      = 0, 
      fbTentative = fbFree + 1, 
      fbBusy      = fbTentative + 1, 
      fbOutOfOffice = fbBusy + 1 
    }

```

## <a name="remarks"></a><span data-ttu-id="eac12-106">说明</span><span class="sxs-lookup"><span data-stu-id="eac12-106">Remarks</span></span>

<span data-ttu-id="eac12-107">一段时间的忙/闲状态确定它在日历上的显示方式：**免费**、**忙碌**、**暂定**，或**外出时的**。</span><span class="sxs-lookup"><span data-stu-id="eac12-107">The free/busy status of a block of time determines how it is displayed on a calendar: **Free**, **Busy**, **Tentative**, or **Out of Office**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="eac12-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eac12-108">See also</span></span>

- [<span data-ttu-id="eac12-109">FBBlock_1</span><span class="sxs-lookup"><span data-stu-id="eac12-109">FBBlock_1</span></span>](fbblock_1.md)
- [<span data-ttu-id="eac12-110">IEnumFBBlock::Next</span><span class="sxs-lookup"><span data-stu-id="eac12-110">IEnumFBBlock::Next</span></span>](ienumfbblock-next.md)

