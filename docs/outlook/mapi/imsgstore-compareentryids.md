---
title: IMsgStoreCompareEntryIDs
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.CompareEntryIDs
api_type:
- COM
ms.assetid: 33d70748-0d3f-4be4-bcb5-7ec048887944
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a1c5cdc67bc64f20dd8ba0a5e8682c5e2f97294f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775866"
---
# <a name="imsgstorecompareentryids"></a><span data-ttu-id="b09b1-103">IMsgStore::CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="b09b1-103">IMsgStore::CompareEntryIDs</span></span>

  
  
<span data-ttu-id="b09b1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b09b1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b09b1-105">比较两个条目标识符来确定它们是否引用中的消息存储的同一个条目。</span><span class="sxs-lookup"><span data-stu-id="b09b1-105">Compares two entry identifiers to determine whether they refer to the same entry in a message store.</span></span> <span data-ttu-id="b09b1-106">MAPI 将传递到的服务提供此呼叫，仅当要比较两个条目 identifiers 中的唯一标识符 (Uid) 处理该服务提供商。</span><span class="sxs-lookup"><span data-stu-id="b09b1-106">MAPI passes this call to a service provider only if the unique identifiers (UIDs) in both entry identifiers to be compared are handled by that provider.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="b09b1-107">参数</span><span class="sxs-lookup"><span data-stu-id="b09b1-107">Parameters</span></span>

 <span data-ttu-id="b09b1-108">_cbEntryID1_</span><span class="sxs-lookup"><span data-stu-id="b09b1-108">_cbEntryID1_</span></span>
  
> <span data-ttu-id="b09b1-109">[in]_LpEntryID1_参数 _。_ 指向该条目标识符中字节数</span><span class="sxs-lookup"><span data-stu-id="b09b1-109">[in] The byte count in the entry identifier pointed to by the  _lpEntryID1_ parameter  _._</span></span>
    
 <span data-ttu-id="b09b1-110">_lpEntryID1_</span><span class="sxs-lookup"><span data-stu-id="b09b1-110">_lpEntryID1_</span></span>
  
> <span data-ttu-id="b09b1-111">[in]指向要进行比较的第一个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="b09b1-111">[in] A pointer to the first entry identifier to be compared.</span></span>
    
 <span data-ttu-id="b09b1-112">_cbEntryID2_</span><span class="sxs-lookup"><span data-stu-id="b09b1-112">_cbEntryID2_</span></span>
  
> <span data-ttu-id="b09b1-113">[in]_LpEntryID2_参数 _。_ 指向该条目标识符中字节数</span><span class="sxs-lookup"><span data-stu-id="b09b1-113">[in] The byte count in the entry identifier pointed to by the  _lpEntryID2_ parameter  _._</span></span>
    
 <span data-ttu-id="b09b1-114">_lpEntryID2_</span><span class="sxs-lookup"><span data-stu-id="b09b1-114">_lpEntryID2_</span></span>
  
> <span data-ttu-id="b09b1-115">[in]指向要进行比较的第二个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="b09b1-115">[in] A pointer to the second entry identifier to be compared.</span></span>
    
 <span data-ttu-id="b09b1-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b09b1-116">_ulFlags_</span></span>
  
> <span data-ttu-id="b09b1-117">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="b09b1-117">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="b09b1-118">_lpulResult_</span><span class="sxs-lookup"><span data-stu-id="b09b1-118">_lpulResult_</span></span>
  
> <span data-ttu-id="b09b1-119">[输出]一个指向比较结果的结果。</span><span class="sxs-lookup"><span data-stu-id="b09b1-119">[out] A pointer to the result of the comparison.</span></span> <span data-ttu-id="b09b1-120">如果两个条目标识符引用同一对象，则为 TRUE否则为返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="b09b1-120">TRUE if the two entry identifiers refer to the same object; otherwise, FALSE.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="b09b1-121">返回值</span><span class="sxs-lookup"><span data-stu-id="b09b1-121">Return value</span></span>

