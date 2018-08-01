---
title: IMSLogonCompareEntryIDs
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSLogon.CompareEntryIDs
api_type:
- COM
ms.assetid: 481812d6-8e94-4510-b288-55501dd5757c
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c2e6600af66f3dab8ff0fbb5442a1354687a3cbb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775907"
---
# <a name="imslogoncompareentryids"></a><span data-ttu-id="cc708-103">IMSLogon::CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="cc708-103">IMSLogon::CompareEntryIDs</span></span>

  
  
<span data-ttu-id="cc708-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="cc708-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="cc708-105">比较两个条目标识符来确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="cc708-105">Compares two entry identifiers to determine whether they refer to the same object.</span></span> <span data-ttu-id="cc708-106">仅当要比较两个条目 identifiers 中的唯一标识符 (Uid) 处理该服务提供商，MAPI 引用到的服务提供此呼叫。</span><span class="sxs-lookup"><span data-stu-id="cc708-106">MAPI refers this call to a service provider only if the unique identifiers (UIDs) in both entry identifiers to be compared are handled by that provider.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="cc708-107">参数</span><span class="sxs-lookup"><span data-stu-id="cc708-107">Parameters</span></span>

 <span data-ttu-id="cc708-108">_cbEntryID1_</span><span class="sxs-lookup"><span data-stu-id="cc708-108">_cbEntryID1_</span></span>
  
> <span data-ttu-id="cc708-109">[in]大小，以字节为单位的项标识符_lpEntryID1_参数指向 _。_</span><span class="sxs-lookup"><span data-stu-id="cc708-109">[in] The size, in bytes, of the entry identifier pointed to by the  _lpEntryID1_ parameter  _._</span></span>
    
 <span data-ttu-id="cc708-110">_lpEntryID1_</span><span class="sxs-lookup"><span data-stu-id="cc708-110">_lpEntryID1_</span></span>
  
> <span data-ttu-id="cc708-111">[in]指向要进行比较的第一个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="cc708-111">[in] A pointer to the first entry identifier to be compared.</span></span>
    
 <span data-ttu-id="cc708-112">_cbEntryID2_</span><span class="sxs-lookup"><span data-stu-id="cc708-112">_cbEntryID2_</span></span>
  
> <span data-ttu-id="cc708-113">[in]大小，以字节为单位的项标识符_lpEntryID2_参数指向 _。_</span><span class="sxs-lookup"><span data-stu-id="cc708-113">[in] The size, in bytes, of the entry identifier pointed to by the  _lpEntryID2_ parameter  _._</span></span>
    
 <span data-ttu-id="cc708-114">_lpEntryID2_</span><span class="sxs-lookup"><span data-stu-id="cc708-114">_lpEntryID2_</span></span>
  
> <span data-ttu-id="cc708-115">[in]指向要进行比较的第二个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="cc708-115">[in] A pointer to the second entry identifier to be compared.</span></span>
    
 <span data-ttu-id="cc708-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="cc708-116">_ulFlags_</span></span>
  
> <span data-ttu-id="cc708-117">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="cc708-117">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="cc708-118">_lpulResult_</span><span class="sxs-lookup"><span data-stu-id="cc708-118">_lpulResult_</span></span>
  
> <span data-ttu-id="cc708-119">[输出]一个指向的比较结果返回的结果。</span><span class="sxs-lookup"><span data-stu-id="cc708-119">[out] A pointer to the returned result of the comparison.</span></span> <span data-ttu-id="cc708-120">如果两个条目标识符引用同一对象，则为 TRUE否则为返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="cc708-120">TRUE if the two entry identifiers refer to the same object; otherwise, FALSE.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="cc708-121">返回值</span><span class="sxs-lookup"><span data-stu-id="cc708-121">Return value</span></span>

<span data-ttu-id="cc708-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="cc708-122">S_OK</span></span> 
  
> <span data-ttu-id="cc708-123">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="cc708-123">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="cc708-124">说明</span><span class="sxs-lookup"><span data-stu-id="cc708-124">Remarks</span></span>

<span data-ttu-id="cc708-125">消息存储提供程序实现**IMSLogon::CompareEntryIDs**方法比较两个条目中的消息存储，以确定它们是否引用同一个对象的给定项标识符。</span><span class="sxs-lookup"><span data-stu-id="cc708-125">Message store providers implement the **IMSLogon::CompareEntryIDs** method to compare two entry identifiers for a given entry in a message store to determine whether they refer to the same object.</span></span> <span data-ttu-id="cc708-126">如果两个条目标识符引用相同的对象，则**CompareEntryIDs**将_lpulResult_参数设置为 TRUE;如果它们引用不同对象， **CompareEntryIDs**将_lpulResult_设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="cc708-126">If the two entry identifiers refer to the same object, **CompareEntryIDs** sets the  _lpulResult_ parameter to TRUE; if they refer to different objects, **CompareEntryIDs** sets  _lpulResult_ to FALSE.</span></span> 
  
 <span data-ttu-id="cc708-127">**CompareEntryIDs**很有用，因为对象可以有多个有效项标识符。</span><span class="sxs-lookup"><span data-stu-id="cc708-127">**CompareEntryIDs** is useful because an object can have more than one valid entry identifier.</span></span> <span data-ttu-id="cc708-128">这可能会发生，例如，安装新版本的消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="cc708-128">This can occur, for example, after a new version of a message store provider is installed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="cc708-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc708-129">See also</span></span>



[<span data-ttu-id="cc708-130">IMSLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="cc708-130">IMSLogon : IUnknown</span></span>](imslogoniunknown.md)

