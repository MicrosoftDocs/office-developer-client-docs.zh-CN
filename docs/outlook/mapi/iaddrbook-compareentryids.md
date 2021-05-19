---
title: IAddrBookCompareEntryIDs
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBookCompareEntryIDs
api_type:
- COM
ms.assetid: 7dabc1d3-5ea4-482f-91a9-9ef3009eddd2
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b6abecc298df7a86afff9338752a15615c73b3a4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424257"
---
# <a name="iaddrbookcompareentryids"></a><span data-ttu-id="20746-103">IAddrBook::CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="20746-103">IAddrBook::CompareEntryIDs</span></span>

  
  
<span data-ttu-id="20746-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="20746-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="20746-105">比较属于特定通讯簿提供程序的两个条目标识符，以确定它们是否引用同一通讯簿对象。</span><span class="sxs-lookup"><span data-stu-id="20746-105">Compares two entry identifiers that belong to a particular address book provider to determine whether they refer to the same address book object.</span></span> 
  
```cpp
HRESULT CompareEntryIDs(
  ULONG cbEntryID1,
  LPENTRYID lpEntryID1,
  ULONG cbEntryID2,
  LPENTRYID lpEntryID2,
  ULONG ulFlags,
  ULONG FAR * lpulResult
);
```

## <a name="parameters"></a><span data-ttu-id="20746-106">参数</span><span class="sxs-lookup"><span data-stu-id="20746-106">Parameters</span></span>

 <span data-ttu-id="20746-107">_cbEntryID1_</span><span class="sxs-lookup"><span data-stu-id="20746-107">_cbEntryID1_</span></span>
  
> <span data-ttu-id="20746-108">[in]  _lpEntryID1_ 参数指向的条目标识符中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="20746-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID1_ parameter.</span></span> 
    
 <span data-ttu-id="20746-109">_lpEntryID1_</span><span class="sxs-lookup"><span data-stu-id="20746-109">_lpEntryID1_</span></span>
  
> <span data-ttu-id="20746-110">[in]指向要比较的第一个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="20746-110">[in] A pointer to the first entry identifier to be compared.</span></span>
    
 <span data-ttu-id="20746-111">_cbEntryID2_</span><span class="sxs-lookup"><span data-stu-id="20746-111">_cbEntryID2_</span></span>
  
> <span data-ttu-id="20746-112">[in]  _lpEntryID2_ 参数指向的条目标识符中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="20746-112">[in] The byte count in the entry identifier pointed to by the  _lpEntryID2_ parameter.</span></span> 
    
 <span data-ttu-id="20746-113">_lpEntryID2_</span><span class="sxs-lookup"><span data-stu-id="20746-113">_lpEntryID2_</span></span>
  
> <span data-ttu-id="20746-114">[in]指向要比较的第二个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="20746-114">[in] A pointer to the second entry identifier to be compared.</span></span>
    
 <span data-ttu-id="20746-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="20746-115">_ulFlags_</span></span>
  
> <span data-ttu-id="20746-116">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="20746-116">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="20746-117">_lpulResult_</span><span class="sxs-lookup"><span data-stu-id="20746-117">_lpulResult_</span></span>
  
> <span data-ttu-id="20746-118">[out]指向比较结果的指针。</span><span class="sxs-lookup"><span data-stu-id="20746-118">[out] A pointer to the result of the comparison.</span></span> <span data-ttu-id="20746-119">如果两个条目标识符引用同一个对象，则  _lpulResult_ 的内容将设置为 TRUE;否则，内容将设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="20746-119">The contents of  _lpulResult_ are set to TRUE if the two entry identifiers refer to the same object; otherwise, the contents are set to FALSE.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="20746-120">返回值</span><span class="sxs-lookup"><span data-stu-id="20746-120">Return value</span></span>

<span data-ttu-id="20746-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="20746-121">S_OK</span></span> 
  
> <span data-ttu-id="20746-122">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="20746-122">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="20746-123">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="20746-123">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="20746-124">任何通讯簿提供程序无法识别使用  _lpEntryID1_ 或  _lpEntryID2_ 参数传入的一个或两个条目标识符。</span><span class="sxs-lookup"><span data-stu-id="20746-124">One or both of the entry identifiers passed in with the  _lpEntryID1_ or  _lpEntryID2_ parameters are not recognized by any address book provider.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="20746-125">备注</span><span class="sxs-lookup"><span data-stu-id="20746-125">Remarks</span></span>

<span data-ttu-id="20746-126">客户端应用程序和服务提供商调用 **CompareEntryIDs** 方法来比较属于单个通讯簿提供程序的两个条目标识符，以确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="20746-126">Client applications and service providers call the **CompareEntryIDs** method to compare two entry identifiers that belongs to a single address book provider to determine whether they refer to the same object.</span></span> <span data-ttu-id="20746-127">**CompareEntryIDs** 非常有用，因为对象可以具有多个有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="20746-127">**CompareEntryIDs** is useful because an object can have more than one valid entry identifier.</span></span> <span data-ttu-id="20746-128">例如，安装通讯簿提供程序的新版本后，可能会出现此情况。</span><span class="sxs-lookup"><span data-stu-id="20746-128">This situation can occur, for example, after a new version of an address book provider is installed.</span></span> 
  
<span data-ttu-id="20746-129">MAPI 将此调用传递给负责条目标识符的通讯簿提供程序，通过匹配条目标识符中的 [MAPIUID](mapiuid.md) 结构与提供程序注册的 **MAPIUID** 结构来确定相应的提供程序。</span><span class="sxs-lookup"><span data-stu-id="20746-129">MAPI passes this call to the address book provider that is responsible for the entry identifiers, determining the appropriate provider by matching the [MAPIUID](mapiuid.md) structure in the entry identifiers with the **MAPIUID** structure registered by the provider.</span></span> 
  
<span data-ttu-id="20746-130">如果两个条目标识符引用同一个对象，则 **CompareEntryIDs** 将  _lpulResult_ 参数的内容设置为 TRUE;如果它们引用不同的对象， **则 CompareEntryIDs** 将内容设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="20746-130">If the two entry identifiers refer to the same object, **CompareEntryIDs** sets the contents of the  _lpulResult_ parameter to TRUE; if they refer to different objects, **CompareEntryIDs** sets the contents to FALSE.</span></span> <span data-ttu-id="20746-131">在任一情况下 **，CompareEntryIDs** 都S_OK。</span><span class="sxs-lookup"><span data-stu-id="20746-131">In either case, **CompareEntryIDs** returns S_OK.</span></span> <span data-ttu-id="20746-132">如果 **CompareEntryIDs** 返回错误，如果没有通讯簿提供程序注册与条目标识符中的 MAPIUID 结构匹配的 **MAPIUID** 结构，则客户端和提供程序不应根据比较结果执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="20746-132">If **CompareEntryIDs** returns an error, which can occur if no address book provider has registered a **MAPIUID** structure that matches the one in the entry identifiers, clients and providers should not take any action based on the result of the comparison.</span></span> <span data-ttu-id="20746-133">相反，他们应采用最保守的方法来执行所执行的操作。</span><span class="sxs-lookup"><span data-stu-id="20746-133">They should instead take the most conservative approach to the action being performed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="20746-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20746-134">See also</span></span>



[<span data-ttu-id="20746-135">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="20746-135">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)

