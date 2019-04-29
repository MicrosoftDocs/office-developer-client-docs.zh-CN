---
title: DTBLPAGE
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTBLPAGE
api_type:
- COM
ms.assetid: f899f434-a5d7-4b4f-98f9-c14c9f21b24b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6f3d98a3133d79f78f4eb676d49ec85ef5a359f1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423998"
---
# <a name="dtblpage"></a><span data-ttu-id="7110f-103">DTBLPAGE</span><span class="sxs-lookup"><span data-stu-id="7110f-103">DTBLPAGE</span></span>

  
  
<span data-ttu-id="7110f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7110f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7110f-105">介绍将在从显示表生成的对话框中使用的选项卡式页面。</span><span class="sxs-lookup"><span data-stu-id="7110f-105">Describes a tabbed page that will be used in a dialog box that is built from a display table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7110f-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="7110f-106">Header file:</span></span>  <br/> |<span data-ttu-id="7110f-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="7110f-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="7110f-108">相关宏:</span><span class="sxs-lookup"><span data-stu-id="7110f-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="7110f-109">SizedDtblPage</span><span class="sxs-lookup"><span data-stu-id="7110f-109">SizedDtblPage</span></span>](sizeddtblpage.md) <br/> |
   
```cpp
typedef struct _DTBLPAGE
{
  ULONG ulbLpszLabel;
  ULONG ulFlags;
  ULONG ulbLpszComponent;
  ULONG ulContext;
} DTBLPAGE, FAR *LPDTBLPAGE;

```

## <a name="members"></a><span data-ttu-id="7110f-110">Members</span><span class="sxs-lookup"><span data-stu-id="7110f-110">Members</span></span>

 <span data-ttu-id="7110f-111">**ulbLpszLabel**</span><span class="sxs-lookup"><span data-stu-id="7110f-111">**ulbLpszLabel**</span></span>
  
> <span data-ttu-id="7110f-112">页面选项卡的字符字符串标签在内存中的位置。</span><span class="sxs-lookup"><span data-stu-id="7110f-112">Position in memory of the character string label for the page tab.</span></span>
    
 <span data-ttu-id="7110f-113">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="7110f-113">**ulFlags**</span></span>
  
> <span data-ttu-id="7110f-114">标志的位掩码, 用于指定**ulbLpszLabelName**成员指向的标签的格式。</span><span class="sxs-lookup"><span data-stu-id="7110f-114">Bitmask of flags used to designate the format of the label pointed to by the **ulbLpszLabelName** member.</span></span> <span data-ttu-id="7110f-115">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="7110f-115">The following flag can be set:</span></span> 
    
<span data-ttu-id="7110f-116">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="7110f-116">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="7110f-117">标签采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="7110f-117">The label is in Unicode format.</span></span> <span data-ttu-id="7110f-118">如果未设置 MAPI_UNICODE 标志, 则标签将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="7110f-118">If the MAPI_UNICODE flag is not set, the label is in ANSI format.</span></span>
    
 <span data-ttu-id="7110f-119">**ulbLpszComponent**</span><span class="sxs-lookup"><span data-stu-id="7110f-119">**ulbLpszComponent**</span></span>
  
> <span data-ttu-id="7110f-120">在内存中标识 mapisvc.inf 中的 **[帮助文件映射]** 部分的字符串的位置 (以字符为单位)。INF 配置文件或0。</span><span class="sxs-lookup"><span data-stu-id="7110f-120">Position in memory of a character string identifying the **[Help File Mappings]** section in the MAPISVC.INF configuration file or 0.</span></span> <span data-ttu-id="7110f-121">mapisvc.inf 中显示的文件名。INF 节可供用户用来通过单击对话框中的 "**帮助**" 按钮来访问选项卡式页面的扩展帮助。</span><span class="sxs-lookup"><span data-stu-id="7110f-121">The file name appearing in the MAPISVC.INF section can be used by a user to access extended Help for the tabbed page by clicking the **Help** button in the dialog box.</span></span> <span data-ttu-id="7110f-122">有关 mapisvc.inf 中的条目的详细信息。INF, 请参阅[mapisvc.inf 的文件格式。INF](file-format-of-mapisvc-inf.md)。</span><span class="sxs-lookup"><span data-stu-id="7110f-122">For more information about the entries in MAPISVC.INF, see [File Format of MAPISVC.INF](file-format-of-mapisvc-inf.md).</span></span>
    
 <span data-ttu-id="7110f-123">**ulContext**</span><span class="sxs-lookup"><span data-stu-id="7110f-123">**ulContext**</span></span>
  
