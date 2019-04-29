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
# <a name="imsprovidercomparestoreids"></a><span data-ttu-id="442e1-103">IMSProvider::CompareStoreIDs</span><span class="sxs-lookup"><span data-stu-id="442e1-103">IMSProvider::CompareStoreIDs</span></span>

  
  
<span data-ttu-id="442e1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="442e1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="442e1-105">比较两个邮件存储区条目标识符, 以确定它们是否引用同一个存储对象。</span><span class="sxs-lookup"><span data-stu-id="442e1-105">Compares two message store entry identifiers to determine whether they refer to the same store object.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="442e1-106">参数</span><span class="sxs-lookup"><span data-stu-id="442e1-106">Parameters</span></span>

 <span data-ttu-id="442e1-107">_cbEntryID1_</span><span class="sxs-lookup"><span data-stu-id="442e1-107">_cbEntryID1_</span></span>
  
> <span data-ttu-id="442e1-108">实时由_lpEntryID1_参数指向的条目标识符的大小 (以字节为单位) _。_</span><span class="sxs-lookup"><span data-stu-id="442e1-108">[in] The size, in bytes, of the entry identifier pointed to by the  _lpEntryID1_ parameter  _._</span></span>
    
 <span data-ttu-id="442e1-109">_lpEntryID1_</span><span class="sxs-lookup"><span data-stu-id="442e1-109">_lpEntryID1_</span></span>
  
> <span data-ttu-id="442e1-110">实时指向要比较的第一个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="442e1-110">[in] A pointer to the first entry identifier to be compared.</span></span>
    
 <span data-ttu-id="442e1-111">_cbEntryID2_</span><span class="sxs-lookup"><span data-stu-id="442e1-111">_cbEntryID2_</span></span>
  
> <span data-ttu-id="442e1-112">实时由_lpEntryID2_参数指向的条目标识符的大小 (以字节为单位) _。_</span><span class="sxs-lookup"><span data-stu-id="442e1-112">[in] The size, in bytes, of the entry identifier pointed to by the  _lpEntryID2_ parameter  _._</span></span>
    
 <span data-ttu-id="442e1-113">_lpEntryID2_</span><span class="sxs-lookup"><span data-stu-id="442e1-113">_lpEntryID2_</span></span>
  
> <span data-ttu-id="442e1-114">实时指向要比较的第二个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="442e1-114">[in] A pointer to the second entry identifier to be compared.</span></span>
    
 <span data-ttu-id="442e1-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="442e1-115">_ulFlags_</span></span>
  
> <span data-ttu-id="442e1-116">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="442e1-116">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="442e1-117">_lpulResult_</span><span class="sxs-lookup"><span data-stu-id="442e1-117">_lpulResult_</span></span>
  
> <span data-ttu-id="442e1-118">排除指向比较的返回结果的指针。</span><span class="sxs-lookup"><span data-stu-id="442e1-118">[out] A pointer to the returned result of the comparison.</span></span> <span data-ttu-id="442e1-119">如果两个条目标识符引用同一个对象, 则为 TRUE; 否则为 false。否则为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="442e1-119">TRUE if the two entry identifiers refer to the same object; otherwise, FALSE.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="442e1-120">返回值</span><span class="sxs-lookup"><span data-stu-id="442e1-120">Return value</span></span>

<span data-ttu-id="442e1-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="442e1-121">S_OK</span></span> 
  
> <span data-ttu-id="442e1-122">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="442e1-122">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="442e1-123">说明</span><span class="sxs-lookup"><span data-stu-id="442e1-123">Remarks</span></span>

<span data-ttu-id="442e1-124">MAPI 在处理对[IMAPISession:: OpenMsgStore](imapisession-openmsgstore.md)方法的调用时调用**IMSProvider:: CompareStoreIDs**方法。</span><span class="sxs-lookup"><span data-stu-id="442e1-124">MAPI calls the **IMSProvider::CompareStoreIDs** method when it processes a call to the [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) method.</span></span> <span data-ttu-id="442e1-125">此时, 将调用**CompareStoreIDs** , 以确定哪个配置文件部分 (如果有) 与要打开的邮件存储区相关联。</span><span class="sxs-lookup"><span data-stu-id="442e1-125">**CompareStoreIDs** is called at this point to determine which profile section, if any, is associated with the message store being opened.</span></span> <span data-ttu-id="442e1-126">当没有打开特定存储提供程序的邮件存储区时, 可以进行**CompareStoreIDs**调用。</span><span class="sxs-lookup"><span data-stu-id="442e1-126">A **CompareStoreIDs** call can be made when no message stores are open for a particular store provider.</span></span> <span data-ttu-id="442e1-127">此外, MAPI 还会在处理对[IMAPISupport:: OpenProfileSection](imapisupport-openprofilesection.md)方法的存储提供程序调用时调用**CompareStoreIDs** 。</span><span class="sxs-lookup"><span data-stu-id="442e1-127">In addition, MAPI also calls **CompareStoreIDs** when it processes a store provider call to the [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md) method.</span></span> 
  
<span data-ttu-id="442e1-128">由**CompareStoreIDs**进行比较的条目标识符均适用于当前存储提供程序的动态链接库 (DLL), 并且都是已包装的存储项标识符。</span><span class="sxs-lookup"><span data-stu-id="442e1-128">The entry identifiers compared by **CompareStoreIDs** are both for the current store provider's dynamic-link library (DLL) and are both unwrapped store entry identifiers.</span></span> <span data-ttu-id="442e1-129">有关包装存储项标识符的详细信息, 请参阅[IMAPISupport:: WrapStoreEntryID](imapisupport-wrapstoreentryid.md)。</span><span class="sxs-lookup"><span data-stu-id="442e1-129">For more information about wrapping store entry identifiers, see [IMAPISupport::WrapStoreEntryID](imapisupport-wrapstoreentryid.md).</span></span>
  
<span data-ttu-id="442e1-130">比较条目标识符很有用, 因为一个对象可以有多个有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="442e1-130">Comparing entry identifiers is useful because an object can have more than one valid entry identifier.</span></span> <span data-ttu-id="442e1-131">例如, 在安装了新版本的邮件存储提供程序后, 可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="442e1-131">This can occur, for example, after a new version of a message store provider is installed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="442e1-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="442e1-132">See also</span></span>



[<span data-ttu-id="442e1-133">IMAPISession::OpenMsgStore</span><span class="sxs-lookup"><span data-stu-id="442e1-133">IMAPISession::OpenMsgStore</span></span>](imapisession-openmsgstore.md)
  
[<span data-ttu-id="442e1-134">IMAPISupport::OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="442e1-134">IMAPISupport::OpenProfileSection</span></span>](imapisupport-openprofilesection.md)
  
[<span data-ttu-id="442e1-135">IMAPISupport::WrapStoreEntryID</span><span class="sxs-lookup"><span data-stu-id="442e1-135">IMAPISupport::WrapStoreEntryID</span></span>](imapisupport-wrapstoreentryid.md)
  
[<span data-ttu-id="442e1-136">IMSProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="442e1-136">IMSProvider : IUnknown</span></span>](imsprovideriunknown.md)

