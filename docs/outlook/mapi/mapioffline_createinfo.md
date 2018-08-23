---
title: MAPIOFFLINE_CREATEINFO
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 539aa31d-7dec-4dbb-93f7-fa060c43565a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ffac4328401b8afbc07eb650ea6c08da5f9c51b2
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594493"
---
# <a name="mapiofflinecreateinfo"></a><span data-ttu-id="65bc6-103">MAPIOFFLINE_CREATEINFO</span><span class="sxs-lookup"><span data-stu-id="65bc6-103">MAPIOFFLINE_CREATEINFO</span></span>

  
  
<span data-ttu-id="65bc6-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="65bc6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="65bc6-105">此结构用于[HrCreateOfflineObj](hrcreateofflineobj.md)。</span><span class="sxs-lookup"><span data-stu-id="65bc6-105">This structure is used with [HrCreateOfflineObj](hrcreateofflineobj.md).</span></span>
  
```cpp
typedef struct
{
  ULONG      ulSize;
  ULONG      ulCreateFlags;
  LPCWSTR      pwszProfileName;
  ULONG      ulCapabilities;
  const GUID*      pGUID;
  const GUID*      pInstance;
  IMAPIOfflineMgr*    pParent;
  IUnknown*      pMAPISupport;
  MAPIOFFLINE_AGGREGATEINFO*  pAggregateInfo;
  MAPIOFFLINE_CONNECTINFO*  pConnectInfo;
} MAPIOFFLINE_CREATEINFO;
```

## <a name="members"></a><span data-ttu-id="65bc6-106">Members</span><span class="sxs-lookup"><span data-stu-id="65bc6-106">Members</span></span>

 <span data-ttu-id="65bc6-107">**ulSize**</span><span class="sxs-lookup"><span data-stu-id="65bc6-107">**ulSize**</span></span>
  
> <span data-ttu-id="65bc6-108">结构的大小。</span><span class="sxs-lookup"><span data-stu-id="65bc6-108">The size of structure.</span></span>
    
 <span data-ttu-id="65bc6-109">**ulCreateFlags**</span><span class="sxs-lookup"><span data-stu-id="65bc6-109">**ulCreateFlags**</span></span>
  
> <span data-ttu-id="65bc6-110">它必须是 0。</span><span class="sxs-lookup"><span data-stu-id="65bc6-110">It must be 0.</span></span>
    
 <span data-ttu-id="65bc6-111">**pwszProfileName**</span><span class="sxs-lookup"><span data-stu-id="65bc6-111">**pwszProfileName**</span></span>
  
> <span data-ttu-id="65bc6-112">配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="65bc6-112">The name of the profile.</span></span>
    
 <span data-ttu-id="65bc6-113">**ulCapabilities**</span><span class="sxs-lookup"><span data-stu-id="65bc6-113">**ulCapabilities**</span></span>
  
> <span data-ttu-id="65bc6-114">以下功能标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="65bc6-114">A bit mask of the following capability flags.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="65bc6-115">MAPIOFFLINE_CAPABILITY_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="65bc6-115">MAPIOFFLINE_CAPABILITY_OFFLINE</span></span>  <br/> |<span data-ttu-id="65bc6-116">脱机对象都能够脱机。</span><span class="sxs-lookup"><span data-stu-id="65bc6-116">The offline object is capable of going offline.</span></span>  <br/> |
|<span data-ttu-id="65bc6-117">MAPIOFFLINE_CAPABILITY_ONLINE</span><span class="sxs-lookup"><span data-stu-id="65bc6-117">MAPIOFFLINE_CAPABILITY_ONLINE</span></span>  <br/> |<span data-ttu-id="65bc6-118">能够上网的脱机对象。</span><span class="sxs-lookup"><span data-stu-id="65bc6-118">The offline object is capable of going online.</span></span>  <br/> |
   
 <span data-ttu-id="65bc6-119">**pGUID**</span><span class="sxs-lookup"><span data-stu-id="65bc6-119">**pGUID**</span></span>
  
