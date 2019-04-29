---
title: ROWENTRY
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ROWENTRY
api_type:
- COM
ms.assetid: bd6c0d8e-68cc-4d60-9029-13ed81c816cd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 243ab1e926171ee66b95cfd8e969cd77e2b31faf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436032"
---
# <a name="rowentry"></a><span data-ttu-id="41b5c-103">ROWENTRY</span><span class="sxs-lookup"><span data-stu-id="41b5c-103">ROWENTRY</span></span>

<span data-ttu-id="41b5c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="41b5c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="41b5c-105">包含通过[IExchangeModifyTable](iexchangemodifytableiunknown.md)接口在表的行上执行的行和操作。</span><span class="sxs-lookup"><span data-stu-id="41b5c-105">Contains a row and the operation that is performed on that row in a table through the [IExchangeModifyTable](iexchangemodifytableiunknown.md) interface.</span></span> 
  
```cpp
typedef struct
{
  ULONG         ulRowFlags;
  ULONG         cValues;
  LPSPropValue  rgPropVals;
}  ROWENTRY, FAR * LPROWENTRY;
```

## <a name="members"></a><span data-ttu-id="41b5c-106">Members</span><span class="sxs-lookup"><span data-stu-id="41b5c-106">Members</span></span>

<span data-ttu-id="41b5c-107">**ulRowFlags**</span><span class="sxs-lookup"><span data-stu-id="41b5c-107">**ulRowFlags**</span></span>
  
> <span data-ttu-id="41b5c-108">要对数据执行以下操作之一:</span><span class="sxs-lookup"><span data-stu-id="41b5c-108">One of the following operations to be performed on the data:</span></span> 
    
  - <span data-ttu-id="41b5c-109">ROW_ADD: 将数据作为新行添加到表中。</span><span class="sxs-lookup"><span data-stu-id="41b5c-109">ROW_ADD: Add the data to the table as a new row.</span></span>
      
  - <span data-ttu-id="41b5c-110">ROW_MODIFY: 修改表中的此行。</span><span class="sxs-lookup"><span data-stu-id="41b5c-110">ROW_MODIFY: Modify this row in the table.</span></span>
      
  - <span data-ttu-id="41b5c-111">ROW_REMOVE: 从表中删除此行。</span><span class="sxs-lookup"><span data-stu-id="41b5c-111">ROW_REMOVE: Remove this row from the table.</span></span>
      
  - <span data-ttu-id="41b5c-112">ROW_EMPTY: 不要将行数据添加到表中。</span><span class="sxs-lookup"><span data-stu-id="41b5c-112">ROW_EMPTY: Do not add the row data to the table.</span></span> <span data-ttu-id="41b5c-113">(行是空的。)</span><span class="sxs-lookup"><span data-stu-id="41b5c-113">(The row is empty.)</span></span>
    
<span data-ttu-id="41b5c-114">**cValues**</span><span class="sxs-lookup"><span data-stu-id="41b5c-114">**cValues**</span></span>
  
> <span data-ttu-id="41b5c-115">**rgPropvals**中的属性值的数目。</span><span class="sxs-lookup"><span data-stu-id="41b5c-115">The number of property values in **rgPropvals**.</span></span>
    
<span data-ttu-id="41b5c-116">**rgPropVals**</span><span class="sxs-lookup"><span data-stu-id="41b5c-116">**rgPropVals**</span></span>
  
> <span data-ttu-id="41b5c-117">[SPropValue](spropvalue.md)结构的数组, 这些结构表示要插入到表中的列的值。</span><span class="sxs-lookup"><span data-stu-id="41b5c-117">An array of [SPropValue](spropvalue.md) structures representing the columns values to be inserted into the table.</span></span> 
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="41b5c-118">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="41b5c-118">MFCMAPI reference</span></span>

<span data-ttu-id="41b5c-119">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="41b5c-119">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="41b5c-120">**文件**</span><span class="sxs-lookup"><span data-stu-id="41b5c-120">**File**</span></span>|<span data-ttu-id="41b5c-121">**函数**</span><span class="sxs-lookup"><span data-stu-id="41b5c-121">**Function**</span></span>|<span data-ttu-id="41b5c-122">**备注**</span><span class="sxs-lookup"><span data-stu-id="41b5c-122">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="41b5c-123">RulesDlg</span><span class="sxs-lookup"><span data-stu-id="41b5c-123">RulesDlg.cpp</span></span>  <br/> |<span data-ttu-id="41b5c-124">CRulesDlg:: GetSelectedItems</span><span class="sxs-lookup"><span data-stu-id="41b5c-124">CRulesDlg::GetSelectedItems</span></span>  <br/> |<span data-ttu-id="41b5c-125">用于为后续**ModifyTable**操作生成选定规则的列表。</span><span class="sxs-lookup"><span data-stu-id="41b5c-125">Used to build a list of selected rules for subsequent **ModifyTable** actions.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="41b5c-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41b5c-126">See also</span></span>
  
- [<span data-ttu-id="41b5c-127">IExchangeModifyTable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="41b5c-127">IExchangeModifyTable : IUnknown</span></span>](iexchangemodifytableiunknown.md)
- [<span data-ttu-id="41b5c-128">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="41b5c-128">MAPI Structures</span></span>](mapi-structures.md)

