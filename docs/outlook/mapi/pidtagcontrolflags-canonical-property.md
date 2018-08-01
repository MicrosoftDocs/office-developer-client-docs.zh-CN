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
ms.openlocfilehash: f6947efe1aa6866efb7a5a3d96262d021c68013f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777507"
---
# <a name="pidtagcontrolflags-canonical-property"></a><span data-ttu-id="e3cf8-103">PidTagControlFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="e3cf8-103">PidTagControlFlags Canonical Property</span></span>

  
  
<span data-ttu-id="e3cf8-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e3cf8-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e3cf8-105">包含调控显示表中生成的对话框中使用控件的行为的标志位的掩码。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-105">Contains a bitmask of flags governing the behavior of a control used in a dialog box built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e3cf8-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e3cf8-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e3cf8-107">PR_CONTROL_FLAGS</span><span class="sxs-lookup"><span data-stu-id="e3cf8-107">PR_CONTROL_FLAGS</span></span>  <br/> |
|<span data-ttu-id="e3cf8-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="e3cf8-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e3cf8-109">0x3F00</span><span class="sxs-lookup"><span data-stu-id="e3cf8-109">0x3F00</span></span>  <br/> |
|<span data-ttu-id="e3cf8-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e3cf8-110">Data type:</span></span>  <br/> |<span data-ttu-id="e3cf8-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="e3cf8-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="e3cf8-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e3cf8-112">Area:</span></span>  <br/> |<span data-ttu-id="e3cf8-113">MAPI 显示表</span><span class="sxs-lookup"><span data-stu-id="e3cf8-113">MAPI display table</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e3cf8-114">说明</span><span class="sxs-lookup"><span data-stu-id="e3cf8-114">Remarks</span></span>

<span data-ttu-id="e3cf8-115">此属性，可以设置一个或多个以下标志：</span><span class="sxs-lookup"><span data-stu-id="e3cf8-115">One or more of the following flags can be set for this property:</span></span>
  
<span data-ttu-id="e3cf8-116">DT_ACCEPT_DBCS</span><span class="sxs-lookup"><span data-stu-id="e3cf8-116">DT_ACCEPT_DBCS</span></span> 
  
> <span data-ttu-id="e3cf8-117">该控件可在其中包含双字节字符集 (DBCS) 字符。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-117">The control can have Double-Byte Character Set (DBCS) characters in it.</span></span> <span data-ttu-id="e3cf8-118">此标志用于编辑控件。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-118">This flag is used with edit controls.</span></span> <span data-ttu-id="e3cf8-119">允许多个字节字符集。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-119">It allows multiple-byte character sets.</span></span>
    
<span data-ttu-id="e3cf8-120">DT_EDITABLE</span><span class="sxs-lookup"><span data-stu-id="e3cf8-120">DT_EDITABLE</span></span> 
  
> <span data-ttu-id="e3cf8-121">可以编辑控件;可以更改与控件关联的值。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-121">The control can be edited; the value associated with the control can be changed.</span></span> <span data-ttu-id="e3cf8-122">当未设置此标志时，控件是只读的。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-122">When this flag is not set, the control is read-only.</span></span> <span data-ttu-id="e3cf8-123">此值，则忽略上标签、 组框、 标准下压按钮、 多值的下拉列表框和列表框控件。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-123">This value is ignored on label, group box, standard push button, multivalued drop down list box and list box controls.</span></span>
    
<span data-ttu-id="e3cf8-124">DT_MULTILINE</span><span class="sxs-lookup"><span data-stu-id="e3cf8-124">DT_MULTILINE</span></span> 
  
> <span data-ttu-id="e3cf8-125">编辑控件可以包含多个行。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-125">The edit control can contain multiple lines.</span></span> <span data-ttu-id="e3cf8-126">这意味着回车符可以输入的控件内。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-126">This means a return character can be entered within the control.</span></span> <span data-ttu-id="e3cf8-127">此标志是有效的编辑控件仅。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-127">This flag is valid for edit controls only.</span></span>
    
