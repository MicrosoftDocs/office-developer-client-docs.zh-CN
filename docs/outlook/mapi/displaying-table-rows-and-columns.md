---
title: 显示表行和列
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 49567a8d-b58d-4636-bead-a1f84b4f111d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f9f1cc0bebf3c90a5c12f2714e8ab7eea59104da
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337021"
---
# <a name="displaying-table-rows-and-columns"></a><span data-ttu-id="1c2ba-103">显示表行和列</span><span class="sxs-lookup"><span data-stu-id="1c2ba-103">Displaying Table Rows and Columns</span></span>

  
  
<span data-ttu-id="1c2ba-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1c2ba-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="1c2ba-105">通讯簿提供程序可以使用属性页来使用户能够定义新的电子邮件收件人。</span><span class="sxs-lookup"><span data-stu-id="1c2ba-105">A property page can be used by an address book provider to enable users to define new email recipients.</span></span> 
  
<span data-ttu-id="1c2ba-106">对应的显示表包含四行, 每个控件一个。</span><span class="sxs-lookup"><span data-stu-id="1c2ba-106">The corresponding display table contains four rows, one for each control.</span></span> <span data-ttu-id="1c2ba-107">指示位置的列的值如下所示。</span><span class="sxs-lookup"><span data-stu-id="1c2ba-107">The values for the columns that indicate position are as follows.</span></span>
  
|<span data-ttu-id="1c2ba-108">**Control**</span><span class="sxs-lookup"><span data-stu-id="1c2ba-108">**Control**</span></span>|<span data-ttu-id="1c2ba-109">**XPOS**</span><span class="sxs-lookup"><span data-stu-id="1c2ba-109">**XPOS**</span></span>|<span data-ttu-id="1c2ba-110">**YPOS**</span><span class="sxs-lookup"><span data-stu-id="1c2ba-110">**YPOS**</span></span>|<span data-ttu-id="1c2ba-111">**DELTAX**</span><span class="sxs-lookup"><span data-stu-id="1c2ba-111">**DELTAX**</span></span>|<span data-ttu-id="1c2ba-112">**DELTAY**</span><span class="sxs-lookup"><span data-stu-id="1c2ba-112">**DELTAY**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1c2ba-113">"显示名称" 标签</span><span class="sxs-lookup"><span data-stu-id="1c2ba-113">Display name label</span></span>  <br/> |<span data-ttu-id="1c2ba-114">日</span><span class="sxs-lookup"><span data-stu-id="1c2ba-114">14</span></span>  <br/> |<span data-ttu-id="1c2ba-115">18</span><span class="sxs-lookup"><span data-stu-id="1c2ba-115">18</span></span>  <br/> |<span data-ttu-id="1c2ba-116">49</span><span class="sxs-lookup"><span data-stu-id="1c2ba-116">49</span></span>  <br/> |<span data-ttu-id="1c2ba-117">utf-8</span><span class="sxs-lookup"><span data-stu-id="1c2ba-117">8</span></span>  <br/> |
|<span data-ttu-id="1c2ba-118">"显示名称" 编辑框</span><span class="sxs-lookup"><span data-stu-id="1c2ba-118">Display name edit box</span></span>  <br/> |<span data-ttu-id="1c2ba-119">76</span><span class="sxs-lookup"><span data-stu-id="1c2ba-119">76</span></span>  <br/> |<span data-ttu-id="1c2ba-120">位</span><span class="sxs-lookup"><span data-stu-id="1c2ba-120">16</span></span>  <br/> |<span data-ttu-id="1c2ba-121">89</span><span class="sxs-lookup"><span data-stu-id="1c2ba-121">89</span></span>  <br/> |<span data-ttu-id="1c2ba-122">12</span><span class="sxs-lookup"><span data-stu-id="1c2ba-122">12</span></span>  <br/> |
|<span data-ttu-id="1c2ba-123">电子邮件地址标签</span><span class="sxs-lookup"><span data-stu-id="1c2ba-123">Email address label</span></span>  <br/> |<span data-ttu-id="1c2ba-124">日</span><span class="sxs-lookup"><span data-stu-id="1c2ba-124">14</span></span>  <br/> |<span data-ttu-id="1c2ba-125">42</span><span class="sxs-lookup"><span data-stu-id="1c2ba-125">42</span></span>  <br/> |<span data-ttu-id="1c2ba-126">50</span><span class="sxs-lookup"><span data-stu-id="1c2ba-126">50</span></span>  <br/> |<span data-ttu-id="1c2ba-127">utf-8</span><span class="sxs-lookup"><span data-stu-id="1c2ba-127">8</span></span>  <br/> |
|<span data-ttu-id="1c2ba-128">"电子邮件地址" 编辑框</span><span class="sxs-lookup"><span data-stu-id="1c2ba-128">Email address edit box</span></span>  <br/> |<span data-ttu-id="1c2ba-129">76</span><span class="sxs-lookup"><span data-stu-id="1c2ba-129">76</span></span>  <br/> |<span data-ttu-id="1c2ba-130">40</span><span class="sxs-lookup"><span data-stu-id="1c2ba-130">40</span></span>  <br/> |<span data-ttu-id="1c2ba-131">89</span><span class="sxs-lookup"><span data-stu-id="1c2ba-131">89</span></span>  <br/> |<span data-ttu-id="1c2ba-132">12</span><span class="sxs-lookup"><span data-stu-id="1c2ba-132">12</span></span>  <br/> |
|<span data-ttu-id="1c2ba-133">复选框</span><span class="sxs-lookup"><span data-stu-id="1c2ba-133">Check box</span></span>  <br/> |<span data-ttu-id="1c2ba-134">日</span><span class="sxs-lookup"><span data-stu-id="1c2ba-134">14</span></span>  <br/> |<span data-ttu-id="1c2ba-135">64</span><span class="sxs-lookup"><span data-stu-id="1c2ba-135">64</span></span>  <br/> |<span data-ttu-id="1c2ba-136">90</span><span class="sxs-lookup"><span data-stu-id="1c2ba-136">90</span></span>  <br/> |<span data-ttu-id="1c2ba-137">12</span><span class="sxs-lookup"><span data-stu-id="1c2ba-137">12</span></span>  <br/> |
   
