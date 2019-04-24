---
title: IFreeBusyDataEnumBlocks
manager: soliver
ms.date: 02/18/2016
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0cd5a5ae-118f-c7da-4eda-e97590fc39d4
description: 获取一个接口, 用于在指定的时间范围内枚举用户的忙/闲数据块。
ms.openlocfilehash: 51a77b2f47166628db07259ef841e0d6173ee370
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317554"
---
# <a name="ifreebusydataenumblocks"></a><span data-ttu-id="b828f-103">IFreeBusyData::EnumBlocks</span><span class="sxs-lookup"><span data-stu-id="b828f-103">IFreeBusyData::EnumBlocks</span></span>

<span data-ttu-id="b828f-104">获取一个接口, 用于在指定的时间范围内枚举用户的忙/闲数据块。</span><span class="sxs-lookup"><span data-stu-id="b828f-104">Gets an interface that enumerates free/busy blocks of data for a user within a specified time range.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="b828f-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="b828f-105">Quick info</span></span>

<span data-ttu-id="b828f-106">请参阅[IFreeBusyData](ifreebusydata.md)。</span><span class="sxs-lookup"><span data-stu-id="b828f-106">See [IFreeBusyData](ifreebusydata.md).</span></span>
  
```cpp
HRESULT EnumBlocks( 
     IEnumFBBlock **ppenumfb,  
     FILETIME ftmStart, 
     FILETIME ftmEnd 
);

```

## <a name="parameters"></a><span data-ttu-id="b828f-107">参数</span><span class="sxs-lookup"><span data-stu-id="b828f-107">Parameters</span></span>

<span data-ttu-id="b828f-108">_ppenumfb_</span><span class="sxs-lookup"><span data-stu-id="b828f-108">_ppenumfb_</span></span>
  
> <span data-ttu-id="b828f-109">排除用于枚举忙/闲块的接口。</span><span class="sxs-lookup"><span data-stu-id="b828f-109">[out] An interface to enumerate free/busy blocks.</span></span>
    
<span data-ttu-id="b828f-110">_ftmStart_</span><span class="sxs-lookup"><span data-stu-id="b828f-110">_ftmStart_</span></span>
  
> <span data-ttu-id="b828f-111">实时枚举的开始时间。</span><span class="sxs-lookup"><span data-stu-id="b828f-111">[in] The start time for the enumeration.</span></span> <span data-ttu-id="b828f-112">它用[FILETIME](https://msdn.microsoft.com/library/ 4af8e79a-697e-44a1-8576-fdc57726e9ef.aspx)表示。</span><span class="sxs-lookup"><span data-stu-id="b828f-112">It is expressed in [FILETIME](https://msdn.microsoft.com/library/ 4af8e79a-697e-44a1-8576-fdc57726e9ef.aspx).</span></span>
    
<span data-ttu-id="b828f-113">_ftmEnd_</span><span class="sxs-lookup"><span data-stu-id="b828f-113">_ftmEnd_</span></span>
  
> <span data-ttu-id="b828f-114">实时枚举的结束时间。</span><span class="sxs-lookup"><span data-stu-id="b828f-114">[in] The end time for the enumeration.</span></span> <span data-ttu-id="b828f-115">它用**FILETIME**表示。</span><span class="sxs-lookup"><span data-stu-id="b828f-115">It is expressed in **FILETIME**.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="b828f-116">返回值</span><span class="sxs-lookup"><span data-stu-id="b828f-116">Return values</span></span>

<span data-ttu-id="b828f-117">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="b828f-117">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="b828f-118">注解</span><span class="sxs-lookup"><span data-stu-id="b828f-118">Remarks</span></span>

<span data-ttu-id="b828f-119">此方法用于指示要检索其详细信息的日历项目的时间范围。</span><span class="sxs-lookup"><span data-stu-id="b828f-119">This method is used to indicate the time range of calendar items for which to retrieve details.</span></span> <span data-ttu-id="b828f-120">*ftmStart*和*ftmEnd*的值在随后对[IFreeBusyData:: GetFBPublishRange](ifreebusydata-getfbpublishrange.md)的调用中进行缓存和返回。</span><span class="sxs-lookup"><span data-stu-id="b828f-120">The values of  *ftmStart* and *ftmEnd* are cached and returned in a subsequent call of [IFreeBusyData::GetFBPublishRange](ifreebusydata-getfbpublishrange.md).</span></span>
  
<span data-ttu-id="b828f-121">闲/忙提供程序随后还可以使用返回的[IEnumFBBlock](ienumfbblock.md)接口访问枚举。</span><span class="sxs-lookup"><span data-stu-id="b828f-121">A free/busy provider can also subsequently use the returned [IEnumFBBlock](ienumfbblock.md) interface to access the enumeration.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b828f-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b828f-122">See also</span></span>

- [<span data-ttu-id="b828f-123">IEnumFBBlock</span><span class="sxs-lookup"><span data-stu-id="b828f-123">IEnumFBBlock</span></span>](ienumfbblock.md)
- [<span data-ttu-id="b828f-124">IFreeBusyData::GetFBPublishRange</span><span class="sxs-lookup"><span data-stu-id="b828f-124">IFreeBusyData::GetFBPublishRange</span></span>](ifreebusydata-getfbpublishrange.md)
- [<span data-ttu-id="b828f-125">IFreeBusyData::SetFBRange</span><span class="sxs-lookup"><span data-stu-id="b828f-125">IFreeBusyData::SetFBRange</span></span>](ifreebusydata-setfbrange.md)
- [<span data-ttu-id="b828f-126">使用访问忙/闲数据的相对时间</span><span class="sxs-lookup"><span data-stu-id="b828f-126">Use relative time to access free/busy data</span></span>](how-to-use-relative-time-to-access-free-busy-data.md)

