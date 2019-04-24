---
title: ActiveXA 控件的自定义属性对话框
TOCTitle: ActiveX control custom properties dialog box
description: 在设计视图中设置 ActiveX 控件的属性时，除了使用 Microsoft Access 属性表中的属性列表以外，还可以使用此自定义属性对话框。
ms:assetid: 124cf679-6efc-567a-84d1-8057dec93bde
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845396(v=office.15)
ms:contentKeyID: 48543338
ms.date: 10/16/2018
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm4040
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: f4574abc86e6eacd38721e601d26c8b8fbf0a0d3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314103"
---
# <a name="activex-control-custom-properties-dialog-box"></a><span data-ttu-id="4d920-103">ActiveXA 控件的自定义属性对话框</span><span class="sxs-lookup"><span data-stu-id="4d920-103">ActiveX control custom properties dialog box</span></span>

<span data-ttu-id="4d920-104">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="4d920-104">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="4d920-p101">在设置 ActiveX 控件的属性时，您可能需要或更喜欢使用该控件的自定义属性对话框。在设计视图中设置 ActiveX 控件的属性时，除了使用 Microsoft Access 属性表中的属性列表以外，还可以使用自定义属性对话框。</span><span class="sxs-lookup"><span data-stu-id="4d920-p101">When setting the properties of an ActiveX control, you may need or prefer to use the control's custom properties dialog box. This custom properties dialog box provides an alternative to the list of properties in the Microsoft Access property sheet for setting ActiveX control properties in Design view.</span></span>

> [!NOTE]
> <span data-ttu-id="4d920-107">[!注释] 以上信息仅适用于 Microsoft Access 数据库环境中的 ActiveX 控件。</span><span class="sxs-lookup"><span data-stu-id="4d920-107">This information only applies to ActiveX controls in a Microsoft Access database environment.</span></span>

## <a name="two-ways-to-set-properties"></a><span data-ttu-id="4d920-108">设置属性的两种方法</span><span class="sxs-lookup"><span data-stu-id="4d920-108">Two ways to set properties</span></span>

<span data-ttu-id="4d920-p102">使用自定义属性对话框的原因在于：并非所有使用 ActiveX 控件的应用程序都提供了 Microsoft Access 中所提供的那种属性表。无论主应用程序提供什么样的界面，自定义属性对话框均会提供一个界面来设置主要的控件属性。</span><span class="sxs-lookup"><span data-stu-id="4d920-p102">The reason for the custom properties dialog box is that not all applications that use ActiveX controls provide a property sheet like the one in Microsoft Access. The custom properties dialog box provides an interface for setting key control properties regardless of the interface supplied by the hosting application.</span></span>

<span data-ttu-id="4d920-111">对于某些 ActiveX 控件属性，可以选择下列两个位置之一设置属性：</span><span class="sxs-lookup"><span data-stu-id="4d920-111">For some ActiveX control properties, you can choose either of these two locations to set the property:</span></span>

- <span data-ttu-id="4d920-112">Microsoft Access 属性表。</span><span class="sxs-lookup"><span data-stu-id="4d920-112">The Microsoft Access property sheet.</span></span>
- <span data-ttu-id="4d920-113">ActiveX 控件的自定义属性对话框。</span><span class="sxs-lookup"><span data-stu-id="4d920-113">The ActiveX control's custom properties dialog box.</span></span>

<span data-ttu-id="4d920-p103">对于某些情况，在“设计”视图中只能使用自定义属性对话框设置属性。通常，当设置属性所需的界面在 Microsoft Access 属性表中无法工作时，就属于这种情况。例如，日历控件的 **GridFont** 属性有多个参数，但在 Microsoft Access 属性表中却不能为每个属性设置多个参数。</span><span class="sxs-lookup"><span data-stu-id="4d920-p103">In some cases, the custom properties dialog box is the only way to set a property in Design view. This is usually the situation when the interface needed to set a property doesn't work inside the Microsoft Access property sheet. For example, the **GridFont** property for the Calendar control has a number of arguments; you can't set more than one argument per property in the Microsoft Access property sheet.</span></span>

## <a name="finding-the-custom-properties-dialog-box"></a><span data-ttu-id="4d920-117">查找自定义属性对话框</span><span class="sxs-lookup"><span data-stu-id="4d920-117">Finding the custom properties dialog box</span></span>

