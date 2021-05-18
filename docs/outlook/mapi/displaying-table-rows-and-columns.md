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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407114"
---
# <a name="displaying-table-rows-and-columns"></a><span data-ttu-id="9d858-103">显示表行和列</span><span class="sxs-lookup"><span data-stu-id="9d858-103">Displaying Table Rows and Columns</span></span>

  
  
<span data-ttu-id="9d858-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9d858-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="9d858-105">通讯簿提供程序可以使用属性页来使用户能够定义新的电子邮件收件人。</span><span class="sxs-lookup"><span data-stu-id="9d858-105">A property page can be used by an address book provider to enable users to define new email recipients.</span></span> 
  
<span data-ttu-id="9d858-106">相应的显示表包含四行，每个控件一行。</span><span class="sxs-lookup"><span data-stu-id="9d858-106">The corresponding display table contains four rows, one for each control.</span></span> <span data-ttu-id="9d858-107">指示位置的列的值如下所示。</span><span class="sxs-lookup"><span data-stu-id="9d858-107">The values for the columns that indicate position are as follows.</span></span>
  
|<span data-ttu-id="9d858-108">**Control**</span><span class="sxs-lookup"><span data-stu-id="9d858-108">**Control**</span></span>|<span data-ttu-id="9d858-109">**XPOS**</span><span class="sxs-lookup"><span data-stu-id="9d858-109">**XPOS**</span></span>|<span data-ttu-id="9d858-110">**YPOS**</span><span class="sxs-lookup"><span data-stu-id="9d858-110">**YPOS**</span></span>|<span data-ttu-id="9d858-111">**DELTAX**</span><span class="sxs-lookup"><span data-stu-id="9d858-111">**DELTAX**</span></span>|<span data-ttu-id="9d858-112">**DELTAY**</span><span class="sxs-lookup"><span data-stu-id="9d858-112">**DELTAY**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9d858-113">显示名称标签</span><span class="sxs-lookup"><span data-stu-id="9d858-113">Display name label</span></span>  <br/> |<span data-ttu-id="9d858-114">14 </span><span class="sxs-lookup"><span data-stu-id="9d858-114">14</span></span>  <br/> |<span data-ttu-id="9d858-115">18 </span><span class="sxs-lookup"><span data-stu-id="9d858-115">18</span></span>  <br/> |<span data-ttu-id="9d858-116">49</span><span class="sxs-lookup"><span data-stu-id="9d858-116">49</span></span>  <br/> |<span data-ttu-id="9d858-117">8 </span><span class="sxs-lookup"><span data-stu-id="9d858-117">8</span></span>  <br/> |
|<span data-ttu-id="9d858-118">显示名称编辑框</span><span class="sxs-lookup"><span data-stu-id="9d858-118">Display name edit box</span></span>  <br/> |<span data-ttu-id="9d858-119">76</span><span class="sxs-lookup"><span data-stu-id="9d858-119">76</span></span>  <br/> |<span data-ttu-id="9d858-120">16 </span><span class="sxs-lookup"><span data-stu-id="9d858-120">16</span></span>  <br/> |<span data-ttu-id="9d858-121">89</span><span class="sxs-lookup"><span data-stu-id="9d858-121">89</span></span>  <br/> |<span data-ttu-id="9d858-122">12 </span><span class="sxs-lookup"><span data-stu-id="9d858-122">12</span></span>  <br/> |
|<span data-ttu-id="9d858-123">电子邮件地址标签</span><span class="sxs-lookup"><span data-stu-id="9d858-123">Email address label</span></span>  <br/> |<span data-ttu-id="9d858-124">14 </span><span class="sxs-lookup"><span data-stu-id="9d858-124">14</span></span>  <br/> |<span data-ttu-id="9d858-125">42</span><span class="sxs-lookup"><span data-stu-id="9d858-125">42</span></span>  <br/> |<span data-ttu-id="9d858-126">50</span><span class="sxs-lookup"><span data-stu-id="9d858-126">50</span></span>  <br/> |<span data-ttu-id="9d858-127">8 </span><span class="sxs-lookup"><span data-stu-id="9d858-127">8</span></span>  <br/> |
|<span data-ttu-id="9d858-128">电子邮件地址编辑框</span><span class="sxs-lookup"><span data-stu-id="9d858-128">Email address edit box</span></span>  <br/> |<span data-ttu-id="9d858-129">76</span><span class="sxs-lookup"><span data-stu-id="9d858-129">76</span></span>  <br/> |<span data-ttu-id="9d858-130">40</span><span class="sxs-lookup"><span data-stu-id="9d858-130">40</span></span>  <br/> |<span data-ttu-id="9d858-131">89</span><span class="sxs-lookup"><span data-stu-id="9d858-131">89</span></span>  <br/> |<span data-ttu-id="9d858-132">12 </span><span class="sxs-lookup"><span data-stu-id="9d858-132">12</span></span>  <br/> |
|<span data-ttu-id="9d858-133">复选框</span><span class="sxs-lookup"><span data-stu-id="9d858-133">Check box</span></span>  <br/> |<span data-ttu-id="9d858-134">14 </span><span class="sxs-lookup"><span data-stu-id="9d858-134">14</span></span>  <br/> |<span data-ttu-id="9d858-135">64</span><span class="sxs-lookup"><span data-stu-id="9d858-135">64</span></span>  <br/> |<span data-ttu-id="9d858-136">90</span><span class="sxs-lookup"><span data-stu-id="9d858-136">90</span></span>  <br/> |<span data-ttu-id="9d858-137">12 </span><span class="sxs-lookup"><span data-stu-id="9d858-137">12</span></span>  <br/> |
   