> <span data-ttu-id="7110f-124">**ulbLpszComponent**成员定义的字符串中选项卡式页面的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="7110f-124">A unique identifier for the tabbed page in the string defined by the **ulbLpszComponent** member.</span></span> <span data-ttu-id="7110f-125">**ulbLpszComponent**成员和**ulContext**成员必须均为非零, "**帮助**" 按钮才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="7110f-125">The **ulbLpszComponent** member and the **ulContext** member must both be nonzero for the **Help** button to work.</span></span> <span data-ttu-id="7110f-126">如果此标识符为零, 并且组件字符串为 NULL, 则没有与该页面关联的帮助。</span><span class="sxs-lookup"><span data-stu-id="7110f-126">If this identifier is zero and the component string is NULL, there is no Help associated with the page.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="7110f-127">说明</span><span class="sxs-lookup"><span data-stu-id="7110f-127">Remarks</span></span>

<span data-ttu-id="7110f-128">**DTBLPAGE**结构描述了一个用于分隔多个相关对话框的选项卡式页面控件。</span><span class="sxs-lookup"><span data-stu-id="7110f-128">A **DTBLPAGE** structure describes a tabbed page a control that is used to separate several related dialog boxes.</span></span> <span data-ttu-id="7110f-129">通常情况下, 这些对话框是用于显示配置、消息或收件人选项的属性表。</span><span class="sxs-lookup"><span data-stu-id="7110f-129">Typically, these dialog boxes are property sheets for displaying configuration, message, or recipient options.</span></span> <span data-ttu-id="7110f-130">通过单击该选项卡, 用户可以从一张工作表切换到另一张。</span><span class="sxs-lookup"><span data-stu-id="7110f-130">By clicking the tab, the user can switch from one sheet to another.</span></span> 
  
<span data-ttu-id="7110f-131">组件字符串和上下文标识符提供有关扩展的帮助是否适用于选项卡式页面的信息。</span><span class="sxs-lookup"><span data-stu-id="7110f-131">The component string and context identifier provide information about whether extended Help is available for the tabbed page.</span></span> <span data-ttu-id="7110f-132">如果扩展的帮助可用, 组件字符串和上下文标识符将提供有关如何访问的信息。</span><span class="sxs-lookup"><span data-stu-id="7110f-132">If extended Help is available, the component string and context identifier will provide information about how to access it.</span></span> <span data-ttu-id="7110f-133">组件字符串映射到帮助文件;上下文标识符映射到初始帮助主题。</span><span class="sxs-lookup"><span data-stu-id="7110f-133">The component string maps to the Help file; the context identifier maps to the initial Help topic.</span></span> <span data-ttu-id="7110f-134">如果上下文标识符为零, 并且组件字符串为 NULL, 则扩展帮助不可用。</span><span class="sxs-lookup"><span data-stu-id="7110f-134">If the context identifier is zero and the component string is NULL, extended Help is not available.</span></span>
  
<span data-ttu-id="7110f-135">有关显示表的概述, 请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="7110f-135">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="7110f-136">有关如何实现显示表的信息, 请参阅[实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="7110f-136">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7110f-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7110f-137">See also</span></span>



[<span data-ttu-id="7110f-138">DTCTL</span><span class="sxs-lookup"><span data-stu-id="7110f-138">DTCTL</span></span>](dtctl.md)


[<span data-ttu-id="7110f-139">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="7110f-139">MAPI Structures</span></span>](mapi-structures.md)

