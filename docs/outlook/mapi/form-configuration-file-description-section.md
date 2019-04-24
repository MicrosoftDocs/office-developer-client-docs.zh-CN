---
title: 表单配置文件 [说明] 部分
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4ce91a65-17db-4ee2-ad59-01fd5b1f1ea7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ddc59d6c503d44a0575679fce694cc34499d8e2a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32320984"
---
# <a name="form-configuration-file-description-section"></a><span data-ttu-id="1dc7c-103">表单配置文件 [说明] 部分</span><span class="sxs-lookup"><span data-stu-id="1dc7c-103">Form Configuration File [Description] Section</span></span>
 
<span data-ttu-id="1dc7c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1dc7c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1dc7c-105">**[说明]** 部分列出了与窗体的用户界面中的控件关联的窗体的所有属性, 以及用于查找窗体的属性。</span><span class="sxs-lookup"><span data-stu-id="1dc7c-105">The **[Description]** section lists all properties of the form that are associated with controls in the form's user interface, plus attributes that are used in locating the form.</span></span> <span data-ttu-id="1dc7c-106">" **MessageClass**"、" **Clsid**" 和 " **DisplayName** " 条目分别标识表单的邮件类的名称、其 GUID 和邮件类的显示名称, 这是用于在表单库中查找表单的必需条目。.</span><span class="sxs-lookup"><span data-stu-id="1dc7c-106">The **MessageClass**, **Clsid**, and **DisplayName** entries, which identify the name of the form's message class, its GUID, and the message class's display name, respectively, are required entries used to locate the form within the form library.</span></span> <span data-ttu-id="1dc7c-107">其余的项是可选的。</span><span class="sxs-lookup"><span data-stu-id="1dc7c-107">The remaining entries are optional.</span></span> <span data-ttu-id="1dc7c-108">**[Description]** 部分的格式为:</span><span class="sxs-lookup"><span data-stu-id="1dc7c-108">The format of the **[Description]** section is:</span></span> 
  
<span data-ttu-id="1dc7c-109">**[说明]** 部分列出了与窗体的用户界面中的控件关联的窗体的所有属性, 以及用于查找窗体的属性。</span><span class="sxs-lookup"><span data-stu-id="1dc7c-109">The **[Description]** section lists all properties of the form that are associated with controls in the form's user interface, plus attributes that are used in locating the form.</span></span> <span data-ttu-id="1dc7c-110">" **MessageClass**"、" **Clsid**" 和 " **DisplayName** " 条目分别标识表单的邮件类的名称、其 GUID 和邮件类的显示名称, 这是用于在表单库中查找表单的必需条目。.</span><span class="sxs-lookup"><span data-stu-id="1dc7c-110">The **MessageClass**, **Clsid**, and **DisplayName** entries, which identify the name of the form's message class, its GUID, and the message class's display name, respectively, are required entries used to locate the form within the form library.</span></span> <span data-ttu-id="1dc7c-111">其余的项是可选的。</span><span class="sxs-lookup"><span data-stu-id="1dc7c-111">The remaining entries are optional.</span></span> <span data-ttu-id="1dc7c-112">**[Description]** 部分的格式为:</span><span class="sxs-lookup"><span data-stu-id="1dc7c-112">The format of the **[Description]** section is:</span></span> 
  
 <span data-ttu-id="1dc7c-113">**产品介绍MessageClass** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="1dc7c-113">**[Description] MessageClass** =  _string_</span></span>
  
 <span data-ttu-id="1dc7c-114">**Clsid** =  _guid_</span><span class="sxs-lookup"><span data-stu-id="1dc7c-114">**Clsid** =  _guid_</span></span>
  
 <span data-ttu-id="1dc7c-115">**DisplayName** =  _displayedstring_</span><span class="sxs-lookup"><span data-stu-id="1dc7c-115">**DisplayName** =  _displayedstring_</span></span>
  
 <span data-ttu-id="1dc7c-116">**SmallIcon** =  _路径_</span><span class="sxs-lookup"><span data-stu-id="1dc7c-116">**SmallIcon** =  _path_</span></span>
  
 <span data-ttu-id="1dc7c-117">**LargeIcon** =  _路径_</span><span class="sxs-lookup"><span data-stu-id="1dc7c-117">**LargeIcon** =  _path_</span></span>
  
