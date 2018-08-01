---
title: 表单配置文件 [说明] 部分
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4ce91a65-17db-4ee2-ad59-01fd5b1f1ea7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d3673c3b10afb55121339e335163ce9b2e5937e3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774955"
---
# <a name="form-configuration-file-description-section"></a><span data-ttu-id="1d36d-103">表单配置文件 [说明] 部分</span><span class="sxs-lookup"><span data-stu-id="1d36d-103">Form Configuration File [Description] Section</span></span>
 
<span data-ttu-id="1d36d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="1d36d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="1d36d-105">**[描述]** 节列出了窗体与窗体的用户界面，以及用于窗体的属性中的控件相关联的所有属性。</span><span class="sxs-lookup"><span data-stu-id="1d36d-105">The **[Description]** section lists all properties of the form that are associated with controls in the form's user interface, plus attributes that are used in locating the form.</span></span> <span data-ttu-id="1d36d-106">**Clsid**， **MessageClass**和**DisplayName**条目，分别标识窗体的邮件类、 其 GUID 和邮件类的显示名称的名称，是用于窗体库中找到的窗体的必填的条目.</span><span class="sxs-lookup"><span data-stu-id="1d36d-106">The **MessageClass**, **Clsid**, and **DisplayName** entries, which identify the name of the form's message class, its GUID, and the message class's display name, respectively, are required entries used to locate the form within the form library.</span></span> <span data-ttu-id="1d36d-107">剩余的条目是可选的。</span><span class="sxs-lookup"><span data-stu-id="1d36d-107">The remaining entries are optional.</span></span> <span data-ttu-id="1d36d-108">**[说明]** 部分的格式为：</span><span class="sxs-lookup"><span data-stu-id="1d36d-108">The format of the **[Description]** section is:</span></span> 
  
<span data-ttu-id="1d36d-109">**[描述]** 节列出了窗体与窗体的用户界面，以及用于窗体的属性中的控件相关联的所有属性。</span><span class="sxs-lookup"><span data-stu-id="1d36d-109">The **[Description]** section lists all properties of the form that are associated with controls in the form's user interface, plus attributes that are used in locating the form.</span></span> <span data-ttu-id="1d36d-110">**Clsid**， **MessageClass**和**DisplayName**条目，分别标识窗体的邮件类、 其 GUID 和邮件类的显示名称的名称，是用于窗体库中找到的窗体的必填的条目.</span><span class="sxs-lookup"><span data-stu-id="1d36d-110">The **MessageClass**, **Clsid**, and **DisplayName** entries, which identify the name of the form's message class, its GUID, and the message class's display name, respectively, are required entries used to locate the form within the form library.</span></span> <span data-ttu-id="1d36d-111">剩余的条目是可选的。</span><span class="sxs-lookup"><span data-stu-id="1d36d-111">The remaining entries are optional.</span></span> <span data-ttu-id="1d36d-112">**[说明]** 部分的格式为：</span><span class="sxs-lookup"><span data-stu-id="1d36d-112">The format of the **[Description]** section is:</span></span> 
  
 <span data-ttu-id="1d36d-113">**[描述]MessageClass** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="1d36d-113">**[Description] MessageClass** =  _string_</span></span>
  
 <span data-ttu-id="1d36d-114">**Clsid** =  _guid_</span><span class="sxs-lookup"><span data-stu-id="1d36d-114">**Clsid** =  _guid_</span></span>
  
 <span data-ttu-id="1d36d-115">**DisplayName** =  _displayedstring_</span><span class="sxs-lookup"><span data-stu-id="1d36d-115">**DisplayName** =  _displayedstring_</span></span>
  
 <span data-ttu-id="1d36d-116">**SmallIcon** =  _路径_</span><span class="sxs-lookup"><span data-stu-id="1d36d-116">**SmallIcon** =  _path_</span></span>
  
 <span data-ttu-id="1d36d-117">**视图** =  _路径_</span><span class="sxs-lookup"><span data-stu-id="1d36d-117">**LargeIcon** =  _path_</span></span>
  
