---
title: IMAPISupportCompareEntryIDs
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.CompareEntryIDs
api_type:
- COM
ms.assetid: be6991d9-6353-4838-bc6b-39de51a94d8d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9dbf02fc94519d40431fb6bd493ef8e68df59d11
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566542"
---
# <a name="imapisupportcompareentryids"></a><span data-ttu-id="0cdcb-103">IMAPISupport::CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="0cdcb-103">IMAPISupport::CompareEntryIDs</span></span>

  
  
<span data-ttu-id="0cdcb-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0cdcb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0cdcb-105">比较两个条目标识符来确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="0cdcb-105">Compares two entry identifiers to determine whether they refer to the same object.</span></span> 
  
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

## <a name="parameters"></a><span data-ttu-id="0cdcb-106">参数</span><span class="sxs-lookup"><span data-stu-id="0cdcb-106">Parameters</span></span>

 <span data-ttu-id="0cdcb-107">_cbEntryID1_</span><span class="sxs-lookup"><span data-stu-id="0cdcb-107">_cbEntryID1_</span></span>
  
> <span data-ttu-id="0cdcb-108">[in]在_lpEntryID1_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="0cdcb-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID1_ parameter.</span></span> 
    
 <span data-ttu-id="0cdcb-109">_lpEntryID1_</span><span class="sxs-lookup"><span data-stu-id="0cdcb-109">_lpEntryID1_</span></span>
  
> <span data-ttu-id="0cdcb-110">[in]指向要进行比较的第一个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="0cdcb-110">[in] A pointer to the first entry identifier to be compared.</span></span>
    
 <span data-ttu-id="0cdcb-111">_cbEntryID2_</span><span class="sxs-lookup"><span data-stu-id="0cdcb-111">_cbEntryID2_</span></span>
  
> <span data-ttu-id="0cdcb-112">[in]在_lpEntryID2_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="0cdcb-112">[in] The byte count in the entry identifier pointed to by the  _lpEntryID2_ parameter.</span></span> 
    
 <span data-ttu-id="0cdcb-113">_lpEntryID2_</span><span class="sxs-lookup"><span data-stu-id="0cdcb-113">_lpEntryID2_</span></span>
  
> <span data-ttu-id="0cdcb-114">[in]指向要进行比较的第二个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="0cdcb-114">[in] A pointer to the second entry identifier to be compared.</span></span>
    
 <span data-ttu-id="0cdcb-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="0cdcb-115">_ulFlags_</span></span>
  
> <span data-ttu-id="0cdcb-116">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="0cdcb-116">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="0cdcb-117">_lpulResult_</span><span class="sxs-lookup"><span data-stu-id="0cdcb-117">_lpulResult_</span></span>
  
> <span data-ttu-id="0cdcb-118">[输出]一个指向比较结果的结果。</span><span class="sxs-lookup"><span data-stu-id="0cdcb-118">[out] A pointer to the result of the comparison.</span></span> <span data-ttu-id="0cdcb-119">如果两个条目标识符引用同一对象，则为 TRUE否则为返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="0cdcb-119">TRUE if the two entry identifiers refer to the same object; otherwise, FALSE.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="0cdcb-120">返回值</span><span class="sxs-lookup"><span data-stu-id="0cdcb-120">Return value</span></span>

<span data-ttu-id="0cdcb-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="0cdcb-121">S_OK</span></span> 
  
> <span data-ttu-id="0cdcb-122">比较成功。</span><span class="sxs-lookup"><span data-stu-id="0cdcb-122">The comparison was successful.</span></span>
    
<span data-ttu-id="0cdcb-123">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="0cdcb-123">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="0cdcb-124">一个或两个条目标识符指定为参数引用不是有效对象，可能是因为它们当前未打开和不可用。</span><span class="sxs-lookup"><span data-stu-id="0cdcb-124">One or both of the entry identifiers specified as parameters do not refer to valid objects, possibly because they are currently unopened and unavailable.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="0cdcb-125">注解</span><span class="sxs-lookup"><span data-stu-id="0cdcb-125">Remarks</span></span>

<span data-ttu-id="0cdcb-126">对于通讯簿和消息存储提供程序支持对象实现**IMAPISupport::CompareEntryIDs**方法。</span><span class="sxs-lookup"><span data-stu-id="0cdcb-126">The **IMAPISupport::CompareEntryIDs** method is implemented for address book and message store provider support objects.</span></span> <span data-ttu-id="0cdcb-127">**CompareEntryIDs**比较两个条目标识符属于单个服务提供程序确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="0cdcb-127">**CompareEntryIDs** compares two entry identifiers that belong to a single service provider to determine whether they refer to the same object.</span></span> <span data-ttu-id="0cdcb-128">MAPI 从条目标识符，以确定服务提供程序负责为对象中提取[MAPIUID](mapiuid.md)部分。</span><span class="sxs-lookup"><span data-stu-id="0cdcb-128">MAPI extracts the [MAPIUID](mapiuid.md) portion from the entry identifiers to determine the service provider responsible for the objects.</span></span> <span data-ttu-id="0cdcb-129">MAPI 然后调用其登录对象**CompareEntryIDs**方法来执行比较。</span><span class="sxs-lookup"><span data-stu-id="0cdcb-129">MAPI then calls its logon object's **CompareEntryIDs** method to perform the comparison.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="0cdcb-130">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="0cdcb-130">Notes to callers</span></span>

 <span data-ttu-id="0cdcb-131">**CompareEntryIDs**很有用，因为对象可以有多个有效项标识符。</span><span class="sxs-lookup"><span data-stu-id="0cdcb-131">**CompareEntryIDs** is useful because an object can have more than one valid entry identifier.</span></span> <span data-ttu-id="0cdcb-132">例如，安装新版本的服务提供商之后，会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="0cdcb-132">This situation can occur, for example, after a new version of a service provider is installed.</span></span> 
  
<span data-ttu-id="0cdcb-133">如果**CompareEntryIDs**返回一个错误，不会根据比较结果的任何操作。</span><span class="sxs-lookup"><span data-stu-id="0cdcb-133">If **CompareEntryIDs** returns an error, do not take any action based on the result of the comparison.</span></span> <span data-ttu-id="0cdcb-134">相反，可能需要最保守的方法。</span><span class="sxs-lookup"><span data-stu-id="0cdcb-134">Instead, take the most conservative approach possible.</span></span> <span data-ttu-id="0cdcb-135">如果一个或两个条目标识符，如包含无效的**MAPIUID**结构， **CompareEntryIDs**可能会失败。</span><span class="sxs-lookup"><span data-stu-id="0cdcb-135">**CompareEntryIDs** might fail if, for example, one or both of the entry identifiers contain an invalid **MAPIUID** structure.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0cdcb-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0cdcb-136">See also</span></span>



[<span data-ttu-id="0cdcb-137">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="0cdcb-137">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="0cdcb-138">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="0cdcb-138">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

