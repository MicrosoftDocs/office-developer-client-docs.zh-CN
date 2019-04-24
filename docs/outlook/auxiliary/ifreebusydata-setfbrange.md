---
title: IFreeBusyDataSetFBRange
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4e7147ea-0eb0-324a-80d8-4f0eef654c32
description: 设置用户的忙/闲数据块枚举的时间范围。
ms.openlocfilehash: 4647453acb0e530521aa808f7f017e3e311644bb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317476"
---
# <a name="ifreebusydatasetfbrange"></a><span data-ttu-id="4c10a-103">IFreeBusyData::SetFBRange</span><span class="sxs-lookup"><span data-stu-id="4c10a-103">IFreeBusyData::SetFBRange</span></span>

<span data-ttu-id="4c10a-104">设置用户的忙/闲数据块枚举的时间范围。</span><span class="sxs-lookup"><span data-stu-id="4c10a-104">Sets the range of time for an enumeration of free/busy blocks of data for a user.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="4c10a-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="4c10a-105">Quick info</span></span>

<span data-ttu-id="4c10a-106">请参阅[IFreeBusyData](ifreebusydata.md)。</span><span class="sxs-lookup"><span data-stu-id="4c10a-106">See [IFreeBusyData](ifreebusydata.md).</span></span>
  
```cpp
HRESULT SetFBRange(
     LONG rtmStart,
     LONG rtmEnd
);
```

## <a name="parameters"></a><span data-ttu-id="4c10a-107">参数</span><span class="sxs-lookup"><span data-stu-id="4c10a-107">Parameters</span></span>

<span data-ttu-id="4c10a-108">_rtmStart_</span><span class="sxs-lookup"><span data-stu-id="4c10a-108">_rtmStart_</span></span>
  
> <span data-ttu-id="4c10a-109">实时忙/闲信息开始的相对时间值。</span><span class="sxs-lookup"><span data-stu-id="4c10a-109">[in] A relative time value for the start of free/busy information.</span></span> <span data-ttu-id="4c10a-110">此值是自1601年1月1日以来的分钟数。</span><span class="sxs-lookup"><span data-stu-id="4c10a-110">This value is the number of minutes since January 1, 1601.</span></span>
    
<span data-ttu-id="4c10a-111">_rtmEnd_</span><span class="sxs-lookup"><span data-stu-id="4c10a-111">_rtmEnd_</span></span>
  
> <span data-ttu-id="4c10a-112">实时忙/闲信息结束的相对时间值。</span><span class="sxs-lookup"><span data-stu-id="4c10a-112">[in] A relative time value for the end of free/busy information.</span></span> <span data-ttu-id="4c10a-113">此值是自1601年1月1日以来的分钟数。</span><span class="sxs-lookup"><span data-stu-id="4c10a-113">This value is the number of minutes since January 1, 1601.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="4c10a-114">返回值</span><span class="sxs-lookup"><span data-stu-id="4c10a-114">Return values</span></span>

<span data-ttu-id="4c10a-115">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="4c10a-115">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="4c10a-116">注解</span><span class="sxs-lookup"><span data-stu-id="4c10a-116">Remarks</span></span>

<span data-ttu-id="4c10a-117">此方法用于指示要检索其详细信息的日历项目的时间范围。</span><span class="sxs-lookup"><span data-stu-id="4c10a-117">This method is used to indicate the time range of calendar items for which to retrieve details.</span></span> <span data-ttu-id="4c10a-118">*ftmStart*和*ftmEnd*的值在随后对[IFreeBusyData:: GetFBPublishRange](ifreebusydata-getfbpublishrange.md)的调用中进行缓存和返回。</span><span class="sxs-lookup"><span data-stu-id="4c10a-118">The values of  *ftmStart*  and  *ftmEnd*  are cached and returned in a subsequent call of [IFreeBusyData::GetFBPublishRange](ifreebusydata-getfbpublishrange.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4c10a-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c10a-119">See also</span></span>

- [<span data-ttu-id="4c10a-120">IFreeBusyData::EnumBlocks</span><span class="sxs-lookup"><span data-stu-id="4c10a-120">IFreeBusyData::EnumBlocks</span></span>](ifreebusydata-enumblocks.md)
- [<span data-ttu-id="4c10a-121">IFreeBusyData::GetFBPublishRange</span><span class="sxs-lookup"><span data-stu-id="4c10a-121">IFreeBusyData::GetFBPublishRange</span></span>](ifreebusydata-getfbpublishrange.md)
- [<span data-ttu-id="4c10a-122">使用访问忙/闲数据的相对时间</span><span class="sxs-lookup"><span data-stu-id="4c10a-122">Use relative time to access free/busy data</span></span>](how-to-use-relative-time-to-access-free-busy-data.md)

