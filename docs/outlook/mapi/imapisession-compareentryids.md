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
ms.openlocfilehash: 4dfde82aa843072168288f4e0b0084dfccd5cd2b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427813"
---
# <a name="imapisessioncompareentryids"></a><span data-ttu-id="3d2dc-103">IMAPISession::CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="3d2dc-103">IMAPISession::CompareEntryIDs</span></span>

  
  
<span data-ttu-id="3d2dc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3d2dc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3d2dc-105">比较两个条目标识符以确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="3d2dc-105">Compares two entry identifiers to determine whether they refer to the same object.</span></span> 
  
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

## <a name="parameters"></a><span data-ttu-id="3d2dc-106">参数</span><span class="sxs-lookup"><span data-stu-id="3d2dc-106">Parameters</span></span>

 <span data-ttu-id="3d2dc-107">_cbEntryID1_</span><span class="sxs-lookup"><span data-stu-id="3d2dc-107">_cbEntryID1_</span></span>
  
> <span data-ttu-id="3d2dc-108">[in]  _lpEntryID1_ 参数指向的条目标识符中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="3d2dc-108">[in] The byte count in the entry identifier pointed to by the  _lpEntryID1_ parameter.</span></span> 
    
 <span data-ttu-id="3d2dc-109">_lpEntryID1_</span><span class="sxs-lookup"><span data-stu-id="3d2dc-109">_lpEntryID1_</span></span>
  
> <span data-ttu-id="3d2dc-110">[in]指向要比较的第一个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="3d2dc-110">[in] A pointer to the first entry identifier to be compared.</span></span>
    
 <span data-ttu-id="3d2dc-111">_cbEntryID2_</span><span class="sxs-lookup"><span data-stu-id="3d2dc-111">_cbEntryID2_</span></span>
  
> <span data-ttu-id="3d2dc-112">[in]  _lpEntryID2_ 参数指向的条目标识符中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="3d2dc-112">[in] The byte count in the entry identifier pointed to by the  _lpEntryID2_ parameter.</span></span> 
    
 <span data-ttu-id="3d2dc-113">_lpEntryID2_</span><span class="sxs-lookup"><span data-stu-id="3d2dc-113">_lpEntryID2_</span></span>
  
> <span data-ttu-id="3d2dc-114">[in]指向要比较的第二个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="3d2dc-114">[in] A pointer to the second entry identifier to be compared.</span></span>
    
 <span data-ttu-id="3d2dc-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="3d2dc-115">_ulFlags_</span></span>
  
> <span data-ttu-id="3d2dc-116">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="3d2dc-116">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="3d2dc-117">_lpulResult_</span><span class="sxs-lookup"><span data-stu-id="3d2dc-117">_lpulResult_</span></span>
  
> <span data-ttu-id="3d2dc-118">[out]指向比较结果的指针。</span><span class="sxs-lookup"><span data-stu-id="3d2dc-118">[out] A pointer to the result of the comparison.</span></span> <span data-ttu-id="3d2dc-119">如果两个条目标识符引用同一个对象，则其为 TRUE;否则为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="3d2dc-119">TRUE if the two entry identifiers refer to the same object; otherwise, FALSE.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="3d2dc-120">返回值</span><span class="sxs-lookup"><span data-stu-id="3d2dc-120">Return value</span></span>

<span data-ttu-id="3d2dc-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="3d2dc-121">S_OK</span></span> 
  
> <span data-ttu-id="3d2dc-122">比较成功。</span><span class="sxs-lookup"><span data-stu-id="3d2dc-122">The comparison was successful.</span></span>
    
<span data-ttu-id="3d2dc-123">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="3d2dc-123">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="3d2dc-124">指定为参数的一个或两个条目标识符不引用对象，可能是因为这些对象当前未打开且不可用。</span><span class="sxs-lookup"><span data-stu-id="3d2dc-124">One or both of the entry identifiers specified as parameters do not refer to objects, possibly because these objects are currently unopened and unavailable.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="3d2dc-125">备注</span><span class="sxs-lookup"><span data-stu-id="3d2dc-125">Remarks</span></span>

