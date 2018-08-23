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
ms.openlocfilehash: d28ce67c6b45f3d0b04d645946ea3f4b3a263c48
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578988"
---
# <a name="iexchangemodifytablegettable"></a><span data-ttu-id="25436-103">IExchangeModifyTable::GetTable</span><span class="sxs-lookup"><span data-stu-id="25436-103">IExchangeModifyTable::GetTable</span></span>

  
  
<span data-ttu-id="25436-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="25436-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="25436-105">返回一个 MAPI table 对象的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="25436-105">Returns a pointer to an interface for a MAPI table object.</span></span>
  
```cpp
HRESULT GetTable( 
  ULONG ulFlags, 
  LPMAPITABLE FAR * lppTable 
); 

```

## <a name="parameters"></a><span data-ttu-id="25436-106">参数</span><span class="sxs-lookup"><span data-stu-id="25436-106">Parameters</span></span>

 <span data-ttu-id="25436-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="25436-107">_ulFlags_</span></span>
  
> <span data-ttu-id="25436-108">[in]保留;必须为 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="25436-108">[in] Reserved; must be 0 (zero).</span></span>
    
<span data-ttu-id="25436-109">ACLTABLE_FREEBUSY</span><span class="sxs-lookup"><span data-stu-id="25436-109">ACLTABLE_FREEBUSY</span></span>
  
> <span data-ttu-id="25436-110">设置新的权限。</span><span class="sxs-lookup"><span data-stu-id="25436-110">Sets new rights.</span></span>
    
<span data-ttu-id="25436-111">frightsFreeBusyDetailed</span><span class="sxs-lookup"><span data-stu-id="25436-111">frightsFreeBusyDetailed</span></span>
  
> <span data-ttu-id="25436-112">当 ACLTABLE_FREEBUSY 传递时，提供了详细的显示新的忙/闲信息的权限。</span><span class="sxs-lookup"><span data-stu-id="25436-112">When ACLTABLE_FREEBUSY is passed, provides a detailed display of new free/busy rights.</span></span>
    
<span data-ttu-id="25436-113">frightsFreeBusySimple</span><span class="sxs-lookup"><span data-stu-id="25436-113">frightsFreeBusySimple</span></span>
  
> <span data-ttu-id="25436-114">当 ACLTABLE_FREEBUSY 传递时，提供新忙/闲信息的权限的简单的显示。</span><span class="sxs-lookup"><span data-stu-id="25436-114">When ACLTABLE_FREEBUSY is passed, provides a simple display of new free/busy rights.</span></span>
    
 <span data-ttu-id="25436-115">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="25436-115">_lppTable_</span></span>
  
> <span data-ttu-id="25436-116">[输出]指向[IMAPITable: IUnknown](imapitableiunknown.md)接口包含 table 对象。</span><span class="sxs-lookup"><span data-stu-id="25436-116">[out] Points to a [IMAPITable : IUnknown](imapitableiunknown.md) interface containing the table object.</span></span> 
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="25436-117">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="25436-117">MFCMAPI reference</span></span>

<span data-ttu-id="25436-118">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="25436-118">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="25436-119">**文件**</span><span class="sxs-lookup"><span data-stu-id="25436-119">**File**</span></span>|<span data-ttu-id="25436-120">**函数**</span><span class="sxs-lookup"><span data-stu-id="25436-120">**Function**</span></span>|<span data-ttu-id="25436-121">**Comment**</span><span class="sxs-lookup"><span data-stu-id="25436-121">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="25436-122">RulesDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="25436-122">RulesDlg.cpp</span></span>  <br/> |<span data-ttu-id="25436-123">CRulesDlg::OnRefreshView</span><span class="sxs-lookup"><span data-stu-id="25436-123">CRulesDlg::OnRefreshView</span></span>  <br/> |<span data-ttu-id="25436-124">MFCMAPI 使用**IExchangeModifyTable::GetTable**方法以获取 table 的规则。</span><span class="sxs-lookup"><span data-stu-id="25436-124">MFCMAPI uses the **IExchangeModifyTable::GetTable** method to get a table of rules.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="25436-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25436-125">See also</span></span>



[<span data-ttu-id="25436-126">IExchangeModifyTable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="25436-126">IExchangeModifyTable : IUnknown</span></span>](iexchangemodifytableiunknown.md)


[<span data-ttu-id="25436-127">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="25436-127">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

