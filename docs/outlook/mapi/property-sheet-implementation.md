---
title: 属性表实现
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f3475206-0237-4b5b-8efd-abd5d5e0b6c3
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 406451adac3cd73286feb787bd6b4d2f356aa283
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778571"
---
# <a name="property-sheet-implementation"></a><span data-ttu-id="d4d7e-103">属性表实现</span><span class="sxs-lookup"><span data-stu-id="d4d7e-103">Property Sheet Implementation</span></span>

  
  
<span data-ttu-id="d4d7e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d4d7e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d4d7e-105">属性表是一个用于显示对象的属性对话框。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-105">A property sheet is a dialog box for displaying the properties of an object.</span></span> <span data-ttu-id="d4d7e-106">属性可以为只读，使用户仅可以查看它们或读/写，使用户可以进行更改。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-106">The properties can be read-only, enabling the user only to view them, or read/write, enabling the user to make changes.</span></span> <span data-ttu-id="d4d7e-107">属性表包含一个或多个调用页面的重叠子窗口。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-107">A property sheet contains one or more overlapping child windows called pages.</span></span> <span data-ttu-id="d4d7e-108">每个页面包含用于设置一组相关的属性的控件窗口。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-108">Each page contains control windows for setting a group of related properties.</span></span> <span data-ttu-id="d4d7e-109">用户通过选择将相应的网页提到的前景色的属性表选项卡导航页面之间。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-109">Users navigate from page to page by selecting a tab that brings the corresponding page to the foreground of the property sheet.</span></span>
  
<span data-ttu-id="d4d7e-110">服务提供商必须实现的属性表显示最小集与邮件服务中配置相关的属性。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-110">Service providers must implement a property sheet that displays a minimal set of properties related to configuration in the message service.</span></span> <span data-ttu-id="d4d7e-111">如果您允许要更改这些消息服务属性，您也可以允许用户的客户端应用程序，如控制面板，以进行更改，或以编程方式实现所做的更改。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-111">If you allow these message service properties to be changed, you can either allow users of client applications, such as the Control Panel, to make the changes or implement the changes programmatically.</span></span> <span data-ttu-id="d4d7e-112">实现属性表以显示和编辑其他类型的属性是可选的。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-112">Implementing property sheets to display and edit other types of properties is optional.</span></span> 
  
<span data-ttu-id="d4d7e-113">通常情况下，您需要在下列情况下显示属性表：</span><span class="sxs-lookup"><span data-stu-id="d4d7e-113">Typically, you will need to display a property sheet in the following situations:</span></span>
  
