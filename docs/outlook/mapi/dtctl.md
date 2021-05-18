---
title: DTCTL
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTCTL
api_type:
- COM
ms.assetid: 6d1589e9-b171-427a-9a3e-b4154ee8ceb6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2a2ca1fba5dceb45b41c2f25a96e163f02c41440
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421499"
---
# <a name="dtctl"></a><span data-ttu-id="4fd2d-103">DTCTL</span><span class="sxs-lookup"><span data-stu-id="4fd2d-103">DTCTL</span></span>

<span data-ttu-id="4fd2d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4fd2d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4fd2d-105">描述将在基于显示表构建的对话框中使用的控件。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-105">Describes a control that will be used in a dialog box built from a display table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4fd2d-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="4fd2d-106">Header file:</span></span>  <br/> |<span data-ttu-id="4fd2d-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="4fd2d-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct
{
  ULONG ulCtlType;
  ULONG ulCtlFlags;
  LPBYTE lpbNotif;
  ULONG cbNotif;
  LPSTR lpszFilter;
  ULONG ulItemID;
  union
  {
    LPVOID lpv;
    LPDTBLLABEL lplabel;
    LPDTBLEDIT lpedit;
    LPDTBLLBX lplbx;
    LPDTBLCOMBOBOX lpcombobox;
    LPDTBLDDLBX lpddlbx;
    LPDTBLCHECKBOX lpcheckbox;
    LPDTBLGROUPBOX lpgroupbox;
    LPDTBLBUTTON lpbutton;
    LPDTBLRADIOBUTTON lpradiobutton;
    LPDTBLMVLISTBOX lpmvlbx;
    LPDTBLMVDDLBX lpmvddlbx;
    LPDTBLPAGE lppage;
  } ctl;
} DTCTL, FAR *LPDTCTL;

