---
title: IFreeBusySupportLoadFreeBusyData
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f0baa310-7a53-07ee-0a7d-33dd1fb465c2
description: 返回，为每个指定的用户，用于枚举忙/闲时间范围内的数据块的接口。
ms.openlocfilehash: 9af5a40da9f0a831de7346b44cee9ca004c02300
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774209"
---
# <a name="ifreebusysupportloadfreebusydata"></a><span data-ttu-id="da62a-103">IFreeBusySupport::LoadFreeBusyData</span><span class="sxs-lookup"><span data-stu-id="da62a-103">IFreeBusySupport::LoadFreeBusyData</span></span>

<span data-ttu-id="da62a-104">返回，为每个指定的用户，用于枚举忙/闲时间范围内的数据块的接口。</span><span class="sxs-lookup"><span data-stu-id="da62a-104">Returns, for each specified user, an interface for enumerating free/busy blocks of data within a time range.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="da62a-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="da62a-105">Quick info</span></span>

<span data-ttu-id="da62a-106">请参阅[IFreeBusySupport](ifreebusysupport.md)。</span><span class="sxs-lookup"><span data-stu-id="da62a-106">See [IFreeBusySupport](ifreebusysupport.md).</span></span>
  
```cpp
HRESULT LoadFreeBusyData( 
    ULONG cMax,  
    FBUser *rgfbuser, 
    IFreeBusyData **prgfbdata,  
    HRESULT *phrStatus, 
    ULONG *pcRead 
);
```

## <a name="parameters"></a><span data-ttu-id="da62a-107">参数</span><span class="sxs-lookup"><span data-stu-id="da62a-107">Parameters</span></span>

<span data-ttu-id="da62a-108">_cMax_</span><span class="sxs-lookup"><span data-stu-id="da62a-108">_cMax_</span></span>
  
> <span data-ttu-id="da62a-109">[in][IFreeBusyData](ifreebusydata.md)接口返回数。</span><span class="sxs-lookup"><span data-stu-id="da62a-109">[in] The number of [IFreeBusyData](ifreebusydata.md) interfaces to return.</span></span> 
    
<span data-ttu-id="da62a-110">_rgfbuser_</span><span class="sxs-lookup"><span data-stu-id="da62a-110">_rgfbuser_</span></span>
  
> <span data-ttu-id="da62a-111">[in]忙/闲信息的用户来检索数据的数组。</span><span class="sxs-lookup"><span data-stu-id="da62a-111">[in] The array of free/busy users to retrieve data for.</span></span>
    
<span data-ttu-id="da62a-112">_prgfbdata_</span><span class="sxs-lookup"><span data-stu-id="da62a-112">_prgfbdata_</span></span>
  
> <span data-ttu-id="da62a-113">[in][输出]**IFreeBusyData**接口对应的[FBUser](fbuser.md)结构_rgfbuser_数组的数组。</span><span class="sxs-lookup"><span data-stu-id="da62a-113">[in][out] The array of **IFreeBusyData** interfaces that correspond to the  _rgfbuser_ array of [FBUser](fbuser.md) structures.</span></span> 
    
   > [!NOTE]
   > <span data-ttu-id="da62a-114">此数组指针是呼叫者分配并释放呼叫者。</span><span class="sxs-lookup"><span data-stu-id="da62a-114">This array of pointers is allocated by the caller and freed by the caller.</span></span> <span data-ttu-id="da62a-115">当呼叫者完成与他们发布指向的实际接口。</span><span class="sxs-lookup"><span data-stu-id="da62a-115">The actual interfaces pointed to are released when the caller is done with them.</span></span> 
  
<span data-ttu-id="da62a-116">_phrStatus_</span><span class="sxs-lookup"><span data-stu-id="da62a-116">_phrStatus_</span></span>
  
> <span data-ttu-id="da62a-117">[输出]用于检索每个相应**IFreeBusyData**接口的**HRESULT**结果的数组。</span><span class="sxs-lookup"><span data-stu-id="da62a-117">[out] The array of **HRESULT** results for retrieving each corresponding **IFreeBusyData** interface.</span></span> <span data-ttu-id="da62a-118">值可能是 NULL。</span><span class="sxs-lookup"><span data-stu-id="da62a-118">The value may be NULL.</span></span> <span data-ttu-id="da62a-119">结果设置为 S_OK 相应_prgfbdata_是否有效。</span><span class="sxs-lookup"><span data-stu-id="da62a-119">A result is set to S_OK if corresponding  _prgfbdata_ is valid.</span></span> 
    
<span data-ttu-id="da62a-120">_pcRead_</span><span class="sxs-lookup"><span data-stu-id="da62a-120">_pcRead_</span></span>
  
>  <span data-ttu-id="da62a-121">[输出]实际已为其找到**IFreeBusyData**接口的用户数。</span><span class="sxs-lookup"><span data-stu-id="da62a-121">[out] The actual number of users for which an **IFreeBusyData** interface has been found.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="da62a-122">返回值</span><span class="sxs-lookup"><span data-stu-id="da62a-122">Return values</span></span>

<span data-ttu-id="da62a-123">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="da62a-123">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="da62a-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da62a-124">See also</span></span>

- [<span data-ttu-id="da62a-125">常量 (忙/闲 API)</span><span class="sxs-lookup"><span data-stu-id="da62a-125">Constants (Free/busy API)</span></span>](constants-free-busy-api.md)

