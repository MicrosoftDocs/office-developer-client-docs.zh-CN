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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420743"
---
# <a name="dtblmvddlbox"></a><span data-ttu-id="ff132-103">DTBLMVDDLBOX</span><span class="sxs-lookup"><span data-stu-id="ff132-103">DTBLMVDDLBOX</span></span>

  
  
<span data-ttu-id="ff132-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ff132-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ff132-105">描述将在从显示表构建的对话框中使用的下拉列表。</span><span class="sxs-lookup"><span data-stu-id="ff132-105">Describes a drop-down list that will be used in a dialog box that is built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ff132-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="ff132-106">Header file:</span></span>  <br/> |<span data-ttu-id="ff132-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ff132-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _DTBLMVDDLBX
{
  ULONG ulFlags;
  ULONG ulMVPropTag;
} DTBLMVDDLBX, FAR * LPDTBLMVDDLBX;

```

## <a name="members"></a><span data-ttu-id="ff132-108">成员</span><span class="sxs-lookup"><span data-stu-id="ff132-108">Members</span></span>

 <span data-ttu-id="ff132-109">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="ff132-109">**ulFlags**</span></span>
  
> <span data-ttu-id="ff132-110">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="ff132-110">Reserved; must be zero.</span></span>
    
 <span data-ttu-id="ff132-111">**ulMVPropTag**</span><span class="sxs-lookup"><span data-stu-id="ff132-111">**ulMVPropTag**</span></span>
  
> <span data-ttu-id="ff132-112">类型为 PT_MV_TSTRING 的多值属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="ff132-112">Property tag for a multi-valued property of type PT_MV_TSTRING.</span></span> <span data-ttu-id="ff132-113">此属性的值在下拉列表中显示为不同的条目。</span><span class="sxs-lookup"><span data-stu-id="ff132-113">The different values of this property are displayed as distinct entries in the drop-down list.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ff132-114">备注</span><span class="sxs-lookup"><span data-stu-id="ff132-114">Remarks</span></span>

<span data-ttu-id="ff132-115">**DTBLMVDDLBOX** 结构描述多值下拉列表（只读项目列表）。</span><span class="sxs-lookup"><span data-stu-id="ff132-115">A **DTBLMVDDLBOX** structure describes a multi-valued drop-down list a read-only list of items.</span></span> <span data-ttu-id="ff132-116">通过使用多值下拉列表，当用户单击滚动条时将显示值。</span><span class="sxs-lookup"><span data-stu-id="ff132-116">By using a multi-valued drop-down list, values are displayed when a user clicks on a scroll bar.</span></span> 
  
<span data-ttu-id="ff132-117">显示的数据来自 **ulMVPropTag** 成员中标识的属性。</span><span class="sxs-lookup"><span data-stu-id="ff132-117">The data that is displayed comes from the property identified in the **ulMVPropTag** member.</span></span> <span data-ttu-id="ff132-118">不需要从与显示表关联的属性接口读取。</span><span class="sxs-lookup"><span data-stu-id="ff132-118">There is no requirement to read from the property interface that is associated with the display table.</span></span> <span data-ttu-id="ff132-119">此外，由于用户无法从这些类型的列表框中进行选择，因此不会将数据写入属性接口。</span><span class="sxs-lookup"><span data-stu-id="ff132-119">Also, because users are not able to make selections from these types of list boxes, data is not written to the property interface.</span></span> 
  
<span data-ttu-id="ff132-120">多值下拉列表仅支持多值字符串属性;不支持其他多值属性类型。</span><span class="sxs-lookup"><span data-stu-id="ff132-120">Only multi-valued string properties are supported for the multi-valued drop-down list; other multi-valued property types are not supported.</span></span> 
  
<span data-ttu-id="ff132-121">有关显示表的概述，请参阅显示 [表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="ff132-121">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="ff132-122">若要了解如何实现显示表，请参阅 [实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="ff132-122">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ff132-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff132-123">See also</span></span>



[<span data-ttu-id="ff132-124">DTCTL</span><span class="sxs-lookup"><span data-stu-id="ff132-124">DTCTL</span></span>](dtctl.md)


[<span data-ttu-id="ff132-125">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="ff132-125">MAPI Structures</span></span>](mapi-structures.md)