<span data-ttu-id="9d858-138">下表为控件的类型、它的 **PR_CONTROL_TYPE** ([PidTagControlType](pidtagcontroltype-canonical-property.md)) 属性和标志的位掩码、PR_CONTROL_FLAGS ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)) 属性提供了相应的建议。 </span><span class="sxs-lookup"><span data-stu-id="9d858-138">This next table suggests appropriate values for the control's type, its **PR_CONTROL_TYPE** ([PidTagControlType](pidtagcontroltype-canonical-property.md)) property, and bitmask of flags, its **PR_CONTROL_FLAGS** ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)) property.</span></span>
  
|<span data-ttu-id="9d858-139">**Control**</span><span class="sxs-lookup"><span data-stu-id="9d858-139">**Control**</span></span>|<span data-ttu-id="9d858-140">**类型**</span><span class="sxs-lookup"><span data-stu-id="9d858-140">**Type**</span></span>|<span data-ttu-id="9d858-141">**Flags**</span><span class="sxs-lookup"><span data-stu-id="9d858-141">**Flags**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9d858-142">显示名称标签</span><span class="sxs-lookup"><span data-stu-id="9d858-142">Display name label</span></span>  <br/> |<span data-ttu-id="9d858-143">DTCT_LABEL</span><span class="sxs-lookup"><span data-stu-id="9d858-143">DTCT_LABEL</span></span>  <br/> |<span data-ttu-id="9d858-144">0</span><span class="sxs-lookup"><span data-stu-id="9d858-144">0</span></span>  <br/> |
|<span data-ttu-id="9d858-145">显示名称编辑框</span><span class="sxs-lookup"><span data-stu-id="9d858-145">Display name edit box</span></span>  <br/> |<span data-ttu-id="9d858-146">DTCT_EDIT</span><span class="sxs-lookup"><span data-stu-id="9d858-146">DTCT_EDIT</span></span>  <br/> |<span data-ttu-id="9d858-147">DT_EDITABLE</span><span class="sxs-lookup"><span data-stu-id="9d858-147">DT_EDITABLE</span></span> | <span data-ttu-id="9d858-148">DT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="9d858-148">DT_REQUIRED</span></span>  <br/> |
|<span data-ttu-id="9d858-149">电子邮件地址标签</span><span class="sxs-lookup"><span data-stu-id="9d858-149">Email address label</span></span>  <br/> |<span data-ttu-id="9d858-150">DTCT_LABEL</span><span class="sxs-lookup"><span data-stu-id="9d858-150">DTCT_LABEL</span></span>  <br/> |<span data-ttu-id="9d858-151">0</span><span class="sxs-lookup"><span data-stu-id="9d858-151">0</span></span>  <br/> |
|<span data-ttu-id="9d858-152">电子邮件地址编辑框</span><span class="sxs-lookup"><span data-stu-id="9d858-152">Email address edit box</span></span>  <br/> |<span data-ttu-id="9d858-153">DTCT_EDIT</span><span class="sxs-lookup"><span data-stu-id="9d858-153">DTCT_EDIT</span></span>  <br/> |<span data-ttu-id="9d858-154">DT_EDITABLE</span><span class="sxs-lookup"><span data-stu-id="9d858-154">DT_EDITABLE</span></span> | <span data-ttu-id="9d858-155">DT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="9d858-155">DT_REQUIRED</span></span>  <br/> |
|<span data-ttu-id="9d858-156">复选框</span><span class="sxs-lookup"><span data-stu-id="9d858-156">Check box</span></span>  <br/> |<span data-ttu-id="9d858-157">DTCT_CHECKBOX</span><span class="sxs-lookup"><span data-stu-id="9d858-157">DTCT_CHECKBOX</span></span>  <br/> |<span data-ttu-id="9d858-158">DT_EDITABLE</span><span class="sxs-lookup"><span data-stu-id="9d858-158">DT_EDITABLE</span></span>  <br/> |
   
