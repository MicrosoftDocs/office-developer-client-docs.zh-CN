---
title: ActiveX 控件的自定义属性对话框
TOCTitle: ActiveX Control's Custom Properties Dialog Box
ms:assetid: 124cf679-6efc-567a-84d1-8057dec93bde
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845396(v=office.15)
ms:contentKeyID: 48543338
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm4040
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 6f5924d04e9ea4febee1434f6ef99f95b02eab6b
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467530"
---
# <a name="activex-controls-custom-properties-dialog-box"></a><span data-ttu-id="39f8b-102">ActiveX 控件的自定义属性对话框</span><span class="sxs-lookup"><span data-stu-id="39f8b-102">ActiveX Control's Custom Properties Dialog Box</span></span>

<span data-ttu-id="39f8b-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="39f8b-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="39f8b-p101">在设置 ActiveX 控件的属性时，您可能需要或更喜欢使用该控件的自定义属性对话框。在设计视图中设置 ActiveX 控件的属性时，除了使用 Microsoft Access 属性表中的属性列表以外，还可以使用自定义属性对话框。</span><span class="sxs-lookup"><span data-stu-id="39f8b-p101">When setting the properties of an ActiveX control, you may need or prefer to use the control's custom properties dialog box. This custom properties dialog box provides an alternative to the list of properties in the Microsoft Access property sheet for setting ActiveX control properties in Design view.</span></span>

> [!NOTE]
> <span data-ttu-id="39f8b-106">[!注释] 以上信息仅适用于 Microsoft Access 数据库环境中的 ActiveX 控件。</span><span class="sxs-lookup"><span data-stu-id="39f8b-106">This information only applies to ActiveX controls in a Microsoft Access database environment.</span></span>



## <a name="two-ways-to-set-properties"></a><span data-ttu-id="39f8b-107">设置属性的两种方法</span><span class="sxs-lookup"><span data-stu-id="39f8b-107">Two Ways to Set Properties</span></span>

<span data-ttu-id="39f8b-p102">使用自定义属性对话框的原因在于：并非所有使用 ActiveX 控件的应用程序都提供了 Microsoft Access 中所提供的那种属性表。无论主应用程序提供什么样的界面，自定义属性对话框均会提供一个界面来设置主要的控件属性。</span><span class="sxs-lookup"><span data-stu-id="39f8b-p102">The reason for the custom properties dialog box is that not all applications that use ActiveX controls provide a property sheet like the one in Microsoft Access. The custom properties dialog box provides an interface for setting key control properties regardless of the interface supplied by the hosting application.</span></span>

<span data-ttu-id="39f8b-110">对于某些 ActiveX 控件属性，可以选择下列两个位置之一来设置属性：</span><span class="sxs-lookup"><span data-stu-id="39f8b-110">For some ActiveX control properties, you can choose either of these two locations to set the property:</span></span>

  - <span data-ttu-id="39f8b-111">Microsoft Access 属性表。</span><span class="sxs-lookup"><span data-stu-id="39f8b-111">The Microsoft Access property sheet.</span></span>

  - <span data-ttu-id="39f8b-112">ActiveX 控件的自定义属性对话框。</span><span class="sxs-lookup"><span data-stu-id="39f8b-112">The ActiveX control's custom properties dialog box.</span></span>

<span data-ttu-id="39f8b-p103">对于某些情况，在"设计"视图中只能使用自定义属性对话框设置属性。通常，当设置属性所需的界面在 Microsoft Access 属性表中无法工作时，就属于这种情况。例如，日历控件的 **GridFont** 属性有多个参数，但在 Microsoft Access 属性表中却不能为每个属性设置多个参数。</span><span class="sxs-lookup"><span data-stu-id="39f8b-p103">In some cases, the custom properties dialog box is the only way to set a property in Design view. This is usually the situation when the interface needed to set a property doesn't work inside the Microsoft Access property sheet. For example, the **GridFont** property for the Calendar control has a number of arguments; you can't set more than one argument per property in the Microsoft Access property sheet.</span></span>

## <a name="finding-the-custom-properties-dialog-box"></a><span data-ttu-id="39f8b-116">查找自定义属性对话框</span><span class="sxs-lookup"><span data-stu-id="39f8b-116">Finding the Custom Properties Dialog Box</span></span>

