---
title: IABLogonCompareEntryIDs
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABLogon.CompareEntryIDs
api_type:
- COM
ms.assetid: cb4a38ff-2fdd-40ac-a613-12c3f11a1df9
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 03256f2dec62d0228c4d5456dcd1b60f66b13ad2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775220"
---
# <a name="iablogoncompareentryids"></a><span data-ttu-id="1246c-103">IABLogon::CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="1246c-103">IABLogon::CompareEntryIDs</span></span>

  
  
<span data-ttu-id="1246c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="1246c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="1246c-105">比较两个条目标识符来确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="1246c-105">Compares two entry identifiers to determine whether they refer to the same object.</span></span>
  
```cpp
HRESULT CompareEntryIDs(
  ULONG cbEntryID1,
  LPENTRYID lpEntryID1,
  ULONG cbEntryID2,
  LPENTRYID lpEntryID2,
  ULONG ulFlags,
  ULONG FAR * lpulRet
);
```

## <a name="parameters"></a><span data-ttu-id="1246c-106">参数</span><span class="sxs-lookup"><span data-stu-id="1246c-106">Parameters</span></span>

 <span data-ttu-id="1246c-107">_cbEntryID1_</span><span class="sxs-lookup"><span data-stu-id="1246c-107">_cbEntryID1_</span></span>
  
> <span data-ttu-id="1246c-108">[in]在_lpEntryID1_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="1246c-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID1_ parameter.</span></span> 
    
 <span data-ttu-id="1246c-109">_lpEntryID1_</span><span class="sxs-lookup"><span data-stu-id="1246c-109">_lpEntryID1_</span></span>
  
> <span data-ttu-id="1246c-110">[in]指向要进行比较的第一个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="1246c-110">[in] A pointer to the first entry identifier to be compared.</span></span>
    
 <span data-ttu-id="1246c-111">_cbEntryID2_</span><span class="sxs-lookup"><span data-stu-id="1246c-111">_cbEntryID2_</span></span>
  
> <span data-ttu-id="1246c-112">[in]在_lpEntryID2_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="1246c-112">[in] The byte count in the entry identifier pointed to by the  _lpEntryID2_ parameter.</span></span> 
    
 <span data-ttu-id="1246c-113">_lpEntryID2_</span><span class="sxs-lookup"><span data-stu-id="1246c-113">_lpEntryID2_</span></span>
  
> <span data-ttu-id="1246c-114">[in]指向要进行比较的第二个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="1246c-114">[in] A pointer to the second entry identifier to be compared.</span></span>
    
 <span data-ttu-id="1246c-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="1246c-115">_ulFlags_</span></span>
  
> <span data-ttu-id="1246c-116">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="1246c-116">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="1246c-117">_lpulRet_</span><span class="sxs-lookup"><span data-stu-id="1246c-117">_lpulRet_</span></span>
  
> <span data-ttu-id="1246c-118">[输出]一个指向比较结果的结果。</span><span class="sxs-lookup"><span data-stu-id="1246c-118">[out] A pointer to the result of the comparison.</span></span> <span data-ttu-id="1246c-119">TRUE 表示的两个条目标识符引用同一对象;否则为返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="1246c-119">TRUE to indicate that the two entry identifiers refer to the same object; otherwise, FALSE.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="1246c-120">返回值</span><span class="sxs-lookup"><span data-stu-id="1246c-120">Return value</span></span>

<span data-ttu-id="1246c-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="1246c-121">S_OK</span></span> 
  
> <span data-ttu-id="1246c-122">已成功比较的项标识符。</span><span class="sxs-lookup"><span data-stu-id="1246c-122">The entry identifiers were successfully compared.</span></span>
    
<span data-ttu-id="1246c-123">MAPI_E_INVALID_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="1246c-123">MAPI_E_INVALID_ENTRYID</span></span> 
  
> <span data-ttu-id="1246c-124">一个或两个条目标识符不属于通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="1246c-124">One or both of the entry identifiers do not belong to the address book provider.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="1246c-125">备注</span><span class="sxs-lookup"><span data-stu-id="1246c-125">Remarks</span></span>

<span data-ttu-id="1246c-126">通讯簿提供程序实现**CompareEntryIDs**方法比较两个条目标识符来确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="1246c-126">Address book providers implement the **CompareEntryIDs** method to compare two entry identifiers to determine whether they refer to the same object.</span></span> 
  
 <span data-ttu-id="1246c-127">**CompareEntryIDs**很有用，因为对象可以有多个有效项标识符;例如，比较具有长期的项标识符的短期条目标识符时，可能发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="1246c-127">**CompareEntryIDs** is useful because an object can have more than one valid entry identifier; such a situation can occur, for example, when you compare a short-term entry identifier with a long-term entry identifier.</span></span> 
  
<span data-ttu-id="1246c-128">有关如何创建条目标识符的详细信息，请参阅[MAPI 条目标识符](mapi-entry-identifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="1246c-128">For more information about how to create entry identifiers, see [MAPI Entry Identifiers](mapi-entry-identifiers.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1246c-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1246c-129">See also</span></span>



[<span data-ttu-id="1246c-130">IABLogon: IUnknown</span><span class="sxs-lookup"><span data-stu-id="1246c-130">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