<span data-ttu-id="e3cf8-128">DT_PASSWORD_EDIT</span><span class="sxs-lookup"><span data-stu-id="e3cf8-128">DT_PASSWORD_EDIT</span></span> 
  
> <span data-ttu-id="e3cf8-129">适用于编辑控件。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-129">Applies to edit controls.</span></span> <span data-ttu-id="e3cf8-130">编辑控件被视为一个密码。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-130">The edit control is treated like a password.</span></span> <span data-ttu-id="e3cf8-131">而不回声输入的实际字符使用星号来显示值。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-131">The value is displayed using asterisks instead of echoing the actual characters entered.</span></span>
    
<span data-ttu-id="e3cf8-132">DT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="e3cf8-132">DT_REQUIRED</span></span> 
  
> <span data-ttu-id="e3cf8-133">如果该控件允许更改 (DT_EDITABLE)，它必须具有一个值，调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)之前。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-133">If the control allows changes (DT_EDITABLE), it must have a value before [IMAPIProp::SaveChanges](imapiprop-savechanges.md) is called.</span></span> 
    
<span data-ttu-id="e3cf8-134">DT_SET_IMMEDIATE</span><span class="sxs-lookup"><span data-stu-id="e3cf8-134">DT_SET_IMMEDIATE</span></span> 
  
> <span data-ttu-id="e3cf8-135">启用即时设置的值;只要在控件中的值更改，MAPI 调用与该控件关联的属性的**SetProps**方法。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-135">Enables immediate setting of a value; as soon as a value in the control changes, MAPI calls the **SetProps** method for the property associated with that control.</span></span> <span data-ttu-id="e3cf8-136">当未设置此标志时，当消除对话框中设置的值。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-136">When this flag is not set, the values are set when the dialog box is dismissed.</span></span> 
    
<span data-ttu-id="e3cf8-137">DT_SET_SELECTION</span><span class="sxs-lookup"><span data-stu-id="e3cf8-137">DT_SET_SELECTION</span></span> 
  
> <span data-ttu-id="e3cf8-138">当列表框中进行选择时，该列表框的索引列被设置为属性。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-138">When a selection is made within the list box, the index column of that list box is set as a property.</span></span> <span data-ttu-id="e3cf8-139">始终与 DT_SET_IMMEDIATE 一起使用。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-139">Always used with DT_SET_IMMEDIATE.</span></span>
    
<span data-ttu-id="e3cf8-140">此属性存储在控件的[DTCTL](dtctl.md)结构的 ulCtlFlags 成员。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-140">This property is stored in the ulCtlFlags member of a control's [DTCTL](dtctl.md) structure.</span></span> <span data-ttu-id="e3cf8-141">大部分控制标志适用于所有控件，允许用户输入;一些仅适用于编辑控件。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-141">Most of the control flags apply to all of the controls that allow user input; a few apply only to the edit control.</span></span> <span data-ttu-id="e3cf8-142">不允许用户输入按钮或标签，如的控制设置其控制标志为 0。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-142">Controls that do not allow user input, such as a button or a label, set 0 for their control flags.</span></span> 
  
<span data-ttu-id="e3cf8-143">许多标志值是显而易见的。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-143">Many of the flag values are self-explanatory.</span></span> <span data-ttu-id="e3cf8-144">例如，当 DT_REQUIRED 设置控件时，它必须包含一个值，对话框允许解除之前。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-144">For example, when DT_REQUIRED is set for a control, it must contain a value before the dialog box is allowed to be dismissed.</span></span> <span data-ttu-id="e3cf8-145">服务提供商可以提供通过**IMAPIProp**实现其值，或者用户可以输入一个。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-145">Either the service provider can supply a value through its **IMAPIProp** implementation or the user can enter one.</span></span> <span data-ttu-id="e3cf8-146">DT_EDITABLE 指示可以修改该控件的值。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-146">DT_EDITABLE indicates that the value for the control can be modified.</span></span> <span data-ttu-id="e3cf8-147">DT_MULTILINE 允许编辑控件以跨多个行的值。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-147">DT_MULTILINE allows the value for an edit control to span multiple lines.</span></span> 
  
