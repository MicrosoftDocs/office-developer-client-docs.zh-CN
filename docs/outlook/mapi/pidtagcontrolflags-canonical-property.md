---
title: PidTagControlFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagControlFlags
api_type:
- HeaderDef
ms.assetid: b97a9e72-fbb7-49ab-a19d-5e9bd1b8a80d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 099f08876eadc83ebb66b9e4226eeeee6277bf01
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331862"
---
# <a name="pidtagcontrolflags-canonical-property"></a><span data-ttu-id="d3243-103">PidTagControlFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="d3243-103">PidTagControlFlags Canonical Property</span></span>

  
  
<span data-ttu-id="d3243-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d3243-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d3243-105">包含用于管理从显示表生成的对话框中所使用的控件行为的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="d3243-105">Contains a bitmask of flags governing the behavior of a control used in a dialog box built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d3243-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d3243-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d3243-107">PR_CONTROL_FLAGS</span><span class="sxs-lookup"><span data-stu-id="d3243-107">PR_CONTROL_FLAGS</span></span>  <br/> |
|<span data-ttu-id="d3243-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d3243-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d3243-109">0x3F00</span><span class="sxs-lookup"><span data-stu-id="d3243-109">0x3F00</span></span>  <br/> |
|<span data-ttu-id="d3243-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d3243-110">Data type:</span></span>  <br/> |<span data-ttu-id="d3243-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="d3243-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="d3243-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d3243-112">Area:</span></span>  <br/> |<span data-ttu-id="d3243-113">MAPI 显示表</span><span class="sxs-lookup"><span data-stu-id="d3243-113">MAPI display table</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d3243-114">注解</span><span class="sxs-lookup"><span data-stu-id="d3243-114">Remarks</span></span>

<span data-ttu-id="d3243-115">可以为此属性设置以下一个或多个标志:</span><span class="sxs-lookup"><span data-stu-id="d3243-115">One or more of the following flags can be set for this property:</span></span>
  
<span data-ttu-id="d3243-116">DT_ACCEPT_DBCS</span><span class="sxs-lookup"><span data-stu-id="d3243-116">DT_ACCEPT_DBCS</span></span> 
  
> <span data-ttu-id="d3243-117">该控件可以包含双字节字符集 (DBCS) 字符。</span><span class="sxs-lookup"><span data-stu-id="d3243-117">The control can have Double-Byte Character Set (DBCS) characters in it.</span></span> <span data-ttu-id="d3243-118">此标志与编辑控件一起使用。</span><span class="sxs-lookup"><span data-stu-id="d3243-118">This flag is used with edit controls.</span></span> <span data-ttu-id="d3243-119">它允许多字节字符集。</span><span class="sxs-lookup"><span data-stu-id="d3243-119">It allows multiple-byte character sets.</span></span>
    
<span data-ttu-id="d3243-120">DT_EDITABLE</span><span class="sxs-lookup"><span data-stu-id="d3243-120">DT_EDITABLE</span></span> 
  
> <span data-ttu-id="d3243-121">可以对该控件进行编辑;可以更改与控件关联的值。</span><span class="sxs-lookup"><span data-stu-id="d3243-121">The control can be edited; the value associated with the control can be changed.</span></span> <span data-ttu-id="d3243-122">如果未设置此标志, 则该控件为只读。</span><span class="sxs-lookup"><span data-stu-id="d3243-122">When this flag is not set, the control is read-only.</span></span> <span data-ttu-id="d3243-123">在标签、分组框、标准下压按钮、多值下拉列表框和列表框控件中, 此值将被忽略。</span><span class="sxs-lookup"><span data-stu-id="d3243-123">This value is ignored on label, group box, standard push button, multivalued drop down list box and list box controls.</span></span>
    
<span data-ttu-id="d3243-124">DT_MULTILINE</span><span class="sxs-lookup"><span data-stu-id="d3243-124">DT_MULTILINE</span></span> 
  
> <span data-ttu-id="d3243-125">编辑控件可以包含多行。</span><span class="sxs-lookup"><span data-stu-id="d3243-125">The edit control can contain multiple lines.</span></span> <span data-ttu-id="d3243-126">这意味着可以在控件中输入一个回车符。</span><span class="sxs-lookup"><span data-stu-id="d3243-126">This means a return character can be entered within the control.</span></span> <span data-ttu-id="d3243-127">此标志对仅编辑控件有效。</span><span class="sxs-lookup"><span data-stu-id="d3243-127">This flag is valid for edit controls only.</span></span>
    
