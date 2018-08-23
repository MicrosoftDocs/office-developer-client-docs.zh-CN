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
ms.openlocfilehash: fb0bfaba1ca0a0d7d34096b3b0b1db9863207097
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576265"
---
# <a name="rowentry"></a><span data-ttu-id="20c1b-103">ROWENTRY</span><span class="sxs-lookup"><span data-stu-id="20c1b-103">ROWENTRY</span></span>

<span data-ttu-id="20c1b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="20c1b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="20c1b-105">包含的行和通过[IExchangeModifyTable](iexchangemodifytableiunknown.md)界面表中的行执行的操作。</span><span class="sxs-lookup"><span data-stu-id="20c1b-105">Contains a row and the operation that is performed on that row in a table through the [IExchangeModifyTable](iexchangemodifytableiunknown.md) interface.</span></span> 
  
```cpp
typedef struct
{
  ULONG         ulRowFlags;
  ULONG         cValues;
  LPSPropValue  rgPropVals;
}  ROWENTRY, FAR * LPROWENTRY;
```

## <a name="members"></a><span data-ttu-id="20c1b-106">Members</span><span class="sxs-lookup"><span data-stu-id="20c1b-106">Members</span></span>

<span data-ttu-id="20c1b-107">**ulRowFlags**</span><span class="sxs-lookup"><span data-stu-id="20c1b-107">**ulRowFlags**</span></span>
  
> <span data-ttu-id="20c1b-108">对数据执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="20c1b-108">One of the following operations to be performed on the data:</span></span> 
    
  - <span data-ttu-id="20c1b-109">ROW_ADD： 将数据添加到表作为新行。</span><span class="sxs-lookup"><span data-stu-id="20c1b-109">ROW_ADD: Add the data to the table as a new row.</span></span>
      
  - <span data-ttu-id="20c1b-110">ROW_MODIFY： 修改此表中的行。</span><span class="sxs-lookup"><span data-stu-id="20c1b-110">ROW_MODIFY: Modify this row in the table.</span></span>
      
  - <span data-ttu-id="20c1b-111">ROW_REMOVE： 从表中删除此行。</span><span class="sxs-lookup"><span data-stu-id="20c1b-111">ROW_REMOVE: Remove this row from the table.</span></span>
      
  - <span data-ttu-id="20c1b-112">ROW_EMPTY： 不要向表中添加行数据。</span><span class="sxs-lookup"><span data-stu-id="20c1b-112">ROW_EMPTY: Do not add the row data to the table.</span></span> <span data-ttu-id="20c1b-113">（行为空。）</span><span class="sxs-lookup"><span data-stu-id="20c1b-113">(The row is empty.)</span></span>
    
<span data-ttu-id="20c1b-114">**cValues**</span><span class="sxs-lookup"><span data-stu-id="20c1b-114">**cValues**</span></span>
  
> <span data-ttu-id="20c1b-115">**RgPropvals**中的属性值的数目。</span><span class="sxs-lookup"><span data-stu-id="20c1b-115">The number of property values in **rgPropvals**.</span></span>
    
<span data-ttu-id="20c1b-116">**rgPropVals**</span><span class="sxs-lookup"><span data-stu-id="20c1b-116">**rgPropVals**</span></span>
  
> <span data-ttu-id="20c1b-117">[SPropValue](spropvalue.md)结构表示要插入到表的列值的数组。</span><span class="sxs-lookup"><span data-stu-id="20c1b-117">An array of [SPropValue](spropvalue.md) structures representing the columns values to be inserted into the table.</span></span> 
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="20c1b-118">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="20c1b-118">MFCMAPI reference</span></span>

<span data-ttu-id="20c1b-119">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="20c1b-119">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="20c1b-120">**文件**</span><span class="sxs-lookup"><span data-stu-id="20c1b-120">**File**</span></span>|<span data-ttu-id="20c1b-121">**函数**</span><span class="sxs-lookup"><span data-stu-id="20c1b-121">**Function**</span></span>|<span data-ttu-id="20c1b-122">**Comment**</span><span class="sxs-lookup"><span data-stu-id="20c1b-122">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="20c1b-123">RulesDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="20c1b-123">RulesDlg.cpp</span></span>  <br/> |<span data-ttu-id="20c1b-124">CRulesDlg::GetSelectedItems</span><span class="sxs-lookup"><span data-stu-id="20c1b-124">CRulesDlg::GetSelectedItems</span></span>  <br/> |<span data-ttu-id="20c1b-125">用于生成的后续**ModifyTable**操作选定的规则列表。</span><span class="sxs-lookup"><span data-stu-id="20c1b-125">Used to build a list of selected rules for subsequent **ModifyTable** actions.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="20c1b-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20c1b-126">See also</span></span>
  
- [<span data-ttu-id="20c1b-127">IExchangeModifyTable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="20c1b-127">IExchangeModifyTable : IUnknown</span></span>](iexchangemodifytableiunknown.md)
- [<span data-ttu-id="20c1b-128">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="20c1b-128">MAPI Structures</span></span>](mapi-structures.md)

