---
title: 表单配置文件 [说明] 节
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4ce91a65-17db-4ee2-ad59-01fd5b1f1ea7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ddc59d6c503d44a0575679fce694cc34499d8e2a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433092"
---
# <a name="form-configuration-file-description-section"></a><span data-ttu-id="93843-103">表单配置文件 [说明] 节</span><span class="sxs-lookup"><span data-stu-id="93843-103">Form Configuration File [Description] Section</span></span>
 
<span data-ttu-id="93843-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="93843-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="93843-105">**[Description]** 节列出与表单用户界面中的控件关联的表单的所有属性，以及用于定位表单的属性。</span><span class="sxs-lookup"><span data-stu-id="93843-105">The **[Description]** section lists all properties of the form that are associated with controls in the form's user interface, plus attributes that are used in locating the form.</span></span> <span data-ttu-id="93843-106">**MessageClass、Clsid** 和 **DisplayName** 条目（分别标识表单的邮件类名称、其 GUID 和邮件类的 显示名称）是用于在表单库中查找表单的必需条目。 </span><span class="sxs-lookup"><span data-stu-id="93843-106">The **MessageClass**, **Clsid**, and **DisplayName** entries, which identify the name of the form's message class, its GUID, and the message class's display name, respectively, are required entries used to locate the form within the form library.</span></span> <span data-ttu-id="93843-107">其余条目是可选的。</span><span class="sxs-lookup"><span data-stu-id="93843-107">The remaining entries are optional.</span></span> <span data-ttu-id="93843-108">**[Description] 部分的格式** 为：</span><span class="sxs-lookup"><span data-stu-id="93843-108">The format of the **[Description]** section is:</span></span> 
  
<span data-ttu-id="93843-109">**[Description]** 节列出与表单用户界面中的控件关联的表单的所有属性，以及用于定位表单的属性。</span><span class="sxs-lookup"><span data-stu-id="93843-109">The **[Description]** section lists all properties of the form that are associated with controls in the form's user interface, plus attributes that are used in locating the form.</span></span> <span data-ttu-id="93843-110">**MessageClass、Clsid** 和 **DisplayName** 条目（分别标识表单的邮件类名称、其 GUID 和邮件类的 显示名称）是用于在表单库中查找表单的必需条目。 </span><span class="sxs-lookup"><span data-stu-id="93843-110">The **MessageClass**, **Clsid**, and **DisplayName** entries, which identify the name of the form's message class, its GUID, and the message class's display name, respectively, are required entries used to locate the form within the form library.</span></span> <span data-ttu-id="93843-111">其余条目是可选的。</span><span class="sxs-lookup"><span data-stu-id="93843-111">The remaining entries are optional.</span></span> <span data-ttu-id="93843-112">**[Description] 部分的格式** 为：</span><span class="sxs-lookup"><span data-stu-id="93843-112">The format of the **[Description]** section is:</span></span> 
  
 <span data-ttu-id="93843-113">**[说明] MessageClass**  =  _string_</span><span class="sxs-lookup"><span data-stu-id="93843-113">**[Description] MessageClass** =  _string_</span></span>
  
 <span data-ttu-id="93843-114">**Clsid**  =  _guid_</span><span class="sxs-lookup"><span data-stu-id="93843-114">**Clsid** =  _guid_</span></span>
  
 <span data-ttu-id="93843-115">**DisplayName**  =  _displayedstring_</span><span class="sxs-lookup"><span data-stu-id="93843-115">**DisplayName** =  _displayedstring_</span></span>
  
 <span data-ttu-id="93843-116">**SmallIcon**  =  _path_</span><span class="sxs-lookup"><span data-stu-id="93843-116">**SmallIcon** =  _path_</span></span>
  
 <span data-ttu-id="93843-117">**LargeIcon**  =  _path_</span><span class="sxs-lookup"><span data-stu-id="93843-117">**LargeIcon** =  _path_</span></span>
  