<span data-ttu-id="1d36d-118">是可选的条目：</span><span class="sxs-lookup"><span data-stu-id="1d36d-118">Optional entries are:</span></span>
  
 <span data-ttu-id="1d36d-119">**类别** =  _显示字符串_</span><span class="sxs-lookup"><span data-stu-id="1d36d-119">**Category** =  _displayed string_</span></span>
  
 <span data-ttu-id="1d36d-120">**子类别** =  _显示字符串_</span><span class="sxs-lookup"><span data-stu-id="1d36d-120">**Subcategory** =  _displayed string_</span></span>
  
 <span data-ttu-id="1d36d-121">**注释** =  _显示字符串_</span><span class="sxs-lookup"><span data-stu-id="1d36d-121">**Comment** =  _displayed string_</span></span>
  
 <span data-ttu-id="1d36d-122">**所有者** =  _显示字符串_</span><span class="sxs-lookup"><span data-stu-id="1d36d-122">**Owner** =  _displayed string_</span></span>
  
 <span data-ttu-id="1d36d-123">**号码** =  _显示字符串_</span><span class="sxs-lookup"><span data-stu-id="1d36d-123">**Number** =  _displayed string_</span></span>
  
 <span data-ttu-id="1d36d-124">**版本** =  _整数_</span><span class="sxs-lookup"><span data-stu-id="1d36d-124">**Version** =  _integer_</span></span>
  
 <span data-ttu-id="1d36d-125">**区域设置** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="1d36d-125">**Locale** =  _string_</span></span>
  
 <span data-ttu-id="1d36d-126">**隐藏** =  _整数_</span><span class="sxs-lookup"><span data-stu-id="1d36d-126">**Hidden** =  _integer_</span></span>
  
 <span data-ttu-id="1d36d-127">**DesignerToolName** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="1d36d-127">**DesignerToolName** =  _string_</span></span>
  
 <span data-ttu-id="1d36d-128">**DesignerToolGuid** =  _clsid_</span><span class="sxs-lookup"><span data-stu-id="1d36d-128">**DesignerToolGuid** =  _clsid_</span></span>
  
 <span data-ttu-id="1d36d-129">**DesignerRuntimeGuid** =  _clsid_</span><span class="sxs-lookup"><span data-stu-id="1d36d-129">**DesignerRuntimeGuid** =  _clsid_</span></span>
  
 <span data-ttu-id="1d36d-130">**ComposeInFolder** =  _0 | 1_</span><span class="sxs-lookup"><span data-stu-id="1d36d-130">**ComposeInFolder** =  _0|1_</span></span>
  
 <span data-ttu-id="1d36d-131">**ComposeCommand** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="1d36d-131">**ComposeCommand** =  _string_</span></span>
  
<span data-ttu-id="1d36d-132">窗体的安装程序使用**类别**和**子类别**条目设置客户端应用程序的用户界面中的窗体的默认分类。</span><span class="sxs-lookup"><span data-stu-id="1d36d-132">The **Category** and **Subcategory** entries are used by form installers to set up the default categorization of forms within client application's user interface.</span></span> <span data-ttu-id="1d36d-133">例如层次结构可以设置"Help Desk"其中是类别和"Software"和"Hardware"已显示子类别。</span><span class="sxs-lookup"><span data-stu-id="1d36d-133">For example a hierarchy could be set up where "Help Desk" is the category and "Software" and "Hardware" were the subcategories.</span></span> <span data-ttu-id="1d36d-134">这种分类然后可查看器应用程序的更多组织方式显示消息。</span><span class="sxs-lookup"><span data-stu-id="1d36d-134">This categorization can then be used by viewer applications to display messages in a more organized way.</span></span> <span data-ttu-id="1d36d-135">**注释**、**所有者**和**号码**条目是在客户端应用程序的用户界面中出现的所有注释字符串。</span><span class="sxs-lookup"><span data-stu-id="1d36d-135">The **Comment**, **Owner**, and **Number** entries are all comment strings that appear in client application's user interface.</span></span> <span data-ttu-id="1d36d-136">这些是可以自行表单开发人员使用的窗体特定属性。</span><span class="sxs-lookup"><span data-stu-id="1d36d-136">These are form specific properties that can be used at the discretion of the form developer.</span></span> <span data-ttu-id="1d36d-137">例如，**注释**项可用于指示用途的窗体、 一起用来指示的人或组织负责维护表单**所有者**条目和用于跟踪不同版本的表单数。</span><span class="sxs-lookup"><span data-stu-id="1d36d-137">For example, the **Comment** entry can be used to indicate the purpose of the form, the **Owner** entry used to indicate the person or organization responsible for maintaining the form, and the number used to track different version of the form.</span></span> <span data-ttu-id="1d36d-138">**注释**可以包含项，最多 10 行的注释。</span><span class="sxs-lookup"><span data-stu-id="1d36d-138">For the **Comment** entry, up to ten lines of comments can be included.</span></span> <span data-ttu-id="1d36d-139">注释的第一行使用 word"注释"键，注释将第二行使用"Comment1"键，等通过"Comment9。"</span><span class="sxs-lookup"><span data-stu-id="1d36d-139">The first line of comments uses the word "Comment" as the key, the second line of comments uses "Comment1" as the key, and so on through "Comment9."</span></span> 
  
