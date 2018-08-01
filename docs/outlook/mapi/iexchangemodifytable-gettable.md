---
title: IExchangeModifyTableGetTable
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IExchangeModifyTable.GetTable
api_type:
- COM
ms.assetid: 97df32c4-07c6-41f1-84e7-c6e87d396e34
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0cf9373c68d533908b857a4d8f1c0e71aa11846f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775311"
---
# <a name="iexchangemodifytablegettable"></a><span data-ttu-id="7af44-103">IExchangeModifyTable::GetTable</span><span class="sxs-lookup"><span data-stu-id="7af44-103">IExchangeModifyTable::GetTable</span></span>

  
  
<span data-ttu-id="7af44-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="7af44-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="7af44-105">返回一个 MAPI table 对象的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="7af44-105">Returns a pointer to an interface for a MAPI table object.</span></span>
  
```cpp
HRESULT GetTable( 
  ULONG ulFlags, 
  LPMAPITABLE FAR * lppTable 
); 

```

## <a name="parameters"></a><span data-ttu-id="7af44-106">参数</span><span class="sxs-lookup"><span data-stu-id="7af44-106">Parameters</span></span>

 <span data-ttu-id="7af44-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="7af44-107">_ulFlags_</span></span>
  
> <span data-ttu-id="7af44-108">[in]保留;必须为 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="7af44-108">[in] Reserved; must be 0 (zero).</span></span>
    
<span data-ttu-id="7af44-109">ACLTABLE_FREEBUSY</span><span class="sxs-lookup"><span data-stu-id="7af44-109">ACLTABLE_FREEBUSY</span></span>
  
> <span data-ttu-id="7af44-110">设置新的权限。</span><span class="sxs-lookup"><span data-stu-id="7af44-110">Sets new rights.</span></span>
    
<span data-ttu-id="7af44-111">frightsFreeBusyDetailed</span><span class="sxs-lookup"><span data-stu-id="7af44-111">frightsFreeBusyDetailed</span></span>
  
> <span data-ttu-id="7af44-112">当 ACLTABLE_FREEBUSY 传递时，提供了详细的显示新的忙/闲信息的权限。</span><span class="sxs-lookup"><span data-stu-id="7af44-112">When ACLTABLE_FREEBUSY is passed, provides a detailed display of new free/busy rights.</span></span>
    
<span data-ttu-id="7af44-113">frightsFreeBusySimple</span><span class="sxs-lookup"><span data-stu-id="7af44-113">frightsFreeBusySimple</span></span>
  
> <span data-ttu-id="7af44-114">当 ACLTABLE_FREEBUSY 传递时，提供新忙/闲信息的权限的简单的显示。</span><span class="sxs-lookup"><span data-stu-id="7af44-114">When ACLTABLE_FREEBUSY is passed, provides a simple display of new free/busy rights.</span></span>
    
 <span data-ttu-id="7af44-115">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="7af44-115">_lppTable_</span></span>
  
> <span data-ttu-id="7af44-116">[输出]指向[IMAPITable: IUnknown](imapitableiunknown.md)接口包含 table 对象。</span><span class="sxs-lookup"><span data-stu-id="7af44-116">[out] Points to a [IMAPITable : IUnknown](imapitableiunknown.md) interface containing the table object.</span></span> 
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="7af44-117">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="7af44-117">MFCMAPI reference</span></span>

<span data-ttu-id="7af44-118">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="7af44-118">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="7af44-119">**文件**</span><span class="sxs-lookup"><span data-stu-id="7af44-119">**File**</span></span>|<span data-ttu-id="7af44-120">**函数**</span><span class="sxs-lookup"><span data-stu-id="7af44-120">**Function**</span></span>|<span data-ttu-id="7af44-121">**Comment**</span><span class="sxs-lookup"><span data-stu-id="7af44-121">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7af44-122">RulesDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="7af44-122">RulesDlg.cpp</span></span>  <br/> |<span data-ttu-id="7af44-123">CRulesDlg::OnRefreshView</span><span class="sxs-lookup"><span data-stu-id="7af44-123">CRulesDlg::OnRefreshView</span></span>  <br/> |<span data-ttu-id="7af44-124">MFCMAPI 使用**IExchangeModifyTable::GetTable**方法以获取 table 的规则。</span><span class="sxs-lookup"><span data-stu-id="7af44-124">MFCMAPI uses the **IExchangeModifyTable::GetTable** method to get a table of rules.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="7af44-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7af44-125">See also</span></span>



[<span data-ttu-id="7af44-126">IExchangeModifyTable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="7af44-126">IExchangeModifyTable : IUnknown</span></span>](iexchangemodifytableiunknown.md)


[<span data-ttu-id="7af44-127">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="7af44-127">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

