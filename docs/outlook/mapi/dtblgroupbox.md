---
title: DTBLGROUPBOX
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTBLGROUPBOX
api_type:
- COM
ms.assetid: 5e444b62-d6b6-4cfc-8601-d34aa004c1e6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 324cfe9d7c412b3bb0e3150b8eec51aaeb6a0e93
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438391"
---
# <a name="dtblgroupbox"></a><span data-ttu-id="1a8a0-103">DTBLGROUPBOX</span><span class="sxs-lookup"><span data-stu-id="1a8a0-103">DTBLGROUPBOX</span></span>

  
  
<span data-ttu-id="1a8a0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1a8a0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1a8a0-105">描述将在基于显示表构建的对话框中使用的组框控件。</span><span class="sxs-lookup"><span data-stu-id="1a8a0-105">Describes a group box control that will be used in a dialog box built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1a8a0-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="1a8a0-106">Header file:</span></span>  <br/> |<span data-ttu-id="1a8a0-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1a8a0-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="1a8a0-108">相关宏：</span><span class="sxs-lookup"><span data-stu-id="1a8a0-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="1a8a0-109">SizedDtblGroupBox</span><span class="sxs-lookup"><span data-stu-id="1a8a0-109">SizedDtblGroupBox</span></span>](sizeddtblgroupbox.md) <br/> |
   
```cpp
typedef struct _DTBLGROUPBOX
{
  ULONG ulbLpszLabel;
  ULONG ulFlags;
} DTBLGROUPBOX, FAR *LPDTBLGROUPBOX;

```

## <a name="members"></a><span data-ttu-id="1a8a0-110">Members</span><span class="sxs-lookup"><span data-stu-id="1a8a0-110">Members</span></span>

 <span data-ttu-id="1a8a0-111">**ulbLpszLabel**</span><span class="sxs-lookup"><span data-stu-id="1a8a0-111">**ulbLpszLabel**</span></span>
  
> <span data-ttu-id="1a8a0-112">在分组框随附的字符串内存中的位置。</span><span class="sxs-lookup"><span data-stu-id="1a8a0-112">Position in memory of the character string that accompanies the group box.</span></span> <span data-ttu-id="1a8a0-113">如果显示，则标签显示在框的左侧顶部。</span><span class="sxs-lookup"><span data-stu-id="1a8a0-113">If displayed, the label appears on the top, left-hand side of the box.</span></span>
    
 <span data-ttu-id="1a8a0-114">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="1a8a0-114">**ulFlags**</span></span>
  
> <span data-ttu-id="1a8a0-115">用于指定 **ulbLpszLabel** 成员指向的标签格式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="1a8a0-115">Bitmask of flags used to designate the format of the label pointed to by the **ulbLpszLabel** member.</span></span> <span data-ttu-id="1a8a0-116">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="1a8a0-116">The following flag can be set:</span></span> 
    
<span data-ttu-id="1a8a0-117">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="1a8a0-117">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="1a8a0-118">标签采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="1a8a0-118">The label is in Unicode format.</span></span> <span data-ttu-id="1a8a0-119">如果未MAPI_UNICODE，则标签采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="1a8a0-119">If the MAPI_UNICODE flag is not set, the label is in ANSI format.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="1a8a0-120">备注</span><span class="sxs-lookup"><span data-stu-id="1a8a0-120">Remarks</span></span>

<span data-ttu-id="1a8a0-121">**DTBLGROUPBOX** 结构描述用于直观关联对话框中其他控件的分组框控件。</span><span class="sxs-lookup"><span data-stu-id="1a8a0-121">A **DTBLGROUPBOX** structure describes a group box control that is used to visually associate other controls in the dialog box.</span></span> <span data-ttu-id="1a8a0-122">突出显示技术涉及用一个框包围其他控件。</span><span class="sxs-lookup"><span data-stu-id="1a8a0-122">The highlighting technique involves surrounding the other controls by a box.</span></span> 
  
<span data-ttu-id="1a8a0-123">有关显示表的概述，请参阅显示 [表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="1a8a0-123">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="1a8a0-124">若要了解如何实现显示表，请参阅 [实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="1a8a0-124">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1a8a0-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1a8a0-125">See also</span></span>



[<span data-ttu-id="1a8a0-126">DTCTL</span><span class="sxs-lookup"><span data-stu-id="1a8a0-126">DTCTL</span></span>](dtctl.md)


[<span data-ttu-id="1a8a0-127">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="1a8a0-127">MAPI Structures</span></span>](mapi-structures.md)

