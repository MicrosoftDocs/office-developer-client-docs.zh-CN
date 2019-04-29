---
title: 快速归档对话框框接口 (OneNote 2013)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: d83e39f0-b259-4c33-8f3e-e03e94c2403d
description: 本主题介绍可用于以编程方式自定义OneNote 2013中的快速归档对话框的接口。
ms.openlocfilehash: dd6b28ae6cb2acb007bae26ea661facaf1f8d4be
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425335"
---
# <a name="quick-filing-dialog-box-interfaces-onenote"></a><span data-ttu-id="43459-103">快速归档对话框框接口 (OneNote 2013)</span><span class="sxs-lookup"><span data-stu-id="43459-103">Quick Filing dialog box interfaces (OneNote)</span></span>

<span data-ttu-id="43459-104">本主题介绍可用于以编程方式自定义OneNote 2013中的快速归档对话框的接口。</span><span class="sxs-lookup"><span data-stu-id="43459-104">This topic describes the interfaces that you can use to programmatically customize the Quick Filing dialog box in OneNote 2013.</span></span>
  
## <a name="quick-filing-dialog-box"></a><span data-ttu-id="43459-105">"快速归档" 对话框</span><span class="sxs-lookup"><span data-stu-id="43459-105">Quick Filing dialog box</span></span>

<span data-ttu-id="43459-p101">OneNote 2013中的快速归档对话框是一个可自定义的对话框，允许用户选择 OneNote 层次结构内的位置。可选位置包括笔记本、 节组、 节、 页和子页。对话框中使用的 OneNote 应用程序内部和外部应用程序通过OneNote 2013 API。图 1 显示在其默认状态的快速归档对话框。</span><span class="sxs-lookup"><span data-stu-id="43459-p101">The Quick Filing dialog box in OneNote 2013 is a customizable dialog box that allows users to select a location within the OneNote hierarchy structure. Selectable locations include notebooks, section groups, sections, pages, and subpages. The dialog box is used both within the OneNote application and by external applications through the OneNote 2013 API. Figure 1 shows the Quick Filing dialog box in its default state.</span></span>
  
<span data-ttu-id="43459-110">**图 1。没有自定义的快速归档对话框**</span><span class="sxs-lookup"><span data-stu-id="43459-110">**Figure 1. Quick Filing dialog box without customizations**</span></span>

<span data-ttu-id="43459-111">![无自定义的快速归档对话框](media/ON15Con_quick_filing_dialog.jpg "无自定义的快速归档对话框")</span><span class="sxs-lookup"><span data-stu-id="43459-111">![Quick Filing dialog box without customizations](media/ON15Con_quick_filing_dialog.jpg "Quick Filing dialog box without customizations")</span></span>
  
<span data-ttu-id="43459-p102">在对话框中，用户可以导航要查找特定位置，或通过在文本框中键入搜索 OneNote 树状结构中的所有笔记本层次结构。可以自定义的对话框中的方面包括标题、 说明、 最近的结果列表、 复选框文本和状态、 树深度、 按钮和可选位置类型。</span><span class="sxs-lookup"><span data-stu-id="43459-p102">Within the dialog box, users can navigate the All Notebooks hierarchy to look for specific locations or search the OneNote tree structure by typing into the text box. Aspects of the dialog box that can be customized include the title, description, recent results list, check box text and state, tree depth, buttons, and selectable location types.</span></span>

<span data-ttu-id="43459-p103">您可以通过两个OneNote 2013接口访问快速归档对话框功能。 **IQuickFilingDialog**界面允许用户实例化，设置，并运行对话框。关闭对话框后，调用 **IQuickFilingDialogCallback**接口。在 OneNote 过程中，运行对话框中，因此保持运行对话框的线程所需的一种机制，然后关闭时捕获用户的选择和对话框中的状态。</span><span class="sxs-lookup"><span data-stu-id="43459-p103">You can access the Quick Filing dialog box functionality through two OneNote 2013 interfaces. The **IQuickFilingDialog** interface allows users to instantiate, set up, and run the dialog box. The **IQuickFilingDialogCallback** interface is called after the dialog box is closed. The dialog box is run in the OneNote process, so a mechanism is needed to keep the dialog box's thread running and then to capture the user's selection and the state of the dialog box when it is closed.</span></span> 
  
## <a name="iquickfilingdialog-interface"></a><span data-ttu-id="43459-118">IQuickFilingDialog 接口</span><span class="sxs-lookup"><span data-stu-id="43459-118">IQuickFilingDialog interface</span></span>
<span data-ttu-id="43459-119"><a name="odc_IQuickFilingDialog"> </a></span><span class="sxs-lookup"><span data-stu-id="43459-119"></span></span>

<span data-ttu-id="43459-p104">此接口允许用户自定义和运行对话框。用户可以通过使用 **Application.QuickFilingDialog**方法实例化一个对话框，通过 **Application**类。该方法返回对话框的实例。一旦设置对话框中的属性， **IQuickFilingDialog.Run**方法用于运行对话框。此方法在新的线程上运行的对话框。</span><span class="sxs-lookup"><span data-stu-id="43459-p104">This interface allows the user to customize and run the dialog box. The user can instantiate a dialog box through the **Application** class by using the **Application.QuickFilingDialog** method. The method returns an instance of the dialog box. Once the properties of the dialog box are set, the **IQuickFilingDialog.Run** method is used to run the dialog box. This method runs the dialog box on a new thread.</span></span> 
  
