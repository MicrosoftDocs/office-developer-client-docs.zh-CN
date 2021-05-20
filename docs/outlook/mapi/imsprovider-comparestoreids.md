---
title: IMSProviderCompareStoreIDs
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSProvider.CompareStoreIDs
api_type:
- COM
ms.assetid: c3e3cfaa-9c4a-482a-9411-9c4ab01d312f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 734e53c1e897c902c72319aa6f2d3d7af2d23fb6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431706"
---
# <a name="imsprovidercomparestoreids"></a><span data-ttu-id="64641-103">IMSProvider::CompareStoreIDs</span><span class="sxs-lookup"><span data-stu-id="64641-103">IMSProvider::CompareStoreIDs</span></span>

  
  
<span data-ttu-id="64641-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="64641-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="64641-105">比较两个邮件存储条目标识符以确定它们是否引用同一存储对象。</span><span class="sxs-lookup"><span data-stu-id="64641-105">Compares two message store entry identifiers to determine whether they refer to the same store object.</span></span>
  
```cpp
HRESULT CompareStoreIDs(
  ULONG cbEntryID1,
  LPENTRYID lpEntryID1,
  ULONG cbEntryID2,
  LPENTRYID lpEntryID2,
  ULONG ulFlags,
  ULONG FAR * lpulResult
);
```

## <a name="parameters"></a><span data-ttu-id="64641-106">参数</span><span class="sxs-lookup"><span data-stu-id="64641-106">Parameters</span></span>

 <span data-ttu-id="64641-107">_cbEntryID1_</span><span class="sxs-lookup"><span data-stu-id="64641-107">_cbEntryID1_</span></span>
  
> <span data-ttu-id="64641-108">[in]  _lpEntryID1_ 参数指向的条目标识符的大小（以字节为单位  _）。_</span><span class="sxs-lookup"><span data-stu-id="64641-108">[in] The size, in bytes, of the entry identifier pointed to by the  _lpEntryID1_ parameter  _._</span></span>
    
 <span data-ttu-id="64641-109">_lpEntryID1_</span><span class="sxs-lookup"><span data-stu-id="64641-109">_lpEntryID1_</span></span>
  
> <span data-ttu-id="64641-110">[in]指向要比较的第一个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="64641-110">[in] A pointer to the first entry identifier to be compared.</span></span>
    
 <span data-ttu-id="64641-111">_cbEntryID2_</span><span class="sxs-lookup"><span data-stu-id="64641-111">_cbEntryID2_</span></span>
  
> <span data-ttu-id="64641-112">[in]  _lpEntryID2_ 参数指向的条目标识符的大小（以字节为单位  _）。_</span><span class="sxs-lookup"><span data-stu-id="64641-112">[in] The size, in bytes, of the entry identifier pointed to by the  _lpEntryID2_ parameter  _._</span></span>
    
 <span data-ttu-id="64641-113">_lpEntryID2_</span><span class="sxs-lookup"><span data-stu-id="64641-113">_lpEntryID2_</span></span>
  
> <span data-ttu-id="64641-114">[in]指向要比较的第二个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="64641-114">[in] A pointer to the second entry identifier to be compared.</span></span>
    
 <span data-ttu-id="64641-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="64641-115">_ulFlags_</span></span>
  
> <span data-ttu-id="64641-116">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="64641-116">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="64641-117">_lpulResult_</span><span class="sxs-lookup"><span data-stu-id="64641-117">_lpulResult_</span></span>
  
> <span data-ttu-id="64641-118">[out]指向比较结果的返回结果的指针。</span><span class="sxs-lookup"><span data-stu-id="64641-118">[out] A pointer to the returned result of the comparison.</span></span> <span data-ttu-id="64641-119">如果两个条目标识符引用同一个对象，则其为 TRUE;否则为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="64641-119">TRUE if the two entry identifiers refer to the same object; otherwise, FALSE.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="64641-120">返回值</span><span class="sxs-lookup"><span data-stu-id="64641-120">Return value</span></span>