<span data-ttu-id="e3cf8-148">一些控制标志不那么明显中及其含义。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-148">Some control flags are not so obvious in their meaning.</span></span> <span data-ttu-id="e3cf8-149">当控件集 DT_SET_IMMEDIATE 标志时、 其值要采取的任何更改将影响只要用户移动到一个新的控件。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-149">When a control sets the DT_SET_IMMEDIATE flag, any changes to its value take affect as soon as the user moves to a new control.</span></span> <span data-ttu-id="e3cf8-150">MAPI 单个调用属性接口的[IMAPIProp::SetProps](imapiprop-setprops.md)方法，用于控件的属性。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-150">MAPI makes a single call to the property interface's [IMAPIProp::SetProps](imapiprop-setprops.md) method for the control's property.</span></span> <span data-ttu-id="e3cf8-151">这一点不同于默认行为，即延迟具有对控件值的更改在用户选择**确定**按钮或消除对话框后会生效。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-151">This is different from the default behavior, which is to postpone having changes to control values take effect until after the user selects the **OK** button or dismisses the dialog box.</span></span> <span data-ttu-id="e3cf8-152">DT_SET_IMMEDIATE 标志常用与显示表通知结合使用。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-152">The DT_SET_IMMEDIATE flag is often used in combination with display table notifications.</span></span> 
  
<span data-ttu-id="e3cf8-153">下表列出的控件的类型和所有可以为每种类型的标志值。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-153">The following table lists the types of controls and all of the flag values that can be set for each type.</span></span>
  
