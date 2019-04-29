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
ms.openlocfilehash: 46bb9b2cc1a4d54807d6929b4e1439b58fb3a531
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418174"
---
# <a name="iexchangemodifytablemodifytable"></a><span data-ttu-id="7472a-103">IExchangeModifyTable::ModifyTable</span><span class="sxs-lookup"><span data-stu-id="7472a-103">IExchangeModifyTable::ModifyTable</span></span>

  
  
<span data-ttu-id="7472a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7472a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7472a-105">更新 MAPI 表对象。</span><span class="sxs-lookup"><span data-stu-id="7472a-105">Updates a MAPI table object.</span></span>
  
```cpp
HRESULT ModifyTable( 
  ULONG ulFlags, 
  LPROWLIST lpMods 
); 

```

## <a name="parameters"></a><span data-ttu-id="7472a-106">参数</span><span class="sxs-lookup"><span data-stu-id="7472a-106">Parameters</span></span>

 <span data-ttu-id="7472a-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="7472a-107">_ulFlags_</span></span>
  
> <span data-ttu-id="7472a-108">实时使用下列值之一:</span><span class="sxs-lookup"><span data-stu-id="7472a-108">[in] Use one of the following values:</span></span> 
    
<span data-ttu-id="7472a-109">0（零）</span><span class="sxs-lookup"><span data-stu-id="7472a-109">0 (zero)</span></span>
  
> <span data-ttu-id="7472a-110">使用[ROWENTRY](rowentry.md)结构的**ulRowFlags**成员的值。</span><span class="sxs-lookup"><span data-stu-id="7472a-110">Use the value of the **ulRowFlags** member of the [ROWENTRY](rowentry.md) structure.</span></span> 
    
<span data-ttu-id="7472a-111">ACLTABLE_FREEBUSY</span><span class="sxs-lookup"><span data-stu-id="7472a-111">ACLTABLE_FREEBUSY</span></span>
  
> <span data-ttu-id="7472a-112">设置新权限。</span><span class="sxs-lookup"><span data-stu-id="7472a-112">Sets new rights.</span></span>
    
<span data-ttu-id="7472a-113">frightsFreeBusyDetailed</span><span class="sxs-lookup"><span data-stu-id="7472a-113">frightsFreeBusyDetailed</span></span>
  
> <span data-ttu-id="7472a-114">当传递 ACLTABLE_FREEBUSY 时, 提供新的忙/闲权限的详细显示。</span><span class="sxs-lookup"><span data-stu-id="7472a-114">When ACLTABLE_FREEBUSY is passed, provides a detailed display of new free/busy rights.</span></span>
    
<span data-ttu-id="7472a-115">frightsFreeBusySimple</span><span class="sxs-lookup"><span data-stu-id="7472a-115">frightsFreeBusySimple</span></span>
  
> <span data-ttu-id="7472a-116">当传递 ACLTABLE_FREEBUSY 时, 将提供新的忙/闲权限的简单显示。</span><span class="sxs-lookup"><span data-stu-id="7472a-116">When ACLTABLE_FREEBUSY is passed, provides a simple display of new free/busy rights.</span></span>
    
<span data-ttu-id="7472a-117">ROWLIST_REPLACE</span><span class="sxs-lookup"><span data-stu-id="7472a-117">ROWLIST_REPLACE</span></span>
  
> <span data-ttu-id="7472a-118">替换表中的所有行。</span><span class="sxs-lookup"><span data-stu-id="7472a-118">Replace all the rows in the table.</span></span>
    
 <span data-ttu-id="7472a-119">_lpMods_</span><span class="sxs-lookup"><span data-stu-id="7472a-119">_lpMods_</span></span>
  
> <span data-ttu-id="7472a-120">实时指向一个[ROWLIST](rowlist.md)结构, 其中包含 table 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="7472a-120">[in] Points to a [ROWLIST](rowlist.md) structure containing the properties for the table object.</span></span> 
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="7472a-121">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="7472a-121">MFCMAPI reference</span></span>

<span data-ttu-id="7472a-122">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="7472a-122">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="7472a-123">**文件**</span><span class="sxs-lookup"><span data-stu-id="7472a-123">**File**</span></span>|<span data-ttu-id="7472a-124">**函数**</span><span class="sxs-lookup"><span data-stu-id="7472a-124">**Function**</span></span>|<span data-ttu-id="7472a-125">**备注**</span><span class="sxs-lookup"><span data-stu-id="7472a-125">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7472a-126">RulesDlg</span><span class="sxs-lookup"><span data-stu-id="7472a-126">RulesDlg.cpp</span></span>  <br/> |<span data-ttu-id="7472a-127">CRulesDlg:: OnModifySelectedItem</span><span class="sxs-lookup"><span data-stu-id="7472a-127">CRulesDlg::OnModifySelectedItem</span></span>  <br/> |<span data-ttu-id="7472a-128">MFCMAPI 使用**IExchangeModifyTable:: ModifyTable**方法将修改的规则写回到规则表中。</span><span class="sxs-lookup"><span data-stu-id="7472a-128">MFCMAPI uses the **IExchangeModifyTable::ModifyTable** method to write a modified rule back to the table of rules.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="7472a-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7472a-129">See also</span></span>



[<span data-ttu-id="7472a-130">IExchangeModifyTable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="7472a-130">IExchangeModifyTable : IUnknown</span></span>](iexchangemodifytableiunknown.md)
  
[<span data-ttu-id="7472a-131">ROWENTRY</span><span class="sxs-lookup"><span data-stu-id="7472a-131">ROWENTRY</span></span>](rowentry.md)
  
[<span data-ttu-id="7472a-132">ROWLIST</span><span class="sxs-lookup"><span data-stu-id="7472a-132">ROWLIST</span></span>](rowlist.md)


[<span data-ttu-id="7472a-133">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="7472a-133">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

