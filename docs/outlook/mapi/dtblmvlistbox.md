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
ms.openlocfilehash: ae8f3ab28837bf0579549ead46c28477f815f35c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439700"
---
# <a name="dtblmvlistbox"></a><span data-ttu-id="98599-103">DTBLMVLISTBOX</span><span class="sxs-lookup"><span data-stu-id="98599-103">DTBLMVLISTBOX</span></span>

  
  
<span data-ttu-id="98599-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="98599-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="98599-105">描述将在从显示表构建的对话框中显示的多值列表。</span><span class="sxs-lookup"><span data-stu-id="98599-105">Describes a multi-valued list that will be displayed in a dialog box that is built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="98599-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="98599-106">Header file:</span></span>  <br/> |<span data-ttu-id="98599-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="98599-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _DTBLMVLISTBOX
{
  ULONG ulFlags;
  ULONG ulMVPropTag;
} DTBLMVLISTBOX, FAR * LPDTBLMVLISTBOX;

```

## <a name="members"></a><span data-ttu-id="98599-108">成员</span><span class="sxs-lookup"><span data-stu-id="98599-108">Members</span></span>

 <span data-ttu-id="98599-109">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="98599-109">**ulFlags**</span></span>
  
> <span data-ttu-id="98599-110">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="98599-110">Reserved; must be zero.</span></span>
    
 <span data-ttu-id="98599-111">**ulMVPropTag**</span><span class="sxs-lookup"><span data-stu-id="98599-111">**ulMVPropTag**</span></span>
  
> <span data-ttu-id="98599-112">类型为 PT_MV_TSTRING 的多值属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="98599-112">Property tag for a multi-valued property of type PT_MV_TSTRING.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="98599-113">备注</span><span class="sxs-lookup"><span data-stu-id="98599-113">Remarks</span></span>

<span data-ttu-id="98599-114">**DTBLMVLISTBOX** 结构描述具有只读项目列表的标准多值列表。</span><span class="sxs-lookup"><span data-stu-id="98599-114">A **DTBLMVLISTBOX** structure describes a standard multi-valued list that has a read-only list of items.</span></span> <span data-ttu-id="98599-115">通过使用标准的多值列表，值将立即显示。</span><span class="sxs-lookup"><span data-stu-id="98599-115">By using a standard multi-valued list, the values are displayed immediately.</span></span> 
  
<span data-ttu-id="98599-116">显示的数据来自 **ulMVPropTag** 成员中标识的属性。</span><span class="sxs-lookup"><span data-stu-id="98599-116">The data that is displayed comes from the property identified in the **ulMVPropTag** member.</span></span> <span data-ttu-id="98599-117">不需要从与显示表关联的属性接口读取。</span><span class="sxs-lookup"><span data-stu-id="98599-117">There is no requirement to read from the property interface that is associated with the display table.</span></span> <span data-ttu-id="98599-118">此外，由于用户无法从这些类型的列表进行选择，因此不会将数据写入属性接口。</span><span class="sxs-lookup"><span data-stu-id="98599-118">Also, because users are not able to make selections from these types of lists, data is not written to the property interface.</span></span> 
  
<span data-ttu-id="98599-119">多值列表仅支持多值字符串属性;不支持其他多值属性类型。</span><span class="sxs-lookup"><span data-stu-id="98599-119">Only multi-valued string properties are supported for the multi-valued list; other multi-valued property types are not supported.</span></span> 
  
<span data-ttu-id="98599-120">有关显示表的概述，请参阅显示 [表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="98599-120">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="98599-121">若要了解如何实现显示表，请参阅 [实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="98599-121">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="98599-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="98599-122">See also</span></span>



[<span data-ttu-id="98599-123">DTCTL</span><span class="sxs-lookup"><span data-stu-id="98599-123">DTCTL</span></span>](dtctl.md)


[<span data-ttu-id="98599-124">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="98599-124">MAPI Structures</span></span>](mapi-structures.md)

