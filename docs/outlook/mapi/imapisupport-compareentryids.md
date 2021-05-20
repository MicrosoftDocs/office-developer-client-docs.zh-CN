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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6c79943792c8c17ee007c39b5c5c215a6fbc0699
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431041"
---
# <a name="imapisupportcompareentryids"></a><span data-ttu-id="3e3df-103">IMAPISupport::CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="3e3df-103">IMAPISupport::CompareEntryIDs</span></span>

  
  
<span data-ttu-id="3e3df-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3e3df-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3e3df-105">比较两个条目标识符以确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="3e3df-105">Compares two entry identifiers to determine whether they refer to the same object.</span></span> 
  
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

## <a name="parameters"></a><span data-ttu-id="3e3df-106">参数</span><span class="sxs-lookup"><span data-stu-id="3e3df-106">Parameters</span></span>

 <span data-ttu-id="3e3df-107">_cbEntryID1_</span><span class="sxs-lookup"><span data-stu-id="3e3df-107">_cbEntryID1_</span></span>
  
> <span data-ttu-id="3e3df-108">[in]  _lpEntryID1_ 参数指向的条目标识符中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="3e3df-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID1_ parameter.</span></span> 
    
 <span data-ttu-id="3e3df-109">_lpEntryID1_</span><span class="sxs-lookup"><span data-stu-id="3e3df-109">_lpEntryID1_</span></span>
  
> <span data-ttu-id="3e3df-110">[in]指向要比较的第一个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="3e3df-110">[in] A pointer to the first entry identifier to be compared.</span></span>
    
 <span data-ttu-id="3e3df-111">_cbEntryID2_</span><span class="sxs-lookup"><span data-stu-id="3e3df-111">_cbEntryID2_</span></span>
  
> <span data-ttu-id="3e3df-112">[in]  _lpEntryID2_ 参数指向的条目标识符中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="3e3df-112">[in] The byte count in the entry identifier pointed to by the  _lpEntryID2_ parameter.</span></span> 
    
 <span data-ttu-id="3e3df-113">_lpEntryID2_</span><span class="sxs-lookup"><span data-stu-id="3e3df-113">_lpEntryID2_</span></span>
  
> <span data-ttu-id="3e3df-114">[in]指向要比较的第二个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="3e3df-114">[in] A pointer to the second entry identifier to be compared.</span></span>
    
 <span data-ttu-id="3e3df-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="3e3df-115">_ulFlags_</span></span>
  
> <span data-ttu-id="3e3df-116">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="3e3df-116">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="3e3df-117">_lpulResult_</span><span class="sxs-lookup"><span data-stu-id="3e3df-117">_lpulResult_</span></span>
  
> <span data-ttu-id="3e3df-118">[out]指向比较结果的指针。</span><span class="sxs-lookup"><span data-stu-id="3e3df-118">[out] A pointer to the result of the comparison.</span></span> <span data-ttu-id="3e3df-119">如果两个条目标识符引用同一个对象，则其为 TRUE;否则为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="3e3df-119">TRUE if the two entry identifiers refer to the same object; otherwise, FALSE.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="3e3df-120">返回值</span><span class="sxs-lookup"><span data-stu-id="3e3df-120">Return value</span></span>

<span data-ttu-id="3e3df-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="3e3df-121">S_OK</span></span> 
  
> <span data-ttu-id="3e3df-122">比较成功。</span><span class="sxs-lookup"><span data-stu-id="3e3df-122">The comparison was successful.</span></span>
    
<span data-ttu-id="3e3df-123">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="3e3df-123">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="3e3df-124">指定为参数的一个或两个条目标识符不引用有效对象，可能是因为它们当前未打开且不可用。</span><span class="sxs-lookup"><span data-stu-id="3e3df-124">One or both of the entry identifiers specified as parameters do not refer to valid objects, possibly because they are currently unopened and unavailable.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="3e3df-125">备注</span><span class="sxs-lookup"><span data-stu-id="3e3df-125">Remarks</span></span>

<span data-ttu-id="3e3df-126">**IMAPISupport：：CompareEntryIDs** 方法针对通讯簿和邮件存储提供程序支持对象实现。</span><span class="sxs-lookup"><span data-stu-id="3e3df-126">The **IMAPISupport::CompareEntryIDs** method is implemented for address book and message store provider support objects.</span></span> <span data-ttu-id="3e3df-127">**CompareEntryIDs** 比较属于单个服务提供商的两个条目标识符，以确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="3e3df-127">**CompareEntryIDs** compares two entry identifiers that belong to a single service provider to determine whether they refer to the same object.</span></span> <span data-ttu-id="3e3df-128">MAPI 从条目标识符中提取 [MAPIUID](mapiuid.md) 部分，以确定负责对象的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="3e3df-128">MAPI extracts the [MAPIUID](mapiuid.md) portion from the entry identifiers to determine the service provider responsible for the objects.</span></span> <span data-ttu-id="3e3df-129">然后，MAPI 调用其登录对象的 **CompareEntryIDs** 方法来执行比较。</span><span class="sxs-lookup"><span data-stu-id="3e3df-129">MAPI then calls its logon object's **CompareEntryIDs** method to perform the comparison.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="3e3df-130">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="3e3df-130">Notes to callers</span></span>

 <span data-ttu-id="3e3df-131">**CompareEntryIDs** 非常有用，因为对象可以具有多个有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="3e3df-131">**CompareEntryIDs** is useful because an object can have more than one valid entry identifier.</span></span> <span data-ttu-id="3e3df-132">例如，安装新版本的服务提供商之后，可能会发生此情况。</span><span class="sxs-lookup"><span data-stu-id="3e3df-132">This situation can occur, for example, after a new version of a service provider is installed.</span></span> 
  
<span data-ttu-id="3e3df-133">如果 **CompareEntryIDs** 返回错误，请不要根据比较结果执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="3e3df-133">If **CompareEntryIDs** returns an error, do not take any action based on the result of the comparison.</span></span> <span data-ttu-id="3e3df-134">相反，尽可能采用最保守的方法。</span><span class="sxs-lookup"><span data-stu-id="3e3df-134">Instead, take the most conservative approach possible.</span></span> <span data-ttu-id="3e3df-135">例如，如果一个或两个条目标识符包含无效 **的 MAPIUID** 结构 **，CompareEntryIDs** 可能会失败。</span><span class="sxs-lookup"><span data-stu-id="3e3df-135">**CompareEntryIDs** might fail if, for example, one or both of the entry identifiers contain an invalid **MAPIUID** structure.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3e3df-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e3df-136">See also</span></span>



[<span data-ttu-id="3e3df-137">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="3e3df-137">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="3e3df-138">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="3e3df-138">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