<span data-ttu-id="93843-118">可选条目包括：</span><span class="sxs-lookup"><span data-stu-id="93843-118">Optional entries are:</span></span>
  
 <span data-ttu-id="93843-119">**类别**  =  _显示的字符串_</span><span class="sxs-lookup"><span data-stu-id="93843-119">**Category** =  _displayed string_</span></span>
  
 <span data-ttu-id="93843-120">**子类别**  =  _显示的字符串_</span><span class="sxs-lookup"><span data-stu-id="93843-120">**Subcategory** =  _displayed string_</span></span>
  
 <span data-ttu-id="93843-121">**注释**  =  _显示的字符串_</span><span class="sxs-lookup"><span data-stu-id="93843-121">**Comment** =  _displayed string_</span></span>
  
 <span data-ttu-id="93843-122">**所有者**  =  _显示的字符串_</span><span class="sxs-lookup"><span data-stu-id="93843-122">**Owner** =  _displayed string_</span></span>
  
 <span data-ttu-id="93843-123">**Number**  =  _显示的字符串_</span><span class="sxs-lookup"><span data-stu-id="93843-123">**Number** =  _displayed string_</span></span>
  
 <span data-ttu-id="93843-124">**版本**  =  _integer_</span><span class="sxs-lookup"><span data-stu-id="93843-124">**Version** =  _integer_</span></span>
  
 <span data-ttu-id="93843-125">**区域设置**  =  _string_</span><span class="sxs-lookup"><span data-stu-id="93843-125">**Locale** =  _string_</span></span>
  
 <span data-ttu-id="93843-126">**Hidden**  =  _integer_</span><span class="sxs-lookup"><span data-stu-id="93843-126">**Hidden** =  _integer_</span></span>
  
 <span data-ttu-id="93843-127">**DesignerToolName**  =  _string_</span><span class="sxs-lookup"><span data-stu-id="93843-127">**DesignerToolName** =  _string_</span></span>
  
 <span data-ttu-id="93843-128">**DesignerToolGuid**  =  _clsid_</span><span class="sxs-lookup"><span data-stu-id="93843-128">**DesignerToolGuid** =  _clsid_</span></span>
  
 <span data-ttu-id="93843-129">**DesignerRuntimeGuid**  =  _clsid_</span><span class="sxs-lookup"><span data-stu-id="93843-129">**DesignerRuntimeGuid** =  _clsid_</span></span>
  
 <span data-ttu-id="93843-130">**ComposeInFolder**  =  _0|1_</span><span class="sxs-lookup"><span data-stu-id="93843-130">**ComposeInFolder** =  _0|1_</span></span>
  
 <span data-ttu-id="93843-131">**ComposeCommand**  =  _string_</span><span class="sxs-lookup"><span data-stu-id="93843-131">**ComposeCommand** =  _string_</span></span>
  
<span data-ttu-id="93843-132">表单 **安装程序** 使用 Category 和 **Subcategory** 条目在客户端应用程序的用户界面中设置表单的默认分类。</span><span class="sxs-lookup"><span data-stu-id="93843-132">The **Category** and **Subcategory** entries are used by form installers to set up the default categorization of forms within client application's user interface.</span></span> <span data-ttu-id="93843-133">例如，可以设置层次结构，其中"Help Desk"为类别，"Software"和"Hardware"为子类别。</span><span class="sxs-lookup"><span data-stu-id="93843-133">For example a hierarchy could be set up where "Help Desk" is the category and "Software" and "Hardware" were the subcategories.</span></span> <span data-ttu-id="93843-134">然后，查看器应用程序可以使用此分类以更加有序的方式显示邮件。</span><span class="sxs-lookup"><span data-stu-id="93843-134">This categorization can then be used by viewer applications to display messages in a more organized way.</span></span> <span data-ttu-id="93843-135">**Comment、Owner** 和 **Number** 条目都是显示在客户端应用程序的用户界面中的注释字符串。 </span><span class="sxs-lookup"><span data-stu-id="93843-135">The **Comment**, **Owner**, and **Number** entries are all comment strings that appear in client application's user interface.</span></span> <span data-ttu-id="93843-136">这些属性是表单特定的属性，可自行由表单开发人员使用。</span><span class="sxs-lookup"><span data-stu-id="93843-136">These are form specific properties that can be used at the discretion of the form developer.</span></span> <span data-ttu-id="93843-137">例如 **，"注释** "条目可用于指示表单的用途、用于指示负责维护表单的人或组织的 **"** 所有者"条目，以及用于跟踪不同版本的表单的编号。</span><span class="sxs-lookup"><span data-stu-id="93843-137">For example, the **Comment** entry can be used to indicate the purpose of the form, the **Owner** entry used to indicate the person or organization responsible for maintaining the form, and the number used to track different version of the form.</span></span> <span data-ttu-id="93843-138">对于 **"注释** "条目，最多包含十行注释。</span><span class="sxs-lookup"><span data-stu-id="93843-138">For the **Comment** entry, up to ten lines of comments can be included.</span></span> <span data-ttu-id="93843-139">第一行注释使用单词"Comment"作为键，第二行注释使用"Comment1"作为键，以此类代"Comment9"。</span><span class="sxs-lookup"><span data-stu-id="93843-139">The first line of comments uses the word "Comment" as the key, the second line of comments uses "Comment1" as the key, and so on through "Comment9."</span></span> 
  
