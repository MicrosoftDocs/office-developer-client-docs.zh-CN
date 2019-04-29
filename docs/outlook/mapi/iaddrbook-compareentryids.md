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
# <a name="iaddrbookcompareentryids"></a><span data-ttu-id="94ac8-103">IAddrBook::CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="94ac8-103">IAddrBook::CompareEntryIDs</span></span>

  
  
<span data-ttu-id="94ac8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="94ac8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="94ac8-105">对属于特定通讯簿提供程序的两个条目标识符进行比较, 以确定它们是否引用相同的通讯簿对象。</span><span class="sxs-lookup"><span data-stu-id="94ac8-105">Compares two entry identifiers that belong to a particular address book provider to determine whether they refer to the same address book object.</span></span> 
  
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

## <a name="parameters"></a><span data-ttu-id="94ac8-106">参数</span><span class="sxs-lookup"><span data-stu-id="94ac8-106">Parameters</span></span>

 <span data-ttu-id="94ac8-107">_cbEntryID1_</span><span class="sxs-lookup"><span data-stu-id="94ac8-107">_cbEntryID1_</span></span>
  
> <span data-ttu-id="94ac8-108">实时条目标识符中由_lpEntryID1_参数指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="94ac8-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID1_ parameter.</span></span> 
    
 <span data-ttu-id="94ac8-109">_lpEntryID1_</span><span class="sxs-lookup"><span data-stu-id="94ac8-109">_lpEntryID1_</span></span>
  
> <span data-ttu-id="94ac8-110">实时指向要比较的第一个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="94ac8-110">[in] A pointer to the first entry identifier to be compared.</span></span>
    
 <span data-ttu-id="94ac8-111">_cbEntryID2_</span><span class="sxs-lookup"><span data-stu-id="94ac8-111">_cbEntryID2_</span></span>
  
> <span data-ttu-id="94ac8-112">实时条目标识符中由_lpEntryID2_参数指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="94ac8-112">[in] The byte count in the entry identifier pointed to by the  _lpEntryID2_ parameter.</span></span> 
    
 <span data-ttu-id="94ac8-113">_lpEntryID2_</span><span class="sxs-lookup"><span data-stu-id="94ac8-113">_lpEntryID2_</span></span>
  
> <span data-ttu-id="94ac8-114">实时指向要比较的第二个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="94ac8-114">[in] A pointer to the second entry identifier to be compared.</span></span>
    
 <span data-ttu-id="94ac8-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="94ac8-115">_ulFlags_</span></span>
  
> <span data-ttu-id="94ac8-116">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="94ac8-116">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="94ac8-117">_lpulResult_</span><span class="sxs-lookup"><span data-stu-id="94ac8-117">_lpulResult_</span></span>
  
> <span data-ttu-id="94ac8-118">排除指向比较结果的指针。</span><span class="sxs-lookup"><span data-stu-id="94ac8-118">[out] A pointer to the result of the comparison.</span></span> <span data-ttu-id="94ac8-119">如果两个条目标识符引用同一个对象, 则_lpulResult_的内容设置为 TRUE; 否则为 false。否则, 内容将设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="94ac8-119">The contents of  _lpulResult_ are set to TRUE if the two entry identifiers refer to the same object; otherwise, the contents are set to FALSE.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="94ac8-120">返回值</span><span class="sxs-lookup"><span data-stu-id="94ac8-120">Return value</span></span>

<span data-ttu-id="94ac8-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="94ac8-121">S_OK</span></span> 
  
> <span data-ttu-id="94ac8-122">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="94ac8-122">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="94ac8-123">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="94ac8-123">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="94ac8-124">任何通讯簿提供程序都不能识别使用_lpEntryID1_或_lpEntryID2_参数传入的一个或两个条目标识符。</span><span class="sxs-lookup"><span data-stu-id="94ac8-124">One or both of the entry identifiers passed in with the  _lpEntryID1_ or  _lpEntryID2_ parameters are not recognized by any address book provider.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="94ac8-125">说明</span><span class="sxs-lookup"><span data-stu-id="94ac8-125">Remarks</span></span>

<span data-ttu-id="94ac8-126">客户端应用程序和服务提供程序调用**CompareEntryIDs**方法来比较属于单个通讯簿提供程序的两个条目标识符, 以确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="94ac8-126">Client applications and service providers call the **CompareEntryIDs** method to compare two entry identifiers that belongs to a single address book provider to determine whether they refer to the same object.</span></span> <span data-ttu-id="94ac8-127">**CompareEntryIDs**很有用, 因为一个对象可以有多个有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="94ac8-127">**CompareEntryIDs** is useful because an object can have more than one valid entry identifier.</span></span> <span data-ttu-id="94ac8-128">例如, 在安装新版本的通讯簿提供程序后, 可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="94ac8-128">This situation can occur, for example, after a new version of an address book provider is installed.</span></span> 
  
<span data-ttu-id="94ac8-129">MAPI 将此调用传递给负责条目标识符的通讯簿提供程序, 通过将条目标识符中的[MAPIUID](mapiuid.md)结构与注册的**MAPIUID**结构进行匹配来确定相应的提供程序。provider.</span><span class="sxs-lookup"><span data-stu-id="94ac8-129">MAPI passes this call to the address book provider that is responsible for the entry identifiers, determining the appropriate provider by matching the [MAPIUID](mapiuid.md) structure in the entry identifiers with the **MAPIUID** structure registered by the provider.</span></span> 
  
<span data-ttu-id="94ac8-130">如果两个条目标识符引用同一个对象, 则**CompareEntryIDs**会将_lpulResult_参数的内容设置为 TRUE;如果这些对象引用不同的对象, 则**CompareEntryIDs**会将内容设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="94ac8-130">If the two entry identifiers refer to the same object, **CompareEntryIDs** sets the contents of the  _lpulResult_ parameter to TRUE; if they refer to different objects, **CompareEntryIDs** sets the contents to FALSE.</span></span> <span data-ttu-id="94ac8-131">在这两种情况下, **CompareEntryIDs**返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="94ac8-131">In either case, **CompareEntryIDs** returns S_OK.</span></span> <span data-ttu-id="94ac8-132">如果**CompareEntryIDs**返回一个错误, 如果没有通讯簿提供程序注册了一个与条目标识符中的 MAPIUID 结构匹配的\*\*\*\* 结构, 则客户端和提供程序不应执行任何操作, 具体取决于而言.</span><span class="sxs-lookup"><span data-stu-id="94ac8-132">If **CompareEntryIDs** returns an error, which can occur if no address book provider has registered a **MAPIUID** structure that matches the one in the entry identifiers, clients and providers should not take any action based on the result of the comparison.</span></span> <span data-ttu-id="94ac8-133">而是应对执行的操作采取最保守的方法。</span><span class="sxs-lookup"><span data-stu-id="94ac8-133">They should instead take the most conservative approach to the action being performed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="94ac8-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94ac8-134">See also</span></span>



[<span data-ttu-id="94ac8-135">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="94ac8-135">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)

