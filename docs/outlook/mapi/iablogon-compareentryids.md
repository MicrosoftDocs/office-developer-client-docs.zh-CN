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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 48ddb5a7c4e013c03138b08d9dadcdc0991faeec
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438370"
---
# <a name="iablogoncompareentryids"></a><span data-ttu-id="f1b46-103">IABLogon::CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="f1b46-103">IABLogon::CompareEntryIDs</span></span>

  
  
<span data-ttu-id="f1b46-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f1b46-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f1b46-105">比较两个条目标识符以确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="f1b46-105">Compares two entry identifiers to determine whether they refer to the same object.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="f1b46-106">参数</span><span class="sxs-lookup"><span data-stu-id="f1b46-106">Parameters</span></span>

 <span data-ttu-id="f1b46-107">_cbEntryID1_</span><span class="sxs-lookup"><span data-stu-id="f1b46-107">_cbEntryID1_</span></span>
  
> <span data-ttu-id="f1b46-108">[in]  _lpEntryID1_ 参数指向的条目标识符中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="f1b46-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID1_ parameter.</span></span> 
    
 <span data-ttu-id="f1b46-109">_lpEntryID1_</span><span class="sxs-lookup"><span data-stu-id="f1b46-109">_lpEntryID1_</span></span>
  
> <span data-ttu-id="f1b46-110">[in]指向要比较的第一个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="f1b46-110">[in] A pointer to the first entry identifier to be compared.</span></span>
    
 <span data-ttu-id="f1b46-111">_cbEntryID2_</span><span class="sxs-lookup"><span data-stu-id="f1b46-111">_cbEntryID2_</span></span>
  
> <span data-ttu-id="f1b46-112">[in]  _lpEntryID2_ 参数指向的条目标识符中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="f1b46-112">[in] The byte count in the entry identifier pointed to by the  _lpEntryID2_ parameter.</span></span> 
    
 <span data-ttu-id="f1b46-113">_lpEntryID2_</span><span class="sxs-lookup"><span data-stu-id="f1b46-113">_lpEntryID2_</span></span>
  
> <span data-ttu-id="f1b46-114">[in]指向要比较的第二个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="f1b46-114">[in] A pointer to the second entry identifier to be compared.</span></span>
    
 <span data-ttu-id="f1b46-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="f1b46-115">_ulFlags_</span></span>
  
> <span data-ttu-id="f1b46-116">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="f1b46-116">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="f1b46-117">_lpulRet_</span><span class="sxs-lookup"><span data-stu-id="f1b46-117">_lpulRet_</span></span>
  
> <span data-ttu-id="f1b46-118">[out]指向比较结果的指针。</span><span class="sxs-lookup"><span data-stu-id="f1b46-118">[out] A pointer to the result of the comparison.</span></span> <span data-ttu-id="f1b46-119">如果为 TRUE，则指示两个条目标识符引用同一个对象;否则为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="f1b46-119">TRUE to indicate that the two entry identifiers refer to the same object; otherwise, FALSE.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f1b46-120">返回值</span><span class="sxs-lookup"><span data-stu-id="f1b46-120">Return value</span></span>

<span data-ttu-id="f1b46-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="f1b46-121">S_OK</span></span> 
  
> <span data-ttu-id="f1b46-122">已成功比较条目标识符。</span><span class="sxs-lookup"><span data-stu-id="f1b46-122">The entry identifiers were successfully compared.</span></span>
    
<span data-ttu-id="f1b46-123">MAPI_E_INVALID_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="f1b46-123">MAPI_E_INVALID_ENTRYID</span></span> 
  
> <span data-ttu-id="f1b46-124">一个或两个条目标识符不属于通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="f1b46-124">One or both of the entry identifiers do not belong to the address book provider.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f1b46-125">备注</span><span class="sxs-lookup"><span data-stu-id="f1b46-125">Remarks</span></span>

<span data-ttu-id="f1b46-126">通讯簿提供程序实现 **CompareEntryIDs** 方法来比较两个条目标识符，以确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="f1b46-126">Address book providers implement the **CompareEntryIDs** method to compare two entry identifiers to determine whether they refer to the same object.</span></span> 
  
 <span data-ttu-id="f1b46-127">**CompareEntryIDs** 非常有用，因为对象可以具有多个有效的条目标识符;例如，将短期条目标识符与长期条目标识符进行比较时，可能会出现此情况。</span><span class="sxs-lookup"><span data-stu-id="f1b46-127">**CompareEntryIDs** is useful because an object can have more than one valid entry identifier; such a situation can occur, for example, when you compare a short-term entry identifier with a long-term entry identifier.</span></span> 
  
<span data-ttu-id="f1b46-128">若要详细了解如何创建条目标识符，请参阅 [MAPI 条目标识符](mapi-entry-identifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="f1b46-128">For more information about how to create entry identifiers, see [MAPI Entry Identifiers](mapi-entry-identifiers.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f1b46-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1b46-129">See also</span></span>



[<span data-ttu-id="f1b46-130">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f1b46-130">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