<span data-ttu-id="43459-125">**属性**</span><span class="sxs-lookup"><span data-stu-id="43459-125">**Properties**</span></span>

|<span data-ttu-id="43459-126">**Name**</span><span class="sxs-lookup"><span data-stu-id="43459-126">**Name**</span></span>|<span data-ttu-id="43459-127">**Type**</span><span class="sxs-lookup"><span data-stu-id="43459-127">**Type**</span></span>|<span data-ttu-id="43459-128">**说明**</span><span class="sxs-lookup"><span data-stu-id="43459-128">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="43459-129">**Title**</span><span class="sxs-lookup"><span data-stu-id="43459-129">**Title**</span></span> <br/> |<span data-ttu-id="43459-130">字符串</span><span class="sxs-lookup"><span data-stu-id="43459-130">string</span></span>  <br/> |<span data-ttu-id="43459-131">获取或设置对话框窗口的标题栏中显示的标题文本。</span><span class="sxs-lookup"><span data-stu-id="43459-131">Gets or sets the title text that appears in the title bar of the dialog box window.</span></span>  <br/> |
|<span data-ttu-id="43459-132">**Description**</span><span class="sxs-lookup"><span data-stu-id="43459-132">**Description**</span></span> <br/> |<span data-ttu-id="43459-133">字符串</span><span class="sxs-lookup"><span data-stu-id="43459-133">string</span></span>  <br/> |<span data-ttu-id="43459-p105">获取或设置以指示要选择的内容有关用户的文本说明。此值可以是多行文本。</span><span class="sxs-lookup"><span data-stu-id="43459-p105">Gets or sets the text description to instruct the user about what to select. This value can be multiple-line text.</span></span>  <br/> |
|<span data-ttu-id="43459-136">**CheckboxText**</span><span class="sxs-lookup"><span data-stu-id="43459-136">**CheckboxText**</span></span> <br/> |<span data-ttu-id="43459-137">字符串</span><span class="sxs-lookup"><span data-stu-id="43459-137">string</span></span>  <br/> |<span data-ttu-id="43459-p106">获取或设置如下所示的复选框的文本。如果此值设置为非空字符串，在对话框中将显示一个复选框。如果值为空字符串，将显示没有复选框。</span><span class="sxs-lookup"><span data-stu-id="43459-p106">Gets or sets the text that follows the check box. If this value is set to a non-empty string, a check box appears in the dialog box. If the value is an empty string, no check box appears.</span></span>  <br/> |
|<span data-ttu-id="43459-141">**CheckboxState**</span><span class="sxs-lookup"><span data-stu-id="43459-141">**CheckboxState**</span></span> <br/> |<span data-ttu-id="43459-142">bool</span><span class="sxs-lookup"><span data-stu-id="43459-142">bool</span></span>  <br/> |<span data-ttu-id="43459-p107">获取或设置状态的复选框。如果值设置为 **false**，启动的对话框时，将清除复选框。如果值设置为 **true**，复选框处于选中状态，当对话框中启动时，只要 **CheckboxText**是一个非空字符串。 </span><span class="sxs-lookup"><span data-stu-id="43459-p107">Gets or sets the state of the check box. If value is set to **false**, the check box is cleared when the dialog box is started. If the value is set to **true**, the check box is selected when the dialog box is started as long as **CheckboxText** is a non-empty string.  </span></span><br/> |
|<span data-ttu-id="43459-146">**WindowHandle**</span><span class="sxs-lookup"><span data-stu-id="43459-146">**WindowHandle**</span></span> <br/> |<span data-ttu-id="43459-147">ulong</span><span class="sxs-lookup"><span data-stu-id="43459-147">ulong</span></span>  <br/> |<span data-ttu-id="43459-148">获取快速归档对话框窗口的句柄 ID。</span><span class="sxs-lookup"><span data-stu-id="43459-148">Gets the handle ID of the Quick Filing dialog box window.</span></span>  <br/> |
|<span data-ttu-id="43459-149">**TreeDepth**</span><span class="sxs-lookup"><span data-stu-id="43459-149">**TreeDepth**</span></span> <br/> |<span data-ttu-id="43459-150">**HierarchyElement**</span><span class="sxs-lookup"><span data-stu-id="43459-150">**HierarchyElement**</span></span> <br/> |<span data-ttu-id="43459-p108">获取或设置 OneNote 树应显示在所有笔记本节的深度。默认情况下，最多为各节显示的树。此属性不会影响可选择哪种类型的元素。 </span><span class="sxs-lookup"><span data-stu-id="43459-p108">Gets or sets how deep the OneNote tree should be displayed in the All Notebooks section. By default, the tree is displayed up to the sections. This property does not affect what type of elements can be selected.  </span></span><br/> <span data-ttu-id="43459-p109">如果 **TreeDepth**设置为一个元素中的 OneNote 层次结构不是可由任何按钮选择较低，显示的树深度将最低可能可选元素。也就是说，如果树深度设置为显示下页，但的最低的可选元素是部分，部分下显示的树。 </span><span class="sxs-lookup"><span data-stu-id="43459-p109">If **TreeDepth** is set to an element lower in the OneNote hierarchy than can be selected by any of the buttons, the displayed tree depth will be the lowest possible selectable element. That is, if tree depth is set to display down to pages, but the lowest selectable element is a section, the tree is displayed down to sections.  </span></span><br/> |
|<span data-ttu-id="43459-156">**ParentWindowHandle**</span><span class="sxs-lookup"><span data-stu-id="43459-156">**ParentWindowHandle**</span></span> <br/> |<span data-ttu-id="43459-157">ulong</span><span class="sxs-lookup"><span data-stu-id="43459-157">ulong</span></span>  <br/> |<span data-ttu-id="43459-p110">获取或设置对话框中的父窗口的句柄 ID。如果设置此属性，快速归档对话框中将在分配的父窗口模式时打开的对话框。即，用户将无法访问父窗口，直到关闭快速归档对话框。</span><span class="sxs-lookup"><span data-stu-id="43459-p110">Gets or sets the handle ID of the parent window of the dialog box. If this property is set, the Quick Filing dialog box will be modal to the assigned parent window when the dialog box opens. That is, a user will not be able to access the parent window until the Quick Filing dialog box is closed.</span></span>  <br/> |
|<span data-ttu-id="43459-161">**Position**</span><span class="sxs-lookup"><span data-stu-id="43459-161">**Position**</span></span> <br/> |<span data-ttu-id="43459-162">tagPOINT</span><span class="sxs-lookup"><span data-stu-id="43459-162">tagPOINT</span></span>  <br/> |<span data-ttu-id="43459-p111">获取或设置与屏幕窗口的位置。默认情况下，在父窗口或桌面的中间显示对话框。</span><span class="sxs-lookup"><span data-stu-id="43459-p111">Gets or sets the position of the window in relation to the screen. By default, the dialog box appears in the middle of the parent window or the desktop.</span></span>  <br/> |
|<span data-ttu-id="43459-165">**SelectedItem**</span><span class="sxs-lookup"><span data-stu-id="43459-165">**SelectedItem**</span></span> <br/> |<span data-ttu-id="43459-166">string</span><span class="sxs-lookup"><span data-stu-id="43459-166">string</span></span>  <br/> |<span data-ttu-id="43459-p112">获取 OneNote 位置时关闭对话框，用户选择的对象 ID。如果用户单击 **取消**按钮，该对象将设置为 null。 </span><span class="sxs-lookup"><span data-stu-id="43459-p112">Gets the object ID of the OneNote location selected by the user when the dialog box is closed. If the user clicks the **Cancel** button, the object is set to null.  </span></span><br/> |
|<span data-ttu-id="43459-169">**PressedButton**</span><span class="sxs-lookup"><span data-stu-id="43459-169">**PressedButton**</span></span> <br/> |<span data-ttu-id="43459-170">ulong</span><span class="sxs-lookup"><span data-stu-id="43459-170">ulong</span></span>  <br/> |<span data-ttu-id="43459-p113">获取时关闭对话框中单击了哪个按钮。如果单击 **取消**按钮，此属性返回值-1。所有其他按钮分配整数值从 0 增加 1 添加到对话框中的每个按钮。默认值 **确定**按钮的整数值为 0。 </span><span class="sxs-lookup"><span data-stu-id="43459-p113">Gets which button was clicked when the dialog box was closed. If the **Cancel** button was clicked, this property returns a value of -1. All other buttons are assigned integer values from 0, incremented by 1 for each button added to the dialog box. The integer value of the default **OK** button is 0.  </span></span><br/> |
   
