---
title: HrCompareABEntryIDsWithExchangeContext
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: e537c25f-51b5-4f06-a20a-44ee540b9a1f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4bada5913623e2eb463a9e72347bd31eb22c414b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436431"
---
# <a name="hrcompareabentryidswithexchangecontext"></a><span data-ttu-id="e2c9f-103">HrCompareABEntryIDsWithExchangeContext</span><span class="sxs-lookup"><span data-stu-id="e2c9f-103">HrCompareABEntryIDsWithExchangeContext</span></span>

  
  
<span data-ttu-id="e2c9f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e2c9f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e2c9f-105">在多通讯簿 **配置文件** 中安全地比较两个Exchange条目。</span><span class="sxs-lookup"><span data-stu-id="e2c9f-105">Compares two address book **entryIDs** safely in a Multiple Exchange profile.</span></span> <span data-ttu-id="e2c9f-106">此函数是 [IAddrBook：：CompareEntryIDs 的替换函数](iaddrbook-compareentryids.md)。</span><span class="sxs-lookup"><span data-stu-id="e2c9f-106">This function is a replacement function for [IAddrBook::CompareEntryIDs](iaddrbook-compareentryids.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e2c9f-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="e2c9f-107">Header file:</span></span>  <br/> |<span data-ttu-id="e2c9f-108">abhelp.h</span><span class="sxs-lookup"><span data-stu-id="e2c9f-108">abhelp.h</span></span>  <br/> |
|<span data-ttu-id="e2c9f-109">实现者：</span><span class="sxs-lookup"><span data-stu-id="e2c9f-109">Implemented by:</span></span>  <br/> |<span data-ttu-id="e2c9f-110">MAPI</span><span class="sxs-lookup"><span data-stu-id="e2c9f-110">MAPI</span></span>  <br/> |
|<span data-ttu-id="e2c9f-111">调用者：</span><span class="sxs-lookup"><span data-stu-id="e2c9f-111">Called by:</span></span>  <br/> |<span data-ttu-id="e2c9f-112">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="e2c9f-112">Client applications and service providers</span></span>  <br/> |
   
```cpp
HRESULT HrCompareABEntryIDsWithExchangeContext(
  LPMAPISESSION pmsess,
  const MAPIUID *pEmsmdbUID,
  LPADRBOOK pAddrBook,
  ULONG cbEntryID1,
  LPENTRYID lpEntryID1,
  ULONG cbEntryID2,
  LPENTRYID lpEntryID2,
  ULONG ulFlags,
  ULONG * lpulResult
);
```

## <a name="parameters"></a><span data-ttu-id="e2c9f-113">参数</span><span class="sxs-lookup"><span data-stu-id="e2c9f-113">Parameters</span></span>

 <span data-ttu-id="e2c9f-114">_pmsess_</span><span class="sxs-lookup"><span data-stu-id="e2c9f-114">_pmsess_</span></span>
  
> <span data-ttu-id="e2c9f-115">[in]登录的 **IMAPISession**。</span><span class="sxs-lookup"><span data-stu-id="e2c9f-115">[in] The logged on **IMAPISession**.</span></span> <span data-ttu-id="e2c9f-116">它不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="e2c9f-116">It cannot be NULL.</span></span>
    
 <span data-ttu-id="e2c9f-117">_pEmsmdbUID_</span><span class="sxs-lookup"><span data-stu-id="e2c9f-117">_pEmsmdbUID_</span></span>
  
> <span data-ttu-id="e2c9f-118">[in]指向 **emsmdbUID** 的指针，标识包含 Exchange 通讯簿提供程序的 Exchange Service，此函数应该使用该提供程序在条目标识符上显示详细信息。</span><span class="sxs-lookup"><span data-stu-id="e2c9f-118">[in] A pointer to an **emsmdbUID** that identifies the Exchange Service that contains the Exchange Address Book Provider that this function should use to display details on the entry identifier.</span></span> <span data-ttu-id="e2c9f-119">如果传入条目标识符不是通讯簿Exchange标识符，则忽略此参数，并且函数调用的行为类似于[IAddrBook：:D etails](iaddrbook-details.md)。</span><span class="sxs-lookup"><span data-stu-id="e2c9f-119">If the incoming entry identifier is not an Exchange Address Book Provider entry identifier, this parameter is ignored and the function call behaves like [IAddrBook::Details](iaddrbook-details.md).</span></span> <span data-ttu-id="e2c9f-120">如果此参数为 NULL 或零 MAPIUID，则此函数的行为类似于 [IAddrBook：:D etails](iaddrbook-details.md)。</span><span class="sxs-lookup"><span data-stu-id="e2c9f-120">If this parameter is NULL or a zero MAPIUID, this function behaves like [IAddrBook::Details](iaddrbook-details.md).</span></span>
    
 <span data-ttu-id="e2c9f-121">_pAddrBook_</span><span class="sxs-lookup"><span data-stu-id="e2c9f-121">_pAddrBook_</span></span>
  
> <span data-ttu-id="e2c9f-122">[in]用于打开条目标识符的通讯簿。</span><span class="sxs-lookup"><span data-stu-id="e2c9f-122">[in] The address book used to open the entry identifier.</span></span> <span data-ttu-id="e2c9f-123">它不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="e2c9f-123">It cannot be NULL.</span></span>
    
 <span data-ttu-id="e2c9f-124">_cbEntryID1_</span><span class="sxs-lookup"><span data-stu-id="e2c9f-124">_cbEntryID1_</span></span>
  
> <span data-ttu-id="e2c9f-125">[in]  _lpEntryID1_ 参数指定的第一个条目标识符的字节计数。</span><span class="sxs-lookup"><span data-stu-id="e2c9f-125">[in] The byte count of the first entry identifier specified by the  _lpEntryID1_ parameter.</span></span> 
    
 <span data-ttu-id="e2c9f-126">_lpEntryID1_</span><span class="sxs-lookup"><span data-stu-id="e2c9f-126">_lpEntryID1_</span></span>
  
> <span data-ttu-id="e2c9f-127">[in]指向表示要比较的通讯簿条目的第一个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="e2c9f-127">[in] A pointer to the first entry identifier that represents the address book entry to compare.</span></span>
    
 <span data-ttu-id="e2c9f-128">_cbEntryID2_</span><span class="sxs-lookup"><span data-stu-id="e2c9f-128">_cbEntryID2_</span></span>
  
> <span data-ttu-id="e2c9f-129">[in]  _lpEntryID2_ 参数指定的第二个条目标识符的字节计数。</span><span class="sxs-lookup"><span data-stu-id="e2c9f-129">[in] The byte count of the second entry identifier specified by the  _lpEntryID2_ parameter.</span></span> 
    
 <span data-ttu-id="e2c9f-130">_lpEntryID2_</span><span class="sxs-lookup"><span data-stu-id="e2c9f-130">_lpEntryID2_</span></span>
  
> <span data-ttu-id="e2c9f-131">[in]指向比较中使用的第二个条目标识符的指针，该标识符表示要比较的通讯簿条目。</span><span class="sxs-lookup"><span data-stu-id="e2c9f-131">[in] A pointer to the second entry identifier used in the comparison that represents the address book entry to compare.</span></span>
    
 <span data-ttu-id="e2c9f-132">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="e2c9f-132">_ulFlags_</span></span>
  
> <span data-ttu-id="e2c9f-133">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="e2c9f-133">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="e2c9f-134">_lpulResult_</span><span class="sxs-lookup"><span data-stu-id="e2c9f-134">_lpulResult_</span></span>
  
> <span data-ttu-id="e2c9f-135">[out]指向包含比较结果的位置的指针。</span><span class="sxs-lookup"><span data-stu-id="e2c9f-135">[out] A pointer to the location that contains the results of the comparison.</span></span> 
    

