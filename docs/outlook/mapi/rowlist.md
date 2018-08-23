---
title: ROWLIST
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ROWLIST
api_type:
- COM
ms.assetid: ce0be0d5-4962-4d53-828f-c93d1c5aae32
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4cbaf08c58a98be45ad33aebb8f230fb53c234f3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577658"
---
# <a name="rowlist"></a><span data-ttu-id="881eb-103">ROWLIST</span><span class="sxs-lookup"><span data-stu-id="881eb-103">ROWLIST</span></span>

  
  
<span data-ttu-id="881eb-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="881eb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="881eb-105">包含一个表示行和通过[IExchangeModifyTable](iexchangemodifytableiunknown.md)界面表格中的行上执行的操作的[ROWENTRY](rowentry.md)结构数组。</span><span class="sxs-lookup"><span data-stu-id="881eb-105">Contains an array of [ROWENTRY](rowentry.md) structures representing rows and the operations that are performed on those rows in a table through the [IExchangeModifyTable](iexchangemodifytableiunknown.md) interface.</span></span> 
  
```cpp
typedef struct
{
  ULONG     cEntries;
  ROWENTRY  aEntries[MAPI_DIM];
}  ROWLIST, FAR * LPROWLIST;

```

## <a name="members"></a><span data-ttu-id="881eb-106">Members</span><span class="sxs-lookup"><span data-stu-id="881eb-106">Members</span></span>

 <span data-ttu-id="881eb-107">**cEntries**</span><span class="sxs-lookup"><span data-stu-id="881eb-107">**cEntries**</span></span>
  
> <span data-ttu-id="881eb-108">指定由**aEntries**成员的数组中的条目的计数。</span><span class="sxs-lookup"><span data-stu-id="881eb-108">Count of entries in the array specified by the **aEntries** member.</span></span> 
    
 <span data-ttu-id="881eb-109">**aEntries [MAPI_DIM]**</span><span class="sxs-lookup"><span data-stu-id="881eb-109">**aEntries[MAPI_DIM]**</span></span>
  
> <span data-ttu-id="881eb-110">**ROWENTRY**结构数组，其中包含的行和表中的行上执行的操作。</span><span class="sxs-lookup"><span data-stu-id="881eb-110">Array of **ROWENTRY** structures that contains the rows and the operations that are performed on those rows in the table.</span></span> 
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="881eb-111">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="881eb-111">MFCMAPI reference</span></span>

<span data-ttu-id="881eb-112">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="881eb-112">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="881eb-113">**文件**</span><span class="sxs-lookup"><span data-stu-id="881eb-113">**File**</span></span>|<span data-ttu-id="881eb-114">**函数**</span><span class="sxs-lookup"><span data-stu-id="881eb-114">**Function**</span></span>|<span data-ttu-id="881eb-115">**Comment**</span><span class="sxs-lookup"><span data-stu-id="881eb-115">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="881eb-116">RulesDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="881eb-116">RulesDlg.cpp</span></span>  <br/> |<span data-ttu-id="881eb-117">CRulesDlg::GetSelectedItems</span><span class="sxs-lookup"><span data-stu-id="881eb-117">CRulesDlg::GetSelectedItems</span></span>  <br/> |<span data-ttu-id="881eb-118">用于生成的后续**ModifyTable**操作选定的规则列表。</span><span class="sxs-lookup"><span data-stu-id="881eb-118">Used to build a list of selected rules for subsequent **ModifyTable** actions.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="881eb-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="881eb-119">See also</span></span>



[<span data-ttu-id="881eb-120">ROWENTRY</span><span class="sxs-lookup"><span data-stu-id="881eb-120">ROWENTRY</span></span>](rowentry.md)
  
[<span data-ttu-id="881eb-121">IExchangeModifyTable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="881eb-121">IExchangeModifyTable : IUnknown</span></span>](iexchangemodifytableiunknown.md)


[<span data-ttu-id="881eb-122">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="881eb-122">MAPI Structures</span></span>](mapi-structures.md)

