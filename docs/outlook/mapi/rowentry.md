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
ms.openlocfilehash: f8ac73b1977886208290285fec2d1bd0de1b4f92
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778658"
---
# <a name="rowentry"></a><span data-ttu-id="59f42-103">ROWENTRY</span><span class="sxs-lookup"><span data-stu-id="59f42-103">ROWENTRY</span></span>

<span data-ttu-id="59f42-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="59f42-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="59f42-105">包含的行和通过[IExchangeModifyTable](iexchangemodifytableiunknown.md)界面表中的行执行的操作。</span><span class="sxs-lookup"><span data-stu-id="59f42-105">Contains a row and the operation that is performed on that row in a table through the [IExchangeModifyTable](iexchangemodifytableiunknown.md) interface.</span></span> 
  
```cpp
typedef struct
{
  ULONG         ulRowFlags;
  ULONG         cValues;
  LPSPropValue  rgPropVals;
}  ROWENTRY, FAR * LPROWENTRY;
```

## <a name="members"></a><span data-ttu-id="59f42-106">Members</span><span class="sxs-lookup"><span data-stu-id="59f42-106">Members</span></span>

<span data-ttu-id="59f42-107">**ulRowFlags**</span><span class="sxs-lookup"><span data-stu-id="59f42-107">**ulRowFlags**</span></span>
  
> <span data-ttu-id="59f42-108">对数据执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="59f42-108">One of the following operations to be performed on the data:</span></span> 
    
  - <span data-ttu-id="59f42-109">ROW_ADD： 将数据添加到表作为新行。</span><span class="sxs-lookup"><span data-stu-id="59f42-109">ROW_ADD: Add the data to the table as a new row.</span></span>
      
  - <span data-ttu-id="59f42-110">ROW_MODIFY： 修改此表中的行。</span><span class="sxs-lookup"><span data-stu-id="59f42-110">ROW_MODIFY: Modify this row in the table.</span></span>
      
  - <span data-ttu-id="59f42-111">ROW_REMOVE： 从表中删除此行。</span><span class="sxs-lookup"><span data-stu-id="59f42-111">ROW_REMOVE: Remove this row from the table.</span></span>
      
  - <span data-ttu-id="59f42-112">ROW_EMPTY： 不要向表中添加行数据。</span><span class="sxs-lookup"><span data-stu-id="59f42-112">ROW_EMPTY: Do not add the row data to the table.</span></span> <span data-ttu-id="59f42-113">（行为空。）</span><span class="sxs-lookup"><span data-stu-id="59f42-113">(The row is empty.)</span></span>
    
<span data-ttu-id="59f42-114">**cValues**</span><span class="sxs-lookup"><span data-stu-id="59f42-114">**cValues**</span></span>
  
> <span data-ttu-id="59f42-115">**RgPropvals**中的属性值的数目。</span><span class="sxs-lookup"><span data-stu-id="59f42-115">The number of property values in **rgPropvals**.</span></span>
    
<span data-ttu-id="59f42-116">**rgPropVals**</span><span class="sxs-lookup"><span data-stu-id="59f42-116">**rgPropVals**</span></span>
  
> <span data-ttu-id="59f42-117">[SPropValue](spropvalue.md)结构表示要插入到表的列值的数组。</span><span class="sxs-lookup"><span data-stu-id="59f42-117">An array of [SPropValue](spropvalue.md) structures representing the columns values to be inserted into the table.</span></span> 
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="59f42-118">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="59f42-118">MFCMAPI reference</span></span>

<span data-ttu-id="59f42-119">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="59f42-119">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="59f42-120">**文件**</span><span class="sxs-lookup"><span data-stu-id="59f42-120">**File**</span></span>|<span data-ttu-id="59f42-121">**函数**</span><span class="sxs-lookup"><span data-stu-id="59f42-121">**Function**</span></span>|<span data-ttu-id="59f42-122">**Comment**</span><span class="sxs-lookup"><span data-stu-id="59f42-122">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="59f42-123">RulesDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="59f42-123">RulesDlg.cpp</span></span>  <br/> |<span data-ttu-id="59f42-124">CRulesDlg::GetSelectedItems</span><span class="sxs-lookup"><span data-stu-id="59f42-124">CRulesDlg::GetSelectedItems</span></span>  <br/> |<span data-ttu-id="59f42-125">用于生成的后续**ModifyTable**操作选定的规则列表。</span><span class="sxs-lookup"><span data-stu-id="59f42-125">Used to build a list of selected rules for subsequent **ModifyTable** actions.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="59f42-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59f42-126">See also</span></span>
  
- [<span data-ttu-id="59f42-127">IExchangeModifyTable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="59f42-127">IExchangeModifyTable : IUnknown</span></span>](iexchangemodifytableiunknown.md)
- [<span data-ttu-id="59f42-128">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="59f42-128">MAPI Structures</span></span>](mapi-structures.md)

