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
ms.openlocfilehash: dba7bd1fb7b0ca9bc23dbc45e07f44d0cc0dc8fe
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568138"
---
# <a name="displaying-table-rows-and-columns"></a><span data-ttu-id="a3525-103">显示表行和列</span><span class="sxs-lookup"><span data-stu-id="a3525-103">Displaying Table Rows and Columns</span></span>

  
  
<span data-ttu-id="a3525-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a3525-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="a3525-105">属性页面可以使用通讯簿提供程序以便用户能够定义新的电子邮件收件人。</span><span class="sxs-lookup"><span data-stu-id="a3525-105">A property page can be used by an address book provider to enable users to define new email recipients.</span></span> 
  
<span data-ttu-id="a3525-106">相应的显示表包含四个行，一个用于每个控件。</span><span class="sxs-lookup"><span data-stu-id="a3525-106">The corresponding display table contains four rows, one for each control.</span></span> <span data-ttu-id="a3525-107">指示位置的列的值如下所示。</span><span class="sxs-lookup"><span data-stu-id="a3525-107">The values for the columns that indicate position are as follows.</span></span>
  
|<span data-ttu-id="a3525-108">**控件**</span><span class="sxs-lookup"><span data-stu-id="a3525-108">**Control**</span></span>|<span data-ttu-id="a3525-109">**XPOS**</span><span class="sxs-lookup"><span data-stu-id="a3525-109">**XPOS**</span></span>|<span data-ttu-id="a3525-110">**YPOS**</span><span class="sxs-lookup"><span data-stu-id="a3525-110">**YPOS**</span></span>|<span data-ttu-id="a3525-111">**DELTAX**</span><span class="sxs-lookup"><span data-stu-id="a3525-111">**DELTAX**</span></span>|<span data-ttu-id="a3525-112">**DELTAY**</span><span class="sxs-lookup"><span data-stu-id="a3525-112">**DELTAY**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a3525-113">显示名称标签</span><span class="sxs-lookup"><span data-stu-id="a3525-113">Display name label</span></span>  <br/> |<span data-ttu-id="a3525-114">14</span><span class="sxs-lookup"><span data-stu-id="a3525-114">14</span></span>  <br/> |<span data-ttu-id="a3525-115">18</span><span class="sxs-lookup"><span data-stu-id="a3525-115">18</span></span>  <br/> |<span data-ttu-id="a3525-116">49</span><span class="sxs-lookup"><span data-stu-id="a3525-116">49</span></span>  <br/> |<span data-ttu-id="a3525-117">8</span><span class="sxs-lookup"><span data-stu-id="a3525-117">8</span></span>  <br/> |
|<span data-ttu-id="a3525-118">显示名称编辑框</span><span class="sxs-lookup"><span data-stu-id="a3525-118">Display name edit box</span></span>  <br/> |<span data-ttu-id="a3525-119">76</span><span class="sxs-lookup"><span data-stu-id="a3525-119">76</span></span>  <br/> |<span data-ttu-id="a3525-120">16</span><span class="sxs-lookup"><span data-stu-id="a3525-120">16</span></span>  <br/> |<span data-ttu-id="a3525-121">89</span><span class="sxs-lookup"><span data-stu-id="a3525-121">89</span></span>  <br/> |<span data-ttu-id="a3525-122">12</span><span class="sxs-lookup"><span data-stu-id="a3525-122">12</span></span>  <br/> |
|<span data-ttu-id="a3525-123">电子邮件地址标签</span><span class="sxs-lookup"><span data-stu-id="a3525-123">Email address label</span></span>  <br/> |<span data-ttu-id="a3525-124">14</span><span class="sxs-lookup"><span data-stu-id="a3525-124">14</span></span>  <br/> |<span data-ttu-id="a3525-125">42</span><span class="sxs-lookup"><span data-stu-id="a3525-125">42</span></span>  <br/> |<span data-ttu-id="a3525-126">50</span><span class="sxs-lookup"><span data-stu-id="a3525-126">50</span></span>  <br/> |<span data-ttu-id="a3525-127">8</span><span class="sxs-lookup"><span data-stu-id="a3525-127">8</span></span>  <br/> |
|<span data-ttu-id="a3525-128">电子邮件地址编辑框</span><span class="sxs-lookup"><span data-stu-id="a3525-128">Email address edit box</span></span>  <br/> |<span data-ttu-id="a3525-129">76</span><span class="sxs-lookup"><span data-stu-id="a3525-129">76</span></span>  <br/> |<span data-ttu-id="a3525-130">40</span><span class="sxs-lookup"><span data-stu-id="a3525-130">40</span></span>  <br/> |<span data-ttu-id="a3525-131">89</span><span class="sxs-lookup"><span data-stu-id="a3525-131">89</span></span>  <br/> |<span data-ttu-id="a3525-132">12</span><span class="sxs-lookup"><span data-stu-id="a3525-132">12</span></span>  <br/> |
|<span data-ttu-id="a3525-133">复选框</span><span class="sxs-lookup"><span data-stu-id="a3525-133">Check box</span></span>  <br/> |<span data-ttu-id="a3525-134">14</span><span class="sxs-lookup"><span data-stu-id="a3525-134">14</span></span>  <br/> |<span data-ttu-id="a3525-135">64</span><span class="sxs-lookup"><span data-stu-id="a3525-135">64</span></span>  <br/> |<span data-ttu-id="a3525-136">90</span><span class="sxs-lookup"><span data-stu-id="a3525-136">90</span></span>  <br/> |<span data-ttu-id="a3525-137">12</span><span class="sxs-lookup"><span data-stu-id="a3525-137">12</span></span>  <br/> |
   
