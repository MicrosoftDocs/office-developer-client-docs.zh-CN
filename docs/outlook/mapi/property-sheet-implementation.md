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
# <a name="property-sheet-implementation"></a><span data-ttu-id="27a1d-103">属性表实现</span><span class="sxs-lookup"><span data-stu-id="27a1d-103">Property Sheet Implementation</span></span>

  
  
<span data-ttu-id="27a1d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="27a1d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="27a1d-105">属性表是一个对话框, 用于显示对象的属性。</span><span class="sxs-lookup"><span data-stu-id="27a1d-105">A property sheet is a dialog box for displaying the properties of an object.</span></span> <span data-ttu-id="27a1d-106">这些属性可以是只读的, 仅允许用户查看它们或读/写, 使用户能够进行更改。</span><span class="sxs-lookup"><span data-stu-id="27a1d-106">The properties can be read-only, enabling the user only to view them, or read/write, enabling the user to make changes.</span></span> <span data-ttu-id="27a1d-107">属性表包含一个或多个称为 pages 的重叠子窗口。</span><span class="sxs-lookup"><span data-stu-id="27a1d-107">A property sheet contains one or more overlapping child windows called pages.</span></span> <span data-ttu-id="27a1d-108">每个页面都包含用于设置一组相关属性的控制窗口。</span><span class="sxs-lookup"><span data-stu-id="27a1d-108">Each page contains control windows for setting a group of related properties.</span></span> <span data-ttu-id="27a1d-109">用户通过选择将相应页面带到属性表的前景的选项卡在页面之间导航。</span><span class="sxs-lookup"><span data-stu-id="27a1d-109">Users navigate from page to page by selecting a tab that brings the corresponding page to the foreground of the property sheet.</span></span>
  
<span data-ttu-id="27a1d-110">服务提供程序必须实现属性表, 以显示与邮件服务中的配置相关的最少属性集。</span><span class="sxs-lookup"><span data-stu-id="27a1d-110">Service providers must implement a property sheet that displays a minimal set of properties related to configuration in the message service.</span></span> <span data-ttu-id="27a1d-111">如果允许更改这些邮件服务属性, 则可以允许客户端应用程序的用户 (如控制面板) 进行更改或以编程方式实现更改。</span><span class="sxs-lookup"><span data-stu-id="27a1d-111">If you allow these message service properties to be changed, you can either allow users of client applications, such as the Control Panel, to make the changes or implement the changes programmatically.</span></span> <span data-ttu-id="27a1d-112">实现属性表以显示和编辑其他类型的属性是可选的。</span><span class="sxs-lookup"><span data-stu-id="27a1d-112">Implementing property sheets to display and edit other types of properties is optional.</span></span> 
  
<span data-ttu-id="27a1d-113">通常, 在以下情况下, 您需要显示属性表:</span><span class="sxs-lookup"><span data-stu-id="27a1d-113">Typically, you will need to display a property sheet in the following situations:</span></span>
  
- <span data-ttu-id="27a1d-114">当客户端调用状态对象的[IMAPIStatus:: SettingsDialog](imapistatus-settingsdialog.md)方法时。</span><span class="sxs-lookup"><span data-stu-id="27a1d-114">When a client calls your status object's [IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md) method.</span></span> 
    
- <span data-ttu-id="27a1d-115">MAPI 调用提供程序对象的登录方法时。</span><span class="sxs-lookup"><span data-stu-id="27a1d-115">When MAPI calls your provider object's logon method.</span></span>
    
- <span data-ttu-id="27a1d-116">当 MAPI 调用提供程序的消息服务的入口点函数时。</span><span class="sxs-lookup"><span data-stu-id="27a1d-116">When MAPI calls the entry point function for your provider's message service.</span></span>
    
