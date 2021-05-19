---
title: DTBLLABEL
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTBLLABEL
api_type:
- COM
ms.assetid: 5837facf-acd3-48fe-9610-f88085d99aef
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: aa3345740c534b5ff156f062e731c98bc6164eed
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410684"
---
# <a name="dtbllabel"></a><span data-ttu-id="5256c-103">DTBLLABEL</span><span class="sxs-lookup"><span data-stu-id="5256c-103">DTBLLABEL</span></span>

  
  
<span data-ttu-id="5256c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5256c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5256c-105">描述将在从显示表构建的对话框中使用的标签。</span><span class="sxs-lookup"><span data-stu-id="5256c-105">Describes a label that will be used in a dialog box that is built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5256c-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="5256c-106">Header file:</span></span>  <br/> |<span data-ttu-id="5256c-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5256c-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="5256c-108">相关宏</span><span class="sxs-lookup"><span data-stu-id="5256c-108">Related macro</span></span>  <br/> |[<span data-ttu-id="5256c-109">SizedDtblLabel</span><span class="sxs-lookup"><span data-stu-id="5256c-109">SizedDtblLabel</span></span>](sizeddtbllabel.md) <br/> |
   
```cpp
typedef struct _DTBLLABEL
{
  ULONG ulbLpszLabelName;
  ULONG ulFlags;
} DTBLLABEL, FAR *LPDTBLLABEL;

```

## <a name="members"></a><span data-ttu-id="5256c-110">Members</span><span class="sxs-lookup"><span data-stu-id="5256c-110">Members</span></span>

 <span data-ttu-id="5256c-111">**ulbLpszLabelName**</span><span class="sxs-lookup"><span data-stu-id="5256c-111">**ulbLpszLabelName**</span></span>
  
> <span data-ttu-id="5256c-112">字符字符串标签的内存位置。</span><span class="sxs-lookup"><span data-stu-id="5256c-112">Position in memory of the character string label.</span></span>
    
 <span data-ttu-id="5256c-113">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="5256c-113">**ulFlags**</span></span>
  
> <span data-ttu-id="5256c-114">用于指定 **ulbLpszLabelName** 成员指向的标签格式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="5256c-114">Bitmask of flags used to designate the format of the label pointed to by the **ulbLpszLabelName** member.</span></span> <span data-ttu-id="5256c-115">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="5256c-115">The following flag can be set:</span></span> 
    
<span data-ttu-id="5256c-116">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="5256c-116">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="5256c-117">标签采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="5256c-117">The label is in Unicode format.</span></span> <span data-ttu-id="5256c-118">如果未MAPI_UNICODE，则标签采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="5256c-118">If the MAPI_UNICODE flag is not set, the label is in ANSI format.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="5256c-119">备注</span><span class="sxs-lookup"><span data-stu-id="5256c-119">Remarks</span></span>

<span data-ttu-id="5256c-120">**DTBLLABEL** 结构描述与另一种类型的控件一起显示的标签控件文本，以向该控件添加含义。</span><span class="sxs-lookup"><span data-stu-id="5256c-120">A **DTBLLABEL** structure describes a label control text that is displayed with another type of control to add meaning to that control.</span></span> <span data-ttu-id="5256c-121">例如，大多数编辑控件都位于标签旁边，以通知用户要输入的信息类型。</span><span class="sxs-lookup"><span data-stu-id="5256c-121">For example, most edit controls are positioned next to labels to inform the user of the type of information to be entered.</span></span> <span data-ttu-id="5256c-122">某些控件（如分组框和单选按钮）会保留它们自己的标签。</span><span class="sxs-lookup"><span data-stu-id="5256c-122">Some controls, such as group boxes and radio buttons, hold their own labels.</span></span> 
  
<span data-ttu-id="5256c-123">标签可以包含一个Windows加速键，该加速键标识为与号 &amp; () 。</span><span class="sxs-lookup"><span data-stu-id="5256c-123">The label can include a Windows accelerator, identified as the character following the ampersand (&amp;).</span></span> <span data-ttu-id="5256c-124">按加速键会将焦点放在显示表中此标签后的第一个非标签非按钮控件中。</span><span class="sxs-lookup"><span data-stu-id="5256c-124">Pressing the accelerator key puts the focus in the first nonlabel, nonbutton control following this label in the display table.</span></span>
  
<span data-ttu-id="5256c-125">不支持多行标签。</span><span class="sxs-lookup"><span data-stu-id="5256c-125">There is no support for multiline labels.</span></span> <span data-ttu-id="5256c-126">显示多行需要多个标签。</span><span class="sxs-lookup"><span data-stu-id="5256c-126">Showing multiple lines requires multiple labels.</span></span>
  
<span data-ttu-id="5256c-127">不能将标签用作只读编辑控件。</span><span class="sxs-lookup"><span data-stu-id="5256c-127">It is not possible to use a label as a read-only edit control.</span></span> <span data-ttu-id="5256c-128">区别在于，可以选择和复制编辑控件，而标签不能。</span><span class="sxs-lookup"><span data-stu-id="5256c-128">The difference is that an edit control can be selected and copied whereas a label cannot.</span></span> 
  
<span data-ttu-id="5256c-129">有关显示表的概述，请参阅显示 [表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="5256c-129">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="5256c-130">若要了解如何实现显示表，请参阅 [实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="5256c-130">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5256c-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5256c-131">See also</span></span>



[<span data-ttu-id="5256c-132">DTCTL</span><span class="sxs-lookup"><span data-stu-id="5256c-132">DTCTL</span></span>](dtctl.md)


[<span data-ttu-id="5256c-133">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="5256c-133">MAPI Structures</span></span>](mapi-structures.md)

