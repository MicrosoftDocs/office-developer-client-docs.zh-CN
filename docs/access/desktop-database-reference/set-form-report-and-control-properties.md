---
title: 设置窗体、报表和控件的属性
TOCTitle: Set form, report, and control properties
description: 每个窗体、报表、节和控件都有各自的属性设置，可以利用这些属性来更改 Access 2013 中特定项的外观和行为。
ms:assetid: 03349d86-f107-9e49-89df-62f55f3a0735
ms:mtpsurl: https://msdn.microsoft.com/library/Ff844789(v=office.15)
ms:contentKeyID: 48542977
ms.date: 10/16/2018
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm12286
f1_categories:
- Office.Version=v15
localization_priority: Priority
ms.openlocfilehash: bacbdc100d147be8bf4327a5a775b199c79347bb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308734"
---
# <a name="set-form-report-and-control-properties"></a><span data-ttu-id="3e644-103">设置窗体、报表和控件的属性</span><span class="sxs-lookup"><span data-stu-id="3e644-103">Set form, report, and control properties</span></span>

<span data-ttu-id="3e644-104">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="3e644-104">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="3e644-p101">每个窗体、报表、节和控件都有各自的属性设置，可以利用这些属性来更改特定项的外观和行为。使用属性表、宏或 Visual Basic 可以查看并更改属性。</span><span class="sxs-lookup"><span data-stu-id="3e644-p101">Each form, report, section, and control has property settings that you can change to alter the look or behavior of that particular item. You view and change properties by using the property sheet, macro, or Visual Basic.</span></span>

## <a name="set-properties"></a><span data-ttu-id="3e644-107">设置属性</span><span class="sxs-lookup"><span data-stu-id="3e644-107">Set properties</span></span>

1. <span data-ttu-id="3e644-p102">在窗体设计视图或报表设计视图中，选择要设置其属性的控件、节、窗体或报表。可以选择：</span><span class="sxs-lookup"><span data-stu-id="3e644-p102">In form Design view or report Design view, select the control, section, form, or report for which you want to set the property. You can select:</span></span>
    
   - <span data-ttu-id="3e644-110">一个或多个控件。</span><span class="sxs-lookup"><span data-stu-id="3e644-110">One or more controls.</span></span> <span data-ttu-id="3e644-111">要选择多个控件，请按住 Shift 键并选择相应控件，或者在要选择的控件上拖动鼠标指针。</span><span class="sxs-lookup"><span data-stu-id="3e644-111">To select multiple controls, hold down the SHIFT key and click the controls, or drag the mouse pointer over the controls you wish to select.</span></span> <span data-ttu-id="3e644-112">如果选择多个控件，属性表将仅显示选中的控件所共有的属性。</span><span class="sxs-lookup"><span data-stu-id="3e644-112">If you select multiple controls, the property sheet will display only those properties that the selected controls have in common.</span></span>
    
   - <span data-ttu-id="3e644-113">一个节。</span><span class="sxs-lookup"><span data-stu-id="3e644-113">One section.</span></span> <span data-ttu-id="3e644-114">选择要选择的节的节选择器。</span><span class="sxs-lookup"><span data-stu-id="3e644-114">Click the section selector of the section you wish to select.</span></span>
    
   - <span data-ttu-id="3e644-115">整个窗体或报表。</span><span class="sxs-lookup"><span data-stu-id="3e644-115">The entire form or report.</span></span> <span data-ttu-id="3e644-116">选择窗体或报表左上角的窗体选择器或报表选择器。</span><span class="sxs-lookup"><span data-stu-id="3e644-116">Click the form selector or report selector in the upper-left corner of the form or report.</span></span>

2. <span data-ttu-id="3e644-117">按如下方法显示属性表：右键单击对象或节，然后选择快捷菜单上的“**属性**”，或者选择工具栏上的“**属性**”。</span><span class="sxs-lookup"><span data-stu-id="3e644-117">Display the property sheet by right-clicking the object or section and then clicking **Properties** on the shortcut menu, or by clicking **Properties** on the toolbar.</span></span>

3. <span data-ttu-id="3e644-118">选择要设置值的属性，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="3e644-118">Click the property for which you want to set the value, and then do one of the following:</span></span>
    
   - <span data-ttu-id="3e644-119">在属性框中，键入适当的设置或表达式。</span><span class="sxs-lookup"><span data-stu-id="3e644-119">In the property box, type the appropriate setting or expression.</span></span>
    
   - <span data-ttu-id="3e644-120">如果属性框包含箭头，选择该箭头，然后选择列表中的值。</span><span class="sxs-lookup"><span data-stu-id="3e644-120">If the property box contains an arrow, click the arrow and then click a value in the list.</span></span>
    
   - <span data-ttu-id="3e644-121">如果属性框的右侧出现“**生成**”按钮，请选择该按钮以显示生成器或显示提供生成器选项的对话框。</span><span class="sxs-lookup"><span data-stu-id="3e644-121">If a **Build** button appears to the right of the property box, click it to display a builder or to display a dialog box giving you a choice of builders.</span></span> <span data-ttu-id="3e644-122">例如，可以使用代码生成器、宏生成器或查询生成器来设置某些属性。</span><span class="sxs-lookup"><span data-stu-id="3e644-122">For example, you can use the Code Builder, Macro Builder, or Query Builder to set some properties.</span></span>

## <a name="tips"></a><span data-ttu-id="3e644-123">提示</span><span class="sxs-lookup"><span data-stu-id="3e644-123">Tips</span></span>

- <span data-ttu-id="3e644-124">Microsoft Access 提供了 **“缩放”** 框来键入和查看表达式或其他长属性设置。</span><span class="sxs-lookup"><span data-stu-id="3e644-124">Microsoft Access provides a **Zoom** box for typing and viewing expressions or other long property settings.</span></span> <span data-ttu-id="3e644-125">若要显示 **“缩放”** 框，选择属性表中的属性框。</span><span class="sxs-lookup"><span data-stu-id="3e644-125">To display the **Zoom** box, click a property box in the property sheet.</span></span> <span data-ttu-id="3e644-126">按 SHIFT+F2，或右键单击，然后在快捷菜单上选择 **“缩放”**。</span><span class="sxs-lookup"><span data-stu-id="3e644-126">Then press SHIFT+F2, or right-click and then click **Zoom** on the shortcut menu.</span></span>

- <span data-ttu-id="3e644-127">对于某些控件，可以通过在控件本身中键入属性设置来设置 **ControlSource** 属性。</span><span class="sxs-lookup"><span data-stu-id="3e644-127">You can set the **ControlSource** property for some controls by typing the property setting in the control itself.</span></span>

- <span data-ttu-id="3e644-128">可以为一类控件更改默认属性设置，以便使未来创建的该类控件具有新的默认设置。</span><span class="sxs-lookup"><span data-stu-id="3e644-128">You can change the default property settings for a type of control so that future controls you create will have the new default settings.</span></span>

- <span data-ttu-id="3e644-129">绑定控件的属性设置可能与控件所绑定到的基础表或基础查询中字段的相应设置不匹配。</span><span class="sxs-lookup"><span data-stu-id="3e644-129">The property settings of a bound control might not match the corresponding settings in the field in the underlying table or query to which the control is bound.</span></span> <span data-ttu-id="3e644-130">如果设置不同，窗体或报表设置通常会覆盖表或查询中的相应设置。</span><span class="sxs-lookup"><span data-stu-id="3e644-130">If the settings are different, the form or report settings typically override those in the table or query.</span></span>