<span data-ttu-id="1dc7c-118">可选条目为:</span><span class="sxs-lookup"><span data-stu-id="1dc7c-118">Optional entries are:</span></span>
  
 <span data-ttu-id="1dc7c-119">**类别** =  _显示字符串_</span><span class="sxs-lookup"><span data-stu-id="1dc7c-119">**Category** =  _displayed string_</span></span>
  
 <span data-ttu-id="1dc7c-120">**子类别** =  _显示字符串_</span><span class="sxs-lookup"><span data-stu-id="1dc7c-120">**Subcategory** =  _displayed string_</span></span>
  
 <span data-ttu-id="1dc7c-121">**注释** =  _显示字符串_</span><span class="sxs-lookup"><span data-stu-id="1dc7c-121">**Comment** =  _displayed string_</span></span>
  
 <span data-ttu-id="1dc7c-122">**所有者** =  _显示字符串_</span><span class="sxs-lookup"><span data-stu-id="1dc7c-122">**Owner** =  _displayed string_</span></span>
  
 <span data-ttu-id="1dc7c-123">**数字** =  _显示字符串_</span><span class="sxs-lookup"><span data-stu-id="1dc7c-123">**Number** =  _displayed string_</span></span>
  
 <span data-ttu-id="1dc7c-124">**版本** =  _整数_</span><span class="sxs-lookup"><span data-stu-id="1dc7c-124">**Version** =  _integer_</span></span>
  
 <span data-ttu-id="1dc7c-125">**区域设置** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="1dc7c-125">**Locale** =  _string_</span></span>
  
 <span data-ttu-id="1dc7c-126">**隐藏** =  _整数_</span><span class="sxs-lookup"><span data-stu-id="1dc7c-126">**Hidden** =  _integer_</span></span>
  
 <span data-ttu-id="1dc7c-127">**DesignerToolName** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="1dc7c-127">**DesignerToolName** =  _string_</span></span>
  
 <span data-ttu-id="1dc7c-128">**DesignerToolGuid** =  _clsid_</span><span class="sxs-lookup"><span data-stu-id="1dc7c-128">**DesignerToolGuid** =  _clsid_</span></span>
  
 <span data-ttu-id="1dc7c-129">**DesignerRuntimeGuid** =  _clsid_</span><span class="sxs-lookup"><span data-stu-id="1dc7c-129">**DesignerRuntimeGuid** =  _clsid_</span></span>
  
 <span data-ttu-id="1dc7c-130">**ComposeInFolder** =  _0 | 1_</span><span class="sxs-lookup"><span data-stu-id="1dc7c-130">**ComposeInFolder** =  _0|1_</span></span>
  
 <span data-ttu-id="1dc7c-131">**ComposeCommand** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="1dc7c-131">**ComposeCommand** =  _string_</span></span>
  
<span data-ttu-id="1dc7c-132">"**类别**" 和 "**子**类别" 条目由窗体安装程序用于设置客户端应用程序用户界面中的窗体的默认分类。</span><span class="sxs-lookup"><span data-stu-id="1dc7c-132">The **Category** and **Subcategory** entries are used by form installers to set up the default categorization of forms within client application's user interface.</span></span> <span data-ttu-id="1dc7c-133">例如, 可以设置一个层次结构, 其中 "技术支持" 是类别, "软件" 和 "硬件" 是子类别。</span><span class="sxs-lookup"><span data-stu-id="1dc7c-133">For example a hierarchy could be set up where "Help Desk" is the category and "Software" and "Hardware" were the subcategories.</span></span> <span data-ttu-id="1dc7c-134">然后, 查看器应用程序可以使用此分类以一种更有条理的方式显示邮件。</span><span class="sxs-lookup"><span data-stu-id="1dc7c-134">This categorization can then be used by viewer applications to display messages in a more organized way.</span></span> <span data-ttu-id="1dc7c-135">**注释**、**所有者**和**编号**条目是在客户端应用程序的用户界面中显示的所有注释字符串。</span><span class="sxs-lookup"><span data-stu-id="1dc7c-135">The **Comment**, **Owner**, and **Number** entries are all comment strings that appear in client application's user interface.</span></span> <span data-ttu-id="1dc7c-136">这些是表单特定的属性, 可由表单开发人员的决定使用。</span><span class="sxs-lookup"><span data-stu-id="1dc7c-136">These are form specific properties that can be used at the discretion of the form developer.</span></span> <span data-ttu-id="1dc7c-137">例如,**注释**条目可用于指示表单的用途、用于指示负责维护表单的人员或组织的**所有者**条目, 以及用于跟踪表单的不同版本的编号。</span><span class="sxs-lookup"><span data-stu-id="1dc7c-137">For example, the **Comment** entry can be used to indicate the purpose of the form, the **Owner** entry used to indicate the person or organization responsible for maintaining the form, and the number used to track different version of the form.</span></span> <span data-ttu-id="1dc7c-138">对于**注释**条目, 最长可包含10行注释。</span><span class="sxs-lookup"><span data-stu-id="1dc7c-138">For the **Comment** entry, up to ten lines of comments can be included.</span></span> <span data-ttu-id="1dc7c-139">注释的第一行使用单词 "Comment" 作为键, 第二行注释使用 "Comment1" 作为键, 依此类推, 通过 "Comment9"。</span><span class="sxs-lookup"><span data-stu-id="1dc7c-139">The first line of comments uses the word "Comment" as the key, the second line of comments uses "Comment1" as the key, and so on through "Comment9."</span></span> 
  
