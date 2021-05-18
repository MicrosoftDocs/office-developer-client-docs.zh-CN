---
title: IFreeBusySupportLoadFreeBusyData
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f0baa310-7a53-07ee-0a7d-33dd1fb465c2
description: 为每个用户返回一个接口，用于枚举一个时间范围内的忙/闲数据块。
ms.openlocfilehash: e55f902117a20bfefaa5d9a2f3a067cb78ec86cb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411230"
---
# <a name="ifreebusysupportloadfreebusydata"></a><span data-ttu-id="61f1c-103">IFreeBusySupport::LoadFreeBusyData</span><span class="sxs-lookup"><span data-stu-id="61f1c-103">IFreeBusySupport::LoadFreeBusyData</span></span>

<span data-ttu-id="61f1c-104">为每个用户返回一个接口，用于枚举一个时间范围内的忙/闲数据块。</span><span class="sxs-lookup"><span data-stu-id="61f1c-104">Returns, for each specified user, an interface for enumerating free/busy blocks of data within a time range.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="61f1c-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="61f1c-105">Quick info</span></span>

<span data-ttu-id="61f1c-106">请参阅 [IFreeBusySupport](ifreebusysupport.md)。</span><span class="sxs-lookup"><span data-stu-id="61f1c-106">See [IFreeBusySupport](ifreebusysupport.md).</span></span>
  
```cpp
HRESULT LoadFreeBusyData( 
    ULONG cMax,  
    FBUser *rgfbuser, 
    IFreeBusyData **prgfbdata,  
    HRESULT *phrStatus, 
    ULONG *pcRead 
);
```

## <a name="parameters"></a><span data-ttu-id="61f1c-107">参数</span><span class="sxs-lookup"><span data-stu-id="61f1c-107">Parameters</span></span>

<span data-ttu-id="61f1c-108">_cMax_</span><span class="sxs-lookup"><span data-stu-id="61f1c-108">_cMax_</span></span>
  
> <span data-ttu-id="61f1c-109">[in]要返回 [的 IFreeBusyData](ifreebusydata.md) 接口的数量。</span><span class="sxs-lookup"><span data-stu-id="61f1c-109">[in] The number of [IFreeBusyData](ifreebusydata.md) interfaces to return.</span></span> 
    
<span data-ttu-id="61f1c-110">_rgfbuser_</span><span class="sxs-lookup"><span data-stu-id="61f1c-110">_rgfbuser_</span></span>
  
> <span data-ttu-id="61f1c-111">[in]要检索其数据的忙/闲用户的数组。</span><span class="sxs-lookup"><span data-stu-id="61f1c-111">[in] The array of free/busy users to retrieve data for.</span></span>
    
<span data-ttu-id="61f1c-112">_prgfbdata_</span><span class="sxs-lookup"><span data-stu-id="61f1c-112">_prgfbdata_</span></span>
  
> <span data-ttu-id="61f1c-113">[in][out]对应于 [FBUser](fbuser.md)结构的 _rgfbuser_ 数组的 **IFreeBusyData** 接口的数组。</span><span class="sxs-lookup"><span data-stu-id="61f1c-113">[in][out] The array of **IFreeBusyData** interfaces that correspond to the  _rgfbuser_ array of [FBUser](fbuser.md) structures.</span></span> 
    
   > [!NOTE]
   > <span data-ttu-id="61f1c-114">此指针数组由调用方分配，由调用方释放。</span><span class="sxs-lookup"><span data-stu-id="61f1c-114">This array of pointers is allocated by the caller and freed by the caller.</span></span> <span data-ttu-id="61f1c-115">当调用方使用它们完成操作时，将释放指向的实际接口。</span><span class="sxs-lookup"><span data-stu-id="61f1c-115">The actual interfaces pointed to are released when the caller is done with them.</span></span> 
  
<span data-ttu-id="61f1c-116">_phrStatus_</span><span class="sxs-lookup"><span data-stu-id="61f1c-116">_phrStatus_</span></span>
  
> <span data-ttu-id="61f1c-117">[out]用于检索每个相应的 **IFreeBusyData** 接口的 **HRESULT** 结果数组。</span><span class="sxs-lookup"><span data-stu-id="61f1c-117">[out] The array of **HRESULT** results for retrieving each corresponding **IFreeBusyData** interface.</span></span> <span data-ttu-id="61f1c-118">该值可能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="61f1c-118">The value may be NULL.</span></span> <span data-ttu-id="61f1c-119">如果相应的  _prgfbdata_ S_OK，则结果设置为"值"。</span><span class="sxs-lookup"><span data-stu-id="61f1c-119">A result is set to S_OK if corresponding  _prgfbdata_ is valid.</span></span> 
    
<span data-ttu-id="61f1c-120">_pcRead_</span><span class="sxs-lookup"><span data-stu-id="61f1c-120">_pcRead_</span></span>
  
>  <span data-ttu-id="61f1c-121">[out]已找到 **IFreeBusyData** 接口的实际用户数。</span><span class="sxs-lookup"><span data-stu-id="61f1c-121">[out] The actual number of users for which an **IFreeBusyData** interface has been found.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="61f1c-122">返回值</span><span class="sxs-lookup"><span data-stu-id="61f1c-122">Return values</span></span>

<span data-ttu-id="61f1c-123">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="61f1c-123">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="61f1c-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61f1c-124">See also</span></span>

- [<span data-ttu-id="61f1c-125">常量 (忙/闲 API) </span><span class="sxs-lookup"><span data-stu-id="61f1c-125">Constants (Free/busy API)</span></span>](constants-free-busy-api.md)