<span data-ttu-id="64641-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="64641-121">S_OK</span></span> 
  
> <span data-ttu-id="64641-122">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="64641-122">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="64641-123">备注</span><span class="sxs-lookup"><span data-stu-id="64641-123">Remarks</span></span>

<span data-ttu-id="64641-124">MAPI 在处理对 [IMAPISession：：OpenMsgStore](imapisession-openmsgstore.md)方法的调用时调用 **IMSProvider：：CompareStoreIDs** 方法。</span><span class="sxs-lookup"><span data-stu-id="64641-124">MAPI calls the **IMSProvider::CompareStoreIDs** method when it processes a call to the [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) method.</span></span> <span data-ttu-id="64641-125">**此时将调用 CompareStoreIDs** 以确定哪个配置文件部分（如果有）与正在打开的邮件存储相关联。</span><span class="sxs-lookup"><span data-stu-id="64641-125">**CompareStoreIDs** is called at this point to determine which profile section, if any, is associated with the message store being opened.</span></span> <span data-ttu-id="64641-126">当没有为特定存储提供程序打开任何邮件存储时，可以调用 **CompareStoreIDs。**</span><span class="sxs-lookup"><span data-stu-id="64641-126">A **CompareStoreIDs** call can be made when no message stores are open for a particular store provider.</span></span> <span data-ttu-id="64641-127">此外，MAPI 还会在处理对 [IMAPISupport：：OpenProfileSection](imapisupport-openprofilesection.md)方法的存储提供程序调用时调用 **CompareStoreIDs。**</span><span class="sxs-lookup"><span data-stu-id="64641-127">In addition, MAPI also calls **CompareStoreIDs** when it processes a store provider call to the [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md) method.</span></span> 
  
<span data-ttu-id="64641-128">**CompareStoreIDs** 比较的条目标识符既适用于当前存储提供程序的动态链接库 (DLL) ，又都是未包存储条目标识符。</span><span class="sxs-lookup"><span data-stu-id="64641-128">The entry identifiers compared by **CompareStoreIDs** are both for the current store provider's dynamic-link library (DLL) and are both unwrapped store entry identifiers.</span></span> <span data-ttu-id="64641-129">有关包装存储条目标识符的信息，请参阅 [IMAPISupport：：WrapStoreEntryID](imapisupport-wrapstoreentryid.md)。</span><span class="sxs-lookup"><span data-stu-id="64641-129">For more information about wrapping store entry identifiers, see [IMAPISupport::WrapStoreEntryID](imapisupport-wrapstoreentryid.md).</span></span>
  
<span data-ttu-id="64641-130">比较条目标识符非常有用，因为对象可以具有多个有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="64641-130">Comparing entry identifiers is useful because an object can have more than one valid entry identifier.</span></span> <span data-ttu-id="64641-131">例如，安装邮件存储提供程序的新版本后，可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="64641-131">This can occur, for example, after a new version of a message store provider is installed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="64641-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64641-132">See also</span></span>



[<span data-ttu-id="64641-133">IMAPISession::OpenMsgStore</span><span class="sxs-lookup"><span data-stu-id="64641-133">IMAPISession::OpenMsgStore</span></span>](imapisession-openmsgstore.md)
  
[<span data-ttu-id="64641-134">IMAPISupport::OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="64641-134">IMAPISupport::OpenProfileSection</span></span>](imapisupport-openprofilesection.md)
  
[<span data-ttu-id="64641-135">IMAPISupport::WrapStoreEntryID</span><span class="sxs-lookup"><span data-stu-id="64641-135">IMAPISupport::WrapStoreEntryID</span></span>](imapisupport-wrapstoreentryid.md)
  
[<span data-ttu-id="64641-136">IMSProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="64641-136">IMSProvider : IUnknown</span></span>](imsprovideriunknown.md)