<span data-ttu-id="1c2ba-138">下一个表为控件的类型、其**PR_CONTROL_TYPE** ([PidTagControlType](pidtagcontroltype-canonical-property.md)) 属性和 flags 的位掩码 ( **PR_CONTROL_FLAGS** ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)) 属性) 提供了相应的值。</span><span class="sxs-lookup"><span data-stu-id="1c2ba-138">This next table suggests appropriate values for the control's type, its **PR_CONTROL_TYPE** ([PidTagControlType](pidtagcontroltype-canonical-property.md)) property, and bitmask of flags, its **PR_CONTROL_FLAGS** ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)) property.</span></span>
  
|<span data-ttu-id="1c2ba-139">**Control**</span><span class="sxs-lookup"><span data-stu-id="1c2ba-139">**Control**</span></span>|<span data-ttu-id="1c2ba-140">**Type**</span><span class="sxs-lookup"><span data-stu-id="1c2ba-140">**Type**</span></span>|<span data-ttu-id="1c2ba-141">**Flags**</span><span class="sxs-lookup"><span data-stu-id="1c2ba-141">**Flags**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1c2ba-142">"显示名称" 标签</span><span class="sxs-lookup"><span data-stu-id="1c2ba-142">Display name label</span></span>  <br/> |<span data-ttu-id="1c2ba-143">DTCT_LABEL</span><span class="sxs-lookup"><span data-stu-id="1c2ba-143">DTCT_LABEL</span></span>  <br/> |<span data-ttu-id="1c2ba-144">0</span><span class="sxs-lookup"><span data-stu-id="1c2ba-144">0</span></span>  <br/> |
|<span data-ttu-id="1c2ba-145">"显示名称" 编辑框</span><span class="sxs-lookup"><span data-stu-id="1c2ba-145">Display name edit box</span></span>  <br/> |<span data-ttu-id="1c2ba-146">DTCT_EDIT</span><span class="sxs-lookup"><span data-stu-id="1c2ba-146">DTCT_EDIT</span></span>  <br/> |<span data-ttu-id="1c2ba-147">DT_EDITABLE</span><span class="sxs-lookup"><span data-stu-id="1c2ba-147">DT_EDITABLE</span></span> | <span data-ttu-id="1c2ba-148">DT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="1c2ba-148">DT_REQUIRED</span></span>  <br/> |
|<span data-ttu-id="1c2ba-149">电子邮件地址标签</span><span class="sxs-lookup"><span data-stu-id="1c2ba-149">Email address label</span></span>  <br/> |<span data-ttu-id="1c2ba-150">DTCT_LABEL</span><span class="sxs-lookup"><span data-stu-id="1c2ba-150">DTCT_LABEL</span></span>  <br/> |<span data-ttu-id="1c2ba-151">0</span><span class="sxs-lookup"><span data-stu-id="1c2ba-151">0</span></span>  <br/> |
|<span data-ttu-id="1c2ba-152">"电子邮件地址" 编辑框</span><span class="sxs-lookup"><span data-stu-id="1c2ba-152">Email address edit box</span></span>  <br/> |<span data-ttu-id="1c2ba-153">DTCT_EDIT</span><span class="sxs-lookup"><span data-stu-id="1c2ba-153">DTCT_EDIT</span></span>  <br/> |<span data-ttu-id="1c2ba-154">DT_EDITABLE</span><span class="sxs-lookup"><span data-stu-id="1c2ba-154">DT_EDITABLE</span></span> | <span data-ttu-id="1c2ba-155">DT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="1c2ba-155">DT_REQUIRED</span></span>  <br/> |
|<span data-ttu-id="1c2ba-156">复选框</span><span class="sxs-lookup"><span data-stu-id="1c2ba-156">Check box</span></span>  <br/> |<span data-ttu-id="1c2ba-157">DTCT_CHECKBOX</span><span class="sxs-lookup"><span data-stu-id="1c2ba-157">DTCT_CHECKBOX</span></span>  <br/> |<span data-ttu-id="1c2ba-158">DT_EDITABLE</span><span class="sxs-lookup"><span data-stu-id="1c2ba-158">DT_EDITABLE</span></span>  <br/> |
   
