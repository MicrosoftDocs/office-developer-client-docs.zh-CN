---
title: IFreeBusyDataGetFBPublishRange
manager: soliver
ms.date: 09/23/2016
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1a8bbe0c-17d1-9349-4c63-f257faf4edda
description: 获取用户的忙/闲数据块枚举的预设时间范围。
ms.openlocfilehash: 26951ea6a885f8d0e5e6a2fb5bcf9a63069c7f44
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430075"
---
# <a name="ifreebusydatagetfbpublishrange"></a><span data-ttu-id="e20fe-103">IFreeBusyData::GetFBPublishRange</span><span class="sxs-lookup"><span data-stu-id="e20fe-103">IFreeBusyData::GetFBPublishRange</span></span>

<span data-ttu-id="e20fe-104">获取用户的忙/闲数据块枚举的预设时间范围。</span><span class="sxs-lookup"><span data-stu-id="e20fe-104">Gets a preset time range for an enumeration of free/busy blocks of data for a user.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="e20fe-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="e20fe-105">Quick info</span></span>

<span data-ttu-id="e20fe-106">请参阅 [IFreeBusyData](ifreebusydata.md)。</span><span class="sxs-lookup"><span data-stu-id="e20fe-106">See [IFreeBusyData](ifreebusydata.md).</span></span>
  
```cpp
HRESULT GetFBPublishRange( 
     LONG *prtmStart,  
     LONG *prtmEnd 
);

```

## <a name="parameters"></a><span data-ttu-id="e20fe-107">参数</span><span class="sxs-lookup"><span data-stu-id="e20fe-107">Parameters</span></span>

<span data-ttu-id="e20fe-108">_prtmStart_</span><span class="sxs-lookup"><span data-stu-id="e20fe-108">_prtmStart_</span></span>
  
> <span data-ttu-id="e20fe-109">[out]忙/闲信息开始的相对时间值。</span><span class="sxs-lookup"><span data-stu-id="e20fe-109">[out] A relative time value for the start of free/busy information.</span></span> <span data-ttu-id="e20fe-110">此值是自 1601 年 1 月 1 日起的分钟数。</span><span class="sxs-lookup"><span data-stu-id="e20fe-110">This value is the number of minutes since January 1, 1601.</span></span>
    
<span data-ttu-id="e20fe-111">_prtmEnd_</span><span class="sxs-lookup"><span data-stu-id="e20fe-111">_prtmEnd_</span></span>
  
> <span data-ttu-id="e20fe-112">[out]忙/闲信息结尾的相对时间值。</span><span class="sxs-lookup"><span data-stu-id="e20fe-112">[out] A relative time value for the end of free/busy information.</span></span> <span data-ttu-id="e20fe-113">此值是自 1601 年 1 月 1 日起的分钟数。</span><span class="sxs-lookup"><span data-stu-id="e20fe-113">This value is the number of minutes since January 1, 1601.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="e20fe-114">返回值</span><span class="sxs-lookup"><span data-stu-id="e20fe-114">Return values</span></span>

<span data-ttu-id="e20fe-115">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="e20fe-115">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="e20fe-116">备注</span><span class="sxs-lookup"><span data-stu-id="e20fe-116">Remarks</span></span>

<span data-ttu-id="e20fe-117">忙/闲提供程序调用 [IFreeBusyData：：EnumBlocks](ifreebusydata-enumblocks.md) 或 [IFreeBusyData：：SetFBRange](ifreebusydata-setfbrange.md) 来设置枚举的时区。</span><span class="sxs-lookup"><span data-stu-id="e20fe-117">A free/busy provider calls [IFreeBusyData::EnumBlocks](ifreebusydata-enumblocks.md) or [IFreeBusyData::SetFBRange](ifreebusydata-setfbrange.md) to set the time range for an enumeration.</span></span> <span data-ttu-id="e20fe-118">如果未调用 [IFreeBusyData：：EnumBlocks](ifreebusydata-enumblocks.md) 或 [IFreeBusyData：：SetFBRange，](ifreebusydata-setfbrange.md) 则必须分别在 1601 年 4 月 1 日 00：00：00Z 和 4500 11：59：59Z 之间设置 **prtmStart** 和 **prtmEnd** 的默认值。</span><span class="sxs-lookup"><span data-stu-id="e20fe-118">If either [IFreeBusyData::EnumBlocks](ifreebusydata-enumblocks.md) or [IFreeBusyData::SetFBRange](ifreebusydata-setfbrange.md) has not been called, the default values for **prtmStart** and **prtmEnd** must be set between April 1st, 1601 00:00:00Z and August 31, 4500 11:59:59Z respectively.</span></span> <span data-ttu-id="e20fe-119">此外，不应将开始时间设置为大于结束时间。</span><span class="sxs-lookup"><span data-stu-id="e20fe-119">Additionally, you should not set the start time to be greater than the end time.</span></span> 
  
<span data-ttu-id="e20fe-120">**IFreeBusyData：：GetFBPublishRange** 必须返回最近一次调用 **IFreeBusyData：：EnumBlocks** 或 **IFreeBusyData：：SetFBRange** 设置的时区的缓存值。</span><span class="sxs-lookup"><span data-stu-id="e20fe-120">**IFreeBusyData::GetFBPublishRange** must return the cached values for the time range set by the most recent call for **IFreeBusyData::EnumBlocks** or **IFreeBusyData::SetFBRange**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e20fe-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e20fe-121">See also</span></span>

- [<span data-ttu-id="e20fe-122">使用访问忙/闲数据的相对时间</span><span class="sxs-lookup"><span data-stu-id="e20fe-122">Use relative time to access free/busy data</span></span>](how-to-use-relative-time-to-access-free-busy-data.md)
- [<span data-ttu-id="e20fe-123">IFreeBusyData::EnumBlocks</span><span class="sxs-lookup"><span data-stu-id="e20fe-123">IFreeBusyData::EnumBlocks</span></span>](ifreebusydata-enumblocks.md)
- [<span data-ttu-id="e20fe-124">IFreeBusyData::SetFBRange</span><span class="sxs-lookup"><span data-stu-id="e20fe-124">IFreeBusyData::SetFBRange</span></span>](ifreebusydata-setfbrange.md)

