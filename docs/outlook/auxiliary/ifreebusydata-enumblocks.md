---
title: IFreeBusyDataEnumBlocks
manager: soliver
ms.date: 02/18/2016
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0cd5a5ae-118f-c7da-4eda-e97590fc39d4
description: 获取枚举忙/闲数据块的指定的时间范围内的用户界面。
ms.openlocfilehash: ab377b1029296b6b4bac68d7169dcf7b8dcd8b87
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774211"
---
# <a name="ifreebusydataenumblocks"></a><span data-ttu-id="d584f-103">IFreeBusyData::EnumBlocks</span><span class="sxs-lookup"><span data-stu-id="d584f-103">IFreeBusyData::EnumBlocks</span></span>

<span data-ttu-id="d584f-104">获取枚举忙/闲数据块的指定的时间范围内的用户界面。</span><span class="sxs-lookup"><span data-stu-id="d584f-104">Gets an interface that enumerates free/busy blocks of data for a user within a specified time range.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="d584f-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="d584f-105">Quick info</span></span>

<span data-ttu-id="d584f-106">请参阅[IFreeBusyData](ifreebusydata.md)。</span><span class="sxs-lookup"><span data-stu-id="d584f-106">See [IFreeBusyData](ifreebusydata.md).</span></span>
  
```cpp
HRESULT EnumBlocks( 
     IEnumFBBlock **ppenumfb,  
     FILETIME ftmStart, 
     FILETIME ftmEnd 
);

```

## <a name="parameters"></a><span data-ttu-id="d584f-107">参数</span><span class="sxs-lookup"><span data-stu-id="d584f-107">Parameters</span></span>

<span data-ttu-id="d584f-108">_ppenumfb_</span><span class="sxs-lookup"><span data-stu-id="d584f-108">_ppenumfb_</span></span>
  
> <span data-ttu-id="d584f-109">[输出]接口来枚举忙/闲块。</span><span class="sxs-lookup"><span data-stu-id="d584f-109">[out] An interface to enumerate free/busy blocks.</span></span>
    
<span data-ttu-id="d584f-110">_ftmStart_</span><span class="sxs-lookup"><span data-stu-id="d584f-110">_ftmStart_</span></span>
  
> <span data-ttu-id="d584f-111">[in]枚举的开始时间。</span><span class="sxs-lookup"><span data-stu-id="d584f-111">[in] The start time for the enumeration.</span></span> <span data-ttu-id="d584f-112">在[FILETIME](http://msdn.microsoft.com/library/ 4af8e79a-697e-44a1-8576-fdc57726e9ef.aspx)表示。</span><span class="sxs-lookup"><span data-stu-id="d584f-112">It is expressed in [FILETIME](http://msdn.microsoft.com/library/ 4af8e79a-697e-44a1-8576-fdc57726e9ef.aspx).</span></span>
    
<span data-ttu-id="d584f-113">_ftmEnd_</span><span class="sxs-lookup"><span data-stu-id="d584f-113">_ftmEnd_</span></span>
  
> <span data-ttu-id="d584f-114">[in]枚举的结束时间。</span><span class="sxs-lookup"><span data-stu-id="d584f-114">[in] The end time for the enumeration.</span></span> <span data-ttu-id="d584f-115">在**FILETIME**表示。</span><span class="sxs-lookup"><span data-stu-id="d584f-115">It is expressed in **FILETIME**.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="d584f-116">返回值</span><span class="sxs-lookup"><span data-stu-id="d584f-116">Return values</span></span>

<span data-ttu-id="d584f-117">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="d584f-117">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d584f-118">注释</span><span class="sxs-lookup"><span data-stu-id="d584f-118">Remarks</span></span>

<span data-ttu-id="d584f-119">此方法用于指示要为其检索详细信息的日历项目的时间范围。</span><span class="sxs-lookup"><span data-stu-id="d584f-119">This method is used to indicate the time range of calendar items for which to retrieve details.</span></span> <span data-ttu-id="d584f-120">缓存和[IFreeBusyData::GetFBPublishRange](ifreebusydata-getfbpublishrange.md)的后续调用中返回*ftmStart*和*ftmEnd*的值。</span><span class="sxs-lookup"><span data-stu-id="d584f-120">The values of  *ftmStart* and *ftmEnd* are cached and returned in a subsequent call of [IFreeBusyData::GetFBPublishRange](ifreebusydata-getfbpublishrange.md).</span></span>
  
<span data-ttu-id="d584f-121">忙/闲信息的提供程序还随后可以使用返回的[IEnumFBBlock](ienumfbblock.md)接口访问枚举。</span><span class="sxs-lookup"><span data-stu-id="d584f-121">A free/busy provider can also subsequently use the returned [IEnumFBBlock](ienumfbblock.md) interface to access the enumeration.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d584f-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d584f-122">See also</span></span>

- [<span data-ttu-id="d584f-123">IEnumFBBlock</span><span class="sxs-lookup"><span data-stu-id="d584f-123">IEnumFBBlock</span></span>](ienumfbblock.md)
- [<span data-ttu-id="d584f-124">IFreeBusyData::GetFBPublishRange</span><span class="sxs-lookup"><span data-stu-id="d584f-124">IFreeBusyData::GetFBPublishRange</span></span>](ifreebusydata-getfbpublishrange.md)
- [<span data-ttu-id="d584f-125">IFreeBusyData::SetFBRange</span><span class="sxs-lookup"><span data-stu-id="d584f-125">IFreeBusyData::SetFBRange</span></span>](ifreebusydata-setfbrange.md)
- [<span data-ttu-id="d584f-126">使用访问忙/闲数据的相对时间</span><span class="sxs-lookup"><span data-stu-id="d584f-126">Use relative time to access free/busy data</span></span>](how-to-use-relative-time-to-access-free-busy-data.md)