```

## <a name="members"></a><span data-ttu-id="4fd2d-108">Members</span><span class="sxs-lookup"><span data-stu-id="4fd2d-108">Members</span></span>

<span data-ttu-id="4fd2d-109">**ulCtlType**</span><span class="sxs-lookup"><span data-stu-id="4fd2d-109">**ulCtlType**</span></span>
  
> <span data-ttu-id="4fd2d-110">包含在 **ctl** 成员中的控件类型，对应于控件的 PR_CONTROL_TYPE ([PidTagControlType](pidtagcontroltype-canonical-property.md)) 属性。 </span><span class="sxs-lookup"><span data-stu-id="4fd2d-110">Type of control that is included in the **ctl** member and corresponds to the control's **PR_CONTROL_TYPE** ([PidTagControlType](pidtagcontroltype-canonical-property.md)) property.</span></span> <span data-ttu-id="4fd2d-111">可能的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="4fd2d-111">Possible values are as follows:</span></span>
    
<span data-ttu-id="4fd2d-112">DTCT_LABEL</span><span class="sxs-lookup"><span data-stu-id="4fd2d-112">DTCT_LABEL</span></span> 
  
> <span data-ttu-id="4fd2d-113">标签控件。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-113">Label control.</span></span>
    
<span data-ttu-id="4fd2d-114">DTCT_EDIT</span><span class="sxs-lookup"><span data-stu-id="4fd2d-114">DTCT_EDIT</span></span> 
  
> <span data-ttu-id="4fd2d-115">编辑控件。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-115">Edit control.</span></span>
    
<span data-ttu-id="4fd2d-116">DTCT_LBX</span><span class="sxs-lookup"><span data-stu-id="4fd2d-116">DTCT_LBX</span></span> 
  
> <span data-ttu-id="4fd2d-117">列表框控件。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-117">List box control.</span></span>
    
<span data-ttu-id="4fd2d-118">DTCT_COMBOBOX</span><span class="sxs-lookup"><span data-stu-id="4fd2d-118">DTCT_COMBOBOX</span></span> 
  
> <span data-ttu-id="4fd2d-119">组合框控件。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-119">Combo box control.</span></span>
    
<span data-ttu-id="4fd2d-120">DTCT_DDLBX</span><span class="sxs-lookup"><span data-stu-id="4fd2d-120">DTCT_DDLBX</span></span> 
  
> <span data-ttu-id="4fd2d-121">下拉列表控件。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-121">Drop-down list control.</span></span>
    
<span data-ttu-id="4fd2d-122">DTCT_CHECKBOX</span><span class="sxs-lookup"><span data-stu-id="4fd2d-122">DTCT_CHECKBOX</span></span> 
  
> <span data-ttu-id="4fd2d-123">复选框控件。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-123">Check box control.</span></span>
    
<span data-ttu-id="4fd2d-124">DTCT_GROUPBOX</span><span class="sxs-lookup"><span data-stu-id="4fd2d-124">DTCT_GROUPBOX</span></span> 
  
> <span data-ttu-id="4fd2d-125">分组框控件。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-125">Group box control.</span></span>
    
<span data-ttu-id="4fd2d-126">DTCT_BUTTON</span><span class="sxs-lookup"><span data-stu-id="4fd2d-126">DTCT_BUTTON</span></span> 
  
> <span data-ttu-id="4fd2d-127">按钮控件。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-127">Button control.</span></span>
    
<span data-ttu-id="4fd2d-128">DTCT_PAGE</span><span class="sxs-lookup"><span data-stu-id="4fd2d-128">DTCT_PAGE</span></span> 
  
> <span data-ttu-id="4fd2d-129">选项卡式页面控件。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-129">Tabbed page control.</span></span>
    
<span data-ttu-id="4fd2d-130">DTCT_RADIOBUTTON</span><span class="sxs-lookup"><span data-stu-id="4fd2d-130">DTCT_RADIOBUTTON</span></span> 
  
> <span data-ttu-id="4fd2d-131">单选按钮控件。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-131">Radio button control.</span></span>
    
<span data-ttu-id="4fd2d-132">DTCT_MVLISTBOX</span><span class="sxs-lookup"><span data-stu-id="4fd2d-132">DTCT_MVLISTBOX</span></span> 
  
> <span data-ttu-id="4fd2d-133">多值列表控件。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-133">Multi-valued list control.</span></span>
    
<span data-ttu-id="4fd2d-134">DTCT_MVDDLBX</span><span class="sxs-lookup"><span data-stu-id="4fd2d-134">DTCT_MVDDLBX</span></span> 
  
> <span data-ttu-id="4fd2d-135">多值下拉列表控件。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-135">Multi-valued drop-down list control.</span></span>
    
<span data-ttu-id="4fd2d-136">**ulCtlFlags**</span><span class="sxs-lookup"><span data-stu-id="4fd2d-136">**ulCtlFlags**</span></span>
  
> <span data-ttu-id="4fd2d-137">描述控件功能并对应于控件的 PR_CONTROL_FLAGS ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)) 标志的位掩码。 </span><span class="sxs-lookup"><span data-stu-id="4fd2d-137">Bitmask of flags that describes the control's features and corresponds to the control's **PR_CONTROL_FLAGS** ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)) property.</span></span> <span data-ttu-id="4fd2d-138">只能为复选框、组合框、列表框和编辑控件设置这些标志。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-138">These flags can be set for check boxes, combo boxes, list boxes, and edit controls only.</span></span> <span data-ttu-id="4fd2d-139">可能的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="4fd2d-139">Possible values are as follows:</span></span>
    
<span data-ttu-id="4fd2d-140">DT_ACCEPT_DBCS</span><span class="sxs-lookup"><span data-stu-id="4fd2d-140">DT_ACCEPT_DBCS</span></span> 
  
> <span data-ttu-id="4fd2d-141">接受 ANSI 或 DBCS 格式。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-141">Either the ANSI or DBCS format is accepted.</span></span> <span data-ttu-id="4fd2d-142">此标志仅对编辑控件有效。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-142">This flag is valid for edit controls only.</span></span>
    
<span data-ttu-id="4fd2d-143">DT_EDITABLE</span><span class="sxs-lookup"><span data-stu-id="4fd2d-143">DT_EDITABLE</span></span> 
  
> <span data-ttu-id="4fd2d-144">用户可以修改控件中的文本。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-144">A user can modify the text in the control.</span></span> 
    
<span data-ttu-id="4fd2d-145">DT_MULTILINE</span><span class="sxs-lookup"><span data-stu-id="4fd2d-145">DT_MULTILINE</span></span> 
  
> <span data-ttu-id="4fd2d-146">控件可以包含多个文本行。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-146">The control can contain multiple text lines.</span></span> <span data-ttu-id="4fd2d-147">此标志仅对编辑控件有效。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-147">This flag is valid for edit controls only.</span></span>
    
<span data-ttu-id="4fd2d-148">DT_PASSWORD_EDIT</span><span class="sxs-lookup"><span data-stu-id="4fd2d-148">DT_PASSWORD_EDIT</span></span> 
  
> <span data-ttu-id="4fd2d-149">控件包含密码;因此，不应向用户显示控件的内容。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-149">The control contains a password; therefore, the contents of the control should not be displayed to the user.</span></span> <span data-ttu-id="4fd2d-150">此标志仅对编辑控件有效。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-150">This flag is valid for edit controls only.</span></span>
    
<span data-ttu-id="4fd2d-151">DT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="4fd2d-151">DT_REQUIRED</span></span> 
  
> <span data-ttu-id="4fd2d-152">对话框控件是必需的。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-152">The dialog box control is required.</span></span> <span data-ttu-id="4fd2d-153">此标志仅对编辑框和组合框控件有效。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-153">This flag is valid only for edit and combo box controls.</span></span>
    
<span data-ttu-id="4fd2d-154">DT_SET_IMMEDIATE</span><span class="sxs-lookup"><span data-stu-id="4fd2d-154">DT_SET_IMMEDIATE</span></span> 
  
> <span data-ttu-id="4fd2d-155">启用在控件中更改时立即输出值。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-155">Enables immediate output of a value upon a change in the control.</span></span> <span data-ttu-id="4fd2d-156">这允许在两个控件之间建立依赖关系。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-156">This allows a dependency relationship to be established between two controls.</span></span> 
    
<span data-ttu-id="4fd2d-157">**lpbNotif**</span><span class="sxs-lookup"><span data-stu-id="4fd2d-157">**lpbNotif**</span></span>
  
> <span data-ttu-id="4fd2d-158">指向由 [GUID](guid.md) 结构组成的结构的指针，用于表示服务提供商和控件的标识符。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-158">Pointer to a structure that consists of a [GUID](guid.md) structure, to represent the service provider and an identifier for the control.</span></span> <span data-ttu-id="4fd2d-159">**lpbNotif** 和 **cbNotif** 成员对应于控件的 **PR_CONTROL_ID** ([PidTagControlId](pidtagcontrolid-canonical-property.md)) 属性，用于在必须更新控件时通知用户界面。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-159">The **lpbNotif** and **cbNotif** members correspond to the control's **PR_CONTROL_ID** ([PidTagControlId](pidtagcontrolid-canonical-property.md)) property and are used to notify the user interface when the control has to be updated.</span></span>
    
<span data-ttu-id="4fd2d-160">**cbNotif**</span><span class="sxs-lookup"><span data-stu-id="4fd2d-160">**cbNotif**</span></span>
  
> <span data-ttu-id="4fd2d-161">**lpbNotif** 成员指向的结构中的字节数。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-161">Count of bytes in the structure pointed to by the **lpbNotif** member.</span></span> 
    
<span data-ttu-id="4fd2d-162">**lpszFilter**</span><span class="sxs-lookup"><span data-stu-id="4fd2d-162">**lpszFilter**</span></span>
  
> <span data-ttu-id="4fd2d-163">指向描述可在编辑或组合框控件中输入哪些字符的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-163">Pointer to a character string that describes which characters can be entered into an edit or combo box control.</span></span> <span data-ttu-id="4fd2d-164">对于其他类型的控件 **，lpszFilter** 成员可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-164">For other types of controls, the **lpszFilter** member can be NULL.</span></span> <span data-ttu-id="4fd2d-165">对于编辑框和组合框控件，它应是一次应用于单个字符的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-165">For edit and combo box controls, it should be a regular expression that applies to a single character at a time.</span></span> <span data-ttu-id="4fd2d-166">相同的筛选器将应用于控件中所有的字符。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-166">The same filter is applied to all characters in the control.</span></span> <span data-ttu-id="4fd2d-167">筛选器字符串的格式如下：</span><span class="sxs-lookup"><span data-stu-id="4fd2d-167">The format of the filter string is as follows:</span></span> 
    
|<span data-ttu-id="4fd2d-168">**字符**</span><span class="sxs-lookup"><span data-stu-id="4fd2d-168">**Character**</span></span>|<span data-ttu-id="4fd2d-169">**说明**</span><span class="sxs-lookup"><span data-stu-id="4fd2d-169">**Description**</span></span>|
|:-----|:-----|
| `*` <br/> | <span data-ttu-id="4fd2d-170">允许任何字符 (例如 `"*"` ，) 。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-170">Any character is allowed (for example, `"*"`).</span></span>  <br/> |
| `[ ]` <br/> |<span data-ttu-id="4fd2d-171">定义一组字符 (例如 `"[0123456789]"` ，.) </span><span class="sxs-lookup"><span data-stu-id="4fd2d-171">Defines a set of characters (for example, `"[0123456789]"`.)</span></span>  <br/> |
| `-` <br/> |<span data-ttu-id="4fd2d-172">指示一系列字符 (例如 `"[a-z]"` ，) 。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-172">Indicates a range of characters (for example, `"[a-z]"`).</span></span>  <br/> |
| `~` <br/> |<span data-ttu-id="4fd2d-173">指示不允许使用这些字符， (例如 ， `"[~0-9]")` 。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-173">Indicates that these characters are not allowed (for example, `"[~0-9]")`.</span></span> <br/>|   
| `\` <br/> |<span data-ttu-id="4fd2d-174">用于引用前面的任何符号 (例如，允许使用 `"[\-\\\[\]]"` -、[和 \, ] 字符) 。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-174">Used to quote any of the previous symbols (for example, `"[\-\\\[\]]"` means -, \, [, and ] characters are allowed).</span></span>  <br/> |
   
<span data-ttu-id="4fd2d-175">**ulItemID**</span><span class="sxs-lookup"><span data-stu-id="4fd2d-175">**ulItemID**</span></span>
  
> <span data-ttu-id="4fd2d-176">用于标识对话框资源中的控件的值。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-176">Value that identifies the control in the dialog box resource.</span></span> <span data-ttu-id="4fd2d-177">对于类型为 DTCT_PAGE的选项卡式页面控件，可以选择使用 **ulItemID** 成员从字符串资源加载页面的组件名称。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-177">For tabbed pages controls of type DTCT_PAGE the **ulItemID** member is optionally used to load the component name for the page from a string resource.</span></span> <span data-ttu-id="4fd2d-178">从对话框资源中读取位置和标签信息。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-178">Position and label information are read from the dialog box resource.</span></span> 
    
<span data-ttu-id="4fd2d-179">**ctl**</span><span class="sxs-lookup"><span data-stu-id="4fd2d-179">**ctl**</span></span>
  
> <span data-ttu-id="4fd2d-180">一个包含控件数据的结构，与控件的 PR_CONTROL_STRUCTURE ([PidTagControlStructure](pidtagcontrolstructure-canonical-property.md)) 属性相对应。 </span><span class="sxs-lookup"><span data-stu-id="4fd2d-180">A structure that holds the data for the control and corresponds to the control's **PR_CONTROL_STRUCTURE** ([PidTagControlStructure](pidtagcontrolstructure-canonical-property.md)) property.</span></span> <span data-ttu-id="4fd2d-181">每种类型的控件都有不同的结构。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-181">Each type of control has a different structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="4fd2d-182">备注</span><span class="sxs-lookup"><span data-stu-id="4fd2d-182">Remarks</span></span>

<span data-ttu-id="4fd2d-183">**DTCTL** 结构描述任何类型的一个控件。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-183">The **DTCTL** structure describes one control of any type.</span></span> <span data-ttu-id="4fd2d-184">它的大多数成员都用于设置控件的属性。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-184">Most of its members are used to set properties on the control.</span></span> 
  
<span data-ttu-id="4fd2d-185">**ctl** 成员是一组与特定类型控件相关的结构。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-185">The **ctl** member is a union of structures that relate to a particular type of control.</span></span> <span data-ttu-id="4fd2d-186">例如 **，如果 DTCTL** 结构描述编辑控件， **则 ctl** 成员将指向 [DTBLEDIT](dtbledit.md) 结构。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-186">If the **DTCTL** structure is describing an edit control, for example, the **ctl** member will point to a [DTBLEDIT](dtbledit.md) structure.</span></span> <span data-ttu-id="4fd2d-187">此结构对应于控件的 **PR_CONTROL_STRUCTURE** 属性。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-187">This structure corresponds to the control's **PR_CONTROL_STRUCTURE** property.</span></span> <span data-ttu-id="4fd2d-188">该联合的第一个成员是 LPVOID 类型的变量，以允许 **DTCTL** 结构的编译时间初始化。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-188">The union has as its first member a variable of type LPVOID to allow compile time initialization of the **DTCTL** structure.</span></span> 
  
<span data-ttu-id="4fd2d-189">尽管 [BuildDisplayTable](builddisplaytable.md) 函数使用 **DTCTL** 结构从控件资源生成显示表， **但 DTCTL** 结构永远不会显示在显示表本身中。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-189">Although the [BuildDisplayTable](builddisplaytable.md) function uses the **DTCTL** structure for building the display table from control resources, the **DTCTL** structure never appears in the display table itself.</span></span> <span data-ttu-id="4fd2d-190">此结构只向 **BuildDisplayTable 提供信息**。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-190">This structure just supplies information to **BuildDisplayTable**.</span></span>
  
<span data-ttu-id="4fd2d-191">在 **ulCtlFlags** 成员中，DT_ACCEPT_DBCS、DT_EDITABLE、DT_MULTILINE_and DT_PASSWORD_EDIT四个标志仅影响编辑控件。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-191">In the **ulCtlFlags** member, four flags DT_ACCEPT_DBCS, DT_EDITABLE, DT_MULTILINE_and DT_PASSWORD_EDIT affect edit controls only.</span></span> <span data-ttu-id="4fd2d-192">其他两DT_REQUIRED和DT_SET_IMMEDIATE可编辑控件。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-192">Two others DT_REQUIRED and DT_SET_IMMEDIATE affect any editable control.</span></span> 
  
<span data-ttu-id="4fd2d-193">对话框可用的控件有标签、文本框、墨迹感知文本框、列表、下拉列表、组合框、复选框、分组框、按钮、单选按钮和选项卡式页面。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-193">The controls available for a dialog box are label, text box, ink-aware text box, list, drop-down list, combo box, check box, group box, button, radio button, and tabbed page.</span></span>
  
<span data-ttu-id="4fd2d-194">有关显示表的概述，请参阅显示 [表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-194">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="4fd2d-195">若要了解如何实现显示表，请参阅 [实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="4fd2d-195">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4fd2d-196">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4fd2d-196">See also</span></span>

- [<span data-ttu-id="4fd2d-197">BuildDisplayTable</span><span class="sxs-lookup"><span data-stu-id="4fd2d-197">BuildDisplayTable</span></span>](builddisplaytable.md)
- [<span data-ttu-id="4fd2d-198">DTBLBUTTON</span><span class="sxs-lookup"><span data-stu-id="4fd2d-198">DTBLBUTTON</span></span>](dtblbutton.md)
- [<span data-ttu-id="4fd2d-199">DTBLCHECKBOX</span><span class="sxs-lookup"><span data-stu-id="4fd2d-199">DTBLCHECKBOX</span></span>](dtblcheckbox.md)
- [<span data-ttu-id="4fd2d-200">DTBLCOMBOBOX</span><span class="sxs-lookup"><span data-stu-id="4fd2d-200">DTBLCOMBOBOX</span></span>](dtblcombobox.md)
- [<span data-ttu-id="4fd2d-201">DTBLDDLBX</span><span class="sxs-lookup"><span data-stu-id="4fd2d-201">DTBLDDLBX</span></span>](dtblddlbx.md)
- [<span data-ttu-id="4fd2d-202">DTBLEDIT</span><span class="sxs-lookup"><span data-stu-id="4fd2d-202">DTBLEDIT</span></span>](dtbledit.md)
- [<span data-ttu-id="4fd2d-203">DTBLGROUPBOX</span><span class="sxs-lookup"><span data-stu-id="4fd2d-203">DTBLGROUPBOX</span></span>](dtblgroupbox.md)
- [<span data-ttu-id="4fd2d-204">DTBLLABEL</span><span class="sxs-lookup"><span data-stu-id="4fd2d-204">DTBLLABEL</span></span>](dtbllabel.md)
- [<span data-ttu-id="4fd2d-205">DTBLLBX</span><span class="sxs-lookup"><span data-stu-id="4fd2d-205">DTBLLBX</span></span>](dtbllbx.md)
- [<span data-ttu-id="4fd2d-206">DTBLMVDDLBOX</span><span class="sxs-lookup"><span data-stu-id="4fd2d-206">DTBLMVDDLBOX</span></span>](dtblmvddlbox.md)
- [<span data-ttu-id="4fd2d-207">DTBLMVLISTBOX</span><span class="sxs-lookup"><span data-stu-id="4fd2d-207">DTBLMVLISTBOX</span></span>](dtblmvlistbox.md)
- [<span data-ttu-id="4fd2d-208">DTBLPAGE</span><span class="sxs-lookup"><span data-stu-id="4fd2d-208">DTBLPAGE</span></span>](dtblpage.md)
- [<span data-ttu-id="4fd2d-209">DTBLRADIOBUTTON</span><span class="sxs-lookup"><span data-stu-id="4fd2d-209">DTBLRADIOBUTTON</span></span>](dtblradiobutton.md)
- [<span data-ttu-id="4fd2d-210">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="4fd2d-210">MAPI Structures</span></span>](mapi-structures.md)

