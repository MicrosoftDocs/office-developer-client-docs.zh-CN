---
title: IMAPISessionCompareEntryIDs
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.CompareEntryIDs
api_type:
- COM
ms.assetid: 319f10e9-db8d-4d16-aa1f-6cf5fef493eb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 745c1b10cbbb24389cace7911d7c5fd37fe09472
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586849"
---
# <a name="imapisessioncompareentryids"></a><span data-ttu-id="fb3f6-103">IMAPISession::CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="fb3f6-103">IMAPISession::CompareEntryIDs</span></span>

  
  
<span data-ttu-id="fb3f6-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fb3f6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fb3f6-105">比较两个条目标识符来确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="fb3f6-105">Compares two entry identifiers to determine whether they refer to the same object.</span></span> 
  
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

## <a name="parameters"></a><span data-ttu-id="fb3f6-106">参数</span><span class="sxs-lookup"><span data-stu-id="fb3f6-106">Parameters</span></span>

 <span data-ttu-id="fb3f6-107">_cbEntryID1_</span><span class="sxs-lookup"><span data-stu-id="fb3f6-107">_cbEntryID1_</span></span>
  
> <span data-ttu-id="fb3f6-108">[in]在_lpEntryID1_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="fb3f6-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID1_ parameter.</span></span> 
    
 <span data-ttu-id="fb3f6-109">_lpEntryID1_</span><span class="sxs-lookup"><span data-stu-id="fb3f6-109">_lpEntryID1_</span></span>
  
> <span data-ttu-id="fb3f6-110">[in]指向要进行比较的第一个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="fb3f6-110">[in] A pointer to the first entry identifier to be compared.</span></span>
    
 <span data-ttu-id="fb3f6-111">_cbEntryID2_</span><span class="sxs-lookup"><span data-stu-id="fb3f6-111">_cbEntryID2_</span></span>
  
> <span data-ttu-id="fb3f6-112">[in]在_lpEntryID2_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="fb3f6-112">[in] The byte count in the entry identifier pointed to by the  _lpEntryID2_ parameter.</span></span> 
    
 <span data-ttu-id="fb3f6-113">_lpEntryID2_</span><span class="sxs-lookup"><span data-stu-id="fb3f6-113">_lpEntryID2_</span></span>
  
> <span data-ttu-id="fb3f6-114">[in]指向要进行比较的第二个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="fb3f6-114">[in] A pointer to the second entry identifier to be compared.</span></span>
    
 <span data-ttu-id="fb3f6-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="fb3f6-115">_ulFlags_</span></span>
  
> <span data-ttu-id="fb3f6-116">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="fb3f6-116">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="fb3f6-117">_lpulResult_</span><span class="sxs-lookup"><span data-stu-id="fb3f6-117">_lpulResult_</span></span>
  
> <span data-ttu-id="fb3f6-118">[输出]一个指向比较结果的结果。</span><span class="sxs-lookup"><span data-stu-id="fb3f6-118">[out] A pointer to the result of the comparison.</span></span> <span data-ttu-id="fb3f6-119">如果两个条目标识符引用同一对象，则为 TRUE否则为返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="fb3f6-119">TRUE if the two entry identifiers refer to the same object; otherwise, FALSE.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="fb3f6-120">返回值</span><span class="sxs-lookup"><span data-stu-id="fb3f6-120">Return value</span></span>

<span data-ttu-id="fb3f6-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="fb3f6-121">S_OK</span></span> 
  
> <span data-ttu-id="fb3f6-122">比较成功。</span><span class="sxs-lookup"><span data-stu-id="fb3f6-122">The comparison was successful.</span></span>
    
<span data-ttu-id="fb3f6-123">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="fb3f6-123">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="fb3f6-124">一个或两个条目标识符指定为参数引用不是对象，可能是因为这些对象是当前未打开和不可用。</span><span class="sxs-lookup"><span data-stu-id="fb3f6-124">One or both of the entry identifiers specified as parameters do not refer to objects, possibly because these objects are currently unopened and unavailable.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="fb3f6-125">注解</span><span class="sxs-lookup"><span data-stu-id="fb3f6-125">Remarks</span></span>