<span data-ttu-id="93843-140">**LargeIcon** 和 **SmallIcon** 条目用于指定用于在客户端应用程序的用户界面中显示图标的图标资源的路径，这通常适用于包含 **PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) 或 **PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) 属性列的表行。</span><span class="sxs-lookup"><span data-stu-id="93843-140">The **LargeIcon** and **SmallIcon** entries are used to specify the path for the icon resources used to display icons in the client application's user interface, typically this is for table rows that include the **PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) or **PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) property columns.</span></span> <span data-ttu-id="93843-141">图标文件名可指定为相对于安装表单配置文件的目录的路径名。</span><span class="sxs-lookup"><span data-stu-id="93843-141">Icon file names can be specified as pathnames relative to the directory where the form configuration file is installed.</span></span> <span data-ttu-id="93843-142">**"版本**"条目用于指示表单的版本号。</span><span class="sxs-lookup"><span data-stu-id="93843-142">The **Version** entry is used to indicate the version number of the form.</span></span> <span data-ttu-id="93843-143">**Locale** 是目标表单库的三个字母的语言标识符。</span><span class="sxs-lookup"><span data-stu-id="93843-143">**Locale** is the three-letter language identifier of the destination form library.</span></span> <span data-ttu-id="93843-144">可以在  _Win32_ 程序员参考中找到这些标识符的列表。</span><span class="sxs-lookup"><span data-stu-id="93843-144">A list of these identifiers can be found in the  _Win32 Programmer's Reference_.</span></span>
  
<span data-ttu-id="93843-145">" **隐藏** "条目指示是否应该在表单库提供程序的用户界面中显示表单：1 表示文件处于隐藏状态，0 表示表单可见。</span><span class="sxs-lookup"><span data-stu-id="93843-145">The **Hidden** entry indicates whether the form should be displayed in a form library provider's user interface: 1 indicates that the file is hidden and 0 indicates that the form is visible.</span></span> <span data-ttu-id="93843-146">下面显示了一个示例表单配置文件。</span><span class="sxs-lookup"><span data-stu-id="93843-146">An example form configuration file is shown following.</span></span> 
  
<span data-ttu-id="93843-147">**ComposeInFolder** 条目控制当用户在撰写邮件时将窗体设计为置于当前文件夹还是用户收件箱中：1 表示该窗体应位于当前文件夹中，0 指示该窗体应位于收件箱中。</span><span class="sxs-lookup"><span data-stu-id="93843-147">The **ComposeInFolder** entry controls whether the form is designed to be placed in the current folder or in the user's Inbox when the user saves the message while composing it: 1 indicates that the form should go in the current folder and 0 indicates that it should go in the Inbox.</span></span> 
  
<span data-ttu-id="93843-148">**ComposeCommand** 条目是要放在客户端应用程序的撰写菜单中的字符串。</span><span class="sxs-lookup"><span data-stu-id="93843-148">The **ComposeCommand** entry is the string to be placed in the client application's compose menu.</span></span> <span data-ttu-id="93843-149">如果未指定，则 **使用 DisplayName** 条目。</span><span class="sxs-lookup"><span data-stu-id="93843-149">If this is not specified, the **DisplayName** entry will be used.</span></span> 
  
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


