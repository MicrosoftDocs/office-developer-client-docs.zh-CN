---
title: 属性表实现
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f3475206-0237-4b5b-8efd-abd5d5e0b6c3
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3f1c6497a182231645691f669d8900d33b495503
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430047"
---
# <a name="property-sheet-implementation"></a><span data-ttu-id="a1d02-103">属性表实现</span><span class="sxs-lookup"><span data-stu-id="a1d02-103">Property Sheet Implementation</span></span>

  
  
<span data-ttu-id="a1d02-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a1d02-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a1d02-105">属性表是一个对话框，用于显示对象的属性。</span><span class="sxs-lookup"><span data-stu-id="a1d02-105">A property sheet is a dialog box for displaying the properties of an object.</span></span> <span data-ttu-id="a1d02-106">这些属性可以是只读的，使用户只能查看它们，也可以读/写，从而允许用户进行更改。</span><span class="sxs-lookup"><span data-stu-id="a1d02-106">The properties can be read-only, enabling the user only to view them, or read/write, enabling the user to make changes.</span></span> <span data-ttu-id="a1d02-107">A 属性表 contains one or more overlapping child windows called pages.</span><span class="sxs-lookup"><span data-stu-id="a1d02-107">A property sheet contains one or more overlapping child windows called pages.</span></span> <span data-ttu-id="a1d02-108">每个页面都包含用于设置一组相关属性的控件窗口。</span><span class="sxs-lookup"><span data-stu-id="a1d02-108">Each page contains control windows for setting a group of related properties.</span></span> <span data-ttu-id="a1d02-109">用户通过选择一个选项卡在页面之间导航，该选项卡将相应的页面带到页面属性表。</span><span class="sxs-lookup"><span data-stu-id="a1d02-109">Users navigate from page to page by selecting a tab that brings the corresponding page to the foreground of the property sheet.</span></span>
  
<span data-ttu-id="a1d02-110">服务提供商必须实现一属性表，它显示与邮件服务中的配置相关的最少属性集。</span><span class="sxs-lookup"><span data-stu-id="a1d02-110">Service providers must implement a property sheet that displays a minimal set of properties related to configuration in the message service.</span></span> <span data-ttu-id="a1d02-111">如果允许更改这些邮件服务属性，您可以允许客户端应用程序（如控制面板）的用户进行更改或以编程方式实现更改。</span><span class="sxs-lookup"><span data-stu-id="a1d02-111">If you allow these message service properties to be changed, you can either allow users of client applications, such as the Control Panel, to make the changes or implement the changes programmatically.</span></span> <span data-ttu-id="a1d02-112">实现属性表以显示和编辑其他类型的属性是可选的。</span><span class="sxs-lookup"><span data-stu-id="a1d02-112">Implementing property sheets to display and edit other types of properties is optional.</span></span> 
  
<span data-ttu-id="a1d02-113">通常，在下列情况下，属性表显示一个视图：</span><span class="sxs-lookup"><span data-stu-id="a1d02-113">Typically, you will need to display a property sheet in the following situations:</span></span>
  
- <span data-ttu-id="a1d02-114">当客户端调用状态对象的 [IMAPIStatus：：SettingsDialog](imapistatus-settingsdialog.md) 方法时。</span><span class="sxs-lookup"><span data-stu-id="a1d02-114">When a client calls your status object's [IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md) method.</span></span> 
    
- <span data-ttu-id="a1d02-115">当 MAPI 调用提供程序对象的登录方法时。</span><span class="sxs-lookup"><span data-stu-id="a1d02-115">When MAPI calls your provider object's logon method.</span></span>
    
- <span data-ttu-id="a1d02-116">当 MAPI 调用提供程序的邮件服务的入口点函数时。</span><span class="sxs-lookup"><span data-stu-id="a1d02-116">When MAPI calls the entry point function for your provider's message service.</span></span>
    
