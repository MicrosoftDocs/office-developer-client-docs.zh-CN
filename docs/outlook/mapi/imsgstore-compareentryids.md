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
ms.openlocfilehash: 2a2439bae79b497f018391983e2c4b03a35eee70
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424250"
---
# <a name="imsgstorecompareentryids"></a><span data-ttu-id="1e7c0-103">IMsgStore::CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="1e7c0-103">IMsgStore::CompareEntryIDs</span></span>

  
  
<span data-ttu-id="1e7c0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1e7c0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1e7c0-105">对两个条目标识符进行比较, 以确定它们是否引用邮件存储区中的相同条目。</span><span class="sxs-lookup"><span data-stu-id="1e7c0-105">Compares two entry identifiers to determine whether they refer to the same entry in a message store.</span></span> <span data-ttu-id="1e7c0-106">仅当该提供程序处理两个条目标识符中的唯一标识符 (uid) 时, MAPI 才会将此调用传递给服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="1e7c0-106">MAPI passes this call to a service provider only if the unique identifiers (UIDs) in both entry identifiers to be compared are handled by that provider.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="1e7c0-107">参数</span><span class="sxs-lookup"><span data-stu-id="1e7c0-107">Parameters</span></span>

 <span data-ttu-id="1e7c0-108">_cbEntryID1_</span><span class="sxs-lookup"><span data-stu-id="1e7c0-108">_cbEntryID1_</span></span>
  
> <span data-ttu-id="1e7c0-109">实时条目标识符中由_lpEntryID1_参数指向的字节数 _。_</span><span class="sxs-lookup"><span data-stu-id="1e7c0-109">[in] The byte count in the entry identifier pointed to by the  _lpEntryID1_ parameter  _._</span></span>
    
 <span data-ttu-id="1e7c0-110">_lpEntryID1_</span><span class="sxs-lookup"><span data-stu-id="1e7c0-110">_lpEntryID1_</span></span>
  
> <span data-ttu-id="1e7c0-111">实时指向要比较的第一个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="1e7c0-111">[in] A pointer to the first entry identifier to be compared.</span></span>
    
 <span data-ttu-id="1e7c0-112">_cbEntryID2_</span><span class="sxs-lookup"><span data-stu-id="1e7c0-112">_cbEntryID2_</span></span>
  
> <span data-ttu-id="1e7c0-113">实时条目标识符中由_lpEntryID2_参数指向的字节数 _。_</span><span class="sxs-lookup"><span data-stu-id="1e7c0-113">[in] The byte count in the entry identifier pointed to by the  _lpEntryID2_ parameter  _._</span></span>
    
 <span data-ttu-id="1e7c0-114">_lpEntryID2_</span><span class="sxs-lookup"><span data-stu-id="1e7c0-114">_lpEntryID2_</span></span>
  
> <span data-ttu-id="1e7c0-115">实时指向要比较的第二个条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="1e7c0-115">[in] A pointer to the second entry identifier to be compared.</span></span>
    
 <span data-ttu-id="1e7c0-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="1e7c0-116">_ulFlags_</span></span>
  
> <span data-ttu-id="1e7c0-117">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="1e7c0-117">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="1e7c0-118">_lpulResult_</span><span class="sxs-lookup"><span data-stu-id="1e7c0-118">_lpulResult_</span></span>
  
> <span data-ttu-id="1e7c0-119">排除指向比较结果的指针。</span><span class="sxs-lookup"><span data-stu-id="1e7c0-119">[out] A pointer to the result of the comparison.</span></span> <span data-ttu-id="1e7c0-120">如果两个条目标识符引用同一个对象, 则为 TRUE; 否则为 false。否则为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="1e7c0-120">TRUE if the two entry identifiers refer to the same object; otherwise, FALSE.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="1e7c0-121">返回值</span><span class="sxs-lookup"><span data-stu-id="1e7c0-121">Return value</span></span>

