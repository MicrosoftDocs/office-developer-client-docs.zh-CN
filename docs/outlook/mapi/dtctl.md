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
ms.openlocfilehash: 68c621f5f73073ed127767cc1db189769dab227d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774881"
---
# <a name="dtctl"></a><span data-ttu-id="5b95b-103">DTCTL</span><span class="sxs-lookup"><span data-stu-id="5b95b-103">DTCTL</span></span>

<span data-ttu-id="5b95b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="5b95b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="5b95b-105">描述将显示表中生成的对话框中使用的控件。</span><span class="sxs-lookup"><span data-stu-id="5b95b-105">Describes a control that will be used in a dialog box built from a display table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="5b95b-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="5b95b-106">Header file:</span></span>  <br/> |<span data-ttu-id="5b95b-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5b95b-107">Mapidefs.h</span></span>  <br/> |
   
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

## <a name="members"></a><span data-ttu-id="5b95b-108">Members</span><span class="sxs-lookup"><span data-stu-id="5b95b-108">Members</span></span>

<span data-ttu-id="5b95b-109">**ulCtlType**</span><span class="sxs-lookup"><span data-stu-id="5b95b-109">**ulCtlType**</span></span>
  
> <span data-ttu-id="5b95b-110">包含**ctl**成员，并且对应于控件的**PR_CONTROL_TYPE** ([PidTagControlType](pidtagcontroltype-canonical-property.md)) 属性的控件的类型。</span><span class="sxs-lookup"><span data-stu-id="5b95b-110">Type of control that is included in the **ctl** member and corresponds to the control's **PR_CONTROL_TYPE** ([PidTagControlType](pidtagcontroltype-canonical-property.md)) property.</span></span> <span data-ttu-id="5b95b-111">可能值如下所示：</span><span class="sxs-lookup"><span data-stu-id="5b95b-111">Possible values are as follows:</span></span>
    
<span data-ttu-id="5b95b-112">DTCT_LABEL</span><span class="sxs-lookup"><span data-stu-id="5b95b-112">DTCT_LABEL</span></span> 
  
> <span data-ttu-id="5b95b-113">标签控件。</span><span class="sxs-lookup"><span data-stu-id="5b95b-113">Label control.</span></span>
    
<span data-ttu-id="5b95b-114">DTCT_EDIT</span><span class="sxs-lookup"><span data-stu-id="5b95b-114">DTCT_EDIT</span></span> 
  
> <span data-ttu-id="5b95b-115">编辑控件。</span><span class="sxs-lookup"><span data-stu-id="5b95b-115">Edit control.</span></span>
    
<span data-ttu-id="5b95b-116">DTCT_LBX</span><span class="sxs-lookup"><span data-stu-id="5b95b-116">DTCT_LBX</span></span> 
  
> <span data-ttu-id="5b95b-117">列表框控件。</span><span class="sxs-lookup"><span data-stu-id="5b95b-117">List box control.</span></span>
    
<span data-ttu-id="5b95b-118">DTCT_COMBOBOX</span><span class="sxs-lookup"><span data-stu-id="5b95b-118">DTCT_COMBOBOX</span></span> 
  
> <span data-ttu-id="5b95b-119">组合框控件。</span><span class="sxs-lookup"><span data-stu-id="5b95b-119">Combo box control.</span></span>
    
<span data-ttu-id="5b95b-120">DTCT_DDLBX</span><span class="sxs-lookup"><span data-stu-id="5b95b-120">DTCT_DDLBX</span></span> 
  
> <span data-ttu-id="5b95b-121">下拉列表控件。</span><span class="sxs-lookup"><span data-stu-id="5b95b-121">Drop-down list control.</span></span>
    
<span data-ttu-id="5b95b-122">DTCT_CHECKBOX</span><span class="sxs-lookup"><span data-stu-id="5b95b-122">DTCT_CHECKBOX</span></span> 
  
> <span data-ttu-id="5b95b-123">复选框控件。</span><span class="sxs-lookup"><span data-stu-id="5b95b-123">Check box control.</span></span>
    
