---
title: FBBlock_1
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: da67171d-d25f-3424-1409-33189ac63a12
description: 定义忙/闲数据块。 这是约会或会议请求所代表的日历上的项目。
ms.openlocfilehash: 60d2ff50081a8950a397df6f2f6bbfd37d3bdb61
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317666"
---
# <a name="fbblock1"></a><span data-ttu-id="87b68-104">FBBlock_1</span><span class="sxs-lookup"><span data-stu-id="87b68-104">FBBlock_1</span></span>

<span data-ttu-id="87b68-105">定义忙/闲数据块。</span><span class="sxs-lookup"><span data-stu-id="87b68-105">Defines a free/busy block of data.</span></span> <span data-ttu-id="87b68-106">这是约会或会议请求所代表的日历上的项目。</span><span class="sxs-lookup"><span data-stu-id="87b68-106">This is an item on a calendar represented by an appointment or meeting request.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="87b68-107">快速信息</span><span class="sxs-lookup"><span data-stu-id="87b68-107">Quick info</span></span>

```cpp
typedef struct  tagFBBlock_1 
    { 
    long m_tmStart; 
    long m_tmEnd; 
    FBStatus m_fbstatus; 
    }FBBlock_1; 

```

## <a name="members"></a><span data-ttu-id="87b68-108">成员</span><span class="sxs-lookup"><span data-stu-id="87b68-108">Members</span></span>

<span data-ttu-id="87b68-109">_m_tmStart_</span><span class="sxs-lookup"><span data-stu-id="87b68-109">_m_tmStart_</span></span>
  
> <span data-ttu-id="87b68-110">块的开始时间, 以相对时间表示。</span><span class="sxs-lookup"><span data-stu-id="87b68-110">The start time for the block, expressed in relative time.</span></span> <span data-ttu-id="87b68-111">有关详细信息, 请参阅[使用相对时间访问忙/闲数据](how-to-use-relative-time-to-access-free-busy-data.md)。</span><span class="sxs-lookup"><span data-stu-id="87b68-111">For more information, see [Use relative time to access free/busy data](how-to-use-relative-time-to-access-free-busy-data.md).</span></span>
    
<span data-ttu-id="87b68-112">_m_tmEnd_</span><span class="sxs-lookup"><span data-stu-id="87b68-112">_m_tmEnd_</span></span>
  
> <span data-ttu-id="87b68-113">块的结束时间, 以相对时间表示。</span><span class="sxs-lookup"><span data-stu-id="87b68-113">The end time for the block, expressed in relative time.</span></span>
    
<span data-ttu-id="87b68-114">_m_fbStatus_</span><span class="sxs-lookup"><span data-stu-id="87b68-114">_m_fbStatus_</span></span>
  
> <span data-ttu-id="87b68-115">此块的忙/闲状态, 指示用户是在_m_tmStart_和_m_tmEnd_之间的时段内是否为外出、忙碌、暂定或空闲状态。</span><span class="sxs-lookup"><span data-stu-id="87b68-115">The free/busy status for this block, indicating whether the user is out-of-office, busy, tentative, or free, during the time period between  _m_tmStart_ and  _m_tmEnd_.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="87b68-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87b68-116">See also</span></span>

- [<span data-ttu-id="87b68-117">FBStatus</span><span class="sxs-lookup"><span data-stu-id="87b68-117">FBStatus</span></span>](fbstatus.md)
- [<span data-ttu-id="87b68-118">IEnumFBBlock::Next</span><span class="sxs-lookup"><span data-stu-id="87b68-118">IEnumFBBlock::Next</span></span>](ienumfbblock-next.md)
- [<span data-ttu-id="87b68-119">使用访问忙/闲数据的相对时间</span><span class="sxs-lookup"><span data-stu-id="87b68-119">Use relative time to access free/busy data</span></span>](how-to-use-relative-time-to-access-free-busy-data.md)

