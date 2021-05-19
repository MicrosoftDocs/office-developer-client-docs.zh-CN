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
# <a name="dtblpage"></a><span data-ttu-id="5a172-103">DTBLPAGE</span><span class="sxs-lookup"><span data-stu-id="5a172-103">DTBLPAGE</span></span>

  
  
<span data-ttu-id="5a172-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5a172-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5a172-105">描述将在从显示表构建的对话框中使用的选项卡式页面。</span><span class="sxs-lookup"><span data-stu-id="5a172-105">Describes a tabbed page that will be used in a dialog box that is built from a display table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="5a172-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="5a172-106">Header file:</span></span>  <br/> |<span data-ttu-id="5a172-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5a172-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="5a172-108">相关宏：</span><span class="sxs-lookup"><span data-stu-id="5a172-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="5a172-109">SizedDtblPage</span><span class="sxs-lookup"><span data-stu-id="5a172-109">SizedDtblPage</span></span>](sizeddtblpage.md) <br/> |
   
```cpp
typedef struct _DTBLPAGE
{
  ULONG ulbLpszLabel;
  ULONG ulFlags;
  ULONG ulbLpszComponent;
  ULONG ulContext;
} DTBLPAGE, FAR *LPDTBLPAGE;

```

## <a name="members"></a><span data-ttu-id="5a172-110">Members</span><span class="sxs-lookup"><span data-stu-id="5a172-110">Members</span></span>

 <span data-ttu-id="5a172-111">**ulbLpszLabel**</span><span class="sxs-lookup"><span data-stu-id="5a172-111">**ulbLpszLabel**</span></span>
  
> <span data-ttu-id="5a172-112">在页面选项卡的字符字符串标签的内存中的位置。</span><span class="sxs-lookup"><span data-stu-id="5a172-112">Position in memory of the character string label for the page tab.</span></span>
    
 <span data-ttu-id="5a172-113">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="5a172-113">**ulFlags**</span></span>
  
> <span data-ttu-id="5a172-114">用于指定 **ulbLpszLabelName** 成员指向的标签格式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="5a172-114">Bitmask of flags used to designate the format of the label pointed to by the **ulbLpszLabelName** member.</span></span> <span data-ttu-id="5a172-115">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="5a172-115">The following flag can be set:</span></span> 
    
<span data-ttu-id="5a172-116">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="5a172-116">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="5a172-117">标签采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="5a172-117">The label is in Unicode format.</span></span> <span data-ttu-id="5a172-118">如果未MAPI_UNICODE，则标签采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="5a172-118">If the MAPI_UNICODE flag is not set, the label is in ANSI format.</span></span>
    
 <span data-ttu-id="5a172-119">**ulbLpszComponent**</span><span class="sxs-lookup"><span data-stu-id="5a172-119">**ulbLpszComponent**</span></span>
  
> <span data-ttu-id="5a172-120">标识 MAPISVC 中的 **[帮助文件映射]** 部分的字符字符串的内存中的位置。INF 配置文件或 0。</span><span class="sxs-lookup"><span data-stu-id="5a172-120">Position in memory of a character string identifying the **[Help File Mappings]** section in the MAPISVC.INF configuration file or 0.</span></span> <span data-ttu-id="5a172-121">显示在 MAPISVC 中的文件名。用户可以使用 INF 部分通过单击对话框中的"帮助"按钮访问选项卡式页面的扩展帮助。</span><span class="sxs-lookup"><span data-stu-id="5a172-121">The file name appearing in the MAPISVC.INF section can be used by a user to access extended Help for the tabbed page by clicking the **Help** button in the dialog box.</span></span> <span data-ttu-id="5a172-122">有关 MAPISVC 中的条目详细信息。INF，请参阅 [MAPISVC 的文件格式。INF](file-format-of-mapisvc-inf.md)。</span><span class="sxs-lookup"><span data-stu-id="5a172-122">For more information about the entries in MAPISVC.INF, see [File Format of MAPISVC.INF](file-format-of-mapisvc-inf.md).</span></span>
    
 <span data-ttu-id="5a172-123">**ulContext**</span><span class="sxs-lookup"><span data-stu-id="5a172-123">**ulContext**</span></span>
  
> <span data-ttu-id="5a172-124">**ulbLpszComponent** 成员定义的字符串中选项卡式页面的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="5a172-124">A unique identifier for the tabbed page in the string defined by the **ulbLpszComponent** member.</span></span> <span data-ttu-id="5a172-125">**ulbLpszComponent** 成员和 **ulContext** 成员必须为非零，"帮助"**按钮必须** 都为非零。</span><span class="sxs-lookup"><span data-stu-id="5a172-125">The **ulbLpszComponent** member and the **ulContext** member must both be nonzero for the **Help** button to work.</span></span> <span data-ttu-id="5a172-126">如果此标识符为零且组件字符串为 NULL，则没有与页面关联的帮助。</span><span class="sxs-lookup"><span data-stu-id="5a172-126">If this identifier is zero and the component string is NULL, there is no Help associated with the page.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="5a172-127">备注</span><span class="sxs-lookup"><span data-stu-id="5a172-127">Remarks</span></span>

<span data-ttu-id="5a172-128">**DTBLPAGE** 结构描述选项卡式页面用于分隔多个相关对话框的控件。</span><span class="sxs-lookup"><span data-stu-id="5a172-128">A **DTBLPAGE** structure describes a tabbed page a control that is used to separate several related dialog boxes.</span></span> <span data-ttu-id="5a172-129">通常，这些对话框是显示配置、邮件或收件人选项的属性表。</span><span class="sxs-lookup"><span data-stu-id="5a172-129">Typically, these dialog boxes are property sheets for displaying configuration, message, or recipient options.</span></span> <span data-ttu-id="5a172-130">通过单击该选项卡，用户可以从一个工作表切换到另一个工作表。</span><span class="sxs-lookup"><span data-stu-id="5a172-130">By clicking the tab, the user can switch from one sheet to another.</span></span> 
  
<span data-ttu-id="5a172-131">组件字符串和上下文标识符提供有关扩展帮助是否可用于选项卡式页面的信息。</span><span class="sxs-lookup"><span data-stu-id="5a172-131">The component string and context identifier provide information about whether extended Help is available for the tabbed page.</span></span> <span data-ttu-id="5a172-132">如果扩展帮助可用，则组件字符串和上下文标识符将提供有关如何访问它的信息。</span><span class="sxs-lookup"><span data-stu-id="5a172-132">If extended Help is available, the component string and context identifier will provide information about how to access it.</span></span> <span data-ttu-id="5a172-133">组件字符串映射到帮助文件;上下文标识符映射到初始帮助主题。</span><span class="sxs-lookup"><span data-stu-id="5a172-133">The component string maps to the Help file; the context identifier maps to the initial Help topic.</span></span> <span data-ttu-id="5a172-134">如果上下文标识符为零且组件字符串为 NULL，则扩展帮助不可用。</span><span class="sxs-lookup"><span data-stu-id="5a172-134">If the context identifier is zero and the component string is NULL, extended Help is not available.</span></span>
  
<span data-ttu-id="5a172-135">有关显示表的概述，请参阅显示 [表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="5a172-135">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="5a172-136">若要了解如何实现显示表，请参阅 [实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="5a172-136">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5a172-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a172-137">See also</span></span>



[<span data-ttu-id="5a172-138">DTCTL</span><span class="sxs-lookup"><span data-stu-id="5a172-138">DTCTL</span></span>](dtctl.md)


[<span data-ttu-id="5a172-139">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="5a172-139">MAPI Structures</span></span>](mapi-structures.md)