<span data-ttu-id="5b95b-124">DTCT_GROUPBOX</span><span class="sxs-lookup"><span data-stu-id="5b95b-124">DTCT_GROUPBOX</span></span> 
  
> <span data-ttu-id="5b95b-125">分组框控件。</span><span class="sxs-lookup"><span data-stu-id="5b95b-125">Group box control.</span></span>
    
<span data-ttu-id="5b95b-126">DTCT_BUTTON</span><span class="sxs-lookup"><span data-stu-id="5b95b-126">DTCT_BUTTON</span></span> 
  
> <span data-ttu-id="5b95b-127">按钮控件。</span><span class="sxs-lookup"><span data-stu-id="5b95b-127">Button control.</span></span>
    
<span data-ttu-id="5b95b-128">DTCT_PAGE</span><span class="sxs-lookup"><span data-stu-id="5b95b-128">DTCT_PAGE</span></span> 
  
> <span data-ttu-id="5b95b-129">选项卡式的页面控件。</span><span class="sxs-lookup"><span data-stu-id="5b95b-129">Tabbed page control.</span></span>
    
<span data-ttu-id="5b95b-130">DTCT_RADIOBUTTON</span><span class="sxs-lookup"><span data-stu-id="5b95b-130">DTCT_RADIOBUTTON</span></span> 
  
> <span data-ttu-id="5b95b-131">单选按钮控件。</span><span class="sxs-lookup"><span data-stu-id="5b95b-131">Radio button control.</span></span>
    
<span data-ttu-id="5b95b-132">DTCT_MVLISTBOX</span><span class="sxs-lookup"><span data-stu-id="5b95b-132">DTCT_MVLISTBOX</span></span> 
  
> <span data-ttu-id="5b95b-133">多值的列表控件。</span><span class="sxs-lookup"><span data-stu-id="5b95b-133">Multi-valued list control.</span></span>
    
<span data-ttu-id="5b95b-134">DTCT_MVDDLBX</span><span class="sxs-lookup"><span data-stu-id="5b95b-134">DTCT_MVDDLBX</span></span> 
  
> <span data-ttu-id="5b95b-135">多值的下拉列表控件。</span><span class="sxs-lookup"><span data-stu-id="5b95b-135">Multi-valued drop-down list control.</span></span>
    
<span data-ttu-id="5b95b-136">**ulCtlFlags**</span><span class="sxs-lookup"><span data-stu-id="5b95b-136">**ulCtlFlags**</span></span>
  
> <span data-ttu-id="5b95b-137">位掩码的标志，描述控件的功能，并对应于控件的**PR_CONTROL_FLAGS** ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="5b95b-137">Bitmask of flags that describes the control's features and corresponds to the control's **PR_CONTROL_FLAGS** ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)) property.</span></span> <span data-ttu-id="5b95b-138">这些标志的复选框、 组合框或列表框中，可以设置和编辑控件仅。</span><span class="sxs-lookup"><span data-stu-id="5b95b-138">These flags can be set for check boxes, combo boxes, list boxes, and edit controls only.</span></span> <span data-ttu-id="5b95b-139">可能值如下所示：</span><span class="sxs-lookup"><span data-stu-id="5b95b-139">Possible values are as follows:</span></span>
    
<span data-ttu-id="5b95b-140">DT_ACCEPT_DBCS</span><span class="sxs-lookup"><span data-stu-id="5b95b-140">DT_ACCEPT_DBCS</span></span> 
  
> <span data-ttu-id="5b95b-141">ANSI 或 DBCS 格式是可接受。</span><span class="sxs-lookup"><span data-stu-id="5b95b-141">Either the ANSI or DBCS format is accepted.</span></span> <span data-ttu-id="5b95b-142">此标志是有效的编辑控件仅。</span><span class="sxs-lookup"><span data-stu-id="5b95b-142">This flag is valid for edit controls only.</span></span>
    
<span data-ttu-id="5b95b-143">DT_EDITABLE</span><span class="sxs-lookup"><span data-stu-id="5b95b-143">DT_EDITABLE</span></span> 
  
