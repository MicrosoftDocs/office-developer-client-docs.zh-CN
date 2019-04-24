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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317526"
---
# <a name="ifreebusydatagetfbpublishrange"></a><span data-ttu-id="fad18-103">IFreeBusyData::GetFBPublishRange</span><span class="sxs-lookup"><span data-stu-id="fad18-103">IFreeBusyData::GetFBPublishRange</span></span>

<span data-ttu-id="fad18-104">获取用户的忙/闲数据块枚举的预设时间范围。</span><span class="sxs-lookup"><span data-stu-id="fad18-104">Gets a preset time range for an enumeration of free/busy blocks of data for a user.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="fad18-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="fad18-105">Quick info</span></span>

<span data-ttu-id="fad18-106">请参阅[IFreeBusyData](ifreebusydata.md)。</span><span class="sxs-lookup"><span data-stu-id="fad18-106">See [IFreeBusyData](ifreebusydata.md).</span></span>
  
```cpp
HRESULT GetFBPublishRange( 
     LONG *prtmStart,  
     LONG *prtmEnd 
);

```

## <a name="parameters"></a><span data-ttu-id="fad18-107">参数</span><span class="sxs-lookup"><span data-stu-id="fad18-107">Parameters</span></span>

<span data-ttu-id="fad18-108">_prtmStart_</span><span class="sxs-lookup"><span data-stu-id="fad18-108">_prtmStart_</span></span>
  
> <span data-ttu-id="fad18-109">排除忙/闲信息开始的相对时间值。</span><span class="sxs-lookup"><span data-stu-id="fad18-109">[out] A relative time value for the start of free/busy information.</span></span> <span data-ttu-id="fad18-110">此值是自1601年1月1日以来的分钟数。</span><span class="sxs-lookup"><span data-stu-id="fad18-110">This value is the number of minutes since January 1, 1601.</span></span>
    
<span data-ttu-id="fad18-111">_prtmEnd_</span><span class="sxs-lookup"><span data-stu-id="fad18-111">_prtmEnd_</span></span>
  
> <span data-ttu-id="fad18-112">排除忙/闲信息结束的相对时间值。</span><span class="sxs-lookup"><span data-stu-id="fad18-112">[out] A relative time value for the end of free/busy information.</span></span> <span data-ttu-id="fad18-113">此值是自1601年1月1日以来的分钟数。</span><span class="sxs-lookup"><span data-stu-id="fad18-113">This value is the number of minutes since January 1, 1601.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="fad18-114">返回值</span><span class="sxs-lookup"><span data-stu-id="fad18-114">Return values</span></span>

<span data-ttu-id="fad18-115">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="fad18-115">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="fad18-116">注解</span><span class="sxs-lookup"><span data-stu-id="fad18-116">Remarks</span></span>

<span data-ttu-id="fad18-117">忙/闲提供程序调用[IFreeBusyData:: EnumBlocks](ifreebusydata-enumblocks.md)或[IFreeBusyData:: SetFBRange](ifreebusydata-setfbrange.md)设置枚举的时间范围。</span><span class="sxs-lookup"><span data-stu-id="fad18-117">A free/busy provider calls [IFreeBusyData::EnumBlocks](ifreebusydata-enumblocks.md) or [IFreeBusyData::SetFBRange](ifreebusydata-setfbrange.md) to set the time range for an enumeration.</span></span> <span data-ttu-id="fad18-118">如果尚未调用[IFreeBusyData:: EnumBlocks](ifreebusydata-enumblocks.md)或[IFreeBusyData:: SetFBRange](ifreebusydata-setfbrange.md) , **prtmStart**和**prtmEnd**的默认值必须设置介于 1601 00:00: 00Z 和8月31日 4500 11:59: 59Z 之间的默认值。分别.</span><span class="sxs-lookup"><span data-stu-id="fad18-118">If either [IFreeBusyData::EnumBlocks](ifreebusydata-enumblocks.md) or [IFreeBusyData::SetFBRange](ifreebusydata-setfbrange.md) has not been called, the default values for **prtmStart** and **prtmEnd** must be set between April 1st, 1601 00:00:00Z and August 31, 4500 11:59:59Z respectively.</span></span> <span data-ttu-id="fad18-119">此外, 不应将开始时间设置为大于结束时间。</span><span class="sxs-lookup"><span data-stu-id="fad18-119">Additionally, you should not set the start time to be greater than the end time.</span></span> 
  
<span data-ttu-id="fad18-120">**IFreeBusyData:: GetFBPublishRange**必须为**IFreeBusyData:: EnumBlocks**或**IFreeBusyData:: SetFBRange**的最近一次调用设置的时间范围返回缓存值。</span><span class="sxs-lookup"><span data-stu-id="fad18-120">**IFreeBusyData::GetFBPublishRange** must return the cached values for the time range set by the most recent call for **IFreeBusyData::EnumBlocks** or **IFreeBusyData::SetFBRange**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="fad18-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fad18-121">See also</span></span>

- [<span data-ttu-id="fad18-122">使用访问忙/闲数据的相对时间</span><span class="sxs-lookup"><span data-stu-id="fad18-122">Use relative time to access free/busy data</span></span>](how-to-use-relative-time-to-access-free-busy-data.md)
- [<span data-ttu-id="fad18-123">IFreeBusyData::EnumBlocks</span><span class="sxs-lookup"><span data-stu-id="fad18-123">IFreeBusyData::EnumBlocks</span></span>](ifreebusydata-enumblocks.md)
- [<span data-ttu-id="fad18-124">IFreeBusyData::SetFBRange</span><span class="sxs-lookup"><span data-stu-id="fad18-124">IFreeBusyData::SetFBRange</span></span>](ifreebusydata-setfbrange.md)

