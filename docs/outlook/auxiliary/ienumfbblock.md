---
title: IEnumFBBlock
manager: soliver
ms.date: 12/08/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: fad9c0fd-b523-db98-ee0d-78aad5914ff2
ms.openlocfilehash: 2b37aa2000218acc0663ee8e2db12f01b93c0663
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317624"
---
# <a name="ienumfbblock"></a><span data-ttu-id="e1cfd-102">IEnumFBBlock</span><span class="sxs-lookup"><span data-stu-id="e1cfd-102">IEnumFBBlock</span></span>

<span data-ttu-id="e1cfd-103">支持在某个时间范围内访问和枚举用户的忙/闲数据块。</span><span class="sxs-lookup"><span data-stu-id="e1cfd-103">Supports accessing and enumerating free/busy blocks of data for a user within a time range.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="e1cfd-104">快速信息</span><span class="sxs-lookup"><span data-stu-id="e1cfd-104">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e1cfd-105">继承自:</span><span class="sxs-lookup"><span data-stu-id="e1cfd-105">Inherits from:</span></span>  <br/> |[<span data-ttu-id="e1cfd-106">IUnknown</span><span class="sxs-lookup"><span data-stu-id="e1cfd-106">IUnknown</span></span>](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) <br/> |
|<span data-ttu-id="e1cfd-107">提供者：</span><span class="sxs-lookup"><span data-stu-id="e1cfd-107">Provided by:</span></span>  <br/> |<span data-ttu-id="e1cfd-108">闲/忙提供商</span><span class="sxs-lookup"><span data-stu-id="e1cfd-108">Free/busy provider</span></span>  <br/> |
|<span data-ttu-id="e1cfd-109">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="e1cfd-109">Interface identifier:</span></span>  <br/> |<span data-ttu-id="e1cfd-110">**IEnumFBBlock**</span><span class="sxs-lookup"><span data-stu-id="e1cfd-110">**IEnumFBBlock**</span></span> <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="e1cfd-111">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="e1cfd-111">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="e1cfd-112">Next</span><span class="sxs-lookup"><span data-stu-id="e1cfd-112">Next</span></span>](ienumfbblock-next.md) <br/> |<span data-ttu-id="e1cfd-113">获取枚举中的下一个指定数量的忙/闲数据块。</span><span class="sxs-lookup"><span data-stu-id="e1cfd-113">Gets the next specified number of blocks of free/busy data in an enumeration.</span></span>  <br/> |
|[<span data-ttu-id="e1cfd-114">Skip</span><span class="sxs-lookup"><span data-stu-id="e1cfd-114">Skip</span></span>](ienumfbblock-skip.md) <br/> |<span data-ttu-id="e1cfd-115">跳过指定数量的忙/闲数据块。</span><span class="sxs-lookup"><span data-stu-id="e1cfd-115">Skips a specified number of blocks of free/busy data.</span></span>  <br/> |
|[<span data-ttu-id="e1cfd-116">Reset</span><span class="sxs-lookup"><span data-stu-id="e1cfd-116">Reset</span></span>](ienumfbblock-reset.md) <br/> |<span data-ttu-id="e1cfd-117">通过将游标设置为开头来重置枚举数。</span><span class="sxs-lookup"><span data-stu-id="e1cfd-117">Resets the enumerator by setting the cursor to the beginning.</span></span>  <br/> |
|[<span data-ttu-id="e1cfd-118">Clone</span><span class="sxs-lookup"><span data-stu-id="e1cfd-118">Clone</span></span>](ienumfbblock-clone.md) <br/> |<span data-ttu-id="e1cfd-119">使用相同的时间限制创建枚举数的副本, 但将游标设置为枚举器的开头。</span><span class="sxs-lookup"><span data-stu-id="e1cfd-119">Creates a copy of the enumerator, using the same time restriction but setting the cursor to the beginning of the enumerator.</span></span>  <br/> |
|[<span data-ttu-id="e1cfd-120">Restrict</span><span class="sxs-lookup"><span data-stu-id="e1cfd-120">Restrict</span></span>](ienumfbblock-restrict.md) <br/> |<span data-ttu-id="e1cfd-121">将枚举限制在指定时间段内。</span><span class="sxs-lookup"><span data-stu-id="e1cfd-121">Restricts the enumeration to a specified time period.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e1cfd-122">注解</span><span class="sxs-lookup"><span data-stu-id="e1cfd-122">Remarks</span></span>

<span data-ttu-id="e1cfd-123">枚举包含不能按时重叠的忙/闲数据块。</span><span class="sxs-lookup"><span data-stu-id="e1cfd-123">An enumeration contains free/busy blocks of data that do not overlap in time.</span></span> <span data-ttu-id="e1cfd-124">当日历上有重叠项目时, Outlook 将基于此优先级顺序, 合并这些项目以形成枚举中不重叠的忙/闲块: 外出、忙碌、暂定。</span><span class="sxs-lookup"><span data-stu-id="e1cfd-124">When there are overlapping items on a calendar, Outlook merges these items to form non-overlapping free/busy blocks in the enumeration based on this order of precedence: out-of-office, busy, tentative.</span></span>
  
<span data-ttu-id="e1cfd-125">忙/闲提供程序通过[IFreeBusyData](ifreebusydata.md)获取用户的时间范围的此接口和枚举。</span><span class="sxs-lookup"><span data-stu-id="e1cfd-125">A free/busy provider obtains this interface and the enumeration for a time range for a user through [IFreeBusyData](ifreebusydata.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e1cfd-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1cfd-126">See also</span></span>

- [<span data-ttu-id="e1cfd-127">关于忙/闲 API</span><span class="sxs-lookup"><span data-stu-id="e1cfd-127">About the Free/Busy API</span></span>](about-the-free-busy-api.md)  
- [<span data-ttu-id="e1cfd-128">常量 (忙/闲 API)</span><span class="sxs-lookup"><span data-stu-id="e1cfd-128">Constants (Free/busy API)</span></span>](constants-free-busy-api.md)  
- [<span data-ttu-id="e1cfd-129">IFreeBusyData</span><span class="sxs-lookup"><span data-stu-id="e1cfd-129">IFreeBusyData</span></span>](ifreebusydata.md)

