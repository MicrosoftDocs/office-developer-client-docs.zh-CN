---
title: 创建显示表和相关结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a8548040-13ed-4a9f-a7ca-de610f94d7df
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 350272324c3827f4630f0cf35e3ade0ff213ac4d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416242"
---
# <a name="creating-display-tables-and-related-structures"></a><span data-ttu-id="c93f4-103">创建显示表和相关结构</span><span class="sxs-lookup"><span data-stu-id="c93f4-103">Creating display tables and related structures</span></span>
  
<span data-ttu-id="c93f4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c93f4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c93f4-105">创建显示表类似于编写带有脚本语言的程序。</span><span class="sxs-lookup"><span data-stu-id="c93f4-105">Creating a display table is similar to writing a program with a scripting language.</span></span> <span data-ttu-id="c93f4-106">您可以通过调用[BuildDisplayTable](builddisplaytable.md)或编写自定义代码来填充表的行和列, 来创建显示表。</span><span class="sxs-lookup"><span data-stu-id="c93f4-106">You can create a display table either by calling [BuildDisplayTable](builddisplaytable.md) or writing custom code to populate the rows and columns of the table.</span></span> <span data-ttu-id="c93f4-107">通常情况下, 应使用**BuildDisplayTable**技术, 因为它更简单。</span><span class="sxs-lookup"><span data-stu-id="c93f4-107">In general, you should use the **BuildDisplayTable** technique because it is simpler.</span></span> 
  
<span data-ttu-id="c93f4-108">在您可以调用**BuildDisplayTable**以提示 MAPI 创建显示表之前, 必须生成一个结构层次结构。</span><span class="sxs-lookup"><span data-stu-id="c93f4-108">Before you can call **BuildDisplayTable** to prompt MAPI to create a display table, there is a hierarchy of structures that you must build.</span></span> <span data-ttu-id="c93f4-109">顶级结构[DTPAGE](dtpage.md)描述单个选项卡式属性页。</span><span class="sxs-lookup"><span data-stu-id="c93f4-109">The top-level structure, [DTPAGE](dtpage.md), describes a single tabbed property page.</span></span> <span data-ttu-id="c93f4-110">在每个**DTPAGE**结构中, 都是一个用于描述单个控件 (如编辑框或选项按钮) 的[DTCTL](dtctl.md)结构。</span><span class="sxs-lookup"><span data-stu-id="c93f4-110">In every **DTPAGE** structure is a [DTCTL](dtctl.md) structure that describes a single control, such as an edit box or an option button.</span></span> <span data-ttu-id="c93f4-111">每个**DTCTL**结构都包含一个特定于控件类型的结构。</span><span class="sxs-lookup"><span data-stu-id="c93f4-111">Each **DTCTL** structure contains a structure that is specific to the type of control.</span></span> <span data-ttu-id="c93f4-112">例如, 如果**DTCTL**结构描述编辑框控件, 它将包含一个**DTBLEDIT**结构。</span><span class="sxs-lookup"><span data-stu-id="c93f4-112">For example, if the **DTCTL** structure describes an edit box control, it will contain a **DTBLEDIT** structure.</span></span> <span data-ttu-id="c93f4-113">选项按钮的**DTCTL**结构包含**DTBLRADIOBUTTON**结构。</span><span class="sxs-lookup"><span data-stu-id="c93f4-113">The **DTCTL** structure for an option button contains a **DTBLRADIOBUTTON** structure.</span></span> 
  
<span data-ttu-id="c93f4-114">这些结构直接与**BuildDisplayTable**相关联。它们在此函数的上下文之外没有任何意义。</span><span class="sxs-lookup"><span data-stu-id="c93f4-114">These structures relate directly to **BuildDisplayTable**; they have no meaning outside the context of this function.</span></span> <span data-ttu-id="c93f4-115">调用**BuildDisplayTable**时, 会将一个或多个**DTPAGE**结构作为输入参数传递。</span><span class="sxs-lookup"><span data-stu-id="c93f4-115">When you call **BuildDisplayTable**, you pass one or more **DTPAGE** structures as input parameters.</span></span> <span data-ttu-id="c93f4-116">**DTPAGE**结构包含**DTCTL**结构的数组以及数组中**DTCTL**结构的数目。</span><span class="sxs-lookup"><span data-stu-id="c93f4-116">The **DTPAGE** structures contain an array of **DTCTL** structures and a count of the number of **DTCTL** structures in the array.</span></span> <span data-ttu-id="c93f4-117">对话框中显示的每个控件都有一个结构。</span><span class="sxs-lookup"><span data-stu-id="c93f4-117">There is one structure for every control to display in the dialog box.</span></span> <span data-ttu-id="c93f4-118">**DTPAGE**结构还具有一个字符串, 表示相应的帮助文件和对话框资源的名称。</span><span class="sxs-lookup"><span data-stu-id="c93f4-118">**DTPAGE** structures also have a character string that represents the name of a corresponding Help file and dialog box resource.</span></span> 
  