<span data-ttu-id="b09b1-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="b09b1-122">S_OK</span></span> 
  
> <span data-ttu-id="b09b1-123">比较成功。</span><span class="sxs-lookup"><span data-stu-id="b09b1-123">The comparison was successful.</span></span>
    
<span data-ttu-id="b09b1-124">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="b09b1-124">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="b09b1-125">显示一个或两个条目标识符指定为参数引用不是对象，可能是因为相应的对象未打开，并在不可用。</span><span class="sxs-lookup"><span data-stu-id="b09b1-125">One or both of the entry identifiers specified as parameters do not refer to objects, possibly because the corresponding objects are unopened and unavailable at present.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b09b1-126">说明</span><span class="sxs-lookup"><span data-stu-id="b09b1-126">Remarks</span></span>

<span data-ttu-id="b09b1-127">**IMsgStore::CompareEntryIDs**方法比较两个条目标识符属于要确定它们是否引用同一个对象的消息存储。</span><span class="sxs-lookup"><span data-stu-id="b09b1-127">The **IMsgStore::CompareEntryIDs** method compares two entry identifiers that belong to the message store to determine whether they refer to the same object.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="b09b1-128">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="b09b1-128">Notes to callers</span></span>

 <span data-ttu-id="b09b1-129">**CompareEntryIDs**很有用，因为对象可以有多个有效项标识符 （例如，安装新版本的消息存储提供程序后）。</span><span class="sxs-lookup"><span data-stu-id="b09b1-129">**CompareEntryIDs** is useful because an object can have more than one valid entry identifier (for example, after a new version of a message store provider is installed).</span></span> 
  
<span data-ttu-id="b09b1-130">如果**CompareEntryIDs**返回一个错误，不会根据比较结果的任何操作。</span><span class="sxs-lookup"><span data-stu-id="b09b1-130">If **CompareEntryIDs** returns an error, do not take any action based on the result of the comparison.</span></span> <span data-ttu-id="b09b1-131">相反，可能需要最保守的方法。</span><span class="sxs-lookup"><span data-stu-id="b09b1-131">Instead, take the most conservative approach possible.</span></span> <span data-ttu-id="b09b1-132">如果一个或两个条目标识符，如包含无效的**MAPIUID**， **CompareEntryIDs**可能会失败。</span><span class="sxs-lookup"><span data-stu-id="b09b1-132">**CompareEntryIDs** might fail if, for example, one or both of the entry identifiers contains an invalid **MAPIUID**.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="b09b1-133">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="b09b1-133">MFCMAPI reference</span></span>

<span data-ttu-id="b09b1-134">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="b09b1-134">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="b09b1-135">**文件**</span><span class="sxs-lookup"><span data-stu-id="b09b1-135">**File**</span></span>|<span data-ttu-id="b09b1-136">**函数**</span><span class="sxs-lookup"><span data-stu-id="b09b1-136">**Function**</span></span>|<span data-ttu-id="b09b1-137">**Comment**</span><span class="sxs-lookup"><span data-stu-id="b09b1-137">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b09b1-138">BaseDialog.cpp</span><span class="sxs-lookup"><span data-stu-id="b09b1-138">BaseDialog.cpp</span></span>  <br/> |<span data-ttu-id="b09b1-139">CBaseDialog::OnCompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="b09b1-139">CBaseDialog::OnCompareEntryIDs</span></span>  <br/> |<span data-ttu-id="b09b1-140">MFCMAPI 使用**IMsgStore::CompareEntryIDs**方法比较条目 Id。</span><span class="sxs-lookup"><span data-stu-id="b09b1-140">MFCMAPI uses the **IMsgStore::CompareEntryIDs** method to compare entry IDs.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b09b1-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b09b1-141">See also</span></span>



[<span data-ttu-id="b09b1-142">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="b09b1-142">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="b09b1-143">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="b09b1-143">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)


[<span data-ttu-id="b09b1-144">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="b09b1-144">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

