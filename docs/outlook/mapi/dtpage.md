---
title: DTPAGE
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTPAGE
api_type:
- COM
ms.assetid: 500f60ed-fdec-4d70-8cf5-664c46643956
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: a187245b2594282bc9908b3075852440f418af2b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774875"
---
# <a name="dtpage"></a><span data-ttu-id="dd59b-103">DTPAGE</span><span class="sxs-lookup"><span data-stu-id="dd59b-103">DTPAGE</span></span>

  
  
<span data-ttu-id="dd59b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="dd59b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="dd59b-105">介绍器构建[BuildDisplayTable](builddisplaytable.md)函数显示表中的对话框。</span><span class="sxs-lookup"><span data-stu-id="dd59b-105">Describes the dialog box that is built from a display table by the [BuildDisplayTable](builddisplaytable.md) function.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="dd59b-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="dd59b-106">Header file:</span></span>  <br/> |<span data-ttu-id="dd59b-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="dd59b-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct DTPAGE
{
  ULONG cctl;
  LPSTR lpszResourceName;
  union
  {
    LPSTR lpszComponent;
    ULONG ulItemID;
  }
  LPDTCTL lpctl;
} DTPAGE, FAR *LPDTPAGE;

```

## <a name="members"></a><span data-ttu-id="dd59b-108">成员</span><span class="sxs-lookup"><span data-stu-id="dd59b-108">Members</span></span>

 <span data-ttu-id="dd59b-109">**cctl**</span><span class="sxs-lookup"><span data-stu-id="dd59b-109">**cctl**</span></span>
  
> <span data-ttu-id="dd59b-110">控件所指的**lpctl**成员数。</span><span class="sxs-lookup"><span data-stu-id="dd59b-110">Count of controls pointed to by the **lpctl** member.</span></span> 
    
 <span data-ttu-id="dd59b-111">**lpszResourceName**</span><span class="sxs-lookup"><span data-stu-id="dd59b-111">**lpszResourceName**</span></span>
  
> <span data-ttu-id="dd59b-112">指向对话框资源的名称或整数标识符。</span><span class="sxs-lookup"><span data-stu-id="dd59b-112">Pointer to the name or integer identifier for the dialog box resource.</span></span> 
    
 <span data-ttu-id="dd59b-113">**lpszComponent**</span><span class="sxs-lookup"><span data-stu-id="dd59b-113">**lpszComponent**</span></span>
  
> <span data-ttu-id="dd59b-114">指向在 MAPISVC.INF 的 **[帮助文件映射]** 节中显示的字符串。</span><span class="sxs-lookup"><span data-stu-id="dd59b-114">Pointer to the string that appears in the **[Help File Mappings]** section in MAPISVC.INF.</span></span> <span data-ttu-id="dd59b-115">因为**lpszComponent**正在**ulItemID**成员具有的联合，这些成员之一具有有效的数据。</span><span class="sxs-lookup"><span data-stu-id="dd59b-115">Because **lpszComponent** is in a union with the **ulItemID** member, only one of these members has valid data.</span></span> 
    
 <span data-ttu-id="dd59b-116">**ulItemID**</span><span class="sxs-lookup"><span data-stu-id="dd59b-116">**ulItemID**</span></span>
  
> <span data-ttu-id="dd59b-117">整数资源标识符的值小于或等于到 65535 可以从中读取的帮助文件名称。</span><span class="sxs-lookup"><span data-stu-id="dd59b-117">Integer resource identifier with a value less than or equal to 65535 from which the Help file name can be read.</span></span> <span data-ttu-id="dd59b-118">因为**ulItemID**正在**lpszComponent**成员具有的联合，这些成员之一具有有效的数据。</span><span class="sxs-lookup"><span data-stu-id="dd59b-118">Because **ulItemID** is in a union with the **lpszComponent** member, only one of these members has valid data.</span></span> 
    
 <span data-ttu-id="dd59b-119">**lpctl**</span><span class="sxs-lookup"><span data-stu-id="dd59b-119">**lpctl**</span></span>
  
> <span data-ttu-id="dd59b-120">指向[DTCTL](dtctl.md)结构，一个用于该页面上的每个控件数组的指针。</span><span class="sxs-lookup"><span data-stu-id="dd59b-120">Pointer to an array of [DTCTL](dtctl.md) structures, one for each control on the page.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="dd59b-121">备注</span><span class="sxs-lookup"><span data-stu-id="dd59b-121">Remarks</span></span>

<span data-ttu-id="dd59b-122">若要确定选项卡式页面的帮助文件，设置为整数资源标识符的硬编码的字符串的**lpszComponent**成员或**ulItemID**成员。</span><span class="sxs-lookup"><span data-stu-id="dd59b-122">To identify the Help file for the tabbed page, set either the **lpszComponent** member to a hard-coded string or the **ulItemID** member to an integer resource identifier.</span></span> 
  
<span data-ttu-id="dd59b-123">在 MAPISVC **[帮助文件映射]** 节中每个项。INF 包含组件字符串，不得多于 30 个字符，在左侧和右侧的帮助文件路径。</span><span class="sxs-lookup"><span data-stu-id="dd59b-123">Each entry in the **[Help File Mappings]** section in MAPISVC.INF consists of a component string, no longer than 30 characters, on the left side and a Help file path on the right.</span></span> <span data-ttu-id="dd59b-124">**UlItemID**和**lpszResourceName** **BuildDisplayTable**的_hInstance_参数中找到。</span><span class="sxs-lookup"><span data-stu-id="dd59b-124">Both **ulItemID** and **lpszResourceName** are found in the  _hInstance_ parameter of **BuildDisplayTable**.</span></span> <span data-ttu-id="dd59b-125">有关详细信息，请参阅[MAPISVC。INF [帮助文件映射] 部分](mapisvc-inf-help-file-mappings-section.md)。</span><span class="sxs-lookup"><span data-stu-id="dd59b-125">For more information, see [MAPISVC.INF [Help File Mappings] Section](mapisvc-inf-help-file-mappings-section.md).</span></span>
  
<span data-ttu-id="dd59b-126">尽管**BuildDisplayTable**使用此结构来构建控件资源中的显示表中显示表本身永远不会显示**DTPAGE**结构。</span><span class="sxs-lookup"><span data-stu-id="dd59b-126">Although **BuildDisplayTable** uses this structure to build the display table from control resources, the **DTPAGE** structure never appears in the display table itself.</span></span> 
  
<span data-ttu-id="dd59b-127">显示表的概述，请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="dd59b-127">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="dd59b-128">有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="dd59b-128">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dd59b-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dd59b-129">See also</span></span>



[<span data-ttu-id="dd59b-130">BuildDisplayTable</span><span class="sxs-lookup"><span data-stu-id="dd59b-130">BuildDisplayTable</span></span>](builddisplaytable.md)
  
[<span data-ttu-id="dd59b-131">DTBLPAGE</span><span class="sxs-lookup"><span data-stu-id="dd59b-131">DTBLPAGE</span></span>](dtblpage.md)
  
[<span data-ttu-id="dd59b-132">DTCTL</span><span class="sxs-lookup"><span data-stu-id="dd59b-132">DTCTL</span></span>](dtctl.md)


[<span data-ttu-id="dd59b-133">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="dd59b-133">MAPI Structures</span></span>](mapi-structures.md)

