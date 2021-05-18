---
title: IFreeBusyDataEnumBlocks
manager: soliver
ms.date: 02/18/2016
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0cd5a5ae-118f-c7da-4eda-e97590fc39d4
description: 获取一个接口，该接口枚举指定时间范围内用户的忙/闲数据块。
ms.openlocfilehash: 51a77b2f47166628db07259ef841e0d6173ee370
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317554"
---
# <a name="ifreebusydataenumblocks"></a><span data-ttu-id="7e86d-103">IFreeBusyData::EnumBlocks</span><span class="sxs-lookup"><span data-stu-id="7e86d-103">IFreeBusyData::EnumBlocks</span></span>

<span data-ttu-id="7e86d-104">获取一个接口，该接口枚举指定时间范围内用户的忙/闲数据块。</span><span class="sxs-lookup"><span data-stu-id="7e86d-104">Gets an interface that enumerates free/busy blocks of data for a user within a specified time range.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="7e86d-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="7e86d-105">Quick info</span></span>

<span data-ttu-id="7e86d-106">请参阅 [IFreeBusyData](ifreebusydata.md)。</span><span class="sxs-lookup"><span data-stu-id="7e86d-106">See [IFreeBusyData](ifreebusydata.md).</span></span>
  
```cpp
HRESULT EnumBlocks( 
     IEnumFBBlock **ppenumfb,  
     FILETIME ftmStart, 
     FILETIME ftmEnd 
);

```

## <a name="parameters"></a><span data-ttu-id="7e86d-107">参数</span><span class="sxs-lookup"><span data-stu-id="7e86d-107">Parameters</span></span>

<span data-ttu-id="7e86d-108">_ppenumfb_</span><span class="sxs-lookup"><span data-stu-id="7e86d-108">_ppenumfb_</span></span>
  
> <span data-ttu-id="7e86d-109">[out]用于枚举忙/闲块的接口。</span><span class="sxs-lookup"><span data-stu-id="7e86d-109">[out] An interface to enumerate free/busy blocks.</span></span>
    
<span data-ttu-id="7e86d-110">_ftmStart_</span><span class="sxs-lookup"><span data-stu-id="7e86d-110">_ftmStart_</span></span>
  
> <span data-ttu-id="7e86d-111">[in]枚举的开始时间。</span><span class="sxs-lookup"><span data-stu-id="7e86d-111">[in] The start time for the enumeration.</span></span> <span data-ttu-id="7e86d-112">它用 [FILETIME 表示](https://msdn.microsoft.com/library/ 4af8e79a-697e-44a1-8576-fdc57726e9ef.aspx)。</span><span class="sxs-lookup"><span data-stu-id="7e86d-112">It is expressed in [FILETIME](https://msdn.microsoft.com/library/ 4af8e79a-697e-44a1-8576-fdc57726e9ef.aspx).</span></span>
    
<span data-ttu-id="7e86d-113">_ftmEnd_</span><span class="sxs-lookup"><span data-stu-id="7e86d-113">_ftmEnd_</span></span>
  
> <span data-ttu-id="7e86d-114">[in]枚举的结束时间。</span><span class="sxs-lookup"><span data-stu-id="7e86d-114">[in] The end time for the enumeration.</span></span> <span data-ttu-id="7e86d-115">它用 **FILETIME 表示**。</span><span class="sxs-lookup"><span data-stu-id="7e86d-115">It is expressed in **FILETIME**.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="7e86d-116">返回值</span><span class="sxs-lookup"><span data-stu-id="7e86d-116">Return values</span></span>

<span data-ttu-id="7e86d-117">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="7e86d-117">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="7e86d-118">备注</span><span class="sxs-lookup"><span data-stu-id="7e86d-118">Remarks</span></span>

<span data-ttu-id="7e86d-119">此方法用于指示要检索其详细信息的日历项目的时区。</span><span class="sxs-lookup"><span data-stu-id="7e86d-119">This method is used to indicate the time range of calendar items for which to retrieve details.</span></span> <span data-ttu-id="7e86d-120">*ftmStart* 和 *ftmEnd* 的值在 [IFreeBusyData：：GetFBPublishRange](ifreebusydata-getfbpublishrange.md)的后续调用中缓存并返回。</span><span class="sxs-lookup"><span data-stu-id="7e86d-120">The values of  *ftmStart* and *ftmEnd* are cached and returned in a subsequent call of [IFreeBusyData::GetFBPublishRange](ifreebusydata-getfbpublishrange.md).</span></span>
  
<span data-ttu-id="7e86d-121">忙/闲提供程序随后还可使用返回的 [IEnumFBBlock](ienumfbblock.md) 接口访问枚举。</span><span class="sxs-lookup"><span data-stu-id="7e86d-121">A free/busy provider can also subsequently use the returned [IEnumFBBlock](ienumfbblock.md) interface to access the enumeration.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7e86d-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e86d-122">See also</span></span>

- [<span data-ttu-id="7e86d-123">IEnumFBBlock</span><span class="sxs-lookup"><span data-stu-id="7e86d-123">IEnumFBBlock</span></span>](ienumfbblock.md)
- [<span data-ttu-id="7e86d-124">IFreeBusyData::GetFBPublishRange</span><span class="sxs-lookup"><span data-stu-id="7e86d-124">IFreeBusyData::GetFBPublishRange</span></span>](ifreebusydata-getfbpublishrange.md)
- [<span data-ttu-id="7e86d-125">IFreeBusyData::SetFBRange</span><span class="sxs-lookup"><span data-stu-id="7e86d-125">IFreeBusyData::SetFBRange</span></span>](ifreebusydata-setfbrange.md)
- [<span data-ttu-id="7e86d-126">使用访问忙/闲数据的相对时间</span><span class="sxs-lookup"><span data-stu-id="7e86d-126">Use relative time to access free/busy data</span></span>](how-to-use-relative-time-to-access-free-busy-data.md)

