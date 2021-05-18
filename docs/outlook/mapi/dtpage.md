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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ad8aec8d015849965bea6ac011c8a45e75c69ca1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408220"
---
# <a name="dtpage"></a><span data-ttu-id="52308-103">DTPAGE</span><span class="sxs-lookup"><span data-stu-id="52308-103">DTPAGE</span></span>

  
  
<span data-ttu-id="52308-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="52308-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="52308-105">描述由 [BuildDisplayTable](builddisplaytable.md) 函数从显示表构建的对话框。</span><span class="sxs-lookup"><span data-stu-id="52308-105">Describes the dialog box that is built from a display table by the [BuildDisplayTable](builddisplaytable.md) function.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="52308-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="52308-106">Header file:</span></span>  <br/> |<span data-ttu-id="52308-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="52308-107">Mapidefs.h</span></span>  <br/> |
   
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

## <a name="members"></a><span data-ttu-id="52308-108">Members</span><span class="sxs-lookup"><span data-stu-id="52308-108">Members</span></span>

 <span data-ttu-id="52308-109">**cctl**</span><span class="sxs-lookup"><span data-stu-id="52308-109">**cctl**</span></span>
  
> <span data-ttu-id="52308-110">**lpctl** 成员指向的控件计数。</span><span class="sxs-lookup"><span data-stu-id="52308-110">Count of controls pointed to by the **lpctl** member.</span></span> 
    
 <span data-ttu-id="52308-111">**lpszResourceName**</span><span class="sxs-lookup"><span data-stu-id="52308-111">**lpszResourceName**</span></span>
  
> <span data-ttu-id="52308-112">指向对话框资源的名称或整数标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="52308-112">Pointer to the name or integer identifier for the dialog box resource.</span></span> 
    
 <span data-ttu-id="52308-113">**lpszComponent**</span><span class="sxs-lookup"><span data-stu-id="52308-113">**lpszComponent**</span></span>
  
> <span data-ttu-id="52308-114">指向出现在 MAPISVC.INF **中的 [帮助文件映射]** 部分中的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="52308-114">Pointer to the string that appears in the **[Help File Mappings]** section in MAPISVC.INF.</span></span> <span data-ttu-id="52308-115">由于 **lpszComponent** 与 **ulItemID** 成员联合，因此只有其中一个成员具有有效数据。</span><span class="sxs-lookup"><span data-stu-id="52308-115">Because **lpszComponent** is in a union with the **ulItemID** member, only one of these members has valid data.</span></span> 
    
 <span data-ttu-id="52308-116">**ulItemID**</span><span class="sxs-lookup"><span data-stu-id="52308-116">**ulItemID**</span></span>
  
> <span data-ttu-id="52308-117">整数资源标识符，其值小于或等于 65535，可以从中读取帮助文件名。</span><span class="sxs-lookup"><span data-stu-id="52308-117">Integer resource identifier with a value less than or equal to 65535 from which the Help file name can be read.</span></span> <span data-ttu-id="52308-118">由于 **ulItemID** 与 **lpszComponent** 成员联合在一起，因此只有其中一个成员具有有效数据。</span><span class="sxs-lookup"><span data-stu-id="52308-118">Because **ulItemID** is in a union with the **lpszComponent** member, only one of these members has valid data.</span></span> 
    
 <span data-ttu-id="52308-119">**lpctl**</span><span class="sxs-lookup"><span data-stu-id="52308-119">**lpctl**</span></span>
  
> <span data-ttu-id="52308-120">指向 [DTCTL](dtctl.md) 结构的数组的指针，页面上每个控件一个。</span><span class="sxs-lookup"><span data-stu-id="52308-120">Pointer to an array of [DTCTL](dtctl.md) structures, one for each control on the page.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="52308-121">备注</span><span class="sxs-lookup"><span data-stu-id="52308-121">Remarks</span></span>

<span data-ttu-id="52308-122">若要标识选项卡式页面的帮助文件，将 **lpszComponent** 成员设置为硬编码字符串或 **ulItemID** 成员设置为整数资源标识符。</span><span class="sxs-lookup"><span data-stu-id="52308-122">To identify the Help file for the tabbed page, set either the **lpszComponent** member to a hard-coded string or the **ulItemID** member to an integer resource identifier.</span></span> 
  
<span data-ttu-id="52308-123">MAPISVC **中 [帮助文件映射]** 部分的每个条目。INF 由左侧的组件字符串（不超过 30 个字符）和右侧帮助文件路径组成。</span><span class="sxs-lookup"><span data-stu-id="52308-123">Each entry in the **[Help File Mappings]** section in MAPISVC.INF consists of a component string, no longer than 30 characters, on the left side and a Help file path on the right.</span></span> <span data-ttu-id="52308-124">**ulItemID 和** **lpszResourceName** 都位于 **BuildDisplayTable** 的 _hInstance_ 参数中。</span><span class="sxs-lookup"><span data-stu-id="52308-124">Both **ulItemID** and **lpszResourceName** are found in the  _hInstance_ parameter of **BuildDisplayTable**.</span></span> <span data-ttu-id="52308-125">有关详细信息，请参阅 [MAPISVC。INF [Help File Mappings] Section](mapisvc-inf-help-file-mappings-section.md).</span><span class="sxs-lookup"><span data-stu-id="52308-125">For more information, see [MAPISVC.INF [Help File Mappings] Section](mapisvc-inf-help-file-mappings-section.md).</span></span>
  
<span data-ttu-id="52308-126">尽管 **BuildDisplayTable** 使用此结构从控件资源构建显示表，但 **DTPAGE** 结构永远不会显示在显示表本身中。</span><span class="sxs-lookup"><span data-stu-id="52308-126">Although **BuildDisplayTable** uses this structure to build the display table from control resources, the **DTPAGE** structure never appears in the display table itself.</span></span> 
  
<span data-ttu-id="52308-127">有关显示表的概述，请参阅显示 [表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="52308-127">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="52308-128">若要了解如何实现显示表，请参阅 [实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="52308-128">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="52308-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52308-129">See also</span></span>



[<span data-ttu-id="52308-130">BuildDisplayTable</span><span class="sxs-lookup"><span data-stu-id="52308-130">BuildDisplayTable</span></span>](builddisplaytable.md)
  
[<span data-ttu-id="52308-131">DTBLPAGE</span><span class="sxs-lookup"><span data-stu-id="52308-131">DTBLPAGE</span></span>](dtblpage.md)
  
[<span data-ttu-id="52308-132">DTCTL</span><span class="sxs-lookup"><span data-stu-id="52308-132">DTCTL</span></span>](dtctl.md)


[<span data-ttu-id="52308-133">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="52308-133">MAPI Structures</span></span>](mapi-structures.md)

