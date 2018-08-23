---
title: 创建显示表和相关的结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a8548040-13ed-4a9f-a7ca-de610f94d7df
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e17306e2b90f26dcef0a0214e78080fe78752e5f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568565"
---
# <a name="creating-display-tables-and-related-structures"></a><span data-ttu-id="ce1ca-103">创建显示表和相关的结构</span><span class="sxs-lookup"><span data-stu-id="ce1ca-103">Creating display tables and related structures</span></span>
  
<span data-ttu-id="ce1ca-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ce1ca-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ce1ca-105">创建显示表是类似于编写脚本语言的程序。</span><span class="sxs-lookup"><span data-stu-id="ce1ca-105">Creating a display table is similar to writing a program with a scripting language.</span></span> <span data-ttu-id="ce1ca-106">您可以创建显示表通过调用[BuildDisplayTable](builddisplaytable.md)或编写自定义代码以填充的行和列的表。</span><span class="sxs-lookup"><span data-stu-id="ce1ca-106">You can create a display table either by calling [BuildDisplayTable](builddisplaytable.md) or writing custom code to populate the rows and columns of the table.</span></span> <span data-ttu-id="ce1ca-107">一般情况下，您应使用**BuildDisplayTable**技术，因为它是简单。</span><span class="sxs-lookup"><span data-stu-id="ce1ca-107">In general, you should use the **BuildDisplayTable** technique because it is simpler.</span></span> 
  
<span data-ttu-id="ce1ca-108">您可以调用**BuildDisplayTable**提示 MAPI 创建显示表之前，没有的层次结构，必须建立。</span><span class="sxs-lookup"><span data-stu-id="ce1ca-108">Before you can call **BuildDisplayTable** to prompt MAPI to create a display table, there is a hierarchy of structures that you must build.</span></span> <span data-ttu-id="ce1ca-109">顶级结构， [DTPAGE](dtpage.md)，描述单个选项卡式的属性页。</span><span class="sxs-lookup"><span data-stu-id="ce1ca-109">The top-level structure, [DTPAGE](dtpage.md), describes a single tabbed property page.</span></span> <span data-ttu-id="ce1ca-110">在每个**DTPAGE**结构是描述单个控件，例如编辑框或选项按钮的[DTCTL](dtctl.md)结构。</span><span class="sxs-lookup"><span data-stu-id="ce1ca-110">In every **DTPAGE** structure is a [DTCTL](dtctl.md) structure that describes a single control, such as an edit box or an option button.</span></span> <span data-ttu-id="ce1ca-111">每个**DTCTL**结构包含特定于控件的类型的结构。</span><span class="sxs-lookup"><span data-stu-id="ce1ca-111">Each **DTCTL** structure contains a structure that is specific to the type of control.</span></span> <span data-ttu-id="ce1ca-112">例如，如果**DTCTL**结构介绍编辑框控件，它将包含**DTBLEDIT**结构。</span><span class="sxs-lookup"><span data-stu-id="ce1ca-112">For example, if the **DTCTL** structure describes an edit box control, it will contain a **DTBLEDIT** structure.</span></span> <span data-ttu-id="ce1ca-113">选项按钮的**DTCTL**结构包含一个**DTBLRADIOBUTTON**结构。</span><span class="sxs-lookup"><span data-stu-id="ce1ca-113">The **DTCTL** structure for an option button contains a **DTBLRADIOBUTTON** structure.</span></span> 
  
<span data-ttu-id="ce1ca-114">这些结构直接相关**BuildDisplayTable**;拥有此函数的上下文之外没有意义。</span><span class="sxs-lookup"><span data-stu-id="ce1ca-114">These structures relate directly to **BuildDisplayTable**; they have no meaning outside the context of this function.</span></span> <span data-ttu-id="ce1ca-115">调用**BuildDisplayTable**时，您将作为输入参数传递一个或多个**DTPAGE**结构。</span><span class="sxs-lookup"><span data-stu-id="ce1ca-115">When you call **BuildDisplayTable**, you pass one or more **DTPAGE** structures as input parameters.</span></span> <span data-ttu-id="ce1ca-116">**DTPAGE**结构包含数组**DTCTL**结构和**DTCTL**结构数组中的数目。</span><span class="sxs-lookup"><span data-stu-id="ce1ca-116">The **DTPAGE** structures contain an array of **DTCTL** structures and a count of the number of **DTCTL** structures in the array.</span></span> <span data-ttu-id="ce1ca-117">没有要显示在对话框中每个控件的一个结构。</span><span class="sxs-lookup"><span data-stu-id="ce1ca-117">There is one structure for every control to display in the dialog box.</span></span> <span data-ttu-id="ce1ca-118">**DTPAGE**结构还具有一个字符字符串，表示相应的帮助文件和对话框框资源的名称。</span><span class="sxs-lookup"><span data-stu-id="ce1ca-118">**DTPAGE** structures also have a character string that represents the name of a corresponding Help file and dialog box resource.</span></span> 
  
