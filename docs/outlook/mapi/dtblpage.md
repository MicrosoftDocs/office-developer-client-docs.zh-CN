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
ms.openlocfilehash: bd0caff8a6c7834bdd01ef4be64805bde66dd6d9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578820"
---
# <a name="dtblpage"></a><span data-ttu-id="75c4e-103">DTBLPAGE</span><span class="sxs-lookup"><span data-stu-id="75c4e-103">DTBLPAGE</span></span>

  
  
<span data-ttu-id="75c4e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="75c4e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="75c4e-105">描述将显示表中生成的对话框中使用的选项卡式的页面。</span><span class="sxs-lookup"><span data-stu-id="75c4e-105">Describes a tabbed page that will be used in a dialog box that is built from a display table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="75c4e-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="75c4e-106">Header file:</span></span>  <br/> |<span data-ttu-id="75c4e-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="75c4e-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="75c4e-108">相关的宏：</span><span class="sxs-lookup"><span data-stu-id="75c4e-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="75c4e-109">SizedDtblPage</span><span class="sxs-lookup"><span data-stu-id="75c4e-109">SizedDtblPage</span></span>](sizeddtblpage.md) <br/> |
   
```cpp
typedef struct _DTBLPAGE
{
  ULONG ulbLpszLabel;
  ULONG ulFlags;
  ULONG ulbLpszComponent;
  ULONG ulContext;
} DTBLPAGE, FAR *LPDTBLPAGE;

```

## <a name="members"></a><span data-ttu-id="75c4e-110">Members</span><span class="sxs-lookup"><span data-stu-id="75c4e-110">Members</span></span>

 <span data-ttu-id="75c4e-111">**ulbLpszLabel**</span><span class="sxs-lookup"><span data-stu-id="75c4e-111">**ulbLpszLabel**</span></span>
  
> <span data-ttu-id="75c4e-112">在页面选项卡的字符的字符串标签的内存中的位置。</span><span class="sxs-lookup"><span data-stu-id="75c4e-112">Position in memory of the character string label for the page tab.</span></span>
    
 <span data-ttu-id="75c4e-113">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="75c4e-113">**ulFlags**</span></span>
  
> <span data-ttu-id="75c4e-114">用于指定所指的**ulbLpszLabelName**成员标签的格式的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="75c4e-114">Bitmask of flags used to designate the format of the label pointed to by the **ulbLpszLabelName** member.</span></span> <span data-ttu-id="75c4e-115">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="75c4e-115">The following flag can be set:</span></span> 
    
<span data-ttu-id="75c4e-116">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="75c4e-116">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="75c4e-117">标签为 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="75c4e-117">The label is in Unicode format.</span></span> <span data-ttu-id="75c4e-118">如果未设置 MAPI_UNICODE 标志，标签为 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="75c4e-118">If the MAPI_UNICODE flag is not set, the label is in ANSI format.</span></span>
    
 <span data-ttu-id="75c4e-119">**ulbLpszComponent**</span><span class="sxs-lookup"><span data-stu-id="75c4e-119">**ulbLpszComponent**</span></span>
  
> <span data-ttu-id="75c4e-120">用于标识 MAPISVC 中的 **[帮助文件映射]** 节字符串的内存中的位置。INF 配置文件或 0。</span><span class="sxs-lookup"><span data-stu-id="75c4e-120">Position in memory of a character string identifying the **[Help File Mappings]** section in the MAPISVC.INF configuration file or 0.</span></span> <span data-ttu-id="75c4e-121">在文件名 MAPISVC 中出现的情况下。INF 部分可以由用户，用于通过单击对话框中的**帮助**按钮访问选项卡式页上的扩展的帮助。</span><span class="sxs-lookup"><span data-stu-id="75c4e-121">The file name appearing in the MAPISVC.INF section can be used by a user to access extended Help for the tabbed page by clicking the **Help** button in the dialog box.</span></span> <span data-ttu-id="75c4e-122">有关 MAPISVC 中的条目的详细信息。INF，请参阅[文件格式的 MAPISVC。INF](file-format-of-mapisvc-inf.md)。</span><span class="sxs-lookup"><span data-stu-id="75c4e-122">For more information about the entries in MAPISVC.INF, see [File Format of MAPISVC.INF](file-format-of-mapisvc-inf.md).</span></span>
    
 <span data-ttu-id="75c4e-123">**ulContext**</span><span class="sxs-lookup"><span data-stu-id="75c4e-123">**ulContext**</span></span>
  
