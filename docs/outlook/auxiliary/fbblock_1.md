---
title: FBBlock_1
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: da67171d-d25f-3424-1409-33189ac63a12
description: 定义一个忙/闲数据块。 这是日历上的一个项目，由约会或会议请求表示。
ms.openlocfilehash: 60d2ff50081a8950a397df6f2f6bbfd37d3bdb61
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413197"
---
# <a name="fbblock_1"></a><span data-ttu-id="6de74-104">FBBlock_1</span><span class="sxs-lookup"><span data-stu-id="6de74-104">FBBlock_1</span></span>

<span data-ttu-id="6de74-105">定义一个忙/闲数据块。</span><span class="sxs-lookup"><span data-stu-id="6de74-105">Defines a free/busy block of data.</span></span> <span data-ttu-id="6de74-106">这是日历上的一个项目，由约会或会议请求表示。</span><span class="sxs-lookup"><span data-stu-id="6de74-106">This is an item on a calendar represented by an appointment or meeting request.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="6de74-107">快速信息</span><span class="sxs-lookup"><span data-stu-id="6de74-107">Quick info</span></span>

```cpp
typedef struct  tagFBBlock_1 
    { 
    long m_tmStart; 
    long m_tmEnd; 
    FBStatus m_fbstatus; 
    }FBBlock_1; 

```

## <a name="members"></a><span data-ttu-id="6de74-108">成员</span><span class="sxs-lookup"><span data-stu-id="6de74-108">Members</span></span>

<span data-ttu-id="6de74-109">_m_tmStart_</span><span class="sxs-lookup"><span data-stu-id="6de74-109">_m_tmStart_</span></span>
  
> <span data-ttu-id="6de74-110">块的开始时间，以相对时间表示。</span><span class="sxs-lookup"><span data-stu-id="6de74-110">The start time for the block, expressed in relative time.</span></span> <span data-ttu-id="6de74-111">有关详细信息，请参阅使用 [相对时间访问忙/闲数据](how-to-use-relative-time-to-access-free-busy-data.md)。</span><span class="sxs-lookup"><span data-stu-id="6de74-111">For more information, see [Use relative time to access free/busy data](how-to-use-relative-time-to-access-free-busy-data.md).</span></span>
    
<span data-ttu-id="6de74-112">_m_tmEnd_</span><span class="sxs-lookup"><span data-stu-id="6de74-112">_m_tmEnd_</span></span>
  
> <span data-ttu-id="6de74-113">块的结束时间，以相对时间表示。</span><span class="sxs-lookup"><span data-stu-id="6de74-113">The end time for the block, expressed in relative time.</span></span>
    
<span data-ttu-id="6de74-114">_m_fbStatus_</span><span class="sxs-lookup"><span data-stu-id="6de74-114">_m_fbStatus_</span></span>
  
> <span data-ttu-id="6de74-115">此块的忙/闲状态，指示用户在 m_tmStart 和 m_tmEnd 之间的时间段是外出、忙碌  _、_ 暂定还是  _空闲_。</span><span class="sxs-lookup"><span data-stu-id="6de74-115">The free/busy status for this block, indicating whether the user is out-of-office, busy, tentative, or free, during the time period between  _m_tmStart_ and  _m_tmEnd_.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6de74-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6de74-116">See also</span></span>

- [<span data-ttu-id="6de74-117">FBStatus</span><span class="sxs-lookup"><span data-stu-id="6de74-117">FBStatus</span></span>](fbstatus.md)
- [<span data-ttu-id="6de74-118">IEnumFBBlock::Next</span><span class="sxs-lookup"><span data-stu-id="6de74-118">IEnumFBBlock::Next</span></span>](ienumfbblock-next.md)
- [<span data-ttu-id="6de74-119">使用访问忙/闲数据的相对时间</span><span class="sxs-lookup"><span data-stu-id="6de74-119">Use relative time to access free/busy data</span></span>](how-to-use-relative-time-to-access-free-busy-data.md)

