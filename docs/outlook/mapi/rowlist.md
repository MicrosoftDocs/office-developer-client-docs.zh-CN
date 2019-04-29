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
ms.openlocfilehash: c13b741b1e0ddfd964b9325d736a26dac4bff2af
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419182"
---
# <a name="rowlist"></a><span data-ttu-id="84319-103">ROWLIST</span><span class="sxs-lookup"><span data-stu-id="84319-103">ROWLIST</span></span>

  
  
<span data-ttu-id="84319-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="84319-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="84319-105">包含[ROWENTRY](rowentry.md)结构的数组, 这些结构表示通过[IExchangeModifyTable](iexchangemodifytableiunknown.md)接口对表中的这些行执行的行和操作。</span><span class="sxs-lookup"><span data-stu-id="84319-105">Contains an array of [ROWENTRY](rowentry.md) structures representing rows and the operations that are performed on those rows in a table through the [IExchangeModifyTable](iexchangemodifytableiunknown.md) interface.</span></span> 
  
```cpp
typedef struct
{
  ULONG     cEntries;
  ROWENTRY  aEntries[MAPI_DIM];
}  ROWLIST, FAR * LPROWLIST;

```

## <a name="members"></a><span data-ttu-id="84319-106">Members</span><span class="sxs-lookup"><span data-stu-id="84319-106">Members</span></span>

 <span data-ttu-id="84319-107">**cEntries**</span><span class="sxs-lookup"><span data-stu-id="84319-107">**cEntries**</span></span>
  
> <span data-ttu-id="84319-108">由**aEntries**成员指定的数组中的条目数。</span><span class="sxs-lookup"><span data-stu-id="84319-108">Count of entries in the array specified by the **aEntries** member.</span></span> 
    
 <span data-ttu-id="84319-109">**aEntries [MAPI_DIM]**</span><span class="sxs-lookup"><span data-stu-id="84319-109">**aEntries[MAPI_DIM]**</span></span>
  
> <span data-ttu-id="84319-110">**ROWENTRY**结构的数组, 其中包含在表中对这些行执行的行和操作。</span><span class="sxs-lookup"><span data-stu-id="84319-110">Array of **ROWENTRY** structures that contains the rows and the operations that are performed on those rows in the table.</span></span> 
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="84319-111">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="84319-111">MFCMAPI reference</span></span>

<span data-ttu-id="84319-112">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="84319-112">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="84319-113">**文件**</span><span class="sxs-lookup"><span data-stu-id="84319-113">**File**</span></span>|<span data-ttu-id="84319-114">**函数**</span><span class="sxs-lookup"><span data-stu-id="84319-114">**Function**</span></span>|<span data-ttu-id="84319-115">**备注**</span><span class="sxs-lookup"><span data-stu-id="84319-115">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="84319-116">RulesDlg</span><span class="sxs-lookup"><span data-stu-id="84319-116">RulesDlg.cpp</span></span>  <br/> |<span data-ttu-id="84319-117">CRulesDlg:: GetSelectedItems</span><span class="sxs-lookup"><span data-stu-id="84319-117">CRulesDlg::GetSelectedItems</span></span>  <br/> |<span data-ttu-id="84319-118">用于为后续**ModifyTable**操作生成选定规则的列表。</span><span class="sxs-lookup"><span data-stu-id="84319-118">Used to build a list of selected rules for subsequent **ModifyTable** actions.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="84319-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="84319-119">See also</span></span>



[<span data-ttu-id="84319-120">ROWENTRY</span><span class="sxs-lookup"><span data-stu-id="84319-120">ROWENTRY</span></span>](rowentry.md)
  
[<span data-ttu-id="84319-121">IExchangeModifyTable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="84319-121">IExchangeModifyTable : IUnknown</span></span>](iexchangemodifytableiunknown.md)


[<span data-ttu-id="84319-122">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="84319-122">MAPI Structures</span></span>](mapi-structures.md)

