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
ms.openlocfilehash: 9295c37a46d3566089f708aaaa0b9fc3b5f30db2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774855"
---
# <a name="dtblgroupbox"></a><span data-ttu-id="932c0-103">DTBLGROUPBOX</span><span class="sxs-lookup"><span data-stu-id="932c0-103">DTBLGROUPBOX</span></span>

  
  
<span data-ttu-id="932c0-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="932c0-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="932c0-105">描述将显示表中生成的对话框中使用的分组框控件。</span><span class="sxs-lookup"><span data-stu-id="932c0-105">Describes a group box control that will be used in a dialog box built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="932c0-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="932c0-106">Header file:</span></span>  <br/> |<span data-ttu-id="932c0-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="932c0-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="932c0-108">相关的宏：</span><span class="sxs-lookup"><span data-stu-id="932c0-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="932c0-109">SizedDtblGroupBox</span><span class="sxs-lookup"><span data-stu-id="932c0-109">SizedDtblGroupBox</span></span>](sizeddtblgroupbox.md) <br/> |
   
```cpp
typedef struct _DTBLGROUPBOX
{
  ULONG ulbLpszLabel;
  ULONG ulFlags;
} DTBLGROUPBOX, FAR *LPDTBLGROUPBOX;

```

## <a name="members"></a><span data-ttu-id="932c0-110">Members</span><span class="sxs-lookup"><span data-stu-id="932c0-110">Members</span></span>

 <span data-ttu-id="932c0-111">**ulbLpszLabel**</span><span class="sxs-lookup"><span data-stu-id="932c0-111">**ulbLpszLabel**</span></span>
  
> <span data-ttu-id="932c0-112">在字符串附带组框的内存中的位置。</span><span class="sxs-lookup"><span data-stu-id="932c0-112">Position in memory of the character string that accompanies the group box.</span></span> <span data-ttu-id="932c0-113">如果显示，标签显示在框中的顶部、 左上方。</span><span class="sxs-lookup"><span data-stu-id="932c0-113">If displayed, the label appears on the top, left-hand side of the box.</span></span>
    
 <span data-ttu-id="932c0-114">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="932c0-114">**ulFlags**</span></span>
  
> <span data-ttu-id="932c0-115">用于指定所指的**ulbLpszLabel**成员标签的格式的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="932c0-115">Bitmask of flags used to designate the format of the label pointed to by the **ulbLpszLabel** member.</span></span> <span data-ttu-id="932c0-116">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="932c0-116">The following flag can be set:</span></span> 
    
<span data-ttu-id="932c0-117">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="932c0-117">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="932c0-118">标签为 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="932c0-118">The label is in Unicode format.</span></span> <span data-ttu-id="932c0-119">如果未设置 MAPI_UNICODE 标志，标签为 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="932c0-119">If the MAPI_UNICODE flag is not set, the label is in ANSI format.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="932c0-120">说明</span><span class="sxs-lookup"><span data-stu-id="932c0-120">Remarks</span></span>

<span data-ttu-id="932c0-121">**DTBLGROUPBOX**结构介绍用于直观地将在对话框中的其他控件相关联的分组框控件。</span><span class="sxs-lookup"><span data-stu-id="932c0-121">A **DTBLGROUPBOX** structure describes a group box control that is used to visually associate other controls in the dialog box.</span></span> <span data-ttu-id="932c0-122">突出显示的项技术涉及周围的框中的其他控件。</span><span class="sxs-lookup"><span data-stu-id="932c0-122">The highlighting technique involves surrounding the other controls by a box.</span></span> 
  
<span data-ttu-id="932c0-123">显示表的概述，请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="932c0-123">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="932c0-124">有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="932c0-124">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="932c0-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="932c0-125">See also</span></span>



[<span data-ttu-id="932c0-126">DTCTL</span><span class="sxs-lookup"><span data-stu-id="932c0-126">DTCTL</span></span>](dtctl.md)


[<span data-ttu-id="932c0-127">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="932c0-127">MAPI Structures</span></span>](mapi-structures.md)

