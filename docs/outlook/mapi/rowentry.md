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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: f8ac73b1977886208290285fec2d1bd0de1b4f92
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778658"
---
# <a name="rowentry"></a><span data-ttu-id="75c27-103">ROWENTRY</span><span class="sxs-lookup"><span data-stu-id="75c27-103">ROWENTRY</span></span>

<span data-ttu-id="75c27-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="75c27-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="75c27-105">包含的行和通过[IExchangeModifyTable](iexchangemodifytableiunknown.md)界面表中的行执行的操作。</span><span class="sxs-lookup"><span data-stu-id="75c27-105">Contains a row and the operation that is performed on that row in a table through the [IExchangeModifyTable](iexchangemodifytableiunknown.md) interface.</span></span> 
  
```cpp
typedef struct
{
  ULONG         ulRowFlags;
  ULONG         cValues;
  LPSPropValue  rgPropVals;
}  ROWENTRY, FAR * LPROWENTRY;
```

## <a name="members"></a><span data-ttu-id="75c27-106">成员</span><span class="sxs-lookup"><span data-stu-id="75c27-106">Members</span></span>

<span data-ttu-id="75c27-107">**ulRowFlags**</span><span class="sxs-lookup"><span data-stu-id="75c27-107">**ulRowFlags**</span></span>
  
> <span data-ttu-id="75c27-108">对数据执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="75c27-108">One of the following operations to be performed on the data:</span></span> 
    
  - <span data-ttu-id="75c27-109">ROW_ADD： 将数据添加到表作为新行。</span><span class="sxs-lookup"><span data-stu-id="75c27-109">ROW_ADD: Add the data to the table as a new row.</span></span>
      
  - <span data-ttu-id="75c27-110">ROW_MODIFY： 修改此表中的行。</span><span class="sxs-lookup"><span data-stu-id="75c27-110">ROW_MODIFY: Modify this row in the table.</span></span>
      
  - <span data-ttu-id="75c27-111">ROW_REMOVE： 从表中删除此行。</span><span class="sxs-lookup"><span data-stu-id="75c27-111">ROW_REMOVE: Remove this row from the table.</span></span>
      
  - <span data-ttu-id="75c27-112">ROW_EMPTY： 不要向表中添加行数据。</span><span class="sxs-lookup"><span data-stu-id="75c27-112">ROW_EMPTY: Do not add the row data to the table.</span></span> <span data-ttu-id="75c27-113">（行为空。）</span><span class="sxs-lookup"><span data-stu-id="75c27-113">(The row is empty.)</span></span>
    
<span data-ttu-id="75c27-114">**cValues**</span><span class="sxs-lookup"><span data-stu-id="75c27-114">**cValues**</span></span>
  
> <span data-ttu-id="75c27-115">**RgPropvals**中的属性值的数目。</span><span class="sxs-lookup"><span data-stu-id="75c27-115">The number of property values in **rgPropvals**.</span></span>
    
<span data-ttu-id="75c27-116">**rgPropVals**</span><span class="sxs-lookup"><span data-stu-id="75c27-116">**rgPropVals**</span></span>
  
> <span data-ttu-id="75c27-117">[SPropValue](spropvalue.md)结构表示要插入到表的列值的数组。</span><span class="sxs-lookup"><span data-stu-id="75c27-117">An array of [SPropValue](spropvalue.md) structures representing the columns values to be inserted into the table.</span></span> 
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="75c27-118">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="75c27-118">MFCMAPI reference</span></span>

<span data-ttu-id="75c27-119">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="75c27-119">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="75c27-120">**文件**</span><span class="sxs-lookup"><span data-stu-id="75c27-120">**File**</span></span>|<span data-ttu-id="75c27-121">**函数**</span><span class="sxs-lookup"><span data-stu-id="75c27-121">**Function**</span></span>|<span data-ttu-id="75c27-122">**Comment**</span><span class="sxs-lookup"><span data-stu-id="75c27-122">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="75c27-123">RulesDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="75c27-123">RulesDlg.cpp</span></span>  <br/> |<span data-ttu-id="75c27-124">CRulesDlg::GetSelectedItems</span><span class="sxs-lookup"><span data-stu-id="75c27-124">CRulesDlg::GetSelectedItems</span></span>  <br/> |<span data-ttu-id="75c27-125">用于生成的后续**ModifyTable**操作选定的规则列表。</span><span class="sxs-lookup"><span data-stu-id="75c27-125">Used to build a list of selected rules for subsequent **ModifyTable** actions.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="75c27-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75c27-126">See also</span></span>
  
- [<span data-ttu-id="75c27-127">IExchangeModifyTable: IUnknown</span><span class="sxs-lookup"><span data-stu-id="75c27-127">IExchangeModifyTable : IUnknown</span></span>](iexchangemodifytableiunknown.md)
- [<span data-ttu-id="75c27-128">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="75c27-128">MAPI Structures</span></span>](mapi-structures.md)