<span data-ttu-id="1e7c0-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="1e7c0-122">S_OK</span></span> 
  
> <span data-ttu-id="1e7c0-123">比较成功。</span><span class="sxs-lookup"><span data-stu-id="1e7c0-123">The comparison was successful.</span></span>
    
<span data-ttu-id="1e7c0-124">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="1e7c0-124">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="1e7c0-125">指定为参数的输入标识符中的一个或两个都不引用对象, 原因可能是相应的对象尚未打开, 并且目前不可用。</span><span class="sxs-lookup"><span data-stu-id="1e7c0-125">One or both of the entry identifiers specified as parameters do not refer to objects, possibly because the corresponding objects are unopened and unavailable at present.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="1e7c0-126">说明</span><span class="sxs-lookup"><span data-stu-id="1e7c0-126">Remarks</span></span>

<span data-ttu-id="1e7c0-127">**IMsgStore:: CompareEntryIDs**方法对属于邮件存储的两个条目标识符进行比较, 以确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="1e7c0-127">The **IMsgStore::CompareEntryIDs** method compares two entry identifiers that belong to the message store to determine whether they refer to the same object.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="1e7c0-128">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="1e7c0-128">Notes to callers</span></span>

 <span data-ttu-id="1e7c0-129">**CompareEntryIDs**很有用, 因为一个对象可以有多个有效条目标识符 (例如, 在安装了新版本的邮件存储提供程序之后)。</span><span class="sxs-lookup"><span data-stu-id="1e7c0-129">**CompareEntryIDs** is useful because an object can have more than one valid entry identifier (for example, after a new version of a message store provider is installed).</span></span> 
  
<span data-ttu-id="1e7c0-130">如果**CompareEntryIDs**返回错误, 则不根据比较结果执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="1e7c0-130">If **CompareEntryIDs** returns an error, do not take any action based on the result of the comparison.</span></span> <span data-ttu-id="1e7c0-131">而是采取尽可能保守的方法。</span><span class="sxs-lookup"><span data-stu-id="1e7c0-131">Instead, take the most conservative approach possible.</span></span> <span data-ttu-id="1e7c0-132">例如, 如果一个或两个条目标识符包含一个无效的**MAPIUID**, **CompareEntryIDs**可能会失败。</span><span class="sxs-lookup"><span data-stu-id="1e7c0-132">**CompareEntryIDs** might fail if, for example, one or both of the entry identifiers contains an invalid **MAPIUID**.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="1e7c0-133">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="1e7c0-133">MFCMAPI reference</span></span>

<span data-ttu-id="1e7c0-134">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="1e7c0-134">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="1e7c0-135">**文件**</span><span class="sxs-lookup"><span data-stu-id="1e7c0-135">**File**</span></span>|<span data-ttu-id="1e7c0-136">**函数**</span><span class="sxs-lookup"><span data-stu-id="1e7c0-136">**Function**</span></span>|<span data-ttu-id="1e7c0-137">**备注**</span><span class="sxs-lookup"><span data-stu-id="1e7c0-137">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1e7c0-138">BaseDialog</span><span class="sxs-lookup"><span data-stu-id="1e7c0-138">BaseDialog.cpp</span></span>  <br/> |<span data-ttu-id="1e7c0-139">CBaseDialog:: OnCompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="1e7c0-139">CBaseDialog::OnCompareEntryIDs</span></span>  <br/> |<span data-ttu-id="1e7c0-140">MFCMAPI 使用**IMsgStore:: CompareEntryIDs**方法来比较条目 id。</span><span class="sxs-lookup"><span data-stu-id="1e7c0-140">MFCMAPI uses the **IMsgStore::CompareEntryIDs** method to compare entry IDs.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1e7c0-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e7c0-141">See also</span></span>



[<span data-ttu-id="1e7c0-142">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="1e7c0-142">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="1e7c0-143">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="1e7c0-143">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)


[<span data-ttu-id="1e7c0-144">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="1e7c0-144">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