<span data-ttu-id="a3525-138">此下表建议控件的类型、 **PR_CONTROL_TYPE** ([PidTagControlType](pidtagcontroltype-canonical-property.md)) 属性和标志，其**PR_CONTROL_FLAGS** ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)) 属性的位掩码的相应的值。</span><span class="sxs-lookup"><span data-stu-id="a3525-138">This next table suggests appropriate values for the control's type, its **PR_CONTROL_TYPE** ([PidTagControlType](pidtagcontroltype-canonical-property.md)) property, and bitmask of flags, its **PR_CONTROL_FLAGS** ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)) property.</span></span>
  
|<span data-ttu-id="a3525-139">**控件**</span><span class="sxs-lookup"><span data-stu-id="a3525-139">**Control**</span></span>|<span data-ttu-id="a3525-140">**类型**</span><span class="sxs-lookup"><span data-stu-id="a3525-140">**Type**</span></span>|<span data-ttu-id="a3525-141">**Flags**</span><span class="sxs-lookup"><span data-stu-id="a3525-141">**Flags**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a3525-142">显示名称标签</span><span class="sxs-lookup"><span data-stu-id="a3525-142">Display name label</span></span>  <br/> |<span data-ttu-id="a3525-143">DTCT_LABEL</span><span class="sxs-lookup"><span data-stu-id="a3525-143">DTCT_LABEL</span></span>  <br/> |<span data-ttu-id="a3525-144">0</span><span class="sxs-lookup"><span data-stu-id="a3525-144">0</span></span>  <br/> |
|<span data-ttu-id="a3525-145">显示名称编辑框</span><span class="sxs-lookup"><span data-stu-id="a3525-145">Display name edit box</span></span>  <br/> |<span data-ttu-id="a3525-146">DTCT_EDIT</span><span class="sxs-lookup"><span data-stu-id="a3525-146">DTCT_EDIT</span></span>  <br/> |<span data-ttu-id="a3525-147">DT_EDITABLE</span><span class="sxs-lookup"><span data-stu-id="a3525-147">DT_EDITABLE</span></span> | <span data-ttu-id="a3525-148">DT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="a3525-148">DT_REQUIRED</span></span>  <br/> |
|<span data-ttu-id="a3525-149">电子邮件地址标签</span><span class="sxs-lookup"><span data-stu-id="a3525-149">Email address label</span></span>  <br/> |<span data-ttu-id="a3525-150">DTCT_LABEL</span><span class="sxs-lookup"><span data-stu-id="a3525-150">DTCT_LABEL</span></span>  <br/> |<span data-ttu-id="a3525-151">0</span><span class="sxs-lookup"><span data-stu-id="a3525-151">0</span></span>  <br/> |
|<span data-ttu-id="a3525-152">电子邮件地址编辑框</span><span class="sxs-lookup"><span data-stu-id="a3525-152">Email address edit box</span></span>  <br/> |<span data-ttu-id="a3525-153">DTCT_EDIT</span><span class="sxs-lookup"><span data-stu-id="a3525-153">DTCT_EDIT</span></span>  <br/> |<span data-ttu-id="a3525-154">DT_EDITABLE</span><span class="sxs-lookup"><span data-stu-id="a3525-154">DT_EDITABLE</span></span> | <span data-ttu-id="a3525-155">DT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="a3525-155">DT_REQUIRED</span></span>  <br/> |
|<span data-ttu-id="a3525-156">复选框</span><span class="sxs-lookup"><span data-stu-id="a3525-156">Check box</span></span>  <br/> |<span data-ttu-id="a3525-157">DTCT_CHECKBOX</span><span class="sxs-lookup"><span data-stu-id="a3525-157">DTCT_CHECKBOX</span></span>  <br/> |<span data-ttu-id="a3525-158">DT_EDITABLE</span><span class="sxs-lookup"><span data-stu-id="a3525-158">DT_EDITABLE</span></span>  <br/> |
   
