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
ms.openlocfilehash: 87c60f424e08eea011bb643041196ca9445a3aa1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436242"
---
# <a name="iexchangemodifytablegettable"></a><span data-ttu-id="ed917-103">IExchangeModifyTable::GetTable</span><span class="sxs-lookup"><span data-stu-id="ed917-103">IExchangeModifyTable::GetTable</span></span>

  
  
<span data-ttu-id="ed917-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ed917-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ed917-105">返回指向 MAPI 表对象的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="ed917-105">Returns a pointer to an interface for a MAPI table object.</span></span>
  
```cpp
HRESULT GetTable( 
  ULONG ulFlags, 
  LPMAPITABLE FAR * lppTable 
); 

```

## <a name="parameters"></a><span data-ttu-id="ed917-106">参数</span><span class="sxs-lookup"><span data-stu-id="ed917-106">Parameters</span></span>

 <span data-ttu-id="ed917-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ed917-107">_ulFlags_</span></span>
  
> <span data-ttu-id="ed917-108">实时保留必须为 0 (零)。</span><span class="sxs-lookup"><span data-stu-id="ed917-108">[in] Reserved; must be 0 (zero).</span></span>
    
<span data-ttu-id="ed917-109">ACLTABLE_FREEBUSY</span><span class="sxs-lookup"><span data-stu-id="ed917-109">ACLTABLE_FREEBUSY</span></span>
  
> <span data-ttu-id="ed917-110">设置新权限。</span><span class="sxs-lookup"><span data-stu-id="ed917-110">Sets new rights.</span></span>
    
<span data-ttu-id="ed917-111">frightsFreeBusyDetailed</span><span class="sxs-lookup"><span data-stu-id="ed917-111">frightsFreeBusyDetailed</span></span>
  
> <span data-ttu-id="ed917-112">当传递 ACLTABLE_FREEBUSY 时, 提供新的忙/闲权限的详细显示。</span><span class="sxs-lookup"><span data-stu-id="ed917-112">When ACLTABLE_FREEBUSY is passed, provides a detailed display of new free/busy rights.</span></span>
    
<span data-ttu-id="ed917-113">frightsFreeBusySimple</span><span class="sxs-lookup"><span data-stu-id="ed917-113">frightsFreeBusySimple</span></span>
  
> <span data-ttu-id="ed917-114">当传递 ACLTABLE_FREEBUSY 时, 将提供新的忙/闲权限的简单显示。</span><span class="sxs-lookup"><span data-stu-id="ed917-114">When ACLTABLE_FREEBUSY is passed, provides a simple display of new free/busy rights.</span></span>
    
 <span data-ttu-id="ed917-115">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="ed917-115">_lppTable_</span></span>
  
> <span data-ttu-id="ed917-116">排除指向包含 table 对象的[IMAPITable: IUnknown](imapitableiunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="ed917-116">[out] Points to a [IMAPITable : IUnknown](imapitableiunknown.md) interface containing the table object.</span></span> 
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="ed917-117">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="ed917-117">MFCMAPI reference</span></span>

<span data-ttu-id="ed917-118">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="ed917-118">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="ed917-119">**文件**</span><span class="sxs-lookup"><span data-stu-id="ed917-119">**File**</span></span>|<span data-ttu-id="ed917-120">**函数**</span><span class="sxs-lookup"><span data-stu-id="ed917-120">**Function**</span></span>|<span data-ttu-id="ed917-121">**备注**</span><span class="sxs-lookup"><span data-stu-id="ed917-121">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ed917-122">RulesDlg</span><span class="sxs-lookup"><span data-stu-id="ed917-122">RulesDlg.cpp</span></span>  <br/> |<span data-ttu-id="ed917-123">CRulesDlg:: OnRefreshView</span><span class="sxs-lookup"><span data-stu-id="ed917-123">CRulesDlg::OnRefreshView</span></span>  <br/> |<span data-ttu-id="ed917-124">MFCMAPI 使用**IExchangeModifyTable:: GetTable**方法获取规则表。</span><span class="sxs-lookup"><span data-stu-id="ed917-124">MFCMAPI uses the **IExchangeModifyTable::GetTable** method to get a table of rules.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="ed917-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed917-125">See also</span></span>



[<span data-ttu-id="ed917-126">IExchangeModifyTable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ed917-126">IExchangeModifyTable : IUnknown</span></span>](iexchangemodifytableiunknown.md)


[<span data-ttu-id="ed917-127">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="ed917-127">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

