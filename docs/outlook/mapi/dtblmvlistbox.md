---
title: DTBLMVLISTBOX
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTBLMVLISTBOX
api_type:
- COM
ms.assetid: 1c22f842-d0e7-44f0-a7d5-c9c2aa6b8820
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f7c1241f2ad31dee8277f3b3b77ac02137067a12
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576307"
---
# <a name="dtblmvlistbox"></a><span data-ttu-id="efe47-103">DTBLMVLISTBOX</span><span class="sxs-lookup"><span data-stu-id="efe47-103">DTBLMVLISTBOX</span></span>

  
  
<span data-ttu-id="efe47-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="efe47-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="efe47-105">描述将显示表中生成的对话框中显示多值的列表。</span><span class="sxs-lookup"><span data-stu-id="efe47-105">Describes a multi-valued list that will be displayed in a dialog box that is built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="efe47-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="efe47-106">Header file:</span></span>  <br/> |<span data-ttu-id="efe47-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="efe47-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _DTBLMVLISTBOX
{
  ULONG ulFlags;
  ULONG ulMVPropTag;
} DTBLMVLISTBOX, FAR * LPDTBLMVLISTBOX;

```

## <a name="members"></a><span data-ttu-id="efe47-108">Members</span><span class="sxs-lookup"><span data-stu-id="efe47-108">Members</span></span>

 <span data-ttu-id="efe47-109">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="efe47-109">**ulFlags**</span></span>
  
> <span data-ttu-id="efe47-110">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="efe47-110">Reserved; must be zero.</span></span>
    
 <span data-ttu-id="efe47-111">**ulMVPropTag**</span><span class="sxs-lookup"><span data-stu-id="efe47-111">**ulMVPropTag**</span></span>
  
> <span data-ttu-id="efe47-112">属性标记类型 PT_MV_TSTRING 的多值属性。</span><span class="sxs-lookup"><span data-stu-id="efe47-112">Property tag for a multi-valued property of type PT_MV_TSTRING.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="efe47-113">注解</span><span class="sxs-lookup"><span data-stu-id="efe47-113">Remarks</span></span>

<span data-ttu-id="efe47-114">**DTBLMVLISTBOX**结构介绍具有只读的项目列表的标准多值的列表。</span><span class="sxs-lookup"><span data-stu-id="efe47-114">A **DTBLMVLISTBOX** structure describes a standard multi-valued list that has a read-only list of items.</span></span> <span data-ttu-id="efe47-115">通过使用标准的多值的列表，立即显示的值。</span><span class="sxs-lookup"><span data-stu-id="efe47-115">By using a standard multi-valued list, the values are displayed immediately.</span></span> 
  
<span data-ttu-id="efe47-116">显示的数据来自**ulMVPropTag**成员中标识的属性。</span><span class="sxs-lookup"><span data-stu-id="efe47-116">The data that is displayed comes from the property identified in the **ulMVPropTag** member.</span></span> <span data-ttu-id="efe47-117">没有任何要求读取与显示表相关联的属性接口。</span><span class="sxs-lookup"><span data-stu-id="efe47-117">There is no requirement to read from the property interface that is associated with the display table.</span></span> <span data-ttu-id="efe47-118">另外，由于用户未能够在这些类型的列表中进行选择，因此是不将数据写入属性界面。</span><span class="sxs-lookup"><span data-stu-id="efe47-118">Also, because users are not able to make selections from these types of lists, data is not written to the property interface.</span></span> 
  
<span data-ttu-id="efe47-119">多值列表中; 支持仅多值的字符串属性不支持其他多值的属性类型。</span><span class="sxs-lookup"><span data-stu-id="efe47-119">Only multi-valued string properties are supported for the multi-valued list; other multi-valued property types are not supported.</span></span> 
  
<span data-ttu-id="efe47-120">显示表的概述，请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="efe47-120">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="efe47-121">有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="efe47-121">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="efe47-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="efe47-122">See also</span></span>



[<span data-ttu-id="efe47-123">DTCTL</span><span class="sxs-lookup"><span data-stu-id="efe47-123">DTCTL</span></span>](dtctl.md)


[<span data-ttu-id="efe47-124">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="efe47-124">MAPI Structures</span></span>](mapi-structures.md)

