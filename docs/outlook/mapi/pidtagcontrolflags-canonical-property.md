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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430880"
---
# <a name="pidtagcontrolflags-canonical-property"></a><span data-ttu-id="0f68a-103">PidTagControlFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="0f68a-103">PidTagControlFlags Canonical Property</span></span>

  
  
<span data-ttu-id="0f68a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0f68a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0f68a-105">包含用于控制控件行为的标志位掩码，该控件在基于显示表构建的对话框中使用。</span><span class="sxs-lookup"><span data-stu-id="0f68a-105">Contains a bitmask of flags governing the behavior of a control used in a dialog box built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0f68a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0f68a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0f68a-107">PR_CONTROL_FLAGS</span><span class="sxs-lookup"><span data-stu-id="0f68a-107">PR_CONTROL_FLAGS</span></span>  <br/> |
|<span data-ttu-id="0f68a-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="0f68a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0f68a-109">0x3F00</span><span class="sxs-lookup"><span data-stu-id="0f68a-109">0x3F00</span></span>  <br/> |
|<span data-ttu-id="0f68a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0f68a-110">Data type:</span></span>  <br/> |<span data-ttu-id="0f68a-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="0f68a-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="0f68a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0f68a-112">Area:</span></span>  <br/> |<span data-ttu-id="0f68a-113">MAPI 显示表</span><span class="sxs-lookup"><span data-stu-id="0f68a-113">MAPI display table</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0f68a-114">备注</span><span class="sxs-lookup"><span data-stu-id="0f68a-114">Remarks</span></span>

<span data-ttu-id="0f68a-115">可以为此属性设置以下一个或多个标志：</span><span class="sxs-lookup"><span data-stu-id="0f68a-115">One or more of the following flags can be set for this property:</span></span>
  
<span data-ttu-id="0f68a-116">DT_ACCEPT_DBCS</span><span class="sxs-lookup"><span data-stu-id="0f68a-116">DT_ACCEPT_DBCS</span></span> 
  
> <span data-ttu-id="0f68a-117">该控件可以Double-Byte DBCS (字符) 字符集。</span><span class="sxs-lookup"><span data-stu-id="0f68a-117">The control can have Double-Byte Character Set (DBCS) characters in it.</span></span> <span data-ttu-id="0f68a-118">此标志与编辑控件一起使用。</span><span class="sxs-lookup"><span data-stu-id="0f68a-118">This flag is used with edit controls.</span></span> <span data-ttu-id="0f68a-119">它允许多字节字符集。</span><span class="sxs-lookup"><span data-stu-id="0f68a-119">It allows multiple-byte character sets.</span></span>
    
<span data-ttu-id="0f68a-120">DT_EDITABLE</span><span class="sxs-lookup"><span data-stu-id="0f68a-120">DT_EDITABLE</span></span> 
  
> <span data-ttu-id="0f68a-121">可以编辑控件;可更改与控件关联的值。</span><span class="sxs-lookup"><span data-stu-id="0f68a-121">The control can be edited; the value associated with the control can be changed.</span></span> <span data-ttu-id="0f68a-122">未设置此标志时，控件为只读。</span><span class="sxs-lookup"><span data-stu-id="0f68a-122">When this flag is not set, the control is read-only.</span></span> <span data-ttu-id="0f68a-123">在标签、分组框、标准推送按钮、多值下拉列表框和列表框控件上忽略此值。</span><span class="sxs-lookup"><span data-stu-id="0f68a-123">This value is ignored on label, group box, standard push button, multivalued drop down list box and list box controls.</span></span>
    
<span data-ttu-id="0f68a-124">DT_MULTILINE</span><span class="sxs-lookup"><span data-stu-id="0f68a-124">DT_MULTILINE</span></span> 
  
> <span data-ttu-id="0f68a-125">编辑控件可以包含多个行。</span><span class="sxs-lookup"><span data-stu-id="0f68a-125">The edit control can contain multiple lines.</span></span> <span data-ttu-id="0f68a-126">这意味着可以在控件中输入返回字符。</span><span class="sxs-lookup"><span data-stu-id="0f68a-126">This means a return character can be entered within the control.</span></span> <span data-ttu-id="0f68a-127">此标志仅对编辑控件有效。</span><span class="sxs-lookup"><span data-stu-id="0f68a-127">This flag is valid for edit controls only.</span></span>
    