<span data-ttu-id="27a1d-117">传输提供程序还实现属性表以显示与邮件选项相关的属性, 通讯簿提供程序实现属性表以查看和编辑有关邮件用户和通讯组列表、高级搜索的详细信息条件, 以及用于输入新用户的模板。</span><span class="sxs-lookup"><span data-stu-id="27a1d-117">Transport providers also implement property sheets to display properties related to message options, and address book providers implement property sheets to view and edit detailed information about messaging users and distribution lists, advanced search criteria, and templates for entering new users.</span></span>
  
<span data-ttu-id="27a1d-118">您可以使用以下三种技术之一来创建属性表:</span><span class="sxs-lookup"><span data-stu-id="27a1d-118">You can use one of the following three techniques to create a property sheet:</span></span>
  
- <span data-ttu-id="27a1d-119">手动, 就像对待任何对话框一样。</span><span class="sxs-lookup"><span data-stu-id="27a1d-119">Manually, as you would any dialog box.</span></span>
    
- <span data-ttu-id="27a1d-120">通过使用 Windows SDK 中提供的 "属性表" 常见控件。</span><span class="sxs-lookup"><span data-stu-id="27a1d-120">By using the property sheet common control provided in the Windows SDK.</span></span>
    
- <span data-ttu-id="27a1d-121">使用 MAPI 显示表。</span><span class="sxs-lookup"><span data-stu-id="27a1d-121">By using a MAPI display table.</span></span>
    
<span data-ttu-id="27a1d-122">提供程序应选择最后一个选项 (使用显示表创建属性表)。</span><span class="sxs-lookup"><span data-stu-id="27a1d-122">Providers should choose the last option (create a property sheet by using a display table).</span></span> <span data-ttu-id="27a1d-123">这是最简单的选项, 因为它无需使用 Windows 用户界面。</span><span class="sxs-lookup"><span data-stu-id="27a1d-123">This is the simplest option because it eliminates the need to work with the Windows user interface.</span></span> 
  
<span data-ttu-id="27a1d-124">若要实现根据消息服务属性的显示表生成的属性表, 请使用以下过程:</span><span class="sxs-lookup"><span data-stu-id="27a1d-124">To implement a property sheet built from a display table for your message service properties, use the following procedure:</span></span>
  
1. <span data-ttu-id="27a1d-125">调用[IMAPISupport:: OpenProfileSection](imapisupport-openprofilesection.md)以打开当前配置文件中的节。</span><span class="sxs-lookup"><span data-stu-id="27a1d-125">Call [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md) to open a section in the current profile.</span></span> <span data-ttu-id="27a1d-126">传递[MAPIUID](mapiuid.md)或 NULL 以打开提供程序的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="27a1d-126">Pass your [MAPIUID](mapiuid.md) or NULL to open your provider's profile section.</span></span> 
    
2. <span data-ttu-id="27a1d-127">调用[CreateIProp](createiprop.md)以创建属性数据对象。</span><span class="sxs-lookup"><span data-stu-id="27a1d-127">Call [CreateIProp](createiprop.md) to create a property data object.</span></span> 
    
3. <span data-ttu-id="27a1d-128">调用 profile 节的[IMAPIProp:: CopyTo](imapiprop-copyto.md)方法将所有节的属性复制到属性数据对象。</span><span class="sxs-lookup"><span data-stu-id="27a1d-128">Call the profile section's [IMAPIProp::CopyTo](imapiprop-copyto.md) method to copy all of the section's properties to the property data object.</span></span> 
    
4. <span data-ttu-id="27a1d-129">通过生成一个或多个描述要在属性表中显示的控件和调用[BuildDisplayTable](builddisplaytable.md)函数的[DTPAGE](dtpage.md)结构, 或通过实现自定义代码来创建显示表。</span><span class="sxs-lookup"><span data-stu-id="27a1d-129">Create a display table either by building one or more [DTPAGE](dtpage.md) structures that describe the controls to appear on the property sheet and calling the [BuildDisplayTable](builddisplaytable.md) function, or by implementing custom code.</span></span> 
    