<span data-ttu-id="c93f4-119">**DTPAGE**结构中的每个**DTCTL**结构都包含用于设置控件属性的以下数据:</span><span class="sxs-lookup"><span data-stu-id="c93f4-119">Each **DTCTL** structure in a **DTPAGE** structure contains the following data that is used to set properties for the control:</span></span> 
  
- <span data-ttu-id="c93f4-120">用于设置**PR_CONTROL_TYPE** ([PidTagControlType](pidtagcontroltype-canonical-property.md)) 的控件类型。</span><span class="sxs-lookup"><span data-stu-id="c93f4-120">The control type for setting **PR_CONTROL_TYPE** ([PidTagControlType](pidtagcontroltype-canonical-property.md)).</span></span>
    
- <span data-ttu-id="c93f4-121">用于设置**PR_CONTROL_FLAGS** ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)) 的控件标志。</span><span class="sxs-lookup"><span data-stu-id="c93f4-121">Control flags for setting **PR_CONTROL_FLAGS** ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)).</span></span>
    
- <span data-ttu-id="c93f4-122">用于设置**PR_CONTROL_ID** ([PidTagControlId](pidtagcontrolid-canonical-property.md)) 的通知数据。</span><span class="sxs-lookup"><span data-stu-id="c93f4-122">Notification data for setting **PR_CONTROL_ID** ([PidTagControlId](pidtagcontrolid-canonical-property.md)).</span></span>
    
- <span data-ttu-id="c93f4-123">用于设置**PR_CONTROL_STRUCTURE** ([PidTagControlStructure](pidtagcontrolstructure-canonical-property.md)) 的控制结构。</span><span class="sxs-lookup"><span data-stu-id="c93f4-123">The control structure for setting **PR_CONTROL_STRUCTURE** ([PidTagControlStructure](pidtagcontrolstructure-canonical-property.md)).</span></span>
    
<span data-ttu-id="c93f4-124">**DTCTL**结构还包含资源标识符和 "编辑" 和 "组合框" 控件 (一个字符筛选器)。</span><span class="sxs-lookup"><span data-stu-id="c93f4-124">**DTCTL** structures also contain a resource identifier and, for edit and combo box controls, a character filter.</span></span> 
  
<span data-ttu-id="c93f4-125">**DTCTL**结构的控制结构成员描述了控件类型所特有的数据。</span><span class="sxs-lookup"><span data-stu-id="c93f4-125">The control structure member of a **DTCTL** structure describes the data that is unique for the type of control.</span></span> <span data-ttu-id="c93f4-126">MAPI 为每种控件类型定义了不同的结构。</span><span class="sxs-lookup"><span data-stu-id="c93f4-126">MAPI defines a different structure for each control type.</span></span> <span data-ttu-id="c93f4-127">例如, 编辑控件的数据由**DTBLEDIT**结构表示;列表框中的数据由**DTBLLBX**结构表示。</span><span class="sxs-lookup"><span data-stu-id="c93f4-127">For example, the data of an edit control is represented by a **DTBLEDIT** structure; the data of a list box is represented by a **DTBLLBX** structure.</span></span> 
  
<span data-ttu-id="c93f4-128">三种类型的显示表结构之间的关系如下图所示。</span><span class="sxs-lookup"><span data-stu-id="c93f4-128">The relationship between the three types of display table structures is shown in the following illustration.</span></span> <span data-ttu-id="c93f4-129">此显示表所描述的对话框包含两个控件: 标签和编辑控件。</span><span class="sxs-lookup"><span data-stu-id="c93f4-129">The dialog box described by this display table has two controls: a label and an edit control.</span></span> <span data-ttu-id="c93f4-130">**DTBLLBX**结构具有一个 label 偏移量成员, 这是几个控制结构, 用于描述标签的字符串的起始位置。</span><span class="sxs-lookup"><span data-stu-id="c93f4-130">The **DTBLLBX** structure has a label offset member, as do several of the control structures, that describes where the character string for the label begins.</span></span> <span data-ttu-id="c93f4-131">标签字符字符串通常放在紧随结构之后的内存中。</span><span class="sxs-lookup"><span data-stu-id="c93f4-131">Label character strings are typically placed in memory immediately following the structure.</span></span> 
  
<span data-ttu-id="c93f4-132">**显示表格结构**</span><span class="sxs-lookup"><span data-stu-id="c93f4-132">**Display table structures**</span></span>
  
<span data-ttu-id="c93f4-133">![显示表结构](media/dtstruct.gif "显示表结构")</span><span class="sxs-lookup"><span data-stu-id="c93f4-133">![Display table structures](media/dtstruct.gif "Display table structures")</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c93f4-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c93f4-134">See also</span></span>

- [<span data-ttu-id="c93f4-135">显示表实现</span><span class="sxs-lookup"><span data-stu-id="c93f4-135">Display table implementation</span></span>](display-table-implementation.md)