### <a name="methods"></a><span data-ttu-id="43459-175">方法</span><span class="sxs-lookup"><span data-stu-id="43459-175">Methods</span></span>

<span data-ttu-id="43459-176">**SetRecentResults**</span><span class="sxs-lookup"><span data-stu-id="43459-176">**SetRecentResults**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="43459-177">**说明**</span><span class="sxs-lookup"><span data-stu-id="43459-177">**Description**</span></span> <br/> |<span data-ttu-id="43459-p114">设置哪些最近的结果列表将显示在快速归档对话框中，并指示是否在列表中包括一些特殊归档位置。用户可以选择[RecentResultType](enumerations-onenote-developer-reference.md#odc_RecentResultType)枚举中的最新的结果列表。用户还可以选择以下选项添加到列表: 当前节、 当前页或未归档笔记。如果 **RecentResultType.rrtNone**处于选中状态，将不显示任何新的结果列表。 </span><span class="sxs-lookup"><span data-stu-id="43459-p114">Sets what recent result list will be displayed in the Quick Filing dialog box, and indicates whether to include some special filing locations in the list. Users can select a recent result list from the [RecentResultType](enumerations-onenote-developer-reference.md#odc_RecentResultType) enumeration. Users can also choose to add the following options to the list: Current Section, Current Page, or Unfiled Notes. If **RecentResultType.rrtNone** is selected, no recent result list is shown.  </span></span><br/> |
|<span data-ttu-id="43459-182">**语法**</span><span class="sxs-lookup"><span data-stu-id="43459-182">**Syntax**</span></span> <br/> | `HRESULT SetRecentResults (`<br/>`[in]RecentResultType recentResults,`<br/>`[in]VARIANT_BOOL fShowCurrentSection,`<br/>`[in]VARIANT_BOOL fShowCurrentPage,`<br/>`[in]VARIANT_BOOL fShowUnfiledNotes);` <br/> |
|<span data-ttu-id="43459-183">**参数**</span><span class="sxs-lookup"><span data-stu-id="43459-183">**Parameters**</span></span> <br/> | <span data-ttu-id="43459-184">_recentResults_&ndash;一个**RecentResultType**类型的对象, 该对象指示应显示的最近结果列表 (如果有)。</span><span class="sxs-lookup"><span data-stu-id="43459-184">_recentResults_ &ndash; An object of type **RecentResultType** that indicates which recent result list, if any, should appear.</span></span> <span data-ttu-id="43459-185">如果 **rrtNone**处于选中状态，没有最新的结果列表将显示在对话框中。</span><span class="sxs-lookup"><span data-stu-id="43459-185">If **rrtNone** is selected, no recent result list appears in the dialog box.</span></span><br/><br/>  <span data-ttu-id="43459-186">_fShowCurrentSection_&ndash;一个布尔值, 指示当前节是否应包含在最近的结果列表中。</span><span class="sxs-lookup"><span data-stu-id="43459-186">_fShowCurrentSection_ &ndash; A Boolean value that indicates whether the current section should be included in the recent result list.</span></span><br/><br/>  <span data-ttu-id="43459-187">_fShowCurrentPage_&ndash;一个布尔值, 指示当前页面是否应包含在最近的结果列表中。</span><span class="sxs-lookup"><span data-stu-id="43459-187">_fShowCurrentPage_ &ndash; A Boolean value that indicates whether the current page should be included in the recent result list.</span></span><br/><br/>  <span data-ttu-id="43459-188">_fShowUnfiledNotes_&ndash;一个布尔值, 该值指示是否应在最近的结果列表中包含未归档笔记部分。</span><span class="sxs-lookup"><span data-stu-id="43459-188">_fShowUnfiledNotes_ &ndash; A Boolean value that indicates whether the Unfiled Notes section should be included in the recent result list.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="43459-p116">[!注释] 如果无法使用任一按钮的对话框中选中的特殊归档位置，则不将其显示在列表中。如果不找到了最近的结果列表中的任何可选项，将显示没有最新的结果列表。</span><span class="sxs-lookup"><span data-stu-id="43459-p116">If a special filing location cannot be selected by using any of the buttons in the dialog box, it is not shown in the list. If no selectable item in the recent results list is found, no recent result list is displayed.</span></span> 
  
<span data-ttu-id="43459-191">下面的示例使用 **SetRecentResults**方法在最近的结果列表中显示当前节、 当前页和未归档的注释部分。</span><span class="sxs-lookup"><span data-stu-id="43459-191">The following example uses the **SetRecentResults** method to display the current section, current page, and the Unfiled Notes section in the recent result list.</span></span> 
  
```cs
        static void Main(string[] args)
        {
            Microsoft.Office.Interop.OneNote.Application app = 
                new Microsoft.Office.Interop.OneNote.Application();
            ... 
            // RECENT RESULTS
            qfDialog.SetRecentResults(RecentResultType.rrtFiling,
                /*Current Section*/ true,
                /*Current Page*/ true,
                /*Unfiled Notes*/ true);
            ...
        }

```

<span data-ttu-id="43459-192">**AddButton**</span><span class="sxs-lookup"><span data-stu-id="43459-192">**AddButton**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="43459-193">**说明**</span><span class="sxs-lookup"><span data-stu-id="43459-193">**Description**</span></span> <br/> |<span data-ttu-id="43459-p117">允许用户添加和自定义对话框中的按钮。用户可以指定的按钮和 OneNote 层次结构的元素可选择通过每个按钮上的文本。</span><span class="sxs-lookup"><span data-stu-id="43459-p117">Allows users to add and customize buttons in the dialog box. Users can specify the text on the buttons and what elements of the OneNote hierarchy can be selected by each button.</span></span>  <br/> |
|<span data-ttu-id="43459-196">**语法**</span><span class="sxs-lookup"><span data-stu-id="43459-196">**Syntax**</span></span> <br/> | `HRESULT AddButton (`<br/>`[in]BSTR bstrText,`<br/>`[in]HierarchyElement allowedElements,`<br/>`[in]HierarchyElement allowedReadOnlyElements,`<br/>`[in]VARIANT_BOOL fDefault);` <br/> |
|<span data-ttu-id="43459-197">**参数**</span><span class="sxs-lookup"><span data-stu-id="43459-197">**Parameters**</span></span> <br/> | <span data-ttu-id="43459-198">_bstrText_&ndash;一个字符串, 指定要在按钮上显示的文本。</span><span class="sxs-lookup"><span data-stu-id="43459-198">_bstrText_ &ndash; A string that specifies the text to appear on the button.</span></span> <span data-ttu-id="43459-199">要自定义的默认 **确定**按钮，将作为 **bstrText**传递中 null 值。</span><span class="sxs-lookup"><span data-stu-id="43459-199">To customize the default **OK** button, pass in a null value as **bstrText**.</span></span>  <br/><br/><span data-ttu-id="43459-200">_allowedElements_&ndash;一个**HierarchyElement** , 指示允许用户通过使用按钮选择的非只读 OneNote 层次结构元素。</span><span class="sxs-lookup"><span data-stu-id="43459-200">_allowedElements_ &ndash; A **HierarchyElement** that indicates what non-read-only OneNote hierarchy elements a user is allowed to select by using the button.</span></span> <span data-ttu-id="43459-201">选择多个项目，用户应通过 **OR**运算符中的所有 **HierarchyElement**类型允许作为 **HierarchyElement**uint 等效值。</span><span class="sxs-lookup"><span data-stu-id="43459-201">For selecting multiple items, the user should pass in the **OR** operator for all the uint equivalent values of the **HierarchyElement** types allowed as a **HierarchyElement**.</span></span><br/><br/>  <span data-ttu-id="43459-202">_allowedReadOnlyElements_&ndash;一个**HierarchyElement** , 指示允许用户使用按钮选择的 OneNote 只读层次结构元素。</span><span class="sxs-lookup"><span data-stu-id="43459-202">_allowedReadOnlyElements_ &ndash; A **HierarchyElement** that indicates what OneNote read-only hierarchy elements a user is allowed to select by using the button.</span></span> <span data-ttu-id="43459-203">选择多个项目，用户应通过在 **OR**运算符 **HierarchyElement**类型允许作为 **HierarchyElement**的所有 **uint** 等效值。</span><span class="sxs-lookup"><span data-stu-id="43459-203">For selecting multiple items, the user should pass in the **OR** operator for all the **uint** equivalents values of the **HierarchyElement** types allowed as a **HierarchyElement**.</span></span><br/><br/>  <span data-ttu-id="43459-204">_fDefault_&ndash;一个布尔值, 该值指定此按钮是否应为默认按钮。</span><span class="sxs-lookup"><span data-stu-id="43459-204">_fDefault_ &ndash; A Boolean value that specifies whether this button should be the default button.</span></span> <span data-ttu-id="43459-205">如果多个按钮设置为默认值，最后一个指定的按钮将成为默认按钮。</span><span class="sxs-lookup"><span data-stu-id="43459-205">If multiple buttons are set as default, the last specified button becomes the default button.</span></span>  <br/> |
   
<span data-ttu-id="43459-p122">下面的示例将三个按钮添加到快速归档对话框。第一个， **所有**，可以选择通过 OneNote 层次结构树中的所有元素。仅当选择其相应的元素，笔记本和页面，可以选择其他， **笔记本**和 **页面**。</span><span class="sxs-lookup"><span data-stu-id="43459-p122">The following example adds three buttons to the Quick Filing dialog box. The first one, **All**, can be selected by all elements in the OneNote hierarchy tree. The others, **Notebooks** and **Pages**, can be selected only if their corresponding elements, Notebooks and Pages, are selected.</span></span>
  
```cs
        static void Main(string[] args)
        {
            Microsoft.Office.Interop.OneNote.Application app = 
                new Microsoft.Office.Interop.OneNote.Application();
            ... 
            
            // BUTTONS
            HierarchyElement heAll = (HierarchyElement) 
                ((uint)HierarchyElement.heNotebooks | 
                (uint)HierarchyElement.heSectionGroups | 
                (uint)HierarchyElement.heSections |  
                (uint)HierarchyElement.hePages);
            
            qfDialog.AddButton("All", heAll, heAll, true);
            qfDialog.AddButton("Notebooks", HierarchyElement.heNotebooks, 
                HierarchyElement.heNotebooks, false);
            qfDialog.AddButton("Pages", HierarchyElement.hePages, 
                HierarchyElement.hePages, false);
            ... 
        }

```

<span data-ttu-id="43459-209">**运行**</span><span class="sxs-lookup"><span data-stu-id="43459-209">**Run**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="43459-210">**说明**</span><span class="sxs-lookup"><span data-stu-id="43459-210">**Description**</span></span> <br/> |<span data-ttu-id="43459-p123">在新线程中的快速归档对话框中显示。计 **IQuickFilingDialogCallback**接口，关闭该对话框后，将调用其 **OnDialogClosed**方法的引用。 </span><span class="sxs-lookup"><span data-stu-id="43459-p123">Displays the Quick Filing dialog box from a new thread. It takes a reference to the **IQuickFilingDialogCallback** interface, whose **OnDialogClosed** method will be called once the dialog box closes.  </span></span><br/> |
|<span data-ttu-id="43459-213">**语法**</span><span class="sxs-lookup"><span data-stu-id="43459-213">**Syntax**</span></span> <br/> | `HRESULT Run (`<br/>`[in]IQuickFilingDialogCallback piCallback);` <br/> |
|<span data-ttu-id="43459-214">**参数**</span><span class="sxs-lookup"><span data-stu-id="43459-214">**Parameters**</span></span> <br/> | <span data-ttu-id="43459-215">_piCallback_&ndash;对**IQuickFilingDialogCallback**接口的引用, 该引用将在对话框关闭后实例化。</span><span class="sxs-lookup"><span data-stu-id="43459-215">_piCallback_ &ndash; A reference to the **IQuickFilingDialogCallback** interface that will be instantiated once the dialog box closes.</span></span>  <br/> |
   
<span data-ttu-id="43459-216">下面的示例使用 **Run**方法显示新线程中的快速归档对话框。</span><span class="sxs-lookup"><span data-stu-id="43459-216">The following example uses the **Run** method to display the Quick Filing dialog box from a new thread.</span></span> 
  
```cs
    class OpenQuickFilingDialog
    {
            ... 
        static void Main(string[] args)
        {
            Microsoft.Office.Interop.OneNote.Application app = 
                new Microsoft.Office.Interop.OneNote.Application();
            ... 
            // Display Quick Filing UI
            qfDialog.Run(new Callback());
            ... 
        }
    }

```

<span data-ttu-id="43459-217">**TreeCollapsedState**</span><span class="sxs-lookup"><span data-stu-id="43459-217">**TreeCollapsedState**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="43459-218">**说明**</span><span class="sxs-lookup"><span data-stu-id="43459-218">**Description**</span></span> <br/> |<span data-ttu-id="43459-219">指示是否应展开或折叠的层次结构树。</span><span class="sxs-lookup"><span data-stu-id="43459-219">Indicates whether the hierarchy tree should be expanded or collapsed.</span></span>  <br/> |
|<span data-ttu-id="43459-220">**语法**</span><span class="sxs-lookup"><span data-stu-id="43459-220">**Syntax**</span></span> <br/> | `HRESULT TreeCollapsedState(`<br/>`[in] TreeCollapsedStateType tcs);` <br/> |
|<span data-ttu-id="43459-221">**参数**</span><span class="sxs-lookup"><span data-stu-id="43459-221">**Parameters**</span></span> <br/> | <span data-ttu-id="43459-222">_tcs_ -指定是否展开或折叠树。</span><span class="sxs-lookup"><span data-stu-id="43459-222">_tcs_ - Specifies whether the tree is expanded or collapsed.</span></span>  <br/> |
   
<span data-ttu-id="43459-223">**NotebookFilterOut**</span><span class="sxs-lookup"><span data-stu-id="43459-223">**NotebookFilterOut**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="43459-224">**说明**</span><span class="sxs-lookup"><span data-stu-id="43459-224">**Description**</span></span> <br/> |<span data-ttu-id="43459-225">筛选器的显示类型的笔记本的列表。</span><span class="sxs-lookup"><span data-stu-id="43459-225">Filters the list of notebooks shown by type.</span></span>  <br/> |
|<span data-ttu-id="43459-226">**语法**</span><span class="sxs-lookup"><span data-stu-id="43459-226">**Syntax**</span></span> <br/> | `HRESULT NotebookFilterOut(`<br/>`[in] NotebookFilterOutType nfo);` <br/> |
|<span data-ttu-id="43459-227">**参数**</span><span class="sxs-lookup"><span data-stu-id="43459-227">**Parameters**</span></span> <br/> | <span data-ttu-id="43459-228">_nfo_ -指定一组的是要从列表中筛选的笔记本</span><span class="sxs-lookup"><span data-stu-id="43459-228">_nfo_ - Specifies the set of notebooks that are to be filtered out of the list</span></span>  <br/> |
   
<span data-ttu-id="43459-229">**ShowCreateNewNotebook**</span><span class="sxs-lookup"><span data-stu-id="43459-229">**ShowCreateNewNotebook**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="43459-230">**说明**</span><span class="sxs-lookup"><span data-stu-id="43459-230">**Description**</span></span> <br/> |<span data-ttu-id="43459-231">在对话框中显示新建笔记本选项。</span><span class="sxs-lookup"><span data-stu-id="43459-231">Displays the create new notebook option in the dialog.</span></span>  <br/> |
|<span data-ttu-id="43459-232">**语法**</span><span class="sxs-lookup"><span data-stu-id="43459-232">**Syntax**</span></span> <br/> | `HRESULT ShowCreateNewNotebook ();` <br/> |
|<span data-ttu-id="43459-233">**参数**</span><span class="sxs-lookup"><span data-stu-id="43459-233">**Parameters**</span></span> <br/> |<span data-ttu-id="43459-234">无</span><span class="sxs-lookup"><span data-stu-id="43459-234">None</span></span>  <br/> |
   
<span data-ttu-id="43459-235">**AddInitialEditor**</span><span class="sxs-lookup"><span data-stu-id="43459-235">**AddInitialEditor**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="43459-236">**说明**</span><span class="sxs-lookup"><span data-stu-id="43459-236">**Description**</span></span> <br/> |<span data-ttu-id="43459-237">到笔记本中的快速归档对话框中，作为初始编辑器中添加用户。</span><span class="sxs-lookup"><span data-stu-id="43459-237">Adds a user as an initial editor to a notebook in the Quick Filing dialog box.</span></span>  <br/> |
|<span data-ttu-id="43459-238">**语法**</span><span class="sxs-lookup"><span data-stu-id="43459-238">**Syntax**</span></span> <br/> | `HRESULT AddInitialEditor (BSTR initialEditor);` <br/> |
|<span data-ttu-id="43459-239">**参数**</span><span class="sxs-lookup"><span data-stu-id="43459-239">**Parameters**</span></span> <br/> | <span data-ttu-id="43459-p124">_initialEditor_ -要将作为编辑器添加到笔记本的用户的电子邮件地址。通过快速归档对话框中创建笔记本后，会自动共享与所有初始编辑器中。  </span><span class="sxs-lookup"><span data-stu-id="43459-p124">_initialEditor_ - The email address of the user you wish to add as an editor to the notebook. When the notebook is created via the Quick Filing dialog box, it is automatically shared with all Initial Editors.  </span></span><br/> |
   
<span data-ttu-id="43459-242">**ClearInitialEditors**</span><span class="sxs-lookup"><span data-stu-id="43459-242">**ClearInitialEditors**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="43459-243">**说明**</span><span class="sxs-lookup"><span data-stu-id="43459-243">**Description**</span></span> <br/> |<span data-ttu-id="43459-244">从快速归档对话框中删除所有的初始编辑器。</span><span class="sxs-lookup"><span data-stu-id="43459-244">Removes all initial editors from the Quick Filing dialog box.</span></span>  <br/> |
|<span data-ttu-id="43459-245">**语法**</span><span class="sxs-lookup"><span data-stu-id="43459-245">**Syntax**</span></span> <br/> | `HRESULT ClearInitialEditors ();` <br/> |
|<span data-ttu-id="43459-246">**参数**</span><span class="sxs-lookup"><span data-stu-id="43459-246">**Parameters**</span></span> <br/> |<span data-ttu-id="43459-247">无</span><span class="sxs-lookup"><span data-stu-id="43459-247">None</span></span>  <br/> |
   
<span data-ttu-id="43459-248">**ShowSharingHyperlink**</span><span class="sxs-lookup"><span data-stu-id="43459-248">**ShowSharingHyperlink**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="43459-249">**说明**</span><span class="sxs-lookup"><span data-stu-id="43459-249">**Description**</span></span> <br/> |<span data-ttu-id="43459-250">在快速归档对话框中显示共享帮助主题超链接。</span><span class="sxs-lookup"><span data-stu-id="43459-250">Displays the Sharing Help Topic Hyperlink in the Quick Filing dialog box.</span></span>  <br/> |
|<span data-ttu-id="43459-251">**语法**</span><span class="sxs-lookup"><span data-stu-id="43459-251">**Syntax**</span></span> <br/> | `HRESULT ShowSharingHyperlink();` <br/> |
|<span data-ttu-id="43459-252">**参数**</span><span class="sxs-lookup"><span data-stu-id="43459-252">**Parameters**</span></span> <br/> |<span data-ttu-id="43459-253">无</span><span class="sxs-lookup"><span data-stu-id="43459-253">None</span></span>  <br/> |
   
## <a name="iquickfilingdialogcallback-interface"></a><span data-ttu-id="43459-254">IQuickFilingDialogCallback 接口</span><span class="sxs-lookup"><span data-stu-id="43459-254">IQuickFilingDialogCallback interface</span></span>
<span data-ttu-id="43459-255"><a name="odc_IQuickFilingDialog"> </a></span><span class="sxs-lookup"><span data-stu-id="43459-255"></span></span>

<span data-ttu-id="43459-p125">此接口允许用户访问对话框属性后将关闭对话框。一旦对话框关闭， OneNote 2013此接口中调用 **IQuickFilingDialogCallback.OnDialogClose**方法。</span><span class="sxs-lookup"><span data-stu-id="43459-p125">This interface allows the user to access the dialog box properties after the dialog box closes. Once the dialog box closes, OneNote 2013 calls the **IQuickFilingDialogCallback.OnDialogClose** method in this interface.</span></span> 
  
<span data-ttu-id="43459-258">继承此接口的类必须定义。</span><span class="sxs-lookup"><span data-stu-id="43459-258">A class that inherits this interface has to be defined.</span></span>
  
### <a name="methods"></a><span data-ttu-id="43459-259">方法</span><span class="sxs-lookup"><span data-stu-id="43459-259">Methods</span></span>

<span data-ttu-id="43459-260">以下部分介绍与前面详细介绍的接口关联的方法。</span><span class="sxs-lookup"><span data-stu-id="43459-260">The following section describes the methods associated with the interfaces detailed previously.</span></span>
  
<span data-ttu-id="43459-261">**OnDialogClosed**</span><span class="sxs-lookup"><span data-stu-id="43459-261">**OnDialogClosed**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="43459-262">**描述**</span><span class="sxs-lookup"><span data-stu-id="43459-262">**Description**</span></span> <br/> |<span data-ttu-id="43459-p126">使用户可以添加捕获并从该对话框中使用用户选择的功能。关闭快速归档对话框中后，调用此方法。此方法是 **IQuickFilingDialogCallback**接口具有定义的函数。 </span><span class="sxs-lookup"><span data-stu-id="43459-p126">Enables users to add functionality to capture and use the user selection from the dialog box. This method is called after the Quick Filing dialog box is closed. This method is a function that **IQuickFilingDialogCallback** interfaces have to define.  </span></span><br/> |
|<span data-ttu-id="43459-266">**语法**</span><span class="sxs-lookup"><span data-stu-id="43459-266">**Syntax**</span></span> <br/> | `HRESULT OnDialogClosed (`<br/>`[in]IQuickFilingDialog dialog);` <br/> |
|<span data-ttu-id="43459-267">**参数**</span><span class="sxs-lookup"><span data-stu-id="43459-267">**Parameters**</span></span> <br/> | <span data-ttu-id="43459-268">_对话框_&ndash;调用**OnDialogClose**方法的**IQuickFilingDialog**对象。</span><span class="sxs-lookup"><span data-stu-id="43459-268">_dialog_ &ndash; The **IQuickFilingDialog** object that called the **OnDialogClose** method.</span></span>  <br/> |
   
<span data-ttu-id="43459-p127">下面的示例是一个示例 **IQuickFilingDialogCallback**接口。 **OnDialogClose**方法将从快速归档对话框中的用户的选择打印到控制台。</span><span class="sxs-lookup"><span data-stu-id="43459-p127">The following example is a sample **IQuickFilingDialogCallback** interface. The **OnDialogClose** method prints the user's selection from the Quick Filing dialog box to the console.</span></span> 
  
```cs
    class Callback : IQuickFilingDialogCallback
    {
        public Callback(){}
        public void OnDialogClosed(IQuickFilingDialog qfDialog)
        {
            Console.WriteLine(qfDialog.SelectedItem);
            Console.WriteLine(qfDialog.PressedButton);
            Console.WriteLine(qfDialog.CheckboxState);
        }
    }

```

## <a name="example"></a><span data-ttu-id="43459-271">示例</span><span class="sxs-lookup"><span data-stu-id="43459-271">Example</span></span>
<span data-ttu-id="43459-272"><a name="odc_IQuickFilingDialog"> </a></span><span class="sxs-lookup"><span data-stu-id="43459-272"></span></span>

<span data-ttu-id="43459-p128">下面的代码示例打开一个快速归档对话框具有自定义的标题、 说明、 最近的结果列表、 树深度、 复选框和按钮。用户的已选定项目，按下按钮，并关闭对话框时将在控制台窗口中显示复选框状态。若要查看已启用页面按钮，用户将具有搜索页面并选择它，因为树深度设置为各节。对话框中不是任何窗口的子级。</span><span class="sxs-lookup"><span data-stu-id="43459-p128">The following code example opens a Quick Filing dialog box that has a customized title, description, recent result list, tree depth, check box, and buttons. The user's selected item, pressed button, and check-box state will be displayed in a console window when the dialog box is closed. To see the page button enabled, the user will have to search for a page and select it, because the tree depth is set down to sections. The dialog box is not a child of any window.</span></span>
  
```cs
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading;
using Microsoft.Office.Interop.OneNote;
namespace SampleQFD
{
    class OpenQuickFilingDialog
    {
        private static EventWaitHandle wh = new AutoResetEvent(false);
        private static IQuickFilingDialog qfDialog;
        private static String strTitle = "Sample Title";
        private static String strDescription = "Sample Description";
        private static String strCheckboxText = "Sample Checkbox";
        static void Main(string[] args)
        {
            Microsoft.Office.Interop.OneNote.Application app = 
                new Microsoft.Office.Interop.OneNote.Application();
            // Instantiate Quick Filing UI
            qfDialog = app.QuickFiling();
            #region//SET API PARAMETERS
            // TITLE
            qfDialog.Title = strTitle;
            // DESCRIPTION
            qfDialog.Description = strDescription;
            // RECENT RESULTS
            qfDialog.SetRecentResults(RecentResultType.rrtFiling,
                /*Current Section*/ true,
                /*Current Page*/ true,
                /*Unfiled Notes*/ true);
            // TREE DEPTH
            qfDialog.TreeDepth = HierarchyElement.heSections;
            // CHECKBOX
            qfDialog.CheckboxText = strCheckboxText;
            qfDialog.CheckboxState = false;
            // BUTTONS
            HierarchyElement heAll = (HierarchyElement) 
                ((uint)HierarchyElement.heNotebooks | 
                (uint)HierarchyElement.heSectionGroups | 
                (uint)HierarchyElement.heSections |  
                (uint)HierarchyElement.hePages);
            
            qfDialog.AddButton("All", heAll, heAll, true);
            qfDialog.AddButton("Notebooks", HierarchyElement.heNotebooks, 
                HierarchyElement.heNotebooks, false);
            qfDialog.AddButton("Pages", HierarchyElement.hePages, 
                HierarchyElement.hePages, false);
            // PARENTWINDOW
            #endregion
            // Display Quick Filing UI
            qfDialog.Run(new Callback());
            // Clean up and Wait so console window does not close
            qfDialog = null;
            wh.WaitOne();
        }
    }
    class Callback : IQuickFilingDialogCallback
    {
        public Callback(){}
        public void OnDialogClosed(IQuickFilingDialog qfDialog)
        {
            Console.WriteLine(qfDialog.SelectedItem);
            Console.WriteLine(qfDialog.PressedButton);
            Console.WriteLine(qfDialog.CheckboxState);
        }
    }
}

```

## <a name="see-also"></a><span data-ttu-id="43459-277">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43459-277">See also</span></span>

- [<span data-ttu-id="43459-278">OneNote 开发人员参考</span><span class="sxs-lookup"><span data-stu-id="43459-278">OneNote developer reference</span></span>](onenote-developer-reference.md)