5. <span data-ttu-id="27a1d-130">调用[IMAPISupport::D oconfigpropsheet](imapisupport-doconfigpropsheet.md)以显示具有已复制属性的属性表。</span><span class="sxs-lookup"><span data-stu-id="27a1d-130">Call [IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md) to display a property sheet that has the copied properties.</span></span> <span data-ttu-id="27a1d-131">将指向属性数据对象的指针作为_lpConfigData_参数, 并将指向显示表的指针作为_lpDisplayTable_参数进行传递。</span><span class="sxs-lookup"><span data-stu-id="27a1d-131">Pass a pointer to the property data object as the  _lpConfigData_ parameter and a pointer to the display table as the  _lpDisplayTable_ parameter.</span></span> <span data-ttu-id="27a1d-132">如果要替代此属性表的默认访问模式, 请勿为显示表中表示只读属性的每个控件设置 DT_EDITABLE 标志。</span><span class="sxs-lookup"><span data-stu-id="27a1d-132">If you want to override the default access mode for this property sheet, do not set the DT_EDITABLE flag for each control in the display table that represents a read-only property.</span></span> 
    
6. <span data-ttu-id="27a1d-133">在属性表中进行所有更改后, 调用属性数据对象的**IMAPIProp:: CopyTo**方法将更改后的属性复制回 "配置文件" 部分。</span><span class="sxs-lookup"><span data-stu-id="27a1d-133">When all of the changes have been made in the property sheet, call the property data object's **IMAPIProp::CopyTo** method to copy the changed properties back to the profile section.</span></span> 
    
<span data-ttu-id="27a1d-134">有关显示表的概述, 请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="27a1d-134">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> 
  
<span data-ttu-id="27a1d-135">有关显示表的详细信息, 请参阅[显示表实现](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="27a1d-135">For detailed information about display tables, see [Display Table Implementation](display-table-implementation.md).</span></span> 
  
<span data-ttu-id="27a1d-136">有关实现控件的信息, 请参阅[control Object 实现](control-object-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="27a1d-136">For information about implementing a control, see [Control Object Implementation](control-object-implementation.md).</span></span>
  
<span data-ttu-id="27a1d-137">若要检索用户在 "显示表" 列表框中选择的控件的索引, 请等待用户单击 **"确定" 或 "** **应用**"。</span><span class="sxs-lookup"><span data-stu-id="27a1d-137">To retrieve the index of a control that a user selects in a display table list box, wait until the user clicks **OK** or **Apply**.</span></span> <span data-ttu-id="27a1d-138">在这种情况下, 所选项的条目标识符被写回到[IMAPIProp: IUnknown](imapipropiunknown.md)接口, 作为[DTBLLBX](dtbllbx.md)结构中**ulPRSetProperty**成员指定的属性的值。</span><span class="sxs-lookup"><span data-stu-id="27a1d-138">At this point, the entry identifier of the selected item is written back to the [IMAPIProp : IUnknown](imapipropiunknown.md) interface as the value of the property specified by the **ulPRSetProperty** member in the [DTBLLBX](dtbllbx.md) structure.</span></span> 
  
<span data-ttu-id="27a1d-139">如果您需要能够在列表框中添加或删除项目, 则使用显示表和[IMAPISupport::D oconfigpropsheet](imapisupport-doconfigpropsheet.md)方法将不起作用。</span><span class="sxs-lookup"><span data-stu-id="27a1d-139">If you need to be able to add or remove items from your list box, using a display table and the [IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md) method will not work.</span></span> <span data-ttu-id="27a1d-140">相反, 请考虑使用 comdlg32 文件中包含的 Win32 属性表 API 实现属性表。</span><span class="sxs-lookup"><span data-stu-id="27a1d-140">Instead, consider implementing a property sheet with the Win32 property sheet API contained in the comdlg32.dll file.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="27a1d-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27a1d-141">See also</span></span>



[<span data-ttu-id="27a1d-142">MAPI 服务提供程序</span><span class="sxs-lookup"><span data-stu-id="27a1d-142">MAPI Service Providers</span></span>](mapi-service-providers.md)

