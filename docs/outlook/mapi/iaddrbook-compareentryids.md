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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d6f983e49132e7ab6ea402a8e32bb5ec56d1efba
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564848"
---
# <a name="iaddrbookcompareentryids"></a><span data-ttu-id="479f3-103">IAddrBook::CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="479f3-103">IAddrBook::CompareEntryIDs</span></span>

  
  
<span data-ttu-id="479f3-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="479f3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="479f3-105">比较两个条目标识符属于特定地址簿提供程序，以确定它们是否引用同一个通讯簿对象。</span><span class="sxs-lookup"><span data-stu-id="479f3-105">Compares two entry identifiers that belong to a particular address book provider to determine whether they refer to the same address book object.</span></span> 
  
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

## <a name="parameters"></a><span data-ttu-id="479f3-106">参数</span><span class="sxs-lookup"><span data-stu-id="479f3-106">Parameters</span></span>

 <span data-ttu-id="479f3-107">_cbEntryID1_</span><span class="sxs-lookup"><span data-stu-id="479f3-107">_cbEntryID1_</span></span>
  
> <span data-ttu-id="479f3-108">[in]在_lpEntryID1_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="479f3-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID1_ parameter.</span></span> 
    
 <span data-ttu-id="479f3-109">_lpEntryID1_</span><span class="sxs-lookup"><span data-stu-id="479f3-109">_lpEntryID1_</span></span>
  
> <span data-ttu-id="479f3-110">[in]指向要进行比较的第一个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="479f3-110">[in] A pointer to the first entry identifier to be compared.</span></span>
    
 <span data-ttu-id="479f3-111">_cbEntryID2_</span><span class="sxs-lookup"><span data-stu-id="479f3-111">_cbEntryID2_</span></span>
  
> <span data-ttu-id="479f3-112">[in]在_lpEntryID2_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="479f3-112">[in] The byte count in the entry identifier pointed to by the  _lpEntryID2_ parameter.</span></span> 
    
 <span data-ttu-id="479f3-113">_lpEntryID2_</span><span class="sxs-lookup"><span data-stu-id="479f3-113">_lpEntryID2_</span></span>
  
> <span data-ttu-id="479f3-114">[in]指向要进行比较的第二个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="479f3-114">[in] A pointer to the second entry identifier to be compared.</span></span>
    
 <span data-ttu-id="479f3-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="479f3-115">_ulFlags_</span></span>
  
> <span data-ttu-id="479f3-116">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="479f3-116">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="479f3-117">_lpulResult_</span><span class="sxs-lookup"><span data-stu-id="479f3-117">_lpulResult_</span></span>
  
> <span data-ttu-id="479f3-118">[输出]一个指向比较结果的结果。</span><span class="sxs-lookup"><span data-stu-id="479f3-118">[out] A pointer to the result of the comparison.</span></span> <span data-ttu-id="479f3-119">如果两个条目标识符引用同一对象，则_lpulResult_的内容设置为 TRUE否则，将内容设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="479f3-119">The contents of  _lpulResult_ are set to TRUE if the two entry identifiers refer to the same object; otherwise, the contents are set to FALSE.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="479f3-120">返回值</span><span class="sxs-lookup"><span data-stu-id="479f3-120">Return value</span></span>

<span data-ttu-id="479f3-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="479f3-121">S_OK</span></span> 
  
> <span data-ttu-id="479f3-122">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="479f3-122">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="479f3-123">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="479f3-123">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="479f3-124">任何通讯簿提供程序无法识别一个或两个使用_lpEntryID1_或_lpEntryID2_参数传递的项标识符。</span><span class="sxs-lookup"><span data-stu-id="479f3-124">One or both of the entry identifiers passed in with the  _lpEntryID1_ or  _lpEntryID2_ parameters are not recognized by any address book provider.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="479f3-125">注解</span><span class="sxs-lookup"><span data-stu-id="479f3-125">Remarks</span></span>

<span data-ttu-id="479f3-126">客户端应用程序和服务提供程序调用**CompareEntryIDs**方法比较两个条目标识符属于单个地址簿提供程序，以确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="479f3-126">Client applications and service providers call the **CompareEntryIDs** method to compare two entry identifiers that belongs to a single address book provider to determine whether they refer to the same object.</span></span> <span data-ttu-id="479f3-127">**CompareEntryIDs**很有用，因为对象可以有多个有效项标识符。</span><span class="sxs-lookup"><span data-stu-id="479f3-127">**CompareEntryIDs** is useful because an object can have more than one valid entry identifier.</span></span> <span data-ttu-id="479f3-128">例如，安装新版本的通讯簿提供程序后，会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="479f3-128">This situation can occur, for example, after a new version of an address book provider is installed.</span></span> 
  
<span data-ttu-id="479f3-129">MAPI 将传递到通讯簿提供程序，它负责条目标识符，确定相应的提供程序通过匹配的项标识符的[MAPIUID](mapiuid.md)结构与**MAPIUID**结构注册的此呼叫提供程序。</span><span class="sxs-lookup"><span data-stu-id="479f3-129">MAPI passes this call to the address book provider that is responsible for the entry identifiers, determining the appropriate provider by matching the [MAPIUID](mapiuid.md) structure in the entry identifiers with the **MAPIUID** structure registered by the provider.</span></span> 
  
<span data-ttu-id="479f3-130">如果两个条目标识符引用相同的对象，则**CompareEntryIDs**将_lpulResult_参数的内容设置为 TRUE;如果它们引用不同对象， **CompareEntryIDs**将内容设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="479f3-130">If the two entry identifiers refer to the same object, **CompareEntryIDs** sets the contents of the  _lpulResult_ parameter to TRUE; if they refer to different objects, **CompareEntryIDs** sets the contents to FALSE.</span></span> <span data-ttu-id="479f3-131">在任一情况下， **CompareEntryIDs**返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="479f3-131">In either case, **CompareEntryIDs** returns S_OK.</span></span> <span data-ttu-id="479f3-132">如果**CompareEntryIDs**返回一个错误，如果没有通讯簿提供程序已注册的**MAPIUID**结构相匹配的项标识符中出现，客户端和提供程序应不执行任何操作的结果比较。</span><span class="sxs-lookup"><span data-stu-id="479f3-132">If **CompareEntryIDs** returns an error, which can occur if no address book provider has registered a **MAPIUID** structure that matches the one in the entry identifiers, clients and providers should not take any action based on the result of the comparison.</span></span> <span data-ttu-id="479f3-133">他们应改为需要最保守的方法，对正在执行的操作。</span><span class="sxs-lookup"><span data-stu-id="479f3-133">They should instead take the most conservative approach to the action being performed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="479f3-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="479f3-134">See also</span></span>



[<span data-ttu-id="479f3-135">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="479f3-135">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)

