---
title: IEnumFBBlock
manager: soliver
ms.date: 12/08/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: fad9c0fd-b523-db98-ee0d-78aad5914ff2
ms.openlocfilehash: 536c19aa314db9fca39298536c12464e71a71407
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774216"
---
# <a name="ienumfbblock"></a><span data-ttu-id="559fc-102">IEnumFBBlock</span><span class="sxs-lookup"><span data-stu-id="559fc-102">IEnumFBBlock</span></span>

<span data-ttu-id="559fc-103">支持访问和枚举忙/闲时间范围内的用户数据块。</span><span class="sxs-lookup"><span data-stu-id="559fc-103">Supports accessing and enumerating free/busy blocks of data for a user within a time range.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="559fc-104">快速信息</span><span class="sxs-lookup"><span data-stu-id="559fc-104">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="559fc-105">继承：</span><span class="sxs-lookup"><span data-stu-id="559fc-105">Inherits from:</span></span>  <br/> |[<span data-ttu-id="559fc-106">IUnknown</span><span class="sxs-lookup"><span data-stu-id="559fc-106">IUnknown</span></span>](http://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) <br/> |
|<span data-ttu-id="559fc-107">提供者：</span><span class="sxs-lookup"><span data-stu-id="559fc-107">Provided by:</span></span>  <br/> |<span data-ttu-id="559fc-108">忙/闲提供程序</span><span class="sxs-lookup"><span data-stu-id="559fc-108">Free/busy provider</span></span>  <br/> |
|<span data-ttu-id="559fc-109">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="559fc-109">Interface identifier:</span></span>  <br/> |<span data-ttu-id="559fc-110">**IEnumFBBlock**</span><span class="sxs-lookup"><span data-stu-id="559fc-110">**IEnumFBBlock**</span></span> <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="559fc-111">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="559fc-111">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="559fc-112">下一步</span><span class="sxs-lookup"><span data-stu-id="559fc-112">Next</span></span>](ienumfbblock-next.md) <br/> |<span data-ttu-id="559fc-113">获取枚举中的下一个指定的数量的忙/闲数据块。</span><span class="sxs-lookup"><span data-stu-id="559fc-113">Gets the next specified number of blocks of free/busy data in an enumeration.</span></span>  <br/> |
|[<span data-ttu-id="559fc-114">跳过</span><span class="sxs-lookup"><span data-stu-id="559fc-114">Skip</span></span>](ienumfbblock-skip.md) <br/> |<span data-ttu-id="559fc-115">跳过指定的数量的忙/闲数据块。</span><span class="sxs-lookup"><span data-stu-id="559fc-115">Skips a specified number of blocks of free/busy data.</span></span>  <br/> |
|[<span data-ttu-id="559fc-116">Reset</span><span class="sxs-lookup"><span data-stu-id="559fc-116">Reset</span></span>](ienumfbblock-reset.md) <br/> |<span data-ttu-id="559fc-117">通过将光标设置为开始重置枚举。</span><span class="sxs-lookup"><span data-stu-id="559fc-117">Resets the enumerator by setting the cursor to the beginning.</span></span>  <br/> |
|[<span data-ttu-id="559fc-118">Clone</span><span class="sxs-lookup"><span data-stu-id="559fc-118">Clone</span></span>](ienumfbblock-clone.md) <br/> |<span data-ttu-id="559fc-119">创建一份枚举数，使用相同的时间限制，但设置光标到枚举的开头。</span><span class="sxs-lookup"><span data-stu-id="559fc-119">Creates a copy of the enumerator, using the same time restriction but setting the cursor to the beginning of the enumerator.</span></span>  <br/> |
|[<span data-ttu-id="559fc-120">限制</span><span class="sxs-lookup"><span data-stu-id="559fc-120">Restrict</span></span>](ienumfbblock-restrict.md) <br/> |<span data-ttu-id="559fc-121">限制到指定的时间段枚举。</span><span class="sxs-lookup"><span data-stu-id="559fc-121">Restricts the enumeration to a specified time period.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="559fc-122">说明</span><span class="sxs-lookup"><span data-stu-id="559fc-122">Remarks</span></span>

<span data-ttu-id="559fc-123">枚举包含忙/闲时间不重叠的数据块。</span><span class="sxs-lookup"><span data-stu-id="559fc-123">An enumeration contains free/busy blocks of data that do not overlap in time.</span></span> <span data-ttu-id="559fc-124">当日历上存在重叠的项目时，Outlook 将合并这些项目以形成枚举基于以下优先顺序中的非重叠忙/闲基块:-外出、 忙碌、 暂定。</span><span class="sxs-lookup"><span data-stu-id="559fc-124">When there are overlapping items on a calendar, Outlook merges these items to form non-overlapping free/busy blocks in the enumeration based on this order of precedence: out-of-office, busy, tentative.</span></span>
  
<span data-ttu-id="559fc-125">忙/闲信息的提供程序获取该接口和时间范围内的用户通过[IFreeBusyData](ifreebusydata.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="559fc-125">A free/busy provider obtains this interface and the enumeration for a time range for a user through [IFreeBusyData](ifreebusydata.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="559fc-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="559fc-126">See also</span></span>

- [<span data-ttu-id="559fc-127">关于忙/闲 API</span><span class="sxs-lookup"><span data-stu-id="559fc-127">About the Free/Busy API</span></span>](about-the-free-busy-api.md)  
- [<span data-ttu-id="559fc-128">常量 (忙/闲 API)</span><span class="sxs-lookup"><span data-stu-id="559fc-128">Constants (Free/busy API)</span></span>](constants-free-busy-api.md)  
- [<span data-ttu-id="559fc-129">IFreeBusyData</span><span class="sxs-lookup"><span data-stu-id="559fc-129">IFreeBusyData</span></span>](ifreebusydata.md)