<span data-ttu-id="0f68a-128">DT_PASSWORD_EDIT</span><span class="sxs-lookup"><span data-stu-id="0f68a-128">DT_PASSWORD_EDIT</span></span> 
  
> <span data-ttu-id="0f68a-129">适用于编辑控件。</span><span class="sxs-lookup"><span data-stu-id="0f68a-129">Applies to edit controls.</span></span> <span data-ttu-id="0f68a-130">编辑控件被视为密码。</span><span class="sxs-lookup"><span data-stu-id="0f68a-130">The edit control is treated like a password.</span></span> <span data-ttu-id="0f68a-131">该值使用星号显示，而不是返回输入的实际字符。</span><span class="sxs-lookup"><span data-stu-id="0f68a-131">The value is displayed using asterisks instead of echoing the actual characters entered.</span></span>
    
<span data-ttu-id="0f68a-132">DT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="0f68a-132">DT_REQUIRED</span></span> 
  
> <span data-ttu-id="0f68a-133">如果控件允许更改 (DT_EDITABLE) ，则必须在调用 [IMAPIProp：：SaveChanges 之前](imapiprop-savechanges.md) 具有值。</span><span class="sxs-lookup"><span data-stu-id="0f68a-133">If the control allows changes (DT_EDITABLE), it must have a value before [IMAPIProp::SaveChanges](imapiprop-savechanges.md) is called.</span></span> 
    
<span data-ttu-id="0f68a-134">DT_SET_IMMEDIATE</span><span class="sxs-lookup"><span data-stu-id="0f68a-134">DT_SET_IMMEDIATE</span></span> 
  
> <span data-ttu-id="0f68a-135">启用值的即时设置;控件中的值更改后，MAPI 就会为与该控件关联的属性调用 **SetProps** 方法。</span><span class="sxs-lookup"><span data-stu-id="0f68a-135">Enables immediate setting of a value; as soon as a value in the control changes, MAPI calls the **SetProps** method for the property associated with that control.</span></span> <span data-ttu-id="0f68a-136">未设置此标志时，在对话框关闭时设置值。</span><span class="sxs-lookup"><span data-stu-id="0f68a-136">When this flag is not set, the values are set when the dialog box is dismissed.</span></span> 
    
<span data-ttu-id="0f68a-137">DT_SET_SELECTION</span><span class="sxs-lookup"><span data-stu-id="0f68a-137">DT_SET_SELECTION</span></span> 
  
> <span data-ttu-id="0f68a-138">在列表框中进行选择时，该列表框的索引列设置为属性。</span><span class="sxs-lookup"><span data-stu-id="0f68a-138">When a selection is made within the list box, the index column of that list box is set as a property.</span></span> <span data-ttu-id="0f68a-139">始终与DT_SET_IMMEDIATE。</span><span class="sxs-lookup"><span data-stu-id="0f68a-139">Always used with DT_SET_IMMEDIATE.</span></span>
    
<span data-ttu-id="0f68a-140">此属性存储在控件的 [DTCTL](dtctl.md) 结构的 ulCtlFlags 成员中。</span><span class="sxs-lookup"><span data-stu-id="0f68a-140">This property is stored in the ulCtlFlags member of a control's [DTCTL](dtctl.md) structure.</span></span> <span data-ttu-id="0f68a-141">大多数控件标志适用于允许用户输入的所有控件;一些仅适用于编辑控件。</span><span class="sxs-lookup"><span data-stu-id="0f68a-141">Most of the control flags apply to all of the controls that allow user input; a few apply only to the edit control.</span></span> <span data-ttu-id="0f68a-142">不允许用户输入的控件（如按钮或标签）会为控件标志设置 0。</span><span class="sxs-lookup"><span data-stu-id="0f68a-142">Controls that do not allow user input, such as a button or a label, set 0 for their control flags.</span></span> 
  