<span data-ttu-id="d3243-128">DT_PASSWORD_EDIT</span><span class="sxs-lookup"><span data-stu-id="d3243-128">DT_PASSWORD_EDIT</span></span> 
  
> <span data-ttu-id="d3243-129">适用于编辑控件。</span><span class="sxs-lookup"><span data-stu-id="d3243-129">Applies to edit controls.</span></span> <span data-ttu-id="d3243-130">编辑控件的处理方式类似于密码。</span><span class="sxs-lookup"><span data-stu-id="d3243-130">The edit control is treated like a password.</span></span> <span data-ttu-id="d3243-131">值以星号显示, 而不是回显输入的实际字符。</span><span class="sxs-lookup"><span data-stu-id="d3243-131">The value is displayed using asterisks instead of echoing the actual characters entered.</span></span>
    
<span data-ttu-id="d3243-132">DT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="d3243-132">DT_REQUIRED</span></span> 
  
> <span data-ttu-id="d3243-133">如果控件允许更改 (DT_EDITABLE), 则在调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)之前, 它必须具有值。</span><span class="sxs-lookup"><span data-stu-id="d3243-133">If the control allows changes (DT_EDITABLE), it must have a value before [IMAPIProp::SaveChanges](imapiprop-savechanges.md) is called.</span></span> 
    
<span data-ttu-id="d3243-134">DT_SET_IMMEDIATE</span><span class="sxs-lookup"><span data-stu-id="d3243-134">DT_SET_IMMEDIATE</span></span> 
  
> <span data-ttu-id="d3243-135">启用值的立即设置;只要控件中的值更改, MAPI 就会为与该控件关联的属性调用**SetProps**方法。</span><span class="sxs-lookup"><span data-stu-id="d3243-135">Enables immediate setting of a value; as soon as a value in the control changes, MAPI calls the **SetProps** method for the property associated with that control.</span></span> <span data-ttu-id="d3243-136">如果未设置此标志, 则在对话框关闭时设置这些值。</span><span class="sxs-lookup"><span data-stu-id="d3243-136">When this flag is not set, the values are set when the dialog box is dismissed.</span></span> 
    
<span data-ttu-id="d3243-137">DT_SET_SELECTION</span><span class="sxs-lookup"><span data-stu-id="d3243-137">DT_SET_SELECTION</span></span> 
  
> <span data-ttu-id="d3243-138">在列表框中进行选择时, 该列表框的索引列将设置为属性。</span><span class="sxs-lookup"><span data-stu-id="d3243-138">When a selection is made within the list box, the index column of that list box is set as a property.</span></span> <span data-ttu-id="d3243-139">始终与 DT_SET_IMMEDIATE 一起使用。</span><span class="sxs-lookup"><span data-stu-id="d3243-139">Always used with DT_SET_IMMEDIATE.</span></span>
    
<span data-ttu-id="d3243-140">此属性存储在控件的[DTCTL](dtctl.md)结构的 ulCtlFlags 成员中。</span><span class="sxs-lookup"><span data-stu-id="d3243-140">This property is stored in the ulCtlFlags member of a control's [DTCTL](dtctl.md) structure.</span></span> <span data-ttu-id="d3243-141">大多数控件标志适用于允许用户输入的所有控件;少数仅适用于编辑控件。</span><span class="sxs-lookup"><span data-stu-id="d3243-141">Most of the control flags apply to all of the controls that allow user input; a few apply only to the edit control.</span></span> <span data-ttu-id="d3243-142">不允许用户输入的控件 (如按钮或标签) 将0设置为其控件标志。</span><span class="sxs-lookup"><span data-stu-id="d3243-142">Controls that do not allow user input, such as a button or a label, set 0 for their control flags.</span></span> 
  