<span data-ttu-id="3d2dc-126">**IMAPISession：：CompareEntryIDs** 方法比较属于单个服务提供商的两个条目标识符，以确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="3d2dc-126">The **IMAPISession::CompareEntryIDs** method compares two entry identifiers that belong to a single service provider to determine whether they refer to the same object.</span></span> <span data-ttu-id="3d2dc-127">MAPI 从条目标识符 [中提取 MAPIUID](mapiuid.md) 部分，以确定负责对象的服务提供商，然后调用其登录对象的 **CompareEntryIDs** 方法来执行比较。</span><span class="sxs-lookup"><span data-stu-id="3d2dc-127">MAPI extracts the [MAPIUID](mapiuid.md) portion from the entry identifiers to determine the service provider responsible for the objects and then calls its logon object's **CompareEntryIDs** method to perform the comparison.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="3d2dc-128">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="3d2dc-128">Notes to callers</span></span>

<span data-ttu-id="3d2dc-129">**CompareEntryIDs** 方法很有用，因为对象可以具有多个有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="3d2dc-129">The **CompareEntryIDs** method is useful because an object can have more than one valid entry identifier.</span></span> <span data-ttu-id="3d2dc-130">例如，安装新版本的服务提供商之后，可能会发生此情况。</span><span class="sxs-lookup"><span data-stu-id="3d2dc-130">This situation can occur, for example, after a new version of a service provider is installed.</span></span> 
  
<span data-ttu-id="3d2dc-131">如果 **CompareEntryIDs** 返回错误，请不要根据比较结果执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="3d2dc-131">If **CompareEntryIDs** returns an error, do not take any action based on the result of the comparison.</span></span> <span data-ttu-id="3d2dc-132">相反，尽可能采用最保守的方法。</span><span class="sxs-lookup"><span data-stu-id="3d2dc-132">Instead, take the most conservative approach possible.</span></span> <span data-ttu-id="3d2dc-133">例如，如果一个或两个条目标识符包含无效 **的 MAPIUID** **，CompareEntryIDs** 可能会失败。</span><span class="sxs-lookup"><span data-stu-id="3d2dc-133">**CompareEntryIDs** might fail if, for example, one or both of the entry identifiers contain an invalid **MAPIUID**.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="3d2dc-134">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="3d2dc-134">MFCMAPI reference</span></span>

<span data-ttu-id="3d2dc-135">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="3d2dc-135">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="3d2dc-136">**文件**</span><span class="sxs-lookup"><span data-stu-id="3d2dc-136">**File**</span></span>|<span data-ttu-id="3d2dc-137">**函数**</span><span class="sxs-lookup"><span data-stu-id="3d2dc-137">**Function**</span></span>|<span data-ttu-id="3d2dc-138">**备注**</span><span class="sxs-lookup"><span data-stu-id="3d2dc-138">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3d2dc-139">BaseDialog.cpp</span><span class="sxs-lookup"><span data-stu-id="3d2dc-139">BaseDialog.cpp</span></span>  <br/> |<span data-ttu-id="3d2dc-140">CbaseDialog：：OnCompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="3d2dc-140">CbaseDialog::OnCompareEntryIDs</span></span>  <br/> |<span data-ttu-id="3d2dc-141">MFCMAPI 使用 **IMAPISession：：CompareEntryIDs** 方法比较用户输入的两个条目 ID。</span><span class="sxs-lookup"><span data-stu-id="3d2dc-141">MFCMAPI uses the **IMAPISession::CompareEntryIDs** method to compare two entry IDs that a user enters.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="3d2dc-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3d2dc-142">See also</span></span>



[<span data-ttu-id="3d2dc-143">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="3d2dc-143">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="3d2dc-144">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="3d2dc-144">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="3d2dc-145">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="3d2dc-145">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

