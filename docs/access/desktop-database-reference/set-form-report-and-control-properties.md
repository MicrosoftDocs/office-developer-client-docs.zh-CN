---
<span data-ttu-id="2c76a-101">标题： 设置窗体、 报表，并控制属性 TOCTitle： 设置窗体、 报表，并控制属性 <<<<<<< 标头 ms:assetid: 03349d86-f107-9e49-89df-62f55f3a0735 ms:mtpsurl: https://msdn.microsoft.com/library/Ff844789(v=office.15) ms:contentKeyID: 48542977 ms.date: 09/18 /2015 === 说明： 每个窗体、 报表、 部分中，和控件具有可以更改来更改外观和行为的 Access 2013 中的特定项目的属性设置。</span><span class="sxs-lookup"><span data-stu-id="2c76a-101">title: Set form, report, and control properties TOCTitle: Set form, report, and control properties <<<<<<< HEAD ms:assetid: 03349d86-f107-9e49-89df-62f55f3a0735 ms:mtpsurl: https://msdn.microsoft.com/library/Ff844789(v=office.15) ms:contentKeyID: 48542977 ms.date: 09/18/2015 ======= description: Each form, report, section, and control has property settings that you can change to alter the look or behavior of that particular item in Access 2013.</span></span>
<span data-ttu-id="2c76a-102">ms:assetid: 03349d86-f107-9e49-89df-62f55f3a0735 ms:mtpsurl: https://msdn.microsoft.com/library/Ff844789(v=office.15) ms:contentKeyID: 48542977 ms.date: 10/16/2018</span><span class="sxs-lookup"><span data-stu-id="2c76a-102">ms:assetid: 03349d86-f107-9e49-89df-62f55f3a0735 ms:mtpsurl: https://msdn.microsoft.com/library/Ff844789(v=office.15) ms:contentKeyID: 48542977 ms.date: 10/16/2018</span></span>
>>>>>>> <span data-ttu-id="2c76a-103">主 mtps_version: office.15.aspx f1_keywords:</span><span class="sxs-lookup"><span data-stu-id="2c76a-103">master mtps_version: v=office.15 f1_keywords:</span></span>
- <span data-ttu-id="2c76a-104">vbaac10.chm12286 f1_categories:</span><span class="sxs-lookup"><span data-stu-id="2c76a-104">vbaac10.chm12286 f1_categories:</span></span>
- <span data-ttu-id="2c76a-105">Office.Version=v15</span><span class="sxs-lookup"><span data-stu-id="2c76a-105">Office.Version=v15</span></span>
---

# <a name="set-form-report-and-control-properties"></a><span data-ttu-id="2c76a-106">设置窗体、 报表和控件属性</span><span class="sxs-lookup"><span data-stu-id="2c76a-106">Set form, report, and control properties</span></span>

<span data-ttu-id="2c76a-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="2c76a-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="2c76a-p102">每个窗体、报表、节和控件都有各自的属性设置，可以利用这些属性来更改特定项的外观和行为。使用属性表、宏或 Visual Basic 可以查看并更改属性。</span><span class="sxs-lookup"><span data-stu-id="2c76a-p102">Each form, report, section, and control has property settings that you can change to alter the look or behavior of that particular item. You view and change properties by using the property sheet, macro, or Visual Basic.</span></span>

## <a name="set-properties"></a><span data-ttu-id="2c76a-110">设置属性</span><span class="sxs-lookup"><span data-stu-id="2c76a-110">Set properties</span></span>

1. <span data-ttu-id="2c76a-p103">在窗体设计视图或报表设计视图中，选择要设置其属性的控件、节、窗体或报表。可以选择：</span><span class="sxs-lookup"><span data-stu-id="2c76a-p103">In form Design view or report Design view, select the control, section, form, or report for which you want to set the property. You can select:</span></span>
    
<span data-ttu-id="2c76a-113"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="2c76a-113"><<<<<<< HEAD</span></span>
   - <span data-ttu-id="2c76a-p104">一个或多个控件。要选择多个控件，请按住 Shift 键并单击相应控件，或者将鼠标指针在要选择的控件上拖动。如果选择多个控件，属性表将仅显示选中的控件所共有的属性。</span><span class="sxs-lookup"><span data-stu-id="2c76a-p104">One or more controls. To select multiple controls, hold down the SHIFT key and click the controls, or drag the mouse pointer over the controls you wish to select. If you select multiple controls, the property sheet will display only those properties that the selected controls have in common.</span></span>
    
   - <span data-ttu-id="2c76a-p105">一个节。单击要选择的节的节选择器。</span><span class="sxs-lookup"><span data-stu-id="2c76a-p105">One section. Click the section selector of the section you wish to select.</span></span>
    
   - <span data-ttu-id="2c76a-p106">整个窗体或报表。单击窗体或报表左上角的窗体选择器或报表选择器。</span><span class="sxs-lookup"><span data-stu-id="2c76a-p106">The entire form or report. Click the form selector or report selector in the upper-left corner of the form or report.</span></span>