<span data-ttu-id="d3243-143">许多标志值都是一目了然的。</span><span class="sxs-lookup"><span data-stu-id="d3243-143">Many of the flag values are self-explanatory.</span></span> <span data-ttu-id="d3243-144">例如, 当为控件设置 DT_REQUIRED 时, 它必须包含一个值, 才能允许该对话框被消除。</span><span class="sxs-lookup"><span data-stu-id="d3243-144">For example, when DT_REQUIRED is set for a control, it must contain a value before the dialog box is allowed to be dismissed.</span></span> <span data-ttu-id="d3243-145">服务提供程序可以通过其**IMAPIProp**实现提供值, 也可以通过用户输入一个值。</span><span class="sxs-lookup"><span data-stu-id="d3243-145">Either the service provider can supply a value through its **IMAPIProp** implementation or the user can enter one.</span></span> <span data-ttu-id="d3243-146">DT_EDITABLE 指示可以修改控件的值。</span><span class="sxs-lookup"><span data-stu-id="d3243-146">DT_EDITABLE indicates that the value for the control can be modified.</span></span> <span data-ttu-id="d3243-147">DT_MULTILINE 允许编辑控件的值跨多行。</span><span class="sxs-lookup"><span data-stu-id="d3243-147">DT_MULTILINE allows the value for an edit control to span multiple lines.</span></span> 
  
<span data-ttu-id="d3243-148">某些控件标志的含义并不明显。</span><span class="sxs-lookup"><span data-stu-id="d3243-148">Some control flags are not so obvious in their meaning.</span></span> <span data-ttu-id="d3243-149">当控件设置 DT_SET_IMMEDIATE 标志时, 只要用户移动到新控件, 对其值所做的任何更改就会生效。</span><span class="sxs-lookup"><span data-stu-id="d3243-149">When a control sets the DT_SET_IMMEDIATE flag, any changes to its value take affect as soon as the user moves to a new control.</span></span> <span data-ttu-id="d3243-150">MAPI 对控件属性的属性接口的[IMAPIProp:: SetProps](imapiprop-setprops.md)方法进行单个调用。</span><span class="sxs-lookup"><span data-stu-id="d3243-150">MAPI makes a single call to the property interface's [IMAPIProp::SetProps](imapiprop-setprops.md) method for the control's property.</span></span> <span data-ttu-id="d3243-151">这不同于默认行为, 即延迟对控制值所做的更改将会生效, 直到用户选择了 **"确定"** 按钮或关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="d3243-151">This is different from the default behavior, which is to postpone having changes to control values take effect until after the user selects the **OK** button or dismisses the dialog box.</span></span> <span data-ttu-id="d3243-152">DT_SET_IMMEDIATE 标志通常与显示表通知结合使用。</span><span class="sxs-lookup"><span data-stu-id="d3243-152">The DT_SET_IMMEDIATE flag is often used in combination with display table notifications.</span></span> 
  
<span data-ttu-id="d3243-153">下表列出了可为每种类型设置的控件类型和所有标志值。</span><span class="sxs-lookup"><span data-stu-id="d3243-153">The following table lists the types of controls and all of the flag values that can be set for each type.</span></span>
  