- <span data-ttu-id="d4d7e-114">当客户端调用状态对象的[IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-114">When a client calls your status object's [IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md) method.</span></span> 
    
- <span data-ttu-id="d4d7e-115">当 MAPI 调用提供商对象的登录方法。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-115">When MAPI calls your provider object's logon method.</span></span>
    
- <span data-ttu-id="d4d7e-116">当 MAPI 提供程序的消息服务调用入口点函数。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-116">When MAPI calls the entry point function for your provider's message service.</span></span>
    
<span data-ttu-id="d4d7e-117">传输提供程序还实现属性表以显示与邮件选项相关的属性和通讯簿提供程序实现的属性页来查看和编辑邮件用户和通讯组列表、 高级搜索的详细的信息条件，然后输入新用户的模板。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-117">Transport providers also implement property sheets to display properties related to message options, and address book providers implement property sheets to view and edit detailed information about messaging users and distribution lists, advanced search criteria, and templates for entering new users.</span></span>
  
<span data-ttu-id="d4d7e-118">您可以使用以下三种方法之一创建属性表：</span><span class="sxs-lookup"><span data-stu-id="d4d7e-118">You can use one of the following three techniques to create a property sheet:</span></span>
  
- <span data-ttu-id="d4d7e-119">手动，就像任何对话框。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-119">Manually, as you would any dialog box.</span></span>
    
- <span data-ttu-id="d4d7e-120">使用 Windows SDK 中提供的属性表常见控件。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-120">By using the property sheet common control provided in the Windows SDK.</span></span>
    
- <span data-ttu-id="d4d7e-121">通过使用 MAPI 显示表。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-121">By using a MAPI display table.</span></span>
    
<span data-ttu-id="d4d7e-122">提供程序应选择最后一个选项 （通过使用显示表创建属性表）。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-122">Providers should choose the last option (create a property sheet by using a display table).</span></span> <span data-ttu-id="d4d7e-123">这是最简单的选项，因为它不需要使用 Windows 用户界面。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-123">This is the simplest option because it eliminates the need to work with the Windows user interface.</span></span> 
  
<span data-ttu-id="d4d7e-124">若要实现构建您的消息服务属性显示表中的属性表，请使用以下过程：</span><span class="sxs-lookup"><span data-stu-id="d4d7e-124">To implement a property sheet built from a display table for your message service properties, use the following procedure:</span></span>
  
1. <span data-ttu-id="d4d7e-125">调用[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)在当前配置文件中打开一节。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-125">Call [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md) to open a section in the current profile.</span></span> <span data-ttu-id="d4d7e-126">传递您[MAPIUID](mapiuid.md)或 NULL，以打开您的提供商的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-126">Pass your [MAPIUID](mapiuid.md) or NULL to open your provider's profile section.</span></span> 
    
2. <span data-ttu-id="d4d7e-127">调用[CreateIProp](createiprop.md)可创建的属性数据对象。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-127">Call [CreateIProp](createiprop.md) to create a property data object.</span></span> 
    
3. <span data-ttu-id="d4d7e-128">调用配置文件部分的[IMAPIProp::CopyTo](imapiprop-copyto.md)方法以将所有节的属性复制到的属性数据对象。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-128">Call the profile section's [IMAPIProp::CopyTo](imapiprop-copyto.md) method to copy all of the section's properties to the property data object.</span></span> 
    
4. <span data-ttu-id="d4d7e-129">创建显示表来构建一个或多个[DTPAGE](dtpage.md)结构描述的控件以显示在属性表和调用[BuildDisplayTable](builddisplaytable.md)函数，或通过实现自定义代码。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-129">Create a display table either by building one or more [DTPAGE](dtpage.md) structures that describe the controls to appear on the property sheet and calling the [BuildDisplayTable](builddisplaytable.md) function, or by implementing custom code.</span></span> 
    
5. <span data-ttu-id="d4d7e-130">调用[IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md)显示属性表已复制的属性。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-130">Call [IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md) to display a property sheet that has the copied properties.</span></span> <span data-ttu-id="d4d7e-131">将指针传递给为_lpConfigData_参数和一个指向作为_lpDisplayTable_参数显示表的属性数据对象。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-131">Pass a pointer to the property data object as the  _lpConfigData_ parameter and a pointer to the display table as the  _lpDisplayTable_ parameter.</span></span> <span data-ttu-id="d4d7e-132">如果您想要替代此属性表的默认访问模式，不要中显示表值，该值代表只读属性设置为每个控件的 DT_EDITABLE 标志。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-132">If you want to override the default access mode for this property sheet, do not set the DT_EDITABLE flag for each control in the display table that represents a read-only property.</span></span> 
    
6. <span data-ttu-id="d4d7e-133">未在属性表中进行的所有更改时, 调用的属性数据对象**IMAPIProp::CopyTo**方法复制更改的属性返回到配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-133">When all of the changes have been made in the property sheet, call the property data object's **IMAPIProp::CopyTo** method to copy the changed properties back to the profile section.</span></span> 
    
<span data-ttu-id="d4d7e-134">显示表的概述，请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-134">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> 
  
<span data-ttu-id="d4d7e-135">有关显示表的详细信息，请参阅[显示表实现](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-135">For detailed information about display tables, see [Display Table Implementation](display-table-implementation.md).</span></span> 
  
<span data-ttu-id="d4d7e-136">有关实现控件的信息，请参阅[控件对象实现](control-object-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-136">For information about implementing a control, see [Control Object Implementation](control-object-implementation.md).</span></span>
  
<span data-ttu-id="d4d7e-137">若要检索的控件的用户显示表列表框中选择的索引，等待用户单击**确定**或**应用**。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-137">To retrieve the index of a control that a user selects in a display table list box, wait until the user clicks **OK** or **Apply**.</span></span> <span data-ttu-id="d4d7e-138">此时，选定项目的项标识符返回写入到[IMAPIProp: IUnknown](imapipropiunknown.md)作为**ulPRSetProperty**成员[DTBLLBX](dtbllbx.md)结构中由指定的属性的值的接口。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-138">At this point, the entry identifier of the selected item is written back to the [IMAPIProp : IUnknown](imapipropiunknown.md) interface as the value of the property specified by the **ulPRSetProperty** member in the [DTBLLBX](dtbllbx.md) structure.</span></span> 
  
<span data-ttu-id="d4d7e-139">如果您需要能够添加或删除项目从列表框，请使用显示表和[IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md)方法不起作用。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-139">If you need to be able to add or remove items from your list box, using a display table and the [IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md) method will not work.</span></span> <span data-ttu-id="d4d7e-140">相反，请考虑实现与 Win32 属性表 API comdlg32.dll 文件中包含的属性表。</span><span class="sxs-lookup"><span data-stu-id="d4d7e-140">Instead, consider implementing a property sheet with the Win32 property sheet API contained in the comdlg32.dll file.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d4d7e-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4d7e-141">See also</span></span>



[<span data-ttu-id="d4d7e-142">MAPI 服务提供商</span><span class="sxs-lookup"><span data-stu-id="d4d7e-142">MAPI Service Providers</span></span>](mapi-service-providers.md)