<span data-ttu-id="9d858-159">最后一个表列出了每个控件及其关联的控件结构的内容。</span><span class="sxs-lookup"><span data-stu-id="9d858-159">The final table lists each control with the contents of its associated control structure.</span></span> <span data-ttu-id="9d858-160">请注意，每个标签控件的值都直接显示在内存中结构之后。</span><span class="sxs-lookup"><span data-stu-id="9d858-160">Notice that the value for each of the label controls appears in memory directly following the structure.</span></span>
  
|<span data-ttu-id="9d858-161">**Control**</span><span class="sxs-lookup"><span data-stu-id="9d858-161">**Control**</span></span>|<span data-ttu-id="9d858-162">**结构**</span><span class="sxs-lookup"><span data-stu-id="9d858-162">**Structure**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9d858-163">显示名称标签</span><span class="sxs-lookup"><span data-stu-id="9d858-163">Display name label</span></span>  <br/> |<span data-ttu-id="9d858-164">{sizeof (DTBLLABEL) ， 0}"显示名称："</span><span class="sxs-lookup"><span data-stu-id="9d858-164">{sizeof(DTBLLABEL), 0} "Display name:"</span></span>  <br/> |
|<span data-ttu-id="9d858-165">显示名称编辑框</span><span class="sxs-lookup"><span data-stu-id="9d858-165">Display name edit box</span></span>  <br/> |<span data-ttu-id="9d858-166">{sizeof (DTBLEDIT) ， 0， 80， PR_DISPLAY_NAME}</span><span class="sxs-lookup"><span data-stu-id="9d858-166">{sizeof(DTBLEDIT), 0, 80, PR_DISPLAY_NAME}</span></span>  <br/> |
|<span data-ttu-id="9d858-167">电子邮件地址标签</span><span class="sxs-lookup"><span data-stu-id="9d858-167">Email address label</span></span>  <br/> |<span data-ttu-id="9d858-168">{sizeof (DTBLLABEL) ， 0}"电子邮件地址："</span><span class="sxs-lookup"><span data-stu-id="9d858-168">{sizeof(DTBLLABEL), 0} "Email address:"</span></span>  <br/> |
|<span data-ttu-id="9d858-169">电子邮件地址编辑框</span><span class="sxs-lookup"><span data-stu-id="9d858-169">Email address edit box</span></span>  <br/> |<span data-ttu-id="9d858-170">{sizeof (DTBLEDIT) ， 0， 80， PR_EMAIL_ADDRESS}</span><span class="sxs-lookup"><span data-stu-id="9d858-170">{sizeof(DTBLEDIT), 0, 80, PR_EMAIL_ADDRESS}</span></span>  <br/> |
|<span data-ttu-id="9d858-171">复选框</span><span class="sxs-lookup"><span data-stu-id="9d858-171">Check box</span></span>  <br/> |<span data-ttu-id="9d858-172">PR_SEND_RICH_INFO</span><span class="sxs-lookup"><span data-stu-id="9d858-172">PR_SEND_RICH_INFO</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="9d858-173">"**确定\*\*\*\*"、"** 取消"和"帮助"按钮不包括在显示表中。</span><span class="sxs-lookup"><span data-stu-id="9d858-173">The **OK**, **Cancel**, and **Help** buttons are not included in the display table.</span></span> <span data-ttu-id="9d858-174">用户界面可以通过添加不在显示表中的控件来向对话框添加上下文。</span><span class="sxs-lookup"><span data-stu-id="9d858-174">The user interface can add context to a dialog box by adding controls not in the display table.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9d858-175">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d858-175">See also</span></span>



[<span data-ttu-id="9d858-176">显示表实现</span><span class="sxs-lookup"><span data-stu-id="9d858-176">Display Table Implementation</span></span>](display-table-implementation.md)