2. <span data-ttu-id="2c76a-121">通过右键单击对象或节，然后在快捷菜单上，单击**属性**或通过单击**属性**工具栏上显示的属性表。</span><span class="sxs-lookup"><span data-stu-id="2c76a-121">Display the property sheet by right-clicking the object or section and then clicking **Properties** on the shortcut menu, or by clicking **Properties** on the toolbar.</span></span>

3. <span data-ttu-id="2c76a-122">单击要为其设置值的属性，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="2c76a-122">Click the property for which you want to set the value, and then do one of the following:</span></span>
    
   - <span data-ttu-id="2c76a-123">在属性框中键入适当的设置或表达式。</span><span class="sxs-lookup"><span data-stu-id="2c76a-123">In the property box, type the appropriate setting or expression.</span></span>
    
   - <span data-ttu-id="2c76a-124">如果属性框包含箭头，单击该箭头，然后单击列表中的值。</span><span class="sxs-lookup"><span data-stu-id="2c76a-124">If the property box contains an arrow, click the arrow and then click a value in the list.</span></span>
    
   - <span data-ttu-id="2c76a-125">如果**生成**按钮显示在右侧的属性框中，单击该按钮以显示生成器或显示一个对话框，使您可以选择生成器。</span><span class="sxs-lookup"><span data-stu-id="2c76a-125">If a **Build** button appears to the right of the property box, click it to display a builder or to display a dialog box giving you a choice of builders.</span></span> <span data-ttu-id="2c76a-126">例如，您可以使用代码生成器、 宏生成器或查询生成器设置某些属性。</span><span class="sxs-lookup"><span data-stu-id="2c76a-126">For example, you can use the Code Builder, Macro Builder, or Query Builder to set some properties.</span></span>

## <a name="tips"></a><span data-ttu-id="2c76a-127">提示</span><span class="sxs-lookup"><span data-stu-id="2c76a-127">Tips</span></span>

- <span data-ttu-id="2c76a-128">Microsoft Access 提供了键入和查看表达式或其他长属性设置的**缩放**框。</span><span class="sxs-lookup"><span data-stu-id="2c76a-128">Microsoft Access provides a **Zoom** box for typing and viewing expressions or other long property settings.</span></span> <span data-ttu-id="2c76a-129">若要显示**缩放**框中，单击属性表中的属性框。</span><span class="sxs-lookup"><span data-stu-id="2c76a-129">To display the **Zoom** box, click a property box in the property sheet.</span></span> <span data-ttu-id="2c76a-130">然后按 SHIFT + F2 或右键单击，然后单击快捷菜单上的**缩放 （英文）** 。</span><span class="sxs-lookup"><span data-stu-id="2c76a-130">Then press SHIFT+F2, or right-click and then click **Zoom** on the shortcut menu.</span></span>
=======
   - <span data-ttu-id="2c76a-131">一个或多个控件。</span><span class="sxs-lookup"><span data-stu-id="2c76a-131">One or more controls.</span></span> <span data-ttu-id="2c76a-132">要选择多个控件，请按住 SHIFT 键选择控件，或者您想要选择的控件中拖动鼠标指针。</span><span class="sxs-lookup"><span data-stu-id="2c76a-132">To select multiple controls, hold down the SHIFT key and choose the controls, or drag the mouse pointer over the controls you wish to select.</span></span> <span data-ttu-id="2c76a-133">如果选择多个控件，属性表将仅显示选中的控件所共有的属性。</span><span class="sxs-lookup"><span data-stu-id="2c76a-133">If you select multiple controls, the property sheet will display only those properties that the selected controls have in common.</span></span>
    
   - <span data-ttu-id="2c76a-134">一个节。</span><span class="sxs-lookup"><span data-stu-id="2c76a-134">One section.</span></span> <span data-ttu-id="2c76a-135">选择选择所需要的节的节选择器。</span><span class="sxs-lookup"><span data-stu-id="2c76a-135">Choose the section selector of the section you wish to select.</span></span>
    
   - <span data-ttu-id="2c76a-136">整个窗体或报表。</span><span class="sxs-lookup"><span data-stu-id="2c76a-136">The entire form or report.</span></span> <span data-ttu-id="2c76a-137">在窗体或报表的左上角中选择窗体选择器或报表选择器。</span><span class="sxs-lookup"><span data-stu-id="2c76a-137">Choose the form selector or report selector in the upper-left corner of the form or report.</span></span>

2. <span data-ttu-id="2c76a-138">通过右键单击对象或节，然后在快捷菜单中，选择**属性**或通过选择**属性**在工具栏上显示的属性表。</span><span class="sxs-lookup"><span data-stu-id="2c76a-138">Display the property sheet by right-clicking the object or section and then choosing **Properties** on the shortcut menu, or by choosing **Properties** on the toolbar.</span></span>

