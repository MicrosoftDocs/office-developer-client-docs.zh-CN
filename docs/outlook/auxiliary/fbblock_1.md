---
title: FBBlock_1
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: da67171d-d25f-3424-1409-33189ac63a12
description: 定义忙/闲数据块。 这是由的约会或会议请求日历的项目。
ms.openlocfilehash: 93418e3777e9d9f0a016822ea5897b8fccc37ac3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774174"
---
# <a name="fbblock1"></a><span data-ttu-id="92b53-104">FBBlock_1</span><span class="sxs-lookup"><span data-stu-id="92b53-104">FBBlock_1</span></span>

<span data-ttu-id="92b53-105">定义忙/闲数据块。</span><span class="sxs-lookup"><span data-stu-id="92b53-105">Defines a free/busy block of data.</span></span> <span data-ttu-id="92b53-106">这是由的约会或会议请求日历的项目。</span><span class="sxs-lookup"><span data-stu-id="92b53-106">This is an item on a calendar represented by an appointment or meeting request.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="92b53-107">快速信息</span><span class="sxs-lookup"><span data-stu-id="92b53-107">Quick info</span></span>

```cpp
typedef struct  tagFBBlock_1 
    { 
    long m_tmStart; 
    long m_tmEnd; 
    FBStatus m_fbstatus; 
    }FBBlock_1; 

```

## <a name="members"></a><span data-ttu-id="92b53-108">Members</span><span class="sxs-lookup"><span data-stu-id="92b53-108">Members</span></span>

<span data-ttu-id="92b53-109">_m_tmStart_</span><span class="sxs-lookup"><span data-stu-id="92b53-109">_m_tmStart_</span></span>
  
> <span data-ttu-id="92b53-110">块，表示相对时间的开始时间。</span><span class="sxs-lookup"><span data-stu-id="92b53-110">The start time for the block, expressed in relative time.</span></span> <span data-ttu-id="92b53-111">有关详细信息，请参阅[使用相对时间访问忙/闲数据](how-to-use-relative-time-to-access-free-busy-data.md)。</span><span class="sxs-lookup"><span data-stu-id="92b53-111">For more information, see [Use relative time to access free/busy data](how-to-use-relative-time-to-access-free-busy-data.md).</span></span>
    
<span data-ttu-id="92b53-112">_m_tmEnd_</span><span class="sxs-lookup"><span data-stu-id="92b53-112">_m_tmEnd_</span></span>
  
> <span data-ttu-id="92b53-113">块，表示相对时间的结束时间。</span><span class="sxs-lookup"><span data-stu-id="92b53-113">The end time for the block, expressed in relative time.</span></span>
    
<span data-ttu-id="92b53-114">_m_fbStatus_</span><span class="sxs-lookup"><span data-stu-id="92b53-114">_m_fbStatus_</span></span>
  
> <span data-ttu-id="92b53-115">此块，指示用户是否-外出、 忙碌、 暂定、 或免费、 _m_tmStart_和_m_tmEnd_之间的时段内的忙/闲状态。</span><span class="sxs-lookup"><span data-stu-id="92b53-115">The free/busy status for this block, indicating whether the user is out-of-office, busy, tentative, or free, during the time period between  _m_tmStart_ and  _m_tmEnd_.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="92b53-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92b53-116">See also</span></span>

- [<span data-ttu-id="92b53-117">FBStatus</span><span class="sxs-lookup"><span data-stu-id="92b53-117">FBStatus</span></span>](fbstatus.md)
- [<span data-ttu-id="92b53-118">IEnumFBBlock::Next</span><span class="sxs-lookup"><span data-stu-id="92b53-118">IEnumFBBlock::Next</span></span>](ienumfbblock-next.md)
- [<span data-ttu-id="92b53-119">使用访问忙/闲数据的相对时间</span><span class="sxs-lookup"><span data-stu-id="92b53-119">Use relative time to access free/busy data</span></span>](how-to-use-relative-time-to-access-free-busy-data.md)