<span data-ttu-id="a3525-159">最终的表列出了每个控件使用其关联的控件结构的内容。</span><span class="sxs-lookup"><span data-stu-id="a3525-159">The final table lists each control with the contents of its associated control structure.</span></span> <span data-ttu-id="a3525-160">请注意，每个标签控件的值显示在紧结构的内存中。</span><span class="sxs-lookup"><span data-stu-id="a3525-160">Notice that the value for each of the label controls appears in memory directly following the structure.</span></span>
  
|<span data-ttu-id="a3525-161">**控件**</span><span class="sxs-lookup"><span data-stu-id="a3525-161">**Control**</span></span>|<span data-ttu-id="a3525-162">**结构**</span><span class="sxs-lookup"><span data-stu-id="a3525-162">**Structure**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a3525-163">显示名称标签</span><span class="sxs-lookup"><span data-stu-id="a3525-163">Display name label</span></span>  <br/> |<span data-ttu-id="a3525-164">{sizeof(DTBLLABEL)，0}"显示名称:"</span><span class="sxs-lookup"><span data-stu-id="a3525-164">{sizeof(DTBLLABEL), 0} "Display name:"</span></span>  <br/> |
|<span data-ttu-id="a3525-165">显示名称编辑框</span><span class="sxs-lookup"><span data-stu-id="a3525-165">Display name edit box</span></span>  <br/> |<span data-ttu-id="a3525-166">{sizeof(DTBLEDIT)，0，80，PR_DISPLAY_NAME}</span><span class="sxs-lookup"><span data-stu-id="a3525-166">{sizeof(DTBLEDIT), 0, 80, PR_DISPLAY_NAME}</span></span>  <br/> |
|<span data-ttu-id="a3525-167">电子邮件地址标签</span><span class="sxs-lookup"><span data-stu-id="a3525-167">Email address label</span></span>  <br/> |<span data-ttu-id="a3525-168">{sizeof(DTBLLABEL)，0}"电子邮件地址:"</span><span class="sxs-lookup"><span data-stu-id="a3525-168">{sizeof(DTBLLABEL), 0} "Email address:"</span></span>  <br/> |
|<span data-ttu-id="a3525-169">电子邮件地址编辑框</span><span class="sxs-lookup"><span data-stu-id="a3525-169">Email address edit box</span></span>  <br/> |<span data-ttu-id="a3525-170">{sizeof(DTBLEDIT)，0，80，PR_EMAIL_ADDRESS}</span><span class="sxs-lookup"><span data-stu-id="a3525-170">{sizeof(DTBLEDIT), 0, 80, PR_EMAIL_ADDRESS}</span></span>  <br/> |
|<span data-ttu-id="a3525-171">复选框</span><span class="sxs-lookup"><span data-stu-id="a3525-171">Check box</span></span>  <br/> |<span data-ttu-id="a3525-172">PR_SEND_RICH_INFO</span><span class="sxs-lookup"><span data-stu-id="a3525-172">PR_SEND_RICH_INFO</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="a3525-173">显示表中不包含**确定**、**取消**和**帮助**按钮。</span><span class="sxs-lookup"><span data-stu-id="a3525-173">The **OK**, **Cancel**, and **Help** buttons are not included in the display table.</span></span> <span data-ttu-id="a3525-174">用户界面可以通过添加控件显示表中没有在对话框中添加上下文。</span><span class="sxs-lookup"><span data-stu-id="a3525-174">The user interface can add context to a dialog box by adding controls not in the display table.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a3525-175">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3525-175">See also</span></span>



[<span data-ttu-id="a3525-176">显示表实现</span><span class="sxs-lookup"><span data-stu-id="a3525-176">Display Table Implementation</span></span>](display-table-implementation.md)