> <span data-ttu-id="75c4e-124">定义由**ulbLpszComponent**成员在字符串中选项卡式页面的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="75c4e-124">A unique identifier for the tabbed page in the string defined by the **ulbLpszComponent** member.</span></span> <span data-ttu-id="75c4e-125">**UlbLpszComponent**成员和**ulContext**成员必须都为非零值来**帮助**按钮正常工作。</span><span class="sxs-lookup"><span data-stu-id="75c4e-125">The **ulbLpszComponent** member and the **ulContext** member must both be nonzero for the **Help** button to work.</span></span> <span data-ttu-id="75c4e-126">如果此标识符为 0，组件字符串为 NULL，则没有与页面相关的帮助。</span><span class="sxs-lookup"><span data-stu-id="75c4e-126">If this identifier is zero and the component string is NULL, there is no Help associated with the page.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="75c4e-127">注解</span><span class="sxs-lookup"><span data-stu-id="75c4e-127">Remarks</span></span>

<span data-ttu-id="75c4e-128">**DTBLPAGE**结构介绍用于分隔多个相关的对话框的控件的选项卡式的页面。</span><span class="sxs-lookup"><span data-stu-id="75c4e-128">A **DTBLPAGE** structure describes a tabbed page a control that is used to separate several related dialog boxes.</span></span> <span data-ttu-id="75c4e-129">通常，这些对话框是用于显示配置、 消息或收件人选项的属性表。</span><span class="sxs-lookup"><span data-stu-id="75c4e-129">Typically, these dialog boxes are property sheets for displaying configuration, message, or recipient options.</span></span> <span data-ttu-id="75c4e-130">通过单击选项卡，用户可以张工作表之间切换。</span><span class="sxs-lookup"><span data-stu-id="75c4e-130">By clicking the tab, the user can switch from one sheet to another.</span></span> 
  
<span data-ttu-id="75c4e-131">组件字符串和上下文标识符提供有关扩展的帮助是否可用于选项卡式页面的信息。</span><span class="sxs-lookup"><span data-stu-id="75c4e-131">The component string and context identifier provide information about whether extended Help is available for the tabbed page.</span></span> <span data-ttu-id="75c4e-132">如果扩展的帮助可用，组件字符串和上下文标识符将提供有关如何访问它的信息。</span><span class="sxs-lookup"><span data-stu-id="75c4e-132">If extended Help is available, the component string and context identifier will provide information about how to access it.</span></span> <span data-ttu-id="75c4e-133">组件字符串映射到的帮助文件;上下文标识符映射到初始的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="75c4e-133">The component string maps to the Help file; the context identifier maps to the initial Help topic.</span></span> <span data-ttu-id="75c4e-134">如果组件字符串为 NULL 的上下文标识符为零，则扩展的帮助不可用。</span><span class="sxs-lookup"><span data-stu-id="75c4e-134">If the context identifier is zero and the component string is NULL, extended Help is not available.</span></span>
  
<span data-ttu-id="75c4e-135">显示表的概述，请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="75c4e-135">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="75c4e-136">有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="75c4e-136">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="75c4e-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75c4e-137">See also</span></span>



[<span data-ttu-id="75c4e-138">DTCTL</span><span class="sxs-lookup"><span data-stu-id="75c4e-138">DTCTL</span></span>](dtctl.md)


[<span data-ttu-id="75c4e-139">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="75c4e-139">MAPI Structures</span></span>](mapi-structures.md)