3. <span data-ttu-id="2c76a-139">选择您要为其设置的值，的属性，然后执行下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="2c76a-139">Choose the property for which you want to set the value, and then do one of the following:</span></span>
    
   - <span data-ttu-id="2c76a-140">在属性框中键入适当的设置或表达式。</span><span class="sxs-lookup"><span data-stu-id="2c76a-140">In the property box, type the appropriate setting or expression.</span></span>
    
   - <span data-ttu-id="2c76a-141">如果属性框包含箭头，选择箭头，然后选择列表中的值。</span><span class="sxs-lookup"><span data-stu-id="2c76a-141">If the property box contains an arrow, choose the arrow and then choose a value in the list.</span></span>
    
   - <span data-ttu-id="2c76a-142">如果**生成**按钮显示在右侧的属性框中，选择它来显示生成器或显示一个对话框，使您可以选择生成器。</span><span class="sxs-lookup"><span data-stu-id="2c76a-142">If a **Build** button appears to the right of the property box, choose it to display a builder or to display a dialog box giving you a choice of builders.</span></span> <span data-ttu-id="2c76a-143">例如，您可以使用代码生成器、 宏生成器或查询生成器设置某些属性。</span><span class="sxs-lookup"><span data-stu-id="2c76a-143">For example, you can use the Code Builder, Macro Builder, or Query Builder to set some properties.</span></span>

## <a name="tips"></a><span data-ttu-id="2c76a-144">提示</span><span class="sxs-lookup"><span data-stu-id="2c76a-144">Tips</span></span>

- <span data-ttu-id="2c76a-145">Microsoft Access 提供了键入和查看表达式或其他长属性设置的**缩放**框。</span><span class="sxs-lookup"><span data-stu-id="2c76a-145">Microsoft Access provides a **Zoom** box for typing and viewing expressions or other long property settings.</span></span> <span data-ttu-id="2c76a-146">若要显示**缩放**框中，选择的属性表中的属性框。</span><span class="sxs-lookup"><span data-stu-id="2c76a-146">To display the **Zoom** box, choose a property box in the property sheet.</span></span> <span data-ttu-id="2c76a-147">按 SHIFT + F2 或单击鼠标右键，，，然后选择快捷菜单上的**缩放**。</span><span class="sxs-lookup"><span data-stu-id="2c76a-147">Press SHIFT+F2, or right-click, and then choose **Zoom** on the shortcut menu.</span></span>
>>>>>>> <span data-ttu-id="2c76a-148">master</span><span class="sxs-lookup"><span data-stu-id="2c76a-148">master</span></span>

- <span data-ttu-id="2c76a-149">对于某些控件，可以通过在控件本身中键入属性设置来设置 **ControlSource** 属性。</span><span class="sxs-lookup"><span data-stu-id="2c76a-149">You can set the **ControlSource** property for some controls by typing the property setting in the control itself.</span></span>

- <span data-ttu-id="2c76a-150">可以为一类控件更改默认属性设置，以便使未来创建的该类控件具有新的默认设置。</span><span class="sxs-lookup"><span data-stu-id="2c76a-150">You can change the default property settings for a type of control so that future controls you create will have the new default settings.</span></span>

<span data-ttu-id="2c76a-151"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="2c76a-151"><<<<<<< HEAD</span></span>
- <span data-ttu-id="2c76a-152">绑定控件的属性设置可能与控件所绑定到的基础表或基础查询中字段的相应设置不匹配。</span><span class="sxs-lookup"><span data-stu-id="2c76a-152">The property settings of a bound control might not match the corresponding settings in the field in the underlying table or query to which the control is bound.</span></span> <span data-ttu-id="2c76a-153">如果设置不同，窗体或报表设置通常会覆盖表或查询中的相应设置。</span><span class="sxs-lookup"><span data-stu-id="2c76a-153">If the settings are different, the form or report settings typically override those in the table or query.</span></span> <span data-ttu-id="2c76a-154">有关如何继承属性的详细信息，请参阅"控件属性与其基础字段的属性的关联方式"。</span><span class="sxs-lookup"><span data-stu-id="2c76a-154">For more information about how properties are inherited, see How control properties relate to properties in their underlying fields.</span></span>
=======
- <span data-ttu-id="2c76a-155">绑定控件的属性设置可能与控件所绑定到的基础表或基础查询中字段的相应设置不匹配。</span><span class="sxs-lookup"><span data-stu-id="2c76a-155">The property settings of a bound control might not match the corresponding settings in the field in the underlying table or query to which the control is bound.</span></span> <span data-ttu-id="2c76a-156">如果设置不同，窗体或报表设置通常会覆盖表或查询中的相应设置。</span><span class="sxs-lookup"><span data-stu-id="2c76a-156">If the settings are different, the form or report settings typically override those in the table or query.</span></span>
>>>>>>> <span data-ttu-id="2c76a-157">master</span><span class="sxs-lookup"><span data-stu-id="2c76a-157">master</span></span>

