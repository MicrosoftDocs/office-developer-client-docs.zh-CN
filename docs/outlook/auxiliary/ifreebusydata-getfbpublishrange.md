---
title: IFreeBusyDataGetFBPublishRange
manager: soliver
ms.date: 09/23/2016
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1a8bbe0c-17d1-9349-4c63-f257faf4edda
description: 获取一个预设的时间范围的忙/闲信息的用户数据块枚举。
ms.openlocfilehash: 2a322a43da38a0b902789f4c83baaabd769154c7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774206"
---
# <a name="ifreebusydatagetfbpublishrange"></a><span data-ttu-id="5b201-103">IFreeBusyData::GetFBPublishRange</span><span class="sxs-lookup"><span data-stu-id="5b201-103">IFreeBusyData::GetFBPublishRange</span></span>

<span data-ttu-id="5b201-104">获取一个预设的时间范围的忙/闲信息的用户数据块枚举。</span><span class="sxs-lookup"><span data-stu-id="5b201-104">Gets a preset time range for an enumeration of free/busy blocks of data for a user.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="5b201-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="5b201-105">Quick info</span></span>

<span data-ttu-id="5b201-106">请参阅[IFreeBusyData](ifreebusydata.md)。</span><span class="sxs-lookup"><span data-stu-id="5b201-106">See [IFreeBusyData](ifreebusydata.md).</span></span>
  
```cpp
HRESULT GetFBPublishRange( 
     LONG *prtmStart,  
     LONG *prtmEnd 
);

```

## <a name="parameters"></a><span data-ttu-id="5b201-107">参数</span><span class="sxs-lookup"><span data-stu-id="5b201-107">Parameters</span></span>

<span data-ttu-id="5b201-108">_prtmStart_</span><span class="sxs-lookup"><span data-stu-id="5b201-108">_prtmStart_</span></span>
  
> <span data-ttu-id="5b201-109">[输出]忙/闲信息的开始相对时间值。</span><span class="sxs-lookup"><span data-stu-id="5b201-109">[out] A relative time value for the start of free/busy information.</span></span> <span data-ttu-id="5b201-110">此值是自 1601 年 1 月 1 日以来的分钟数。</span><span class="sxs-lookup"><span data-stu-id="5b201-110">This value is the number of minutes since January 1, 1601.</span></span>
    
<span data-ttu-id="5b201-111">_prtmEnd_</span><span class="sxs-lookup"><span data-stu-id="5b201-111">_prtmEnd_</span></span>
  
> <span data-ttu-id="5b201-112">[输出]忙/闲信息的末尾相对时间值。</span><span class="sxs-lookup"><span data-stu-id="5b201-112">[out] A relative time value for the end of free/busy information.</span></span> <span data-ttu-id="5b201-113">此值是自 1601 年 1 月 1 日以来的分钟数。</span><span class="sxs-lookup"><span data-stu-id="5b201-113">This value is the number of minutes since January 1, 1601.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="5b201-114">返回值</span><span class="sxs-lookup"><span data-stu-id="5b201-114">Return values</span></span>

<span data-ttu-id="5b201-115">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="5b201-115">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5b201-116">注释</span><span class="sxs-lookup"><span data-stu-id="5b201-116">Remarks</span></span>

<span data-ttu-id="5b201-117">忙/闲信息的提供程序调用[IFreeBusyData::EnumBlocks](ifreebusydata-enumblocks.md)或[IFreeBusyData::SetFBRange](ifreebusydata-setfbrange.md)设置枚举的时间范围。</span><span class="sxs-lookup"><span data-stu-id="5b201-117">A free/busy provider calls [IFreeBusyData::EnumBlocks](ifreebusydata-enumblocks.md) or [IFreeBusyData::SetFBRange](ifreebusydata-setfbrange.md) to set the time range for an enumeration.</span></span> <span data-ttu-id="5b201-118">如果尚未调用[IFreeBusyData::EnumBlocks](ifreebusydata-enumblocks.md)或[IFreeBusyData::SetFBRange](ifreebusydata-setfbrange.md) ，必须 00:00:00Z 1601 年 4 月 1 日和年 8 月 31 日 4500 11:59:59Z 之间设置**prtmStart**和**prtmEnd**的默认值分别。</span><span class="sxs-lookup"><span data-stu-id="5b201-118">If either [IFreeBusyData::EnumBlocks](ifreebusydata-enumblocks.md) or [IFreeBusyData::SetFBRange](ifreebusydata-setfbrange.md) has not been called, the default values for **prtmStart** and **prtmEnd** must be set between April 1st, 1601 00:00:00Z and August 31, 4500 11:59:59Z respectively.</span></span> <span data-ttu-id="5b201-119">此外，您不应设置为大于结束时间的开始时间。</span><span class="sxs-lookup"><span data-stu-id="5b201-119">Additionally, you should not set the start time to be greater than the end time.</span></span> 
  
<span data-ttu-id="5b201-120">**IFreeBusyData::GetFBPublishRange**必须返回**IFreeBusyData::EnumBlocks**或**IFreeBusyData::SetFBRange**最近呼叫的时间范围的缓存的值设置。</span><span class="sxs-lookup"><span data-stu-id="5b201-120">**IFreeBusyData::GetFBPublishRange** must return the cached values for the time range set by the most recent call for **IFreeBusyData::EnumBlocks** or **IFreeBusyData::SetFBRange**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5b201-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b201-121">See also</span></span>

- [<span data-ttu-id="5b201-122">使用访问忙/闲数据的相对时间</span><span class="sxs-lookup"><span data-stu-id="5b201-122">Use relative time to access free/busy data</span></span>](how-to-use-relative-time-to-access-free-busy-data.md)
- [<span data-ttu-id="5b201-123">IFreeBusyData::EnumBlocks</span><span class="sxs-lookup"><span data-stu-id="5b201-123">IFreeBusyData::EnumBlocks</span></span>](ifreebusydata-enumblocks.md)
- [<span data-ttu-id="5b201-124">IFreeBusyData::SetFBRange</span><span class="sxs-lookup"><span data-stu-id="5b201-124">IFreeBusyData::SetFBRange</span></span>](ifreebusydata-setfbrange.md)