> <span data-ttu-id="5b95b-144">用户可以修改控件中的文本。</span><span class="sxs-lookup"><span data-stu-id="5b95b-144">A user can modify the text in the control.</span></span> 
    
<span data-ttu-id="5b95b-145">DT_MULTILINE</span><span class="sxs-lookup"><span data-stu-id="5b95b-145">DT_MULTILINE</span></span> 
  
> <span data-ttu-id="5b95b-146">控件可以包含多个文本行。</span><span class="sxs-lookup"><span data-stu-id="5b95b-146">The control can contain multiple text lines.</span></span> <span data-ttu-id="5b95b-147">此标志是有效的编辑控件仅。</span><span class="sxs-lookup"><span data-stu-id="5b95b-147">This flag is valid for edit controls only.</span></span>
    
<span data-ttu-id="5b95b-148">DT_PASSWORD_EDIT</span><span class="sxs-lookup"><span data-stu-id="5b95b-148">DT_PASSWORD_EDIT</span></span> 
  
> <span data-ttu-id="5b95b-149">控件包含密码;因此，控件的内容不应显示给用户。</span><span class="sxs-lookup"><span data-stu-id="5b95b-149">The control contains a password; therefore, the contents of the control should not be displayed to the user.</span></span> <span data-ttu-id="5b95b-150">此标志是有效的编辑控件仅。</span><span class="sxs-lookup"><span data-stu-id="5b95b-150">This flag is valid for edit controls only.</span></span>
    
<span data-ttu-id="5b95b-151">DT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="5b95b-151">DT_REQUIRED</span></span> 
  
> <span data-ttu-id="5b95b-152">对话框控件是必需的。</span><span class="sxs-lookup"><span data-stu-id="5b95b-152">The dialog box control is required.</span></span> <span data-ttu-id="5b95b-153">此标志是仅对编辑和组合框控件有效。</span><span class="sxs-lookup"><span data-stu-id="5b95b-153">This flag is valid only for edit and combo box controls.</span></span>
    
<span data-ttu-id="5b95b-154">DT_SET_IMMEDIATE</span><span class="sxs-lookup"><span data-stu-id="5b95b-154">DT_SET_IMMEDIATE</span></span> 
  
> <span data-ttu-id="5b95b-155">启用即时输出时控件中更改的值。</span><span class="sxs-lookup"><span data-stu-id="5b95b-155">Enables immediate output of a value upon a change in the control.</span></span> <span data-ttu-id="5b95b-156">这样，同时建立两个控件之间的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="5b95b-156">This allows a dependency relationship to be established between two controls.</span></span> 
    
<span data-ttu-id="5b95b-157">**lpbNotif**</span><span class="sxs-lookup"><span data-stu-id="5b95b-157">**lpbNotif**</span></span>
  
> <span data-ttu-id="5b95b-158">指向结构组成的[GUID](guid.md)结构，以表示服务提供商和控件的标识符。</span><span class="sxs-lookup"><span data-stu-id="5b95b-158">Pointer to a structure that consists of a [GUID](guid.md) structure, to represent the service provider and an identifier for the control.</span></span> <span data-ttu-id="5b95b-159">**LpbNotif**和**cbNotif**成员对应于控件的**PR_CONTROL_ID** ([PidTagControlId](pidtagcontrolid-canonical-property.md)) 属性，用于在控件具有要更新时通知用户界面。</span><span class="sxs-lookup"><span data-stu-id="5b95b-159">The **lpbNotif** and **cbNotif** members correspond to the control's **PR_CONTROL_ID** ([PidTagControlId](pidtagcontrolid-canonical-property.md)) property and are used to notify the user interface when the control has to be updated.</span></span>
    
<span data-ttu-id="5b95b-160">**cbNotif**</span><span class="sxs-lookup"><span data-stu-id="5b95b-160">**cbNotif**</span></span>
  
> <span data-ttu-id="5b95b-161">由**lpbNotif**成员指向结构中的字节数。</span><span class="sxs-lookup"><span data-stu-id="5b95b-161">Count of bytes in the structure pointed to by the **lpbNotif** member.</span></span> 
    
