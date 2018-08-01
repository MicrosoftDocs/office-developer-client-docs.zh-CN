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
ms.openlocfilehash: 28f6471f74fb0fcc4f7e2f4114f0790e1564e17e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774856"
---
# <a name="dtbllabel"></a><span data-ttu-id="77f15-103">DTBLLABEL</span><span class="sxs-lookup"><span data-stu-id="77f15-103">DTBLLABEL</span></span>

  
  
<span data-ttu-id="77f15-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="77f15-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="77f15-105">描述将显示表中生成的对话框中使用的标签。</span><span class="sxs-lookup"><span data-stu-id="77f15-105">Describes a label that will be used in a dialog box that is built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="77f15-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="77f15-106">Header file:</span></span>  <br/> |<span data-ttu-id="77f15-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="77f15-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="77f15-108">相关的宏</span><span class="sxs-lookup"><span data-stu-id="77f15-108">Related macro</span></span>  <br/> |[<span data-ttu-id="77f15-109">SizedDtblLabel</span><span class="sxs-lookup"><span data-stu-id="77f15-109">SizedDtblLabel</span></span>](sizeddtbllabel.md) <br/> |
   
```cpp
typedef struct _DTBLLABEL
{
  ULONG ulbLpszLabelName;
  ULONG ulFlags;
} DTBLLABEL, FAR *LPDTBLLABEL;

```

## <a name="members"></a><span data-ttu-id="77f15-110">Members</span><span class="sxs-lookup"><span data-stu-id="77f15-110">Members</span></span>

 <span data-ttu-id="77f15-111">**ulbLpszLabelName**</span><span class="sxs-lookup"><span data-stu-id="77f15-111">**ulbLpszLabelName**</span></span>
  
> <span data-ttu-id="77f15-112">在内存中的字符的字符串标签的位置。</span><span class="sxs-lookup"><span data-stu-id="77f15-112">Position in memory of the character string label.</span></span>
    
 <span data-ttu-id="77f15-113">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="77f15-113">**ulFlags**</span></span>
  
> <span data-ttu-id="77f15-114">用于指定所指的**ulbLpszLabelName**成员标签的格式的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="77f15-114">Bitmask of flags used to designate the format of the label pointed to by the **ulbLpszLabelName** member.</span></span> <span data-ttu-id="77f15-115">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="77f15-115">The following flag can be set:</span></span> 
    
<span data-ttu-id="77f15-116">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="77f15-116">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="77f15-117">标签为 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="77f15-117">The label is in Unicode format.</span></span> <span data-ttu-id="77f15-118">如果未设置 MAPI_UNICODE 标志，标签为 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="77f15-118">If the MAPI_UNICODE flag is not set, the label is in ANSI format.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="77f15-119">说明</span><span class="sxs-lookup"><span data-stu-id="77f15-119">Remarks</span></span>

<span data-ttu-id="77f15-120">**DTBLLABEL**结构介绍与另一种控件添加到该控件的含义显示一个标签控件文本。</span><span class="sxs-lookup"><span data-stu-id="77f15-120">A **DTBLLABEL** structure describes a label control text that is displayed with another type of control to add meaning to that control.</span></span> <span data-ttu-id="77f15-121">例如，大多数编辑控件位于旁边通知的类型信息的用户输入的标签。</span><span class="sxs-lookup"><span data-stu-id="77f15-121">For example, most edit controls are positioned next to labels to inform the user of the type of information to be entered.</span></span> <span data-ttu-id="77f15-122">某些控件，如组框和单选按钮，将保留其自己的标签。</span><span class="sxs-lookup"><span data-stu-id="77f15-122">Some controls, such as group boxes and radio buttons, hold their own labels.</span></span> 
  
<span data-ttu-id="77f15-123">标签可以包括 Windows 加速键，标识为关注连字符的字符 (&amp;)。</span><span class="sxs-lookup"><span data-stu-id="77f15-123">The label can include a Windows accelerator, identified as the character following the ampersand (&amp;).</span></span> <span data-ttu-id="77f15-124">按下加速键将焦点放入第一个 nonlabel，nonbutton 关注此标签显示表中的控件。</span><span class="sxs-lookup"><span data-stu-id="77f15-124">Pressing the accelerator key puts the focus in the first nonlabel, nonbutton control following this label in the display table.</span></span>
  
<span data-ttu-id="77f15-125">没有支持多行标签。</span><span class="sxs-lookup"><span data-stu-id="77f15-125">There is no support for multiline labels.</span></span> <span data-ttu-id="77f15-126">显示多行需要多个标签。</span><span class="sxs-lookup"><span data-stu-id="77f15-126">Showing multiple lines requires multiple labels.</span></span>
  
<span data-ttu-id="77f15-127">不能设置为只读的编辑控件中使用标签。</span><span class="sxs-lookup"><span data-stu-id="77f15-127">It is not possible to use a label as a read-only edit control.</span></span> <span data-ttu-id="77f15-128">区别在于，可以选择并复制而标签不能编辑控件。</span><span class="sxs-lookup"><span data-stu-id="77f15-128">The difference is that an edit control can be selected and copied whereas a label cannot.</span></span> 
  
<span data-ttu-id="77f15-129">显示表的概述，请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="77f15-129">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="77f15-130">有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="77f15-130">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="77f15-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77f15-131">See also</span></span>



[<span data-ttu-id="77f15-132">DTCTL</span><span class="sxs-lookup"><span data-stu-id="77f15-132">DTCTL</span></span>](dtctl.md)


[<span data-ttu-id="77f15-133">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="77f15-133">MAPI Structures</span></span>](mapi-structures.md)

