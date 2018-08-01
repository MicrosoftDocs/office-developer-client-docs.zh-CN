---
title: IExchangeModifyTableModifyTable
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IExchangeModifyTable.ModifyTable
api_type:
- COM
ms.assetid: b9a745cc-260d-4a1c-896e-6a038ab3cfb9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9e7f24fb4b444f63b6277d1844a7948f5ab0c590
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775299"
---
# <a name="iexchangemodifytablemodifytable"></a><span data-ttu-id="19ab7-103">IExchangeModifyTable::ModifyTable</span><span class="sxs-lookup"><span data-stu-id="19ab7-103">IExchangeModifyTable::ModifyTable</span></span>

  
  
<span data-ttu-id="19ab7-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="19ab7-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="19ab7-105">更新 MAPI table 对象。</span><span class="sxs-lookup"><span data-stu-id="19ab7-105">Updates a MAPI table object.</span></span>
  
```cpp
HRESULT ModifyTable( 
  ULONG ulFlags, 
  LPROWLIST lpMods 
); 

```

## <a name="parameters"></a><span data-ttu-id="19ab7-106">参数</span><span class="sxs-lookup"><span data-stu-id="19ab7-106">Parameters</span></span>

 <span data-ttu-id="19ab7-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="19ab7-107">_ulFlags_</span></span>
  
> <span data-ttu-id="19ab7-108">[in]使用下列值之一：</span><span class="sxs-lookup"><span data-stu-id="19ab7-108">[in] Use one of the following values:</span></span> 
    
<span data-ttu-id="19ab7-109">0（零）</span><span class="sxs-lookup"><span data-stu-id="19ab7-109">0 (zero)</span></span>
  
> <span data-ttu-id="19ab7-110">使用[ROWENTRY](rowentry.md)结构的**ulRowFlags**成员的值。</span><span class="sxs-lookup"><span data-stu-id="19ab7-110">Use the value of the **ulRowFlags** member of the [ROWENTRY](rowentry.md) structure.</span></span> 
    
<span data-ttu-id="19ab7-111">ACLTABLE_FREEBUSY</span><span class="sxs-lookup"><span data-stu-id="19ab7-111">ACLTABLE_FREEBUSY</span></span>
  
> <span data-ttu-id="19ab7-112">设置新的权限。</span><span class="sxs-lookup"><span data-stu-id="19ab7-112">Sets new rights.</span></span>
    
<span data-ttu-id="19ab7-113">frightsFreeBusyDetailed</span><span class="sxs-lookup"><span data-stu-id="19ab7-113">frightsFreeBusyDetailed</span></span>
  
> <span data-ttu-id="19ab7-114">当 ACLTABLE_FREEBUSY 传递时，提供了详细的显示新的忙/闲信息的权限。</span><span class="sxs-lookup"><span data-stu-id="19ab7-114">When ACLTABLE_FREEBUSY is passed, provides a detailed display of new free/busy rights.</span></span>
    
<span data-ttu-id="19ab7-115">frightsFreeBusySimple</span><span class="sxs-lookup"><span data-stu-id="19ab7-115">frightsFreeBusySimple</span></span>
  
> <span data-ttu-id="19ab7-116">当 ACLTABLE_FREEBUSY 传递时，提供新忙/闲信息的权限的简单的显示。</span><span class="sxs-lookup"><span data-stu-id="19ab7-116">When ACLTABLE_FREEBUSY is passed, provides a simple display of new free/busy rights.</span></span>
    
<span data-ttu-id="19ab7-117">ROWLIST_REPLACE</span><span class="sxs-lookup"><span data-stu-id="19ab7-117">ROWLIST_REPLACE</span></span>
  
> <span data-ttu-id="19ab7-118">将表中的所有行。</span><span class="sxs-lookup"><span data-stu-id="19ab7-118">Replace all the rows in the table.</span></span>
    
 <span data-ttu-id="19ab7-119">_lpMods_</span><span class="sxs-lookup"><span data-stu-id="19ab7-119">_lpMods_</span></span>
  
> <span data-ttu-id="19ab7-120">[in]指向包含 table 对象的属性的[ROWLIST](rowlist.md)结构。</span><span class="sxs-lookup"><span data-stu-id="19ab7-120">[in] Points to a [ROWLIST](rowlist.md) structure containing the properties for the table object.</span></span> 
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="19ab7-121">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="19ab7-121">MFCMAPI reference</span></span>

<span data-ttu-id="19ab7-122">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="19ab7-122">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="19ab7-123">**文件**</span><span class="sxs-lookup"><span data-stu-id="19ab7-123">**File**</span></span>|<span data-ttu-id="19ab7-124">**函数**</span><span class="sxs-lookup"><span data-stu-id="19ab7-124">**Function**</span></span>|<span data-ttu-id="19ab7-125">**Comment**</span><span class="sxs-lookup"><span data-stu-id="19ab7-125">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="19ab7-126">RulesDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="19ab7-126">RulesDlg.cpp</span></span>  <br/> |<span data-ttu-id="19ab7-127">CRulesDlg::OnModifySelectedItem</span><span class="sxs-lookup"><span data-stu-id="19ab7-127">CRulesDlg::OnModifySelectedItem</span></span>  <br/> |<span data-ttu-id="19ab7-128">MFCMAPI 使用**IExchangeModifyTable::ModifyTable**方法修改的规则写回表中的规则。</span><span class="sxs-lookup"><span data-stu-id="19ab7-128">MFCMAPI uses the **IExchangeModifyTable::ModifyTable** method to write a modified rule back to the table of rules.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="19ab7-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19ab7-129">See also</span></span>



[<span data-ttu-id="19ab7-130">IExchangeModifyTable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="19ab7-130">IExchangeModifyTable : IUnknown</span></span>](iexchangemodifytableiunknown.md)
  
[<span data-ttu-id="19ab7-131">ROWENTRY</span><span class="sxs-lookup"><span data-stu-id="19ab7-131">ROWENTRY</span></span>](rowentry.md)
  
[<span data-ttu-id="19ab7-132">ROWLIST</span><span class="sxs-lookup"><span data-stu-id="19ab7-132">ROWLIST</span></span>](rowlist.md)


[<span data-ttu-id="19ab7-133">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="19ab7-133">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