<span data-ttu-id="5b95b-162">**lpszFilter**</span><span class="sxs-lookup"><span data-stu-id="5b95b-162">**lpszFilter**</span></span>
  
> <span data-ttu-id="5b95b-163">指向介绍可以编辑或组合框控件中输入的字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="5b95b-163">Pointer to a character string that describes which characters can be entered into an edit or combo box control.</span></span> <span data-ttu-id="5b95b-164">对于其他类型的控件， **lpszFilter**成员可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="5b95b-164">For other types of controls, the **lpszFilter** member can be NULL.</span></span> <span data-ttu-id="5b95b-165">对于编辑和组合框控件，它应为每次应用于单个字符的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="5b95b-165">For edit and combo box controls, it should be a regular expression that applies to a single character at a time.</span></span> <span data-ttu-id="5b95b-166">相同的筛选器应用于该控件中的所有字符。</span><span class="sxs-lookup"><span data-stu-id="5b95b-166">The same filter is applied to all characters in the control.</span></span> <span data-ttu-id="5b95b-167">筛选器字符串的格式如下所示：</span><span class="sxs-lookup"><span data-stu-id="5b95b-167">The format of the filter string is as follows:</span></span> 
    
|<span data-ttu-id="5b95b-168">**字符**</span><span class="sxs-lookup"><span data-stu-id="5b95b-168">**Character**</span></span>|<span data-ttu-id="5b95b-169">**说明**</span><span class="sxs-lookup"><span data-stu-id="5b95b-169">**Description**</span></span>|
|:-----|:-----|
| `*` <br/> | <span data-ttu-id="5b95b-170">允许任何字符 (例如， `"*"`)。</span><span class="sxs-lookup"><span data-stu-id="5b95b-170">Any character is allowed (for example, `"*"`).</span></span>  <br/> |
| `[ ]` <br/> |<span data-ttu-id="5b95b-171">定义一组字符 (例如， `"[0123456789]"`。)</span><span class="sxs-lookup"><span data-stu-id="5b95b-171">Defines a set of characters (for example, `"[0123456789]"`.)</span></span>  <br/> |
| `-` <br/> |<span data-ttu-id="5b95b-172">指示某个范围的字符 (例如， `"[a-z]"`)。</span><span class="sxs-lookup"><span data-stu-id="5b95b-172">Indicates a range of characters (for example, `"[a-z]"`).</span></span>  <br/> |
| `~` <br/> |<span data-ttu-id="5b95b-173">指示不允许这些字符 (例如， `"[~0-9]")`。</span><span class="sxs-lookup"><span data-stu-id="5b95b-173">Indicates that these characters are not allowed (for example, `"[~0-9]")`.</span></span> <br/>|   
| `\` <br/> |<span data-ttu-id="5b95b-174">用于 quote 任何以前符号 (例如，`"[\-\\\[\]]"`是指-， \, [，和] 允许字符)。</span><span class="sxs-lookup"><span data-stu-id="5b95b-174">Used to quote any of the previous symbols (for example, `"[\-\\\[\]]"` means -, \, [, and ] characters are allowed).</span></span>  <br/> |
   
<span data-ttu-id="5b95b-175">**ulItemID**</span><span class="sxs-lookup"><span data-stu-id="5b95b-175">**ulItemID**</span></span>
  
> <span data-ttu-id="5b95b-176">标识对话框资源中的控件的值。</span><span class="sxs-lookup"><span data-stu-id="5b95b-176">Value that identifies the control in the dialog box resource.</span></span> <span data-ttu-id="5b95b-177">对于类型 DTCT_PAGE **ulItemID**的选项卡式的页面控件成员 （可选） 用于从字符串资源加载页面组件名称。</span><span class="sxs-lookup"><span data-stu-id="5b95b-177">For tabbed pages controls of type DTCT_PAGE the **ulItemID** member is optionally used to load the component name for the page from a string resource.</span></span> <span data-ttu-id="5b95b-178">位置和标签信息读取对话框资源。</span><span class="sxs-lookup"><span data-stu-id="5b95b-178">Position and label information are read from the dialog box resource.</span></span> 
    
<span data-ttu-id="5b95b-179">**ctl**</span><span class="sxs-lookup"><span data-stu-id="5b95b-179">**ctl**</span></span>
  
> <span data-ttu-id="5b95b-180">一个包含控件的数据，并且与控件的**PR_CONTROL_STRUCTURE** ([PidTagControlStructure](pidtagcontrolstructure-canonical-property.md)) 属性相对应的结构。</span><span class="sxs-lookup"><span data-stu-id="5b95b-180">A structure that holds the data for the control and corresponds to the control's **PR_CONTROL_STRUCTURE** ([PidTagControlStructure](pidtagcontrolstructure-canonical-property.md)) property.</span></span> <span data-ttu-id="5b95b-181">每种类型的控件具有不同的结构。</span><span class="sxs-lookup"><span data-stu-id="5b95b-181">Each type of control has a different structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="5b95b-182">说明</span><span class="sxs-lookup"><span data-stu-id="5b95b-182">Remarks</span></span>

<span data-ttu-id="5b95b-183">**DTCTL**结构描述任何类型的一个控件。</span><span class="sxs-lookup"><span data-stu-id="5b95b-183">The **DTCTL** structure describes one control of any type.</span></span> <span data-ttu-id="5b95b-184">大部分及其成员用于为控件设置属性。</span><span class="sxs-lookup"><span data-stu-id="5b95b-184">Most of its members are used to set properties on the control.</span></span> 
  
<span data-ttu-id="5b95b-185">**Ctl**成员的结构与特定类型的控制相关的联合。</span><span class="sxs-lookup"><span data-stu-id="5b95b-185">The **ctl** member is a union of structures that relate to a particular type of control.</span></span> <span data-ttu-id="5b95b-186">如果**DTCTL**结构描述编辑控件，例如， **ctl**成员将指向[DTBLEDIT](dtbledit.md)结构。</span><span class="sxs-lookup"><span data-stu-id="5b95b-186">If the **DTCTL** structure is describing an edit control, for example, the **ctl** member will point to a [DTBLEDIT](dtbledit.md) structure.</span></span> <span data-ttu-id="5b95b-187">此结构对应于控件的**PR_CONTROL_STRUCTURE**属性。</span><span class="sxs-lookup"><span data-stu-id="5b95b-187">This structure corresponds to the control's **PR_CONTROL_STRUCTURE** property.</span></span> <span data-ttu-id="5b95b-188">联合具有作为其第一个成员 LPVOID 允许编译时间初始化**DTCTL**结构的类型的变量。</span><span class="sxs-lookup"><span data-stu-id="5b95b-188">The union has as its first member a variable of type LPVOID to allow compile time initialization of the **DTCTL** structure.</span></span> 
  
<span data-ttu-id="5b95b-189">尽管[BuildDisplayTable](builddisplaytable.md)函数用于生成控件资源中的显示表使用**DTCTL**结构，但**DTCTL**结构永远不会显示表格本身中显示。</span><span class="sxs-lookup"><span data-stu-id="5b95b-189">Although the [BuildDisplayTable](builddisplaytable.md) function uses the **DTCTL** structure for building the display table from control resources, the **DTCTL** structure never appears in the display table itself.</span></span> <span data-ttu-id="5b95b-190">此结构仅信息提供给**BuildDisplayTable**。</span><span class="sxs-lookup"><span data-stu-id="5b95b-190">This structure just supplies information to **BuildDisplayTable**.</span></span>
  
<span data-ttu-id="5b95b-191">**UlCtlFlags**成员，在四个标志 DT_ACCEPT_DBCS，DT_EDITABLE，DT_MULTILINE_and DT_PASSWORD_EDIT 影响编辑控件仅。</span><span class="sxs-lookup"><span data-stu-id="5b95b-191">In the **ulCtlFlags** member, four flags DT_ACCEPT_DBCS, DT_EDITABLE, DT_MULTILINE_and DT_PASSWORD_EDIT affect edit controls only.</span></span> <span data-ttu-id="5b95b-192">两个其他人 DT_REQUIRED DT_SET_IMMEDIATE 影响任何可编辑控件。</span><span class="sxs-lookup"><span data-stu-id="5b95b-192">Two others DT_REQUIRED and DT_SET_IMMEDIATE affect any editable control.</span></span> 
  
<span data-ttu-id="5b95b-193">可用的对话框中的控件的标签、 文本框、 墨迹感知文本框、 列表、 下拉列表、 组合框、 复选框、 组框、 按钮、 单选按钮和选项卡式的页面。</span><span class="sxs-lookup"><span data-stu-id="5b95b-193">The controls available for a dialog box are label, text box, ink-aware text box, list, drop-down list, combo box, check box, group box, button, radio button, and tabbed page.</span></span>
  
<span data-ttu-id="5b95b-194">显示表的概述，请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="5b95b-194">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="5b95b-195">有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="5b95b-195">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5b95b-196">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b95b-196">See also</span></span>

- [<span data-ttu-id="5b95b-197">BuildDisplayTable</span><span class="sxs-lookup"><span data-stu-id="5b95b-197">BuildDisplayTable</span></span>](builddisplaytable.md)
- [<span data-ttu-id="5b95b-198">DTBLBUTTON</span><span class="sxs-lookup"><span data-stu-id="5b95b-198">DTBLBUTTON</span></span>](dtblbutton.md)
- [<span data-ttu-id="5b95b-199">DTBLCHECKBOX</span><span class="sxs-lookup"><span data-stu-id="5b95b-199">DTBLCHECKBOX</span></span>](dtblcheckbox.md)
- [<span data-ttu-id="5b95b-200">DTBLCOMBOBOX</span><span class="sxs-lookup"><span data-stu-id="5b95b-200">DTBLCOMBOBOX</span></span>](dtblcombobox.md)
- [<span data-ttu-id="5b95b-201">DTBLDDLBX</span><span class="sxs-lookup"><span data-stu-id="5b95b-201">DTBLDDLBX</span></span>](dtblddlbx.md)
- [<span data-ttu-id="5b95b-202">DTBLEDIT</span><span class="sxs-lookup"><span data-stu-id="5b95b-202">DTBLEDIT</span></span>](dtbledit.md)
- [<span data-ttu-id="5b95b-203">DTBLGROUPBOX</span><span class="sxs-lookup"><span data-stu-id="5b95b-203">DTBLGROUPBOX</span></span>](dtblgroupbox.md)
- [<span data-ttu-id="5b95b-204">DTBLLABEL</span><span class="sxs-lookup"><span data-stu-id="5b95b-204">DTBLLABEL</span></span>](dtbllabel.md)
- [<span data-ttu-id="5b95b-205">DTBLLBX</span><span class="sxs-lookup"><span data-stu-id="5b95b-205">DTBLLBX</span></span>](dtbllbx.md)
- [<span data-ttu-id="5b95b-206">DTBLMVDDLBOX</span><span class="sxs-lookup"><span data-stu-id="5b95b-206">DTBLMVDDLBOX</span></span>](dtblmvddlbox.md)
- [<span data-ttu-id="5b95b-207">DTBLMVLISTBOX</span><span class="sxs-lookup"><span data-stu-id="5b95b-207">DTBLMVLISTBOX</span></span>](dtblmvlistbox.md)
- [<span data-ttu-id="5b95b-208">DTBLPAGE</span><span class="sxs-lookup"><span data-stu-id="5b95b-208">DTBLPAGE</span></span>](dtblpage.md)
- [<span data-ttu-id="5b95b-209">DTBLRADIOBUTTON</span><span class="sxs-lookup"><span data-stu-id="5b95b-209">DTBLRADIOBUTTON</span></span>](dtblradiobutton.md)
- [<span data-ttu-id="5b95b-210">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="5b95b-210">MAPI Structures</span></span>](mapi-structures.md)