> <span data-ttu-id="65bc6-120">指向用于唯一标识此类型的其他脱机对象从脱机对象的 GUID。</span><span class="sxs-lookup"><span data-stu-id="65bc6-120">Pointer to a GUID that is used to uniquely identify this type of offline object from other offline objects.</span></span> <span data-ttu-id="65bc6-121">GUID_GlobalState 指全局脱机对象的对象可用作父对象。</span><span class="sxs-lookup"><span data-stu-id="65bc6-121">GUID_GlobalState refers to the global offline object that objects can use as a parent object.</span></span>
    
 <span data-ttu-id="65bc6-122">**pInstance**</span><span class="sxs-lookup"><span data-stu-id="65bc6-122">**pInstance**</span></span>
  
> <span data-ttu-id="65bc6-123">用于唯一标识此脱机对象的 guid 的指针。</span><span class="sxs-lookup"><span data-stu-id="65bc6-123">Pointer to GUID that uniquely identifies this offline object.</span></span> <span data-ttu-id="65bc6-124">它用于消除歧义此脱机对象从其他对象。</span><span class="sxs-lookup"><span data-stu-id="65bc6-124">It is used to disambiguate this offline objects from other objects.</span></span>
    
 <span data-ttu-id="65bc6-125">**pParent**</span><span class="sxs-lookup"><span data-stu-id="65bc6-125">**pParent**</span></span>
  
> <span data-ttu-id="65bc6-126">对脱机对象的父级的脱机对象，它的指针更改此脱机对象将继承。</span><span class="sxs-lookup"><span data-stu-id="65bc6-126">Pointer to offline object that is the parent of this offline object and whose changes this offline object will inherit.</span></span>
    
 <span data-ttu-id="65bc6-127">**pMAPISupport**</span><span class="sxs-lookup"><span data-stu-id="65bc6-127">**pMAPISupport**</span></span>
  
>  <span data-ttu-id="65bc6-128">标识的将使用此脱机对象的 MAPI 支持对象。</span><span class="sxs-lookup"><span data-stu-id="65bc6-128">Identifies the MAPI support object that that will use this offline object.</span></span> <span data-ttu-id="65bc6-129">例如，如果脱机使用此对象以跟踪存储脱机和联机状态，则这是存储支持对象。</span><span class="sxs-lookup"><span data-stu-id="65bc6-129">For example, if this offline object is used to keep track of a store's offline and online state, then this is the stores support object.</span></span> <span data-ttu-id="65bc6-130">但是，如果这是具有不支持对象的对象的脱机对象它可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="65bc6-130">However, if this is an offline object for an object with no support object then it can be NULL.</span></span> 
    
 <span data-ttu-id="65bc6-131">**pAggregateInfo**</span><span class="sxs-lookup"><span data-stu-id="65bc6-131">**pAggregateInfo**</span></span>
  
> <span data-ttu-id="65bc6-132">指向 MAPIOFFLINE_AGGREGATEINFO 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="65bc6-132">A pointer to a MAPIOFFLINE_AGGREGATEINFO structure.</span></span> <span data-ttu-id="65bc6-133">有关详细信息，请参阅[MAPIOFFLINE_AGGREGATEINFO](mapioffline_aggregateinfo.md)。</span><span class="sxs-lookup"><span data-stu-id="65bc6-133">For more information, see [MAPIOFFLINE_AGGREGATEINFO](mapioffline_aggregateinfo.md).</span></span>
    
 <span data-ttu-id="65bc6-134">**pConnectInfo**</span><span class="sxs-lookup"><span data-stu-id="65bc6-134">**pConnectInfo**</span></span>
  
> <span data-ttu-id="65bc6-135">必须为空。</span><span class="sxs-lookup"><span data-stu-id="65bc6-135">Must be null.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="65bc6-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65bc6-136">See also</span></span>



[<span data-ttu-id="65bc6-137">HrCreateOfflineObj</span><span class="sxs-lookup"><span data-stu-id="65bc6-137">HrCreateOfflineObj</span></span>](hrcreateofflineobj.md)
  
[<span data-ttu-id="65bc6-138">MAPIOFFLINE_AGGREGATEINFO</span><span class="sxs-lookup"><span data-stu-id="65bc6-138">MAPIOFFLINE_AGGREGATEINFO</span></span>](mapioffline_aggregateinfo.md)