<span data-ttu-id="1c2ba-159">最终表格列出了每个控件及其关联的控制结构的内容。</span><span class="sxs-lookup"><span data-stu-id="1c2ba-159">The final table lists each control with the contents of its associated control structure.</span></span> <span data-ttu-id="1c2ba-160">请注意, 每个标签控件的值将直接出现在内存中的结构后面。</span><span class="sxs-lookup"><span data-stu-id="1c2ba-160">Notice that the value for each of the label controls appears in memory directly following the structure.</span></span>
  
|<span data-ttu-id="1c2ba-161">**Control**</span><span class="sxs-lookup"><span data-stu-id="1c2ba-161">**Control**</span></span>|<span data-ttu-id="1c2ba-162">**结构**</span><span class="sxs-lookup"><span data-stu-id="1c2ba-162">**Structure**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1c2ba-163">"显示名称" 标签</span><span class="sxs-lookup"><span data-stu-id="1c2ba-163">Display name label</span></span>  <br/> |<span data-ttu-id="1c2ba-164">{sizeof (DTBLLABEL), 0}"显示名称:"</span><span class="sxs-lookup"><span data-stu-id="1c2ba-164">{sizeof(DTBLLABEL), 0} "Display name:"</span></span>  <br/> |
|<span data-ttu-id="1c2ba-165">"显示名称" 编辑框</span><span class="sxs-lookup"><span data-stu-id="1c2ba-165">Display name edit box</span></span>  <br/> |<span data-ttu-id="1c2ba-166">{sizeof (DTBLEDIT)、0、80、PR_DISPLAY_NAME}</span><span class="sxs-lookup"><span data-stu-id="1c2ba-166">{sizeof(DTBLEDIT), 0, 80, PR_DISPLAY_NAME}</span></span>  <br/> |
|<span data-ttu-id="1c2ba-167">电子邮件地址标签</span><span class="sxs-lookup"><span data-stu-id="1c2ba-167">Email address label</span></span>  <br/> |<span data-ttu-id="1c2ba-168">{sizeof (DTBLLABEL), 0}"电子邮件地址:"</span><span class="sxs-lookup"><span data-stu-id="1c2ba-168">{sizeof(DTBLLABEL), 0} "Email address:"</span></span>  <br/> |
|<span data-ttu-id="1c2ba-169">"电子邮件地址" 编辑框</span><span class="sxs-lookup"><span data-stu-id="1c2ba-169">Email address edit box</span></span>  <br/> |<span data-ttu-id="1c2ba-170">{sizeof (DTBLEDIT)、0、80、PR_EMAIL_ADDRESS}</span><span class="sxs-lookup"><span data-stu-id="1c2ba-170">{sizeof(DTBLEDIT), 0, 80, PR_EMAIL_ADDRESS}</span></span>  <br/> |
|<span data-ttu-id="1c2ba-171">复选框</span><span class="sxs-lookup"><span data-stu-id="1c2ba-171">Check box</span></span>  <br/> |<span data-ttu-id="1c2ba-172">PR_SEND_RICH_INFO</span><span class="sxs-lookup"><span data-stu-id="1c2ba-172">PR_SEND_RICH_INFO</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="1c2ba-173">**"确定**"、"**取消**" 和 "**帮助**" 按钮不包含在显示表中。</span><span class="sxs-lookup"><span data-stu-id="1c2ba-173">The **OK**, **Cancel**, and **Help** buttons are not included in the display table.</span></span> <span data-ttu-id="1c2ba-174">用户界面可以通过添加不在显示表中的控件, 向对话框添加上下文。</span><span class="sxs-lookup"><span data-stu-id="1c2ba-174">The user interface can add context to a dialog box by adding controls not in the display table.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1c2ba-175">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c2ba-175">See also</span></span>



[<span data-ttu-id="1c2ba-176">显示表实现</span><span class="sxs-lookup"><span data-stu-id="1c2ba-176">Display Table Implementation</span></span>](display-table-implementation.md)