<span data-ttu-id="a1d02-117">传输提供程序还实现属性表以显示与邮件选项相关的属性，通讯簿提供程序实现属性表以查看和编辑有关邮件用户和通讯组列表、高级搜索条件以及用于输入新用户的模板的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a1d02-117">Transport providers also implement property sheets to display properties related to message options, and address book providers implement property sheets to view and edit detailed information about messaging users and distribution lists, advanced search criteria, and templates for entering new users.</span></span>
  
<span data-ttu-id="a1d02-118">可以使用以下三种技术之一创建属性表：</span><span class="sxs-lookup"><span data-stu-id="a1d02-118">You can use one of the following three techniques to create a property sheet:</span></span>
  
- <span data-ttu-id="a1d02-119">手动，就像任何对话框一样。</span><span class="sxs-lookup"><span data-stu-id="a1d02-119">Manually, as you would any dialog box.</span></span>
    
- <span data-ttu-id="a1d02-120">通过使用 属性表 SDK 中提供的Windows控件。</span><span class="sxs-lookup"><span data-stu-id="a1d02-120">By using the property sheet common control provided in the Windows SDK.</span></span>
    
- <span data-ttu-id="a1d02-121">通过使用 MAPI 显示表。</span><span class="sxs-lookup"><span data-stu-id="a1d02-121">By using a MAPI display table.</span></span>
    
<span data-ttu-id="a1d02-122">提供程序应选择最后一 (，属性表显示表创建) 。</span><span class="sxs-lookup"><span data-stu-id="a1d02-122">Providers should choose the last option (create a property sheet by using a display table).</span></span> <span data-ttu-id="a1d02-123">这是最简单的选项，因为它无需使用Windows用户界面。</span><span class="sxs-lookup"><span data-stu-id="a1d02-123">This is the simplest option because it eliminates the need to work with the Windows user interface.</span></span> 
  
<span data-ttu-id="a1d02-124">若要实现属性表显示表为邮件服务属性构建的自定义设置，请使用以下过程：</span><span class="sxs-lookup"><span data-stu-id="a1d02-124">To implement a property sheet built from a display table for your message service properties, use the following procedure:</span></span>
  
1. <span data-ttu-id="a1d02-125">调用 [IMAPISupport：：OpenProfileSection](imapisupport-openprofilesection.md) 以打开当前配置文件中的节。</span><span class="sxs-lookup"><span data-stu-id="a1d02-125">Call [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md) to open a section in the current profile.</span></span> <span data-ttu-id="a1d02-126">传递 [MAPIUID](mapiuid.md) 或 NULL 以打开提供程序的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="a1d02-126">Pass your [MAPIUID](mapiuid.md) or NULL to open your provider's profile section.</span></span> 
    
2. <span data-ttu-id="a1d02-127">调用 [CreateIProp](createiprop.md) 以创建属性数据对象。</span><span class="sxs-lookup"><span data-stu-id="a1d02-127">Call [CreateIProp](createiprop.md) to create a property data object.</span></span> 
    
3. <span data-ttu-id="a1d02-128">调用配置文件节的 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 方法，将节的所有属性复制到属性数据对象。</span><span class="sxs-lookup"><span data-stu-id="a1d02-128">Call the profile section's [IMAPIProp::CopyTo](imapiprop-copyto.md) method to copy all of the section's properties to the property data object.</span></span> 
    
4. <span data-ttu-id="a1d02-129">通过生成一个或多个描述要显示在 属性表 上的控件的 [DTPAGE](dtpage.md) 结构并调用 [BuildDisplayTable](builddisplaytable.md) 函数，或者通过实现自定义代码来创建显示表。</span><span class="sxs-lookup"><span data-stu-id="a1d02-129">Create a display table either by building one or more [DTPAGE](dtpage.md) structures that describe the controls to appear on the property sheet and calling the [BuildDisplayTable](builddisplaytable.md) function, or by implementing custom code.</span></span> 
    