<span data-ttu-id="39f8b-117">并非所有的 ActiveX 控件提供自定义属性对话框。</span><span class="sxs-lookup"><span data-stu-id="39f8b-117">Not all ActiveX controls provide a custom properties dialog box.</span></span> <span data-ttu-id="39f8b-118">若要查看控件是否提供此自定义属性对话框中，此控件的 Microsoft Access 属性表中的**自定义**属性的外观。</span><span class="sxs-lookup"><span data-stu-id="39f8b-118">To see whether a control provides this custom properties dialog box, look for the **Custom** property in the Microsoft Access property sheet for this control.</span></span> <span data-ttu-id="39f8b-119">如果属性的列表包含**自定义**的名称，控件将提供自定义属性对话框。</span><span class="sxs-lookup"><span data-stu-id="39f8b-119">If the list of properties contains the name **Custom**, then the control provides the custom properties dialog box.</span></span>

## <a name="using-the-custom-properties-dialog-box"></a><span data-ttu-id="39f8b-120">使用自定义属性对话框</span><span class="sxs-lookup"><span data-stu-id="39f8b-120">Using the Custom Properties Dialog Box</span></span>

<span data-ttu-id="39f8b-p105">单击 Microsoft Access 属性表在 **自定义** 属性框，再单击右侧的属性框中以显示控件的自定义属性对话框，通常显示为选项卡式的对话框的 **生成** 按钮。选择包含要设置的属性的界面的选项卡。</span><span class="sxs-lookup"><span data-stu-id="39f8b-p105">After you click the **Custom** property box in the Microsoft Access property sheet, click the **Build** button to the right of the property box to display the control's custom properties dialog box, often presented as a tabbed dialog box. Choose the tab that contains the interface for setting the properties that you want to set.</span></span>

<span data-ttu-id="39f8b-123">一个选项卡上做出更改后，您可以应用这些更改立即通过单击**应用**按钮 （如果提供）。</span><span class="sxs-lookup"><span data-stu-id="39f8b-123">After you make changes on one tab, you can often apply those changes immediately by clicking the **Apply** button (if provided).</span></span> <span data-ttu-id="39f8b-124">您可以单击其他选项卡，根据需要设置其他属性。</span><span class="sxs-lookup"><span data-stu-id="39f8b-124">You can click other tabs to set other properties as needed.</span></span> <span data-ttu-id="39f8b-125">要接受所有更改在自定义属性对话框中，单击**确定**按钮。</span><span class="sxs-lookup"><span data-stu-id="39f8b-125">To approve all changes made in the custom properties dialog box, click the **OK** button.</span></span> <span data-ttu-id="39f8b-126">若要返回的 Microsoft Access 属性表而不更改属性的任何设置，请单击**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="39f8b-126">To return to the Microsoft Access property sheet without changing any property settings, click the **Cancel** button.</span></span>

<span data-ttu-id="39f8b-127">您还可以查看自定义属性对话框中，单击**编辑**菜单上的 ActiveX 控件 （例如， **Calendar 控件对象**） 中的**对象**命令**属性**子命令或通过单击同一子命令ActiveX 控件的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="39f8b-127">You can also view the custom properties dialog box by clicking the **Properties** subcommand of the ActiveX control **Object** command (for example, **Calendar Control Object**) on the **Edit** menu, or by clicking this same subcommand on the shortcut menu for the ActiveX control.</span></span> <span data-ttu-id="39f8b-128">此外，在 Microsoft Access 属性表中的 ActiveX 控件，如**GridFontColor**属性的日历控件中，有些属性具有属性框右侧的**生成**按钮。</span><span class="sxs-lookup"><span data-stu-id="39f8b-128">In addition, some properties in the Microsoft Access property sheet for the ActiveX control, like the **GridFontColor** property of the Calendar control, have a **Build** button to the right of the property box.</span></span> <span data-ttu-id="39f8b-129">单击**生成**按钮，将显示自定义属性对话框中，选择适当的选项卡 （例如，**颜色**）。</span><span class="sxs-lookup"><span data-stu-id="39f8b-129">When you click the **Build** button, the custom properties dialog box is displayed, with the appropriate tab selected (for example, **Colors**).</span></span>