<span data-ttu-id="1d36d-140">**视图**和**SmallIcon**条目用于指定用于在客户端应用程序的用户界面中显示图标的图标资源的路径，这通常是用于包括**PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) 的表格行或**PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) 属性列。</span><span class="sxs-lookup"><span data-stu-id="1d36d-140">The **LargeIcon** and **SmallIcon** entries are used to specify the path for the icon resources used to display icons in the client application's user interface, typically this is for table rows that include the **PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) or **PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) property columns.</span></span> <span data-ttu-id="1d36d-141">可以为相对于窗体配置文件的安装位置的目录的路径名指定图标文件的名称。</span><span class="sxs-lookup"><span data-stu-id="1d36d-141">Icon file names can be specified as pathnames relative to the directory where the form configuration file is installed.</span></span> <span data-ttu-id="1d36d-142">**版本**条目用于指示表单的版本号。</span><span class="sxs-lookup"><span data-stu-id="1d36d-142">The **Version** entry is used to indicate the version number of the form.</span></span> <span data-ttu-id="1d36d-143">**区域设置**是目标表单库的三个字母语言标识符。</span><span class="sxs-lookup"><span data-stu-id="1d36d-143">**Locale** is the three-letter language identifier of the destination form library.</span></span> <span data-ttu-id="1d36d-144">_Win32 程序员参考_中找不到这些标识符的列表。</span><span class="sxs-lookup"><span data-stu-id="1d36d-144">A list of these identifiers can be found in the  _Win32 Programmer's Reference_.</span></span>
  
<span data-ttu-id="1d36d-145">**隐藏**条目指示是否应在窗体库提供商的用户界面中显示窗体： 1 表示文件被隐藏，0 表示窗体处于可见。</span><span class="sxs-lookup"><span data-stu-id="1d36d-145">The **Hidden** entry indicates whether the form should be displayed in a form library provider's user interface: 1 indicates that the file is hidden and 0 indicates that the form is visible.</span></span> <span data-ttu-id="1d36d-146">以下显示窗体配置文件的示例。</span><span class="sxs-lookup"><span data-stu-id="1d36d-146">An example form configuration file is shown following.</span></span> 
  
<span data-ttu-id="1d36d-147">**ComposeInFolder**项控制是否表单设计能放置在当前文件夹或用户的收件箱中时用户撰写同时保存邮件： 1 表示表单应转到当前文件夹中，0 指示它应转收件箱中。</span><span class="sxs-lookup"><span data-stu-id="1d36d-147">The **ComposeInFolder** entry controls whether the form is designed to be placed in the current folder or in the user's Inbox when the user saves the message while composing it: 1 indicates that the form should go in the current folder and 0 indicates that it should go in the Inbox.</span></span> 
  
<span data-ttu-id="1d36d-148">**ComposeCommand**条目是要放置在客户端应用程序的字符串的撰写菜单。</span><span class="sxs-lookup"><span data-stu-id="1d36d-148">The **ComposeCommand** entry is the string to be placed in the client application's compose menu.</span></span> <span data-ttu-id="1d36d-149">如果未指定此参数，将使用的**DisplayName**条目。</span><span class="sxs-lookup"><span data-stu-id="1d36d-149">If this is not specified, the **DisplayName** entry will be used.</span></span> 
  
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


