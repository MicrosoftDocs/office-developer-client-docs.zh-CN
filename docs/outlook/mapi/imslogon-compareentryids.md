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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4196ed8b949ecb9e23c4bd34380db9cc5a369e23
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348725"
---
# <a name="imslogoncompareentryids"></a><span data-ttu-id="208dc-103">IMSLogon::CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="208dc-103">IMSLogon::CompareEntryIDs</span></span>

  
  
<span data-ttu-id="208dc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="208dc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="208dc-105">对两个条目标识符进行比较, 以确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="208dc-105">Compares two entry identifiers to determine whether they refer to the same object.</span></span> <span data-ttu-id="208dc-106">MAPI 仅当该提供程序处理两个条目标识符中的唯一标识符 (uid) 时, 才会将此调用指向服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="208dc-106">MAPI refers this call to a service provider only if the unique identifiers (UIDs) in both entry identifiers to be compared are handled by that provider.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="208dc-107">参数</span><span class="sxs-lookup"><span data-stu-id="208dc-107">Parameters</span></span>

 <span data-ttu-id="208dc-108">_cbEntryID1_</span><span class="sxs-lookup"><span data-stu-id="208dc-108">_cbEntryID1_</span></span>
  
> <span data-ttu-id="208dc-109">实时由_lpEntryID1_参数指向的条目标识符的大小 (以字节为单位) _。_</span><span class="sxs-lookup"><span data-stu-id="208dc-109">[in] The size, in bytes, of the entry identifier pointed to by the  _lpEntryID1_ parameter  _._</span></span>
    
 <span data-ttu-id="208dc-110">_lpEntryID1_</span><span class="sxs-lookup"><span data-stu-id="208dc-110">_lpEntryID1_</span></span>
  
> <span data-ttu-id="208dc-111">实时指向要比较的第一个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="208dc-111">[in] A pointer to the first entry identifier to be compared.</span></span>
    
 <span data-ttu-id="208dc-112">_cbEntryID2_</span><span class="sxs-lookup"><span data-stu-id="208dc-112">_cbEntryID2_</span></span>
  
> <span data-ttu-id="208dc-113">实时由_lpEntryID2_参数指向的条目标识符的大小 (以字节为单位) _。_</span><span class="sxs-lookup"><span data-stu-id="208dc-113">[in] The size, in bytes, of the entry identifier pointed to by the  _lpEntryID2_ parameter  _._</span></span>
    
 <span data-ttu-id="208dc-114">_lpEntryID2_</span><span class="sxs-lookup"><span data-stu-id="208dc-114">_lpEntryID2_</span></span>
  
> <span data-ttu-id="208dc-115">实时指向要比较的第二个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="208dc-115">[in] A pointer to the second entry identifier to be compared.</span></span>
    
 <span data-ttu-id="208dc-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="208dc-116">_ulFlags_</span></span>
  
> <span data-ttu-id="208dc-117">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="208dc-117">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="208dc-118">_lpulResult_</span><span class="sxs-lookup"><span data-stu-id="208dc-118">_lpulResult_</span></span>
  
> <span data-ttu-id="208dc-119">排除指向比较的返回结果的指针。</span><span class="sxs-lookup"><span data-stu-id="208dc-119">[out] A pointer to the returned result of the comparison.</span></span> <span data-ttu-id="208dc-120">如果两个条目标识符引用同一个对象, 则为 TRUE; 否则为 false。否则为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="208dc-120">TRUE if the two entry identifiers refer to the same object; otherwise, FALSE.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="208dc-121">返回值</span><span class="sxs-lookup"><span data-stu-id="208dc-121">Return value</span></span>

<span data-ttu-id="208dc-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="208dc-122">S_OK</span></span> 
  
> <span data-ttu-id="208dc-123">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="208dc-123">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="208dc-124">注解</span><span class="sxs-lookup"><span data-stu-id="208dc-124">Remarks</span></span>

<span data-ttu-id="208dc-125">邮件存储提供程序实现**IMSLogon:: CompareEntryIDs**方法, 以比较邮件存储区中给定条目的两个条目标识符, 以确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="208dc-125">Message store providers implement the **IMSLogon::CompareEntryIDs** method to compare two entry identifiers for a given entry in a message store to determine whether they refer to the same object.</span></span> <span data-ttu-id="208dc-126">如果两个条目标识符引用同一个对象, 则**CompareEntryIDs**会将_lpulResult_参数设置为 TRUE;如果这些对象引用不同的对象, 则**CompareEntryIDs**会将_lpulResult_设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="208dc-126">If the two entry identifiers refer to the same object, **CompareEntryIDs** sets the  _lpulResult_ parameter to TRUE; if they refer to different objects, **CompareEntryIDs** sets  _lpulResult_ to FALSE.</span></span> 
  
 <span data-ttu-id="208dc-127">**CompareEntryIDs**很有用, 因为一个对象可以有多个有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="208dc-127">**CompareEntryIDs** is useful because an object can have more than one valid entry identifier.</span></span> <span data-ttu-id="208dc-128">例如, 在安装了新版本的邮件存储提供程序后, 可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="208dc-128">This can occur, for example, after a new version of a message store provider is installed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="208dc-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="208dc-129">See also</span></span>



[<span data-ttu-id="208dc-130">IMSLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="208dc-130">IMSLogon : IUnknown</span></span>](imslogoniunknown.md)

