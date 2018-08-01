---
title: DTBLMVDDLBOX
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTBLMVDDLBOX
api_type:
- COM
ms.assetid: 0e6283dc-9a08-460f-9400-03f0ceb4081c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ede0a448a32565446e614fc2d14f2a72a9549dad
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774859"
---
# <a name="dtblmvddlbox"></a><span data-ttu-id="2bff5-103">DTBLMVDDLBOX</span><span class="sxs-lookup"><span data-stu-id="2bff5-103">DTBLMVDDLBOX</span></span>

  
  
<span data-ttu-id="2bff5-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2bff5-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2bff5-105">描述将显示表中生成的对话框中使用下拉列表。</span><span class="sxs-lookup"><span data-stu-id="2bff5-105">Describes a drop-down list that will be used in a dialog box that is built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2bff5-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="2bff5-106">Header file:</span></span>  <br/> |<span data-ttu-id="2bff5-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2bff5-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _DTBLMVDDLBX
{
  ULONG ulFlags;
  ULONG ulMVPropTag;
} DTBLMVDDLBX, FAR * LPDTBLMVDDLBX;

```

## <a name="members"></a><span data-ttu-id="2bff5-108">Members</span><span class="sxs-lookup"><span data-stu-id="2bff5-108">Members</span></span>

 <span data-ttu-id="2bff5-109">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="2bff5-109">**ulFlags**</span></span>
  
> <span data-ttu-id="2bff5-110">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="2bff5-110">Reserved; must be zero.</span></span>
    
 <span data-ttu-id="2bff5-111">**ulMVPropTag**</span><span class="sxs-lookup"><span data-stu-id="2bff5-111">**ulMVPropTag**</span></span>
  
> <span data-ttu-id="2bff5-112">属性标记类型 PT_MV_TSTRING 的多值属性。</span><span class="sxs-lookup"><span data-stu-id="2bff5-112">Property tag for a multi-valued property of type PT_MV_TSTRING.</span></span> <span data-ttu-id="2bff5-113">此属性的不同值显示为下拉列表中的不同条目。</span><span class="sxs-lookup"><span data-stu-id="2bff5-113">The different values of this property are displayed as distinct entries in the drop-down list.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2bff5-114">说明</span><span class="sxs-lookup"><span data-stu-id="2bff5-114">Remarks</span></span>

<span data-ttu-id="2bff5-115">**DTBLMVDDLBOX**结构介绍多值的下拉列表项的只读的列表。</span><span class="sxs-lookup"><span data-stu-id="2bff5-115">A **DTBLMVDDLBOX** structure describes a multi-valued drop-down list a read-only list of items.</span></span> <span data-ttu-id="2bff5-116">通过使用多值的下拉列表，当用户单击滚动条上显示值。</span><span class="sxs-lookup"><span data-stu-id="2bff5-116">By using a multi-valued drop-down list, values are displayed when a user clicks on a scroll bar.</span></span> 
  
<span data-ttu-id="2bff5-117">显示的数据来自**ulMVPropTag**成员中标识的属性。</span><span class="sxs-lookup"><span data-stu-id="2bff5-117">The data that is displayed comes from the property identified in the **ulMVPropTag** member.</span></span> <span data-ttu-id="2bff5-118">没有任何要求读取与显示表相关联的属性接口。</span><span class="sxs-lookup"><span data-stu-id="2bff5-118">There is no requirement to read from the property interface that is associated with the display table.</span></span> <span data-ttu-id="2bff5-119">另外，由于用户未能够从这些类型的列表框中进行选择，因此是不将数据写入属性界面。</span><span class="sxs-lookup"><span data-stu-id="2bff5-119">Also, because users are not able to make selections from these types of list boxes, data is not written to the property interface.</span></span> 
  
<span data-ttu-id="2bff5-120">多值的下拉列表中; 支持仅多值的字符串属性不支持其他多值的属性类型。</span><span class="sxs-lookup"><span data-stu-id="2bff5-120">Only multi-valued string properties are supported for the multi-valued drop-down list; other multi-valued property types are not supported.</span></span> 
  
<span data-ttu-id="2bff5-121">显示表的概述，请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="2bff5-121">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="2bff5-122">有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="2bff5-122">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2bff5-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2bff5-123">See also</span></span>



[<span data-ttu-id="2bff5-124">DTCTL</span><span class="sxs-lookup"><span data-stu-id="2bff5-124">DTCTL</span></span>](dtctl.md)


[<span data-ttu-id="2bff5-125">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="2bff5-125">MAPI Structures</span></span>](mapi-structures.md)

