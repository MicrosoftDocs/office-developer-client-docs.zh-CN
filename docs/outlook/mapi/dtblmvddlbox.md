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
ms.openlocfilehash: 33b4fd87f33c26db15e1a6a28f077c393168db91
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32325758"
---
# <a name="dtblmvddlbox"></a><span data-ttu-id="0395a-103">DTBLMVDDLBOX</span><span class="sxs-lookup"><span data-stu-id="0395a-103">DTBLMVDDLBOX</span></span>

  
  
<span data-ttu-id="0395a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0395a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0395a-105">介绍将在从显示表生成的对话框中使用的下拉列表。</span><span class="sxs-lookup"><span data-stu-id="0395a-105">Describes a drop-down list that will be used in a dialog box that is built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0395a-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="0395a-106">Header file:</span></span>  <br/> |<span data-ttu-id="0395a-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="0395a-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _DTBLMVDDLBX
{
  ULONG ulFlags;
  ULONG ulMVPropTag;
} DTBLMVDDLBX, FAR * LPDTBLMVDDLBX;

```

## <a name="members"></a><span data-ttu-id="0395a-108">成员</span><span class="sxs-lookup"><span data-stu-id="0395a-108">Members</span></span>

 <span data-ttu-id="0395a-109">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="0395a-109">**ulFlags**</span></span>
  
> <span data-ttu-id="0395a-110">保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="0395a-110">Reserved; must be zero.</span></span>
    
 <span data-ttu-id="0395a-111">**ulMVPropTag**</span><span class="sxs-lookup"><span data-stu-id="0395a-111">**ulMVPropTag**</span></span>
  
> <span data-ttu-id="0395a-112">类型为 PT_MV_TSTRING 的多值属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="0395a-112">Property tag for a multi-valued property of type PT_MV_TSTRING.</span></span> <span data-ttu-id="0395a-113">此属性的不同值在下拉列表中显示为不同的条目。</span><span class="sxs-lookup"><span data-stu-id="0395a-113">The different values of this property are displayed as distinct entries in the drop-down list.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="0395a-114">注解</span><span class="sxs-lookup"><span data-stu-id="0395a-114">Remarks</span></span>

<span data-ttu-id="0395a-115">**DTBLMVDDLBOX**结构描述多值下拉列表项的只读列表。</span><span class="sxs-lookup"><span data-stu-id="0395a-115">A **DTBLMVDDLBOX** structure describes a multi-valued drop-down list a read-only list of items.</span></span> <span data-ttu-id="0395a-116">通过使用多值下拉列表, 当用户单击滚动条时, 将显示值。</span><span class="sxs-lookup"><span data-stu-id="0395a-116">By using a multi-valued drop-down list, values are displayed when a user clicks on a scroll bar.</span></span> 
  
<span data-ttu-id="0395a-117">显示的数据来自**ulMVPropTag**成员中标识的属性。</span><span class="sxs-lookup"><span data-stu-id="0395a-117">The data that is displayed comes from the property identified in the **ulMVPropTag** member.</span></span> <span data-ttu-id="0395a-118">不需要从与显示表相关联的属性接口中进行读取。</span><span class="sxs-lookup"><span data-stu-id="0395a-118">There is no requirement to read from the property interface that is associated with the display table.</span></span> <span data-ttu-id="0395a-119">此外, 因为用户无法从这些类型的列表框中进行选择, 所以不会将数据写入属性接口。</span><span class="sxs-lookup"><span data-stu-id="0395a-119">Also, because users are not able to make selections from these types of list boxes, data is not written to the property interface.</span></span> 
  
<span data-ttu-id="0395a-120">多值下拉列表仅支持多值字符串属性;不支持其他多值属性类型。</span><span class="sxs-lookup"><span data-stu-id="0395a-120">Only multi-valued string properties are supported for the multi-valued drop-down list; other multi-valued property types are not supported.</span></span> 
  
<span data-ttu-id="0395a-121">有关显示表的概述, 请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="0395a-121">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="0395a-122">有关如何实现显示表的信息, 请参阅[实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="0395a-122">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0395a-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0395a-123">See also</span></span>



[<span data-ttu-id="0395a-124">DTCTL</span><span class="sxs-lookup"><span data-stu-id="0395a-124">DTCTL</span></span>](dtctl.md)


[<span data-ttu-id="0395a-125">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="0395a-125">MAPI Structures</span></span>](mapi-structures.md)