5. <span data-ttu-id="a1d02-130">调用 [IMAPISupport：:D oConfigPropsheet](imapisupport-doconfigpropsheet.md) 以显示属性表复制的属性的行。</span><span class="sxs-lookup"><span data-stu-id="a1d02-130">Call [IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md) to display a property sheet that has the copied properties.</span></span> <span data-ttu-id="a1d02-131">将指向属性数据对象的指针作为  _lpConfigData_ 参数传递，将指向显示表的指针作为  _lpDisplayTable_ 参数传递。</span><span class="sxs-lookup"><span data-stu-id="a1d02-131">Pass a pointer to the property data object as the  _lpConfigData_ parameter and a pointer to the display table as the  _lpDisplayTable_ parameter.</span></span> <span data-ttu-id="a1d02-132">如果要覆盖此控件的默认访问属性表，请不要为显示表中代表只读属性的每个控件设置 DT_EDITABLE 标志。</span><span class="sxs-lookup"><span data-stu-id="a1d02-132">If you want to override the default access mode for this property sheet, do not set the DT_EDITABLE flag for each control in the display table that represents a read-only property.</span></span> 
    
6. <span data-ttu-id="a1d02-133">当在配置文件中进行了所有更改属性表，请调用属性数据对象的 **IMAPIProp：：CopyTo** 方法将更改的属性复制回配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="a1d02-133">When all of the changes have been made in the property sheet, call the property data object's **IMAPIProp::CopyTo** method to copy the changed properties back to the profile section.</span></span> 
    
<span data-ttu-id="a1d02-134">有关显示表的概述，请参阅显示 [表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="a1d02-134">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> 
  
<span data-ttu-id="a1d02-135">有关显示表的详细信息，请参阅 [显示表实现](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="a1d02-135">For detailed information about display tables, see [Display Table Implementation](display-table-implementation.md).</span></span> 
  
<span data-ttu-id="a1d02-136">有关实现控件的信息，请参阅 [控件对象实现](control-object-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="a1d02-136">For information about implementing a control, see [Control Object Implementation](control-object-implementation.md).</span></span>
  
<span data-ttu-id="a1d02-137">若要检索用户在显示表列表框中选择的控件的索引，请等到 **用户单击"** 确定"或"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="a1d02-137">To retrieve the index of a control that a user selects in a display table list box, wait until the user clicks **OK** or **Apply**.</span></span> <span data-ttu-id="a1d02-138">此时，所选项目的条目标识符作为 [DTBLLBX](dtbllbx.md)结构中 **ulPRSetProperty** 成员指定的属性值写回 [IMAPIProp ： IUnknown](imapipropiunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="a1d02-138">At this point, the entry identifier of the selected item is written back to the [IMAPIProp : IUnknown](imapipropiunknown.md) interface as the value of the property specified by the **ulPRSetProperty** member in the [DTBLLBX](dtbllbx.md) structure.</span></span> 
  
<span data-ttu-id="a1d02-139">如果需要能够在列表框中添加或删除项目，则使用显示表和 [IMAPISupport：:D oConfigPropsheet](imapisupport-doconfigpropsheet.md) 方法将不起作用。</span><span class="sxs-lookup"><span data-stu-id="a1d02-139">If you need to be able to add or remove items from your list box, using a display table and the [IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md) method will not work.</span></span> <span data-ttu-id="a1d02-140">相反，请考虑使用 属性表 文件中包含的 Win32 属性表 API 实现comdlg32.dll API。</span><span class="sxs-lookup"><span data-stu-id="a1d02-140">Instead, consider implementing a property sheet with the Win32 property sheet API contained in the comdlg32.dll file.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a1d02-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1d02-141">See also</span></span>



[<span data-ttu-id="a1d02-142">MAPI 服务提供程序</span><span class="sxs-lookup"><span data-stu-id="a1d02-142">MAPI Service Providers</span></span>](mapi-service-providers.md)

