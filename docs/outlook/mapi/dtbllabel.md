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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287158"
---
# <a name="dtbllabel"></a><span data-ttu-id="c8d9a-103">DTBLLABEL</span><span class="sxs-lookup"><span data-stu-id="c8d9a-103">DTBLLABEL</span></span>

  
  
<span data-ttu-id="c8d9a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c8d9a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c8d9a-105">介绍将在从显示表生成的对话框中使用的标签。</span><span class="sxs-lookup"><span data-stu-id="c8d9a-105">Describes a label that will be used in a dialog box that is built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c8d9a-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="c8d9a-106">Header file:</span></span>  <br/> |<span data-ttu-id="c8d9a-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="c8d9a-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="c8d9a-108">相关宏</span><span class="sxs-lookup"><span data-stu-id="c8d9a-108">Related macro</span></span>  <br/> |[<span data-ttu-id="c8d9a-109">SizedDtblLabel</span><span class="sxs-lookup"><span data-stu-id="c8d9a-109">SizedDtblLabel</span></span>](sizeddtbllabel.md) <br/> |
   
```cpp
typedef struct _DTBLLABEL
{
  ULONG ulbLpszLabelName;
  ULONG ulFlags;
} DTBLLABEL, FAR *LPDTBLLABEL;

```

## <a name="members"></a><span data-ttu-id="c8d9a-110">Members</span><span class="sxs-lookup"><span data-stu-id="c8d9a-110">Members</span></span>

 <span data-ttu-id="c8d9a-111">**ulbLpszLabelName**</span><span class="sxs-lookup"><span data-stu-id="c8d9a-111">**ulbLpszLabelName**</span></span>
  
> <span data-ttu-id="c8d9a-112">字符字符串标签在内存中的位置。</span><span class="sxs-lookup"><span data-stu-id="c8d9a-112">Position in memory of the character string label.</span></span>
    
 <span data-ttu-id="c8d9a-113">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="c8d9a-113">**ulFlags**</span></span>
  
> <span data-ttu-id="c8d9a-114">标志的位掩码, 用于指定**ulbLpszLabelName**成员指向的标签的格式。</span><span class="sxs-lookup"><span data-stu-id="c8d9a-114">Bitmask of flags used to designate the format of the label pointed to by the **ulbLpszLabelName** member.</span></span> <span data-ttu-id="c8d9a-115">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="c8d9a-115">The following flag can be set:</span></span> 
    
<span data-ttu-id="c8d9a-116">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="c8d9a-116">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="c8d9a-117">标签采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="c8d9a-117">The label is in Unicode format.</span></span> <span data-ttu-id="c8d9a-118">如果未设置 MAPI_UNICODE 标志, 则标签将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="c8d9a-118">If the MAPI_UNICODE flag is not set, the label is in ANSI format.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c8d9a-119">注解</span><span class="sxs-lookup"><span data-stu-id="c8d9a-119">Remarks</span></span>

<span data-ttu-id="c8d9a-120">**DTBLLABEL**结构描述了与另一种类型的控件一起显示的标签控件文本, 以向该控件添加含义。</span><span class="sxs-lookup"><span data-stu-id="c8d9a-120">A **DTBLLABEL** structure describes a label control text that is displayed with another type of control to add meaning to that control.</span></span> <span data-ttu-id="c8d9a-121">例如, 大多数编辑控件放置在标签旁边, 以通知用户要输入的信息类型。</span><span class="sxs-lookup"><span data-stu-id="c8d9a-121">For example, most edit controls are positioned next to labels to inform the user of the type of information to be entered.</span></span> <span data-ttu-id="c8d9a-122">某些控件 (如分组框和单选按钮) 包含自己的标签。</span><span class="sxs-lookup"><span data-stu-id="c8d9a-122">Some controls, such as group boxes and radio buttons, hold their own labels.</span></span> 
  
<span data-ttu-id="c8d9a-123">该标签可以包括 Windows 加速器, 标识为 "&" 符后面的字符&amp;()。</span><span class="sxs-lookup"><span data-stu-id="c8d9a-123">The label can include a Windows accelerator, identified as the character following the ampersand (&amp;).</span></span> <span data-ttu-id="c8d9a-124">按加速键会将焦点放在显示表中此标签后面的第一个 nonlabel、nonbutton 控件中。</span><span class="sxs-lookup"><span data-stu-id="c8d9a-124">Pressing the accelerator key puts the focus in the first nonlabel, nonbutton control following this label in the display table.</span></span>
  
<span data-ttu-id="c8d9a-125">不支持多行标签。</span><span class="sxs-lookup"><span data-stu-id="c8d9a-125">There is no support for multiline labels.</span></span> <span data-ttu-id="c8d9a-126">显示多个行需要多个标签。</span><span class="sxs-lookup"><span data-stu-id="c8d9a-126">Showing multiple lines requires multiple labels.</span></span>
  
<span data-ttu-id="c8d9a-127">不能将标签用作只读的编辑控件。</span><span class="sxs-lookup"><span data-stu-id="c8d9a-127">It is not possible to use a label as a read-only edit control.</span></span> <span data-ttu-id="c8d9a-128">区别在于, 可以选择和复制编辑控件, 而不能复制标签。</span><span class="sxs-lookup"><span data-stu-id="c8d9a-128">The difference is that an edit control can be selected and copied whereas a label cannot.</span></span> 
  
<span data-ttu-id="c8d9a-129">有关显示表的概述, 请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="c8d9a-129">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="c8d9a-130">有关如何实现显示表的信息, 请参阅[实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="c8d9a-130">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c8d9a-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8d9a-131">See also</span></span>



[<span data-ttu-id="c8d9a-132">DTCTL</span><span class="sxs-lookup"><span data-stu-id="c8d9a-132">DTCTL</span></span>](dtctl.md)


[<span data-ttu-id="c8d9a-133">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="c8d9a-133">MAPI Structures</span></span>](mapi-structures.md)