|<span data-ttu-id="e3cf8-154">**控件**</span><span class="sxs-lookup"><span data-stu-id="e3cf8-154">**Control**</span></span>|<span data-ttu-id="e3cf8-155">**此属性的有效值**</span><span class="sxs-lookup"><span data-stu-id="e3cf8-155">**Valid values for this property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e3cf8-156">按钮</span><span class="sxs-lookup"><span data-stu-id="e3cf8-156">Button</span></span>  <br/> |<span data-ttu-id="e3cf8-157">必须为零</span><span class="sxs-lookup"><span data-stu-id="e3cf8-157">Must be zero</span></span>  <br/> |
|<span data-ttu-id="e3cf8-158">复选框</span><span class="sxs-lookup"><span data-stu-id="e3cf8-158">Check box</span></span>  <br/> |<span data-ttu-id="e3cf8-159">DT_EDITABLE DT_SET_IMMEDIATE</span><span class="sxs-lookup"><span data-stu-id="e3cf8-159">DT_EDITABLE, DT_SET_IMMEDIATE</span></span>  <br/> |
|<span data-ttu-id="e3cf8-160">组合框</span><span class="sxs-lookup"><span data-stu-id="e3cf8-160">Combo box</span></span>  <br/> |<span data-ttu-id="e3cf8-161">DT_EDITABLE，DT_REQUIRED，DT_SET_IMMEDIATE</span><span class="sxs-lookup"><span data-stu-id="e3cf8-161">DT_EDITABLE, DT_REQUIRED, DT_SET_IMMEDIATE</span></span>  <br/> |
|<span data-ttu-id="e3cf8-162">下拉列表框</span><span class="sxs-lookup"><span data-stu-id="e3cf8-162">Drop-down list box</span></span>  <br/> |<span data-ttu-id="e3cf8-163">DT_EDITABLE DT_SET_IMMEDIATE</span><span class="sxs-lookup"><span data-stu-id="e3cf8-163">DT_EDITABLE, DT_SET_IMMEDIATE</span></span>  <br/> |
|<span data-ttu-id="e3cf8-164">编辑</span><span class="sxs-lookup"><span data-stu-id="e3cf8-164">Edit</span></span>  <br/> |<span data-ttu-id="e3cf8-165">DT_ACCEPT_DBCS、 DT_MULTILINE、 DT_EDITABLE、 DT_PASSWORD_EDIT、 DT_REQUIRED、 DT_SET_IMMEDIATE</span><span class="sxs-lookup"><span data-stu-id="e3cf8-165">DT_ACCEPT_DBCS, DT_MULTILINE, DT_EDITABLE, DT_PASSWORD_EDIT, DT_REQUIRED, DT_SET_IMMEDIATE</span></span>  <br/> |
|<span data-ttu-id="e3cf8-166">分组框</span><span class="sxs-lookup"><span data-stu-id="e3cf8-166">Group box</span></span>  <br/> |<span data-ttu-id="e3cf8-167">必须为零</span><span class="sxs-lookup"><span data-stu-id="e3cf8-167">Must be zero</span></span>  <br/> |
|<span data-ttu-id="e3cf8-168">标签</span><span class="sxs-lookup"><span data-stu-id="e3cf8-168">Label</span></span>  <br/> |<span data-ttu-id="e3cf8-169">必须为零</span><span class="sxs-lookup"><span data-stu-id="e3cf8-169">Must be zero</span></span>  <br/> |
|<span data-ttu-id="e3cf8-170">列表框</span><span class="sxs-lookup"><span data-stu-id="e3cf8-170">List box</span></span>  <br/> |<span data-ttu-id="e3cf8-171">必须为零</span><span class="sxs-lookup"><span data-stu-id="e3cf8-171">Must be zero</span></span>  <br/> |
|<span data-ttu-id="e3cf8-172">多值下拉列表框</span><span class="sxs-lookup"><span data-stu-id="e3cf8-172">Multivalue drop-down list box</span></span>  <br/> |<span data-ttu-id="e3cf8-173">必须为零</span><span class="sxs-lookup"><span data-stu-id="e3cf8-173">Must be zero</span></span>  <br/> |
|<span data-ttu-id="e3cf8-174">多值列表框</span><span class="sxs-lookup"><span data-stu-id="e3cf8-174">Multivalue list box</span></span>  <br/> |<span data-ttu-id="e3cf8-175">必须为零</span><span class="sxs-lookup"><span data-stu-id="e3cf8-175">Must be zero</span></span>  <br/> |
|<span data-ttu-id="e3cf8-176">选项卡式的页面</span><span class="sxs-lookup"><span data-stu-id="e3cf8-176">Tabbed page</span></span>  <br/> |<span data-ttu-id="e3cf8-177">必须为零</span><span class="sxs-lookup"><span data-stu-id="e3cf8-177">Must be zero</span></span>  <br/> |
|<span data-ttu-id="e3cf8-178">单选按钮</span><span class="sxs-lookup"><span data-stu-id="e3cf8-178">Radio button</span></span>  <br/> |<span data-ttu-id="e3cf8-179">必须为零</span><span class="sxs-lookup"><span data-stu-id="e3cf8-179">Must be zero</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="e3cf8-180">相关资源</span><span class="sxs-lookup"><span data-stu-id="e3cf8-180">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="e3cf8-181">头文件</span><span class="sxs-lookup"><span data-stu-id="e3cf8-181">Header files</span></span>

<span data-ttu-id="e3cf8-182">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e3cf8-182">Mapidefs.h</span></span>
  
> <span data-ttu-id="e3cf8-183">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-183">Provides data type definitions.</span></span>
    
<span data-ttu-id="e3cf8-184">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e3cf8-184">Mapitags.h</span></span>
  
> <span data-ttu-id="e3cf8-185">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e3cf8-185">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e3cf8-186">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3cf8-186">See also</span></span>



[<span data-ttu-id="e3cf8-187">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e3cf8-187">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e3cf8-188">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e3cf8-188">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e3cf8-189">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e3cf8-189">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e3cf8-190">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e3cf8-190">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