|<span data-ttu-id="d3243-154">**Control**</span><span class="sxs-lookup"><span data-stu-id="d3243-154">**Control**</span></span>|<span data-ttu-id="d3243-155">**此属性的有效值**</span><span class="sxs-lookup"><span data-stu-id="d3243-155">**Valid values for this property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d3243-156">按钮</span><span class="sxs-lookup"><span data-stu-id="d3243-156">Button</span></span>  <br/> |<span data-ttu-id="d3243-157">必须为零</span><span class="sxs-lookup"><span data-stu-id="d3243-157">Must be zero</span></span>  <br/> |
|<span data-ttu-id="d3243-158">复选框</span><span class="sxs-lookup"><span data-stu-id="d3243-158">Check box</span></span>  <br/> |<span data-ttu-id="d3243-159">DT_EDITABLE、DT_SET_IMMEDIATE</span><span class="sxs-lookup"><span data-stu-id="d3243-159">DT_EDITABLE, DT_SET_IMMEDIATE</span></span>  <br/> |
|<span data-ttu-id="d3243-160">组合框</span><span class="sxs-lookup"><span data-stu-id="d3243-160">Combo box</span></span>  <br/> |<span data-ttu-id="d3243-161">DT_EDITABLE、DT_REQUIRED、DT_SET_IMMEDIATE</span><span class="sxs-lookup"><span data-stu-id="d3243-161">DT_EDITABLE, DT_REQUIRED, DT_SET_IMMEDIATE</span></span>  <br/> |
|<span data-ttu-id="d3243-162">下拉列表框</span><span class="sxs-lookup"><span data-stu-id="d3243-162">Drop-down list box</span></span>  <br/> |<span data-ttu-id="d3243-163">DT_EDITABLE、DT_SET_IMMEDIATE</span><span class="sxs-lookup"><span data-stu-id="d3243-163">DT_EDITABLE, DT_SET_IMMEDIATE</span></span>  <br/> |
|<span data-ttu-id="d3243-164">编辑</span><span class="sxs-lookup"><span data-stu-id="d3243-164">Edit</span></span>  <br/> |<span data-ttu-id="d3243-165">DT_ACCEPT_DBCS、DT_MULTILINE、DT_EDITABLE、DT_PASSWORD_EDIT、DT_REQUIRED、DT_SET_IMMEDIATE</span><span class="sxs-lookup"><span data-stu-id="d3243-165">DT_ACCEPT_DBCS, DT_MULTILINE, DT_EDITABLE, DT_PASSWORD_EDIT, DT_REQUIRED, DT_SET_IMMEDIATE</span></span>  <br/> |
|<span data-ttu-id="d3243-166">分组框</span><span class="sxs-lookup"><span data-stu-id="d3243-166">Group box</span></span>  <br/> |<span data-ttu-id="d3243-167">必须为零</span><span class="sxs-lookup"><span data-stu-id="d3243-167">Must be zero</span></span>  <br/> |
|<span data-ttu-id="d3243-168">标签</span><span class="sxs-lookup"><span data-stu-id="d3243-168">Label</span></span>  <br/> |<span data-ttu-id="d3243-169">必须为零</span><span class="sxs-lookup"><span data-stu-id="d3243-169">Must be zero</span></span>  <br/> |
|<span data-ttu-id="d3243-170">列表框</span><span class="sxs-lookup"><span data-stu-id="d3243-170">List box</span></span>  <br/> |<span data-ttu-id="d3243-171">必须为零</span><span class="sxs-lookup"><span data-stu-id="d3243-171">Must be zero</span></span>  <br/> |
|<span data-ttu-id="d3243-172">多值下拉列表框</span><span class="sxs-lookup"><span data-stu-id="d3243-172">Multivalue drop-down list box</span></span>  <br/> |<span data-ttu-id="d3243-173">必须为零</span><span class="sxs-lookup"><span data-stu-id="d3243-173">Must be zero</span></span>  <br/> |
|<span data-ttu-id="d3243-174">多值列表框</span><span class="sxs-lookup"><span data-stu-id="d3243-174">Multivalue list box</span></span>  <br/> |<span data-ttu-id="d3243-175">必须为零</span><span class="sxs-lookup"><span data-stu-id="d3243-175">Must be zero</span></span>  <br/> |
|<span data-ttu-id="d3243-176">选项卡页</span><span class="sxs-lookup"><span data-stu-id="d3243-176">Tabbed page</span></span>  <br/> |<span data-ttu-id="d3243-177">必须为零</span><span class="sxs-lookup"><span data-stu-id="d3243-177">Must be zero</span></span>  <br/> |
|<span data-ttu-id="d3243-178">单选按钮</span><span class="sxs-lookup"><span data-stu-id="d3243-178">Radio button</span></span>  <br/> |<span data-ttu-id="d3243-179">必须为零</span><span class="sxs-lookup"><span data-stu-id="d3243-179">Must be zero</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="d3243-180">相关资源</span><span class="sxs-lookup"><span data-stu-id="d3243-180">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="d3243-181">头文件</span><span class="sxs-lookup"><span data-stu-id="d3243-181">Header files</span></span>

<span data-ttu-id="d3243-182">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="d3243-182">Mapidefs.h</span></span>
  
> <span data-ttu-id="d3243-183">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d3243-183">Provides data type definitions.</span></span>
    
<span data-ttu-id="d3243-184">Mapitags</span><span class="sxs-lookup"><span data-stu-id="d3243-184">Mapitags.h</span></span>
  
> <span data-ttu-id="d3243-185">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d3243-185">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d3243-186">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3243-186">See also</span></span>



[<span data-ttu-id="d3243-187">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d3243-187">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d3243-188">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d3243-188">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d3243-189">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d3243-189">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d3243-190">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d3243-190">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