<span data-ttu-id="0f68a-143">许多标志值都一目了然。</span><span class="sxs-lookup"><span data-stu-id="0f68a-143">Many of the flag values are self-explanatory.</span></span> <span data-ttu-id="0f68a-144">例如，当DT_REQUIRED控件时，控件必须包含一个值，然后才能允许对话框关闭。</span><span class="sxs-lookup"><span data-stu-id="0f68a-144">For example, when DT_REQUIRED is set for a control, it must contain a value before the dialog box is allowed to be dismissed.</span></span> <span data-ttu-id="0f68a-145">服务提供商可以通过 **IMAPIProp** 实现提供值，或者用户可以输入值。</span><span class="sxs-lookup"><span data-stu-id="0f68a-145">Either the service provider can supply a value through its **IMAPIProp** implementation or the user can enter one.</span></span> <span data-ttu-id="0f68a-146">DT_EDITABLE指示可以修改控件的值。</span><span class="sxs-lookup"><span data-stu-id="0f68a-146">DT_EDITABLE indicates that the value for the control can be modified.</span></span> <span data-ttu-id="0f68a-147">DT_MULTILINE允许编辑控件的值跨越多行。</span><span class="sxs-lookup"><span data-stu-id="0f68a-147">DT_MULTILINE allows the value for an edit control to span multiple lines.</span></span> 
  
<span data-ttu-id="0f68a-148">某些控件标志的含义并不明显。</span><span class="sxs-lookup"><span data-stu-id="0f68a-148">Some control flags are not so obvious in their meaning.</span></span> <span data-ttu-id="0f68a-149">当控件设置DT_SET_IMMEDIATE标志时，只要用户移动到新控件，其值的任何更改都会生效。</span><span class="sxs-lookup"><span data-stu-id="0f68a-149">When a control sets the DT_SET_IMMEDIATE flag, any changes to its value take affect as soon as the user moves to a new control.</span></span> <span data-ttu-id="0f68a-150">MAPI 对控件属性的属性的 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法进行单个调用。</span><span class="sxs-lookup"><span data-stu-id="0f68a-150">MAPI makes a single call to the property interface's [IMAPIProp::SetProps](imapiprop-setprops.md) method for the control's property.</span></span> <span data-ttu-id="0f68a-151">这不同于默认行为，即推迟更改控件值生效，直到用户选择"确定"按钮或关闭对话框。 </span><span class="sxs-lookup"><span data-stu-id="0f68a-151">This is different from the default behavior, which is to postpone having changes to control values take effect until after the user selects the **OK** button or dismisses the dialog box.</span></span> <span data-ttu-id="0f68a-152">DT_SET_IMMEDIATE标志通常与显示表通知结合使用。</span><span class="sxs-lookup"><span data-stu-id="0f68a-152">The DT_SET_IMMEDIATE flag is often used in combination with display table notifications.</span></span> 
  
<span data-ttu-id="0f68a-153">下表列出了控件的类型以及可以针对每种类型设置的所有标志值。</span><span class="sxs-lookup"><span data-stu-id="0f68a-153">The following table lists the types of controls and all of the flag values that can be set for each type.</span></span>
  