<span data-ttu-id="4d920-118">Not all ActiveX controls provide a custom properties dialog box.</span><span class="sxs-lookup"><span data-stu-id="4d920-118">Not all ActiveX controls provide a custom properties dialog box.</span></span> <span data-ttu-id="4d920-119">To see whether a control provides this custom properties dialog box, look for the **Custom** property in the Microsoft Access property sheet for this control.</span><span class="sxs-lookup"><span data-stu-id="4d920-119">To see whether a control provides this custom properties dialog box, look for the **Custom** property in the Microsoft Access property sheet for this control.</span></span> <span data-ttu-id="4d920-120">如果属性列表包含名称**custom**, 则该控件提供自定义属性对话框。</span><span class="sxs-lookup"><span data-stu-id="4d920-120">If the list of properties contains the name **Custom**, the control provides the custom properties dialog box.</span></span>

## <a name="using-the-custom-properties-dialog-box"></a><span data-ttu-id="4d920-121">使用 "自定义属性" 对话框</span><span class="sxs-lookup"><span data-stu-id="4d920-121">Using the custom properties dialog box</span></span>

<span data-ttu-id="4d920-122">在 Microsoft Access 属性表中选择 "**自定义**" 属性框后, 选择属性框右侧的 "**生成**" 按钮, 以显示控件的自定义属性对话框, 通常显示为选项卡式对话框。</span><span class="sxs-lookup"><span data-stu-id="4d920-122">After you choose the **Custom** property box in the Microsoft Access property sheet, choose the **Build** button to the right of the property box to display the control's custom properties dialog box, often presented as a tabbed dialog box.</span></span> <span data-ttu-id="4d920-123">可以选择一个包含可在其中设置所需属性的界面的选项卡。</span><span class="sxs-lookup"><span data-stu-id="4d920-123">Choose the tab that contains the interface for setting the properties that you want to set.</span></span>

<span data-ttu-id="4d920-124">在某个选项卡上进行更改后, 通常可以通过选择 "**应用**" 按钮 (如果有的话) 来应用这些更改。</span><span class="sxs-lookup"><span data-stu-id="4d920-124">After you make changes on one tab, you can often apply those changes immediately by choosing the **Apply** button (if provided).</span></span> <span data-ttu-id="4d920-125">您可以根据需要选择其他选项卡来设置其他属性。</span><span class="sxs-lookup"><span data-stu-id="4d920-125">You can choose other tabs to set other properties as needed.</span></span> <span data-ttu-id="4d920-126">若要批准在自定义属性对话框中所做的所有更改, 请选择 **"确定"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="4d920-126">To approve all changes made in the custom properties dialog box, choose the **OK** button.</span></span> <span data-ttu-id="4d920-127">若要返回到 Microsoft Access 属性表而不更改任何属性设置, 请选择 "**取消**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="4d920-127">To return to the Microsoft Access property sheet without changing any property settings, choose the **Cancel** button.</span></span>

<span data-ttu-id="4d920-128">您还可以通过在 "**编辑**" 菜单上选择 "ActiveX 控件**对象**" 命令 (例如, "**日历" 控件对象**) 的 "**属性**" 子命令, 或选择相同的子命令, 来查看 "自定义属性" 对话框ActiveX 控件的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="4d920-128">You can also view the custom properties dialog box by choosing the **Properties** subcommand of the ActiveX control **Object** command (for example, **Calendar Control Object**) on the **Edit** menu, or by choosing this same subcommand on the shortcut menu for the ActiveX control.</span></span> <span data-ttu-id="4d920-129">此外，在 Microsoft Access 属性表中某些 ActiveX 控件属性（如日历控件的 **GridFontColor** 属性）框的右侧有一个“生成器”\*\*\*\* 按钮。</span><span class="sxs-lookup"><span data-stu-id="4d920-129">In addition, some properties in the Microsoft Access property sheet for the ActiveX control, like the **GridFontColor** property of the Calendar control, have a **Build** button to the right of the property box.</span></span> <span data-ttu-id="4d920-130">当您选择 "**生成**" 按钮时, 将显示 "自定义属性" 对话框, 并选中相应的选项卡 (例如, "**颜色**")。</span><span class="sxs-lookup"><span data-stu-id="4d920-130">When you choose the **Build** button, the custom properties dialog box is displayed, with the appropriate tab selected (for example, **Colors**).</span></span>