<span data-ttu-id="ce1ca-119">**DTPAGE**结构中的每个**DTCTL**结构包含用于设置控件的属性的以下数据：</span><span class="sxs-lookup"><span data-stu-id="ce1ca-119">Each **DTCTL** structure in a **DTPAGE** structure contains the following data that is used to set properties for the control:</span></span> 
  
- <span data-ttu-id="ce1ca-120">设置**PR_CONTROL_TYPE** ([PidTagControlType](pidtagcontroltype-canonical-property.md)) 控件类型。</span><span class="sxs-lookup"><span data-stu-id="ce1ca-120">The control type for setting **PR_CONTROL_TYPE** ([PidTagControlType](pidtagcontroltype-canonical-property.md)).</span></span>
    
- <span data-ttu-id="ce1ca-121">用于设置**PR_CONTROL_FLAGS** ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)) 控制标志。</span><span class="sxs-lookup"><span data-stu-id="ce1ca-121">Control flags for setting **PR_CONTROL_FLAGS** ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)).</span></span>
    
- <span data-ttu-id="ce1ca-122">通知设置**PR_CONTROL_ID** ([PidTagControlId](pidtagcontrolid-canonical-property.md)) 的数据。</span><span class="sxs-lookup"><span data-stu-id="ce1ca-122">Notification data for setting **PR_CONTROL_ID** ([PidTagControlId](pidtagcontrolid-canonical-property.md)).</span></span>
    
- <span data-ttu-id="ce1ca-123">用于设置**PR_CONTROL_STRUCTURE** ([PidTagControlStructure](pidtagcontrolstructure-canonical-property.md)) 控制结构。</span><span class="sxs-lookup"><span data-stu-id="ce1ca-123">The control structure for setting **PR_CONTROL_STRUCTURE** ([PidTagControlStructure](pidtagcontrolstructure-canonical-property.md)).</span></span>
    
<span data-ttu-id="ce1ca-124">**DTCTL**结构还包含资源标识符以及编辑和组合框控件、 字符筛选器。</span><span class="sxs-lookup"><span data-stu-id="ce1ca-124">**DTCTL** structures also contain a resource identifier and, for edit and combo box controls, a character filter.</span></span> 
  
<span data-ttu-id="ce1ca-125">**DTCTL**结构的控制结构成员介绍了唯一的控件的类型的数据。</span><span class="sxs-lookup"><span data-stu-id="ce1ca-125">The control structure member of a **DTCTL** structure describes the data that is unique for the type of control.</span></span> <span data-ttu-id="ce1ca-126">MAPI 定义每个控件类型不同的结构。</span><span class="sxs-lookup"><span data-stu-id="ce1ca-126">MAPI defines a different structure for each control type.</span></span> <span data-ttu-id="ce1ca-127">例如，编辑控件的数据表示由**DTBLEDIT**结构;由**DTBLLBX**结构表示列表框的数据。</span><span class="sxs-lookup"><span data-stu-id="ce1ca-127">For example, the data of an edit control is represented by a **DTBLEDIT** structure; the data of a list box is represented by a **DTBLLBX** structure.</span></span> 
  
<span data-ttu-id="ce1ca-128">下图中显示三种类型的显示表结构之间的关系。</span><span class="sxs-lookup"><span data-stu-id="ce1ca-128">The relationship between the three types of display table structures is shown in the following illustration.</span></span> <span data-ttu-id="ce1ca-129">通过此显示表所述的对话框中有两个控件： 标签和编辑控件。</span><span class="sxs-lookup"><span data-stu-id="ce1ca-129">The dialog box described by this display table has two controls: a label and an edit control.</span></span> <span data-ttu-id="ce1ca-130">**DTBLLBX**结构有一个标签偏移的成员，如执行几个控制结构，描述标签的字符串的开始位置。</span><span class="sxs-lookup"><span data-stu-id="ce1ca-130">The **DTBLLBX** structure has a label offset member, as do several of the control structures, that describes where the character string for the label begins.</span></span> <span data-ttu-id="ce1ca-131">标签字符串通常放置在紧挨结构的内存。</span><span class="sxs-lookup"><span data-stu-id="ce1ca-131">Label character strings are typically placed in memory immediately following the structure.</span></span> 
  
<span data-ttu-id="ce1ca-132">**显示表格结构**</span><span class="sxs-lookup"><span data-stu-id="ce1ca-132">**Display table structures**</span></span>
  
<span data-ttu-id="ce1ca-133">![显示表结构](media/dtstruct.gif "显示表结构")</span><span class="sxs-lookup"><span data-stu-id="ce1ca-133">![Display table structures](media/dtstruct.gif "Display table structures")</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ce1ca-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce1ca-134">See also</span></span>

- [<span data-ttu-id="ce1ca-135">显示表实现</span><span class="sxs-lookup"><span data-stu-id="ce1ca-135">Display table implementation</span></span>](display-table-implementation.md)