|<span data-ttu-id="0f68a-154">**Control**</span><span class="sxs-lookup"><span data-stu-id="0f68a-154">**Control**</span></span>|<span data-ttu-id="0f68a-155">**此属性的有效值**</span><span class="sxs-lookup"><span data-stu-id="0f68a-155">**Valid values for this property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0f68a-156">按钮</span><span class="sxs-lookup"><span data-stu-id="0f68a-156">Button</span></span>  <br/> |<span data-ttu-id="0f68a-157">必须为零</span><span class="sxs-lookup"><span data-stu-id="0f68a-157">Must be zero</span></span>  <br/> |
|<span data-ttu-id="0f68a-158">复选框</span><span class="sxs-lookup"><span data-stu-id="0f68a-158">Check box</span></span>  <br/> |<span data-ttu-id="0f68a-159">DT_EDITABLE、DT_SET_IMMEDIATE</span><span class="sxs-lookup"><span data-stu-id="0f68a-159">DT_EDITABLE, DT_SET_IMMEDIATE</span></span>  <br/> |
|<span data-ttu-id="0f68a-160">组合框</span><span class="sxs-lookup"><span data-stu-id="0f68a-160">Combo box</span></span>  <br/> |<span data-ttu-id="0f68a-161">DT_EDITABLE、DT_REQUIRED、DT_SET_IMMEDIATE</span><span class="sxs-lookup"><span data-stu-id="0f68a-161">DT_EDITABLE, DT_REQUIRED, DT_SET_IMMEDIATE</span></span>  <br/> |
|<span data-ttu-id="0f68a-162">下拉列表框</span><span class="sxs-lookup"><span data-stu-id="0f68a-162">Drop-down list box</span></span>  <br/> |<span data-ttu-id="0f68a-163">DT_EDITABLE、DT_SET_IMMEDIATE</span><span class="sxs-lookup"><span data-stu-id="0f68a-163">DT_EDITABLE, DT_SET_IMMEDIATE</span></span>  <br/> |
|<span data-ttu-id="0f68a-164">编辑</span><span class="sxs-lookup"><span data-stu-id="0f68a-164">Edit</span></span>  <br/> |<span data-ttu-id="0f68a-165">DT_ACCEPT_DBCS、DT_MULTILINE、DT_EDITABLE、DT_PASSWORD_EDIT、DT_REQUIRED、DT_SET_IMMEDIATE</span><span class="sxs-lookup"><span data-stu-id="0f68a-165">DT_ACCEPT_DBCS, DT_MULTILINE, DT_EDITABLE, DT_PASSWORD_EDIT, DT_REQUIRED, DT_SET_IMMEDIATE</span></span>  <br/> |
|<span data-ttu-id="0f68a-166">分组框</span><span class="sxs-lookup"><span data-stu-id="0f68a-166">Group box</span></span>  <br/> |<span data-ttu-id="0f68a-167">必须为零</span><span class="sxs-lookup"><span data-stu-id="0f68a-167">Must be zero</span></span>  <br/> |
|<span data-ttu-id="0f68a-168">标签</span><span class="sxs-lookup"><span data-stu-id="0f68a-168">Label</span></span>  <br/> |<span data-ttu-id="0f68a-169">必须为零</span><span class="sxs-lookup"><span data-stu-id="0f68a-169">Must be zero</span></span>  <br/> |
|<span data-ttu-id="0f68a-170">列表框</span><span class="sxs-lookup"><span data-stu-id="0f68a-170">List box</span></span>  <br/> |<span data-ttu-id="0f68a-171">必须为零</span><span class="sxs-lookup"><span data-stu-id="0f68a-171">Must be zero</span></span>  <br/> |
|<span data-ttu-id="0f68a-172">多值下拉列表框</span><span class="sxs-lookup"><span data-stu-id="0f68a-172">Multivalue drop-down list box</span></span>  <br/> |<span data-ttu-id="0f68a-173">必须为零</span><span class="sxs-lookup"><span data-stu-id="0f68a-173">Must be zero</span></span>  <br/> |
|<span data-ttu-id="0f68a-174">多值列表框</span><span class="sxs-lookup"><span data-stu-id="0f68a-174">Multivalue list box</span></span>  <br/> |<span data-ttu-id="0f68a-175">必须为零</span><span class="sxs-lookup"><span data-stu-id="0f68a-175">Must be zero</span></span>  <br/> |
|<span data-ttu-id="0f68a-176">选项卡式页面</span><span class="sxs-lookup"><span data-stu-id="0f68a-176">Tabbed page</span></span>  <br/> |<span data-ttu-id="0f68a-177">必须为零</span><span class="sxs-lookup"><span data-stu-id="0f68a-177">Must be zero</span></span>  <br/> |
|<span data-ttu-id="0f68a-178">单选按钮</span><span class="sxs-lookup"><span data-stu-id="0f68a-178">Radio button</span></span>  <br/> |<span data-ttu-id="0f68a-179">必须为零</span><span class="sxs-lookup"><span data-stu-id="0f68a-179">Must be zero</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="0f68a-180">相关资源</span><span class="sxs-lookup"><span data-stu-id="0f68a-180">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="0f68a-181">头文件</span><span class="sxs-lookup"><span data-stu-id="0f68a-181">Header files</span></span>

<span data-ttu-id="0f68a-182">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0f68a-182">Mapidefs.h</span></span>
  
> <span data-ttu-id="0f68a-183">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0f68a-183">Provides data type definitions.</span></span>
    
<span data-ttu-id="0f68a-184">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="0f68a-184">Mapitags.h</span></span>
  
> <span data-ttu-id="0f68a-185">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0f68a-185">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0f68a-186">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f68a-186">See also</span></span>



[<span data-ttu-id="0f68a-187">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0f68a-187">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0f68a-188">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0f68a-188">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0f68a-189">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0f68a-189">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0f68a-190">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0f68a-190">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

