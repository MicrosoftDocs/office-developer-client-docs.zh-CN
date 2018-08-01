---
title: IFreeBusyDataSetFBRange
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4e7147ea-0eb0-324a-80d8-4f0eef654c32
description: 设置用户的忙/闲数据块枚举的时间范围。
ms.openlocfilehash: 84a25a2dd43f594caa075d90e4f183086452184a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774224"
---
# <a name="ifreebusydatasetfbrange"></a><span data-ttu-id="71696-103">IFreeBusyData::SetFBRange</span><span class="sxs-lookup"><span data-stu-id="71696-103">IFreeBusyData::SetFBRange</span></span>

<span data-ttu-id="71696-104">设置用户的忙/闲数据块枚举的时间范围。</span><span class="sxs-lookup"><span data-stu-id="71696-104">Sets the range of time for an enumeration of free/busy blocks of data for a user.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="71696-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="71696-105">Quick info</span></span>

<span data-ttu-id="71696-106">请参阅[IFreeBusyData](ifreebusydata.md)。</span><span class="sxs-lookup"><span data-stu-id="71696-106">See [IFreeBusyData](ifreebusydata.md).</span></span>
  
```cpp
HRESULT SetFBRange(
     LONG rtmStart,
     LONG rtmEnd
);
```

## <a name="parameters"></a><span data-ttu-id="71696-107">参数</span><span class="sxs-lookup"><span data-stu-id="71696-107">Parameters</span></span>

<span data-ttu-id="71696-108">_rtmStart_</span><span class="sxs-lookup"><span data-stu-id="71696-108">_rtmStart_</span></span>
  
> <span data-ttu-id="71696-109">[in]忙/闲信息的开始相对时间值。</span><span class="sxs-lookup"><span data-stu-id="71696-109">[in] A relative time value for the start of free/busy information.</span></span> <span data-ttu-id="71696-110">此值是自 1601 年 1 月 1 日以来的分钟数。</span><span class="sxs-lookup"><span data-stu-id="71696-110">This value is the number of minutes since January 1, 1601.</span></span>
    
<span data-ttu-id="71696-111">_rtmEnd_</span><span class="sxs-lookup"><span data-stu-id="71696-111">_rtmEnd_</span></span>
  
> <span data-ttu-id="71696-112">[in]忙/闲信息的末尾相对时间值。</span><span class="sxs-lookup"><span data-stu-id="71696-112">[in] A relative time value for the end of free/busy information.</span></span> <span data-ttu-id="71696-113">此值是自 1601 年 1 月 1 日以来的分钟数。</span><span class="sxs-lookup"><span data-stu-id="71696-113">This value is the number of minutes since January 1, 1601.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="71696-114">返回值</span><span class="sxs-lookup"><span data-stu-id="71696-114">Return values</span></span>

<span data-ttu-id="71696-115">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="71696-115">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="71696-116">注释</span><span class="sxs-lookup"><span data-stu-id="71696-116">Remarks</span></span>

<span data-ttu-id="71696-117">此方法用于指示要为其检索详细信息的日历项目的时间范围。</span><span class="sxs-lookup"><span data-stu-id="71696-117">This method is used to indicate the time range of calendar items for which to retrieve details.</span></span> <span data-ttu-id="71696-118">缓存和[IFreeBusyData::GetFBPublishRange](ifreebusydata-getfbpublishrange.md)的后续调用中返回*ftmStart*和*ftmEnd*的值。</span><span class="sxs-lookup"><span data-stu-id="71696-118">The values of  *ftmStart*  and  *ftmEnd*  are cached and returned in a subsequent call of [IFreeBusyData::GetFBPublishRange](ifreebusydata-getfbpublishrange.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="71696-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71696-119">See also</span></span>

- [<span data-ttu-id="71696-120">IFreeBusyData::EnumBlocks</span><span class="sxs-lookup"><span data-stu-id="71696-120">IFreeBusyData::EnumBlocks</span></span>](ifreebusydata-enumblocks.md)
- [<span data-ttu-id="71696-121">IFreeBusyData::GetFBPublishRange</span><span class="sxs-lookup"><span data-stu-id="71696-121">IFreeBusyData::GetFBPublishRange</span></span>](ifreebusydata-getfbpublishrange.md)
- [<span data-ttu-id="71696-122">使用访问忙/闲数据的相对时间</span><span class="sxs-lookup"><span data-stu-id="71696-122">Use relative time to access free/busy data</span></span>](how-to-use-relative-time-to-access-free-busy-data.md)