<span data-ttu-id="fb3f6-126">**IMAPISession::CompareEntryIDs**方法比较两个条目标识符属于单个服务提供程序确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="fb3f6-126">The **IMAPISession::CompareEntryIDs** method compares two entry identifiers that belong to a single service provider to determine whether they refer to the same object.</span></span> <span data-ttu-id="fb3f6-127">MAPI [MAPIUID](mapiuid.md)部分提取条目标识符，以确定服务提供程序负责对象，然后调用其登录对象**CompareEntryIDs**方法以执行比较。</span><span class="sxs-lookup"><span data-stu-id="fb3f6-127">MAPI extracts the [MAPIUID](mapiuid.md) portion from the entry identifiers to determine the service provider responsible for the objects and then calls its logon object's **CompareEntryIDs** method to perform the comparison.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="fb3f6-128">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="fb3f6-128">Notes to callers</span></span>

<span data-ttu-id="fb3f6-129">**CompareEntryIDs**方法很有用，因为对象可以有多个有效项标识符。</span><span class="sxs-lookup"><span data-stu-id="fb3f6-129">The **CompareEntryIDs** method is useful because an object can have more than one valid entry identifier.</span></span> <span data-ttu-id="fb3f6-130">例如，安装新版本的服务提供商之后，会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="fb3f6-130">This situation can occur, for example, after a new version of a service provider is installed.</span></span> 
  
<span data-ttu-id="fb3f6-131">如果**CompareEntryIDs**返回一个错误，不会根据比较结果的任何操作。</span><span class="sxs-lookup"><span data-stu-id="fb3f6-131">If **CompareEntryIDs** returns an error, do not take any action based on the result of the comparison.</span></span> <span data-ttu-id="fb3f6-132">相反，可能需要最保守的方法。</span><span class="sxs-lookup"><span data-stu-id="fb3f6-132">Instead, take the most conservative approach possible.</span></span> <span data-ttu-id="fb3f6-133">如果一个或两个条目标识符，如包含无效的**MAPIUID**， **CompareEntryIDs**可能会失败。</span><span class="sxs-lookup"><span data-stu-id="fb3f6-133">**CompareEntryIDs** might fail if, for example, one or both of the entry identifiers contain an invalid **MAPIUID**.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="fb3f6-134">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="fb3f6-134">MFCMAPI reference</span></span>

<span data-ttu-id="fb3f6-135">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="fb3f6-135">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="fb3f6-136">**文件**</span><span class="sxs-lookup"><span data-stu-id="fb3f6-136">**File**</span></span>|<span data-ttu-id="fb3f6-137">**函数**</span><span class="sxs-lookup"><span data-stu-id="fb3f6-137">**Function**</span></span>|<span data-ttu-id="fb3f6-138">**Comment**</span><span class="sxs-lookup"><span data-stu-id="fb3f6-138">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fb3f6-139">BaseDialog.cpp</span><span class="sxs-lookup"><span data-stu-id="fb3f6-139">BaseDialog.cpp</span></span>  <br/> |<span data-ttu-id="fb3f6-140">CbaseDialog::OnCompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="fb3f6-140">CbaseDialog::OnCompareEntryIDs</span></span>  <br/> |<span data-ttu-id="fb3f6-141">MFCMAPI 使用**IMAPISession::CompareEntryIDs**方法比较用户输入的两个条目 Id。</span><span class="sxs-lookup"><span data-stu-id="fb3f6-141">MFCMAPI uses the **IMAPISession::CompareEntryIDs** method to compare two entry IDs that a user enters.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="fb3f6-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb3f6-142">See also</span></span>



[<span data-ttu-id="fb3f6-143">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="fb3f6-143">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="fb3f6-144">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="fb3f6-144">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="fb3f6-145">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="fb3f6-145">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