<span data-ttu-id="1dc7c-140">**LargeIcon**和**SmallIcon**项用于指定用于在客户端应用程序的用户界面中显示图标的图标资源的路径, 这通常适用于包含**PR_ICON**的表行 ([PidTagIcon](pidtagicon-canonical-property.md))或**PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) 属性列。</span><span class="sxs-lookup"><span data-stu-id="1dc7c-140">The **LargeIcon** and **SmallIcon** entries are used to specify the path for the icon resources used to display icons in the client application's user interface, typically this is for table rows that include the **PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) or **PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) property columns.</span></span> <span data-ttu-id="1dc7c-141">可以将图标文件名称指定为相对于安装表单配置文件的目录的路径名。</span><span class="sxs-lookup"><span data-stu-id="1dc7c-141">Icon file names can be specified as pathnames relative to the directory where the form configuration file is installed.</span></span> <span data-ttu-id="1dc7c-142">**版本**条目用于指示表单的版本号。</span><span class="sxs-lookup"><span data-stu-id="1dc7c-142">The **Version** entry is used to indicate the version number of the form.</span></span> <span data-ttu-id="1dc7c-143">**区域设置**是目标表单库的三个字母的语言标识符。</span><span class="sxs-lookup"><span data-stu-id="1dc7c-143">**Locale** is the three-letter language identifier of the destination form library.</span></span> <span data-ttu-id="1dc7c-144">可以在_Win32 程序员参考_中找到这些标识符的列表。</span><span class="sxs-lookup"><span data-stu-id="1dc7c-144">A list of these identifiers can be found in the  _Win32 Programmer's Reference_.</span></span>
  
<span data-ttu-id="1dc7c-145">**隐藏**条目指示表单是否应显示在表单库提供程序的用户界面中: 1 表示文件处于隐藏状态, 0 表示窗体可见。</span><span class="sxs-lookup"><span data-stu-id="1dc7c-145">The **Hidden** entry indicates whether the form should be displayed in a form library provider's user interface: 1 indicates that the file is hidden and 0 indicates that the form is visible.</span></span> <span data-ttu-id="1dc7c-146">示例表单配置文件如下所示。</span><span class="sxs-lookup"><span data-stu-id="1dc7c-146">An example form configuration file is shown following.</span></span> 
  
<span data-ttu-id="1dc7c-147">**ComposeInFolder**条目控制在用户保存邮件时是否将窗体放置在当前文件夹或用户的收件箱中: 1 表示该表单应进入当前文件夹, 0 表示应转到 "收件箱"。</span><span class="sxs-lookup"><span data-stu-id="1dc7c-147">The **ComposeInFolder** entry controls whether the form is designed to be placed in the current folder or in the user's Inbox when the user saves the message while composing it: 1 indicates that the form should go in the current folder and 0 indicates that it should go in the Inbox.</span></span> 
  
<span data-ttu-id="1dc7c-148">**ComposeCommand**条目是要放置在客户端应用程序的撰写菜单中的字符串。</span><span class="sxs-lookup"><span data-stu-id="1dc7c-148">The **ComposeCommand** entry is the string to be placed in the client application's compose menu.</span></span> <span data-ttu-id="1dc7c-149">如果未指定此名称, 则使用**DisplayName**条目。</span><span class="sxs-lookup"><span data-stu-id="1dc7c-149">If this is not specified, the **DisplayName** entry will be used.</span></span> 
  
```cpp
[Description]
MessageClass = IPM.Help
Clsid = {00020D31-0000-0000-C000-000000000046}
DisplayName = Help Desk Request Form
;optional entries
Category = Help Desk Requests
Subcategory = New Requests
Comment = Use this form to request network assistance
Owner = Help Desk
Number = 1
SmallIcon = C:\WINDOWS|EFORMS\HELPDESK\HDSMALL.ICO
LargeIcon = C:\WINDOWS|EFORMS\HELPDESK\HDLARGE.ICO
Version = 1.00
Locale = enu
Hidden = 0
ComposeInFolder = 0
ComposeCommand = &Help Desk Request
 
```


