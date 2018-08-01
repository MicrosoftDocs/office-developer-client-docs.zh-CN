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
ms.openlocfilehash: 730c24a179cc6aaf8dc2068199ffc206d30156b4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775144"
---
# <a name="hrcompareabentryidswithexchangecontext"></a><span data-ttu-id="5fc40-103">HrCompareABEntryIDsWithExchangeContext</span><span class="sxs-lookup"><span data-stu-id="5fc40-103">HrCompareABEntryIDsWithExchangeContext</span></span>

  
  
<span data-ttu-id="5fc40-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="5fc40-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="5fc40-105">比较多个 Exchange 配置文件中的安全地两个地址簿**Entryid** 。</span><span class="sxs-lookup"><span data-stu-id="5fc40-105">Compares two address book **entryIDs** safely in a Multiple Exchange profile.</span></span> <span data-ttu-id="5fc40-106">此函数是[IAddrBook::CompareEntryIDs](iaddrbook-compareentryids.md)替换函数。</span><span class="sxs-lookup"><span data-stu-id="5fc40-106">This function is a replacement function for [IAddrBook::CompareEntryIDs](iaddrbook-compareentryids.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5fc40-107">头文件：</span><span class="sxs-lookup"><span data-stu-id="5fc40-107">Header file:</span></span>  <br/> |<span data-ttu-id="5fc40-108">abhelp.h</span><span class="sxs-lookup"><span data-stu-id="5fc40-108">abhelp.h</span></span>  <br/> |
|<span data-ttu-id="5fc40-109">通过实现：</span><span class="sxs-lookup"><span data-stu-id="5fc40-109">Implemented by:</span></span>  <br/> |<span data-ttu-id="5fc40-110">MAPI</span><span class="sxs-lookup"><span data-stu-id="5fc40-110">MAPI</span></span>  <br/> |
|<span data-ttu-id="5fc40-111">调用：</span><span class="sxs-lookup"><span data-stu-id="5fc40-111">Called by:</span></span>  <br/> |<span data-ttu-id="5fc40-112">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="5fc40-112">Client applications and service providers</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="5fc40-113">参数</span><span class="sxs-lookup"><span data-stu-id="5fc40-113">Parameters</span></span>

 <span data-ttu-id="5fc40-114">_pmsess_</span><span class="sxs-lookup"><span data-stu-id="5fc40-114">_pmsess_</span></span>
  
> <span data-ttu-id="5fc40-115">[in]登录**IMAPISession**。</span><span class="sxs-lookup"><span data-stu-id="5fc40-115">[in] The logged on **IMAPISession**.</span></span> <span data-ttu-id="5fc40-116">它不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="5fc40-116">It cannot be NULL.</span></span>
    
 <span data-ttu-id="5fc40-117">_pEmsmdbUID_</span><span class="sxs-lookup"><span data-stu-id="5fc40-117">_pEmsmdbUID_</span></span>
  
> <span data-ttu-id="5fc40-118">[in]指向标识包含 Exchange 通讯簿提供程序，此函数应该使用要显示的项标识符的详细信息的 Exchange 服务**emsmdbUID**的指针。</span><span class="sxs-lookup"><span data-stu-id="5fc40-118">[in] A pointer to an **emsmdbUID** that identifies the Exchange Service that contains the Exchange Address Book Provider that this function should use to display details on the entry identifier.</span></span> <span data-ttu-id="5fc40-119">如果传入的项标识符不是 Exchange 通讯簿提供程序条目标识符，则忽略此参数，并函数调用与[IAddrBook::Details](iaddrbook-details.md)相似之处。</span><span class="sxs-lookup"><span data-stu-id="5fc40-119">If the incoming entry identifier is not an Exchange Address Book Provider entry identifier, this parameter is ignored and the function call behaves like [IAddrBook::Details](iaddrbook-details.md).</span></span> <span data-ttu-id="5fc40-120">如果此参数为 NULL 或零 MAPIUID，此函数的行为类似[IAddrBook::Details](iaddrbook-details.md)。</span><span class="sxs-lookup"><span data-stu-id="5fc40-120">If this parameter is NULL or a zero MAPIUID, this function behaves like [IAddrBook::Details](iaddrbook-details.md).</span></span>
    
 <span data-ttu-id="5fc40-121">_pAddrBook_</span><span class="sxs-lookup"><span data-stu-id="5fc40-121">_pAddrBook_</span></span>
  
> <span data-ttu-id="5fc40-122">[in]通讯簿用于打开的项标识符。</span><span class="sxs-lookup"><span data-stu-id="5fc40-122">[in] The address book used to open the entry identifier.</span></span> <span data-ttu-id="5fc40-123">它不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="5fc40-123">It cannot be NULL.</span></span>
    
 <span data-ttu-id="5fc40-124">_cbEntryID1_</span><span class="sxs-lookup"><span data-stu-id="5fc40-124">_cbEntryID1_</span></span>
  
> <span data-ttu-id="5fc40-125">[in]第一个条目标识符_lpEntryID1_参数指定的字节数。</span><span class="sxs-lookup"><span data-stu-id="5fc40-125">[in] The byte count of the first entry identifier specified by the  _lpEntryID1_ parameter.</span></span> 
    
 <span data-ttu-id="5fc40-126">_lpEntryID1_</span><span class="sxs-lookup"><span data-stu-id="5fc40-126">_lpEntryID1_</span></span>
  
> <span data-ttu-id="5fc40-127">[in]一个指向代表通讯簿条目进行比较的第一个条目标识符。</span><span class="sxs-lookup"><span data-stu-id="5fc40-127">[in] A pointer to the first entry identifier that represents the address book entry to compare.</span></span>
    
 <span data-ttu-id="5fc40-128">_cbEntryID2_</span><span class="sxs-lookup"><span data-stu-id="5fc40-128">_cbEntryID2_</span></span>
  
> <span data-ttu-id="5fc40-129">[in]第二个条目标识符_lpEntryID2_参数指定的字节数。</span><span class="sxs-lookup"><span data-stu-id="5fc40-129">[in] The byte count of the second entry identifier specified by the  _lpEntryID2_ parameter.</span></span> 
    
 <span data-ttu-id="5fc40-130">_lpEntryID2_</span><span class="sxs-lookup"><span data-stu-id="5fc40-130">_lpEntryID2_</span></span>
  
> <span data-ttu-id="5fc40-131">[in]一个指向代表通讯簿条目，以比较比较中使用的第二个条目标识符。</span><span class="sxs-lookup"><span data-stu-id="5fc40-131">[in] A pointer to the second entry identifier used in the comparison that represents the address book entry to compare.</span></span>
    
 <span data-ttu-id="5fc40-132">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="5fc40-132">_ulFlags_</span></span>
  
> <span data-ttu-id="5fc40-133">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="5fc40-133">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="5fc40-134">_lpulResult_</span><span class="sxs-lookup"><span data-stu-id="5fc40-134">_lpulResult_</span></span>
  
> <span data-ttu-id="5fc40-135">[输出]指向包含的比较结果的位置的指针。</span><span class="sxs-lookup"><span data-stu-id="5fc40-135">[out] A pointer to the location that contains the results of the comparison.</span></span> 
    

