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
# <a name="quick-filing-dialog-box-interfaces-onenote"></a>快速归档对话框框接口 (OneNote 2013)

本主题介绍可用于以编程方式自定义OneNote 2013中的快速归档对话框的接口。
  
## <a name="quick-filing-dialog-box"></a>"快速归档" 对话框

OneNote 2013中的快速归档对话框是一个可自定义的对话框，允许用户选择 OneNote 层次结构内的位置。可选位置包括笔记本、 节组、 节、 页和子页。对话框中使用的 OneNote 应用程序内部和外部应用程序通过OneNote 2013 API。图 1 显示在其默认状态的快速归档对话框。
  
**图 1。没有自定义的快速归档对话框**

![无自定义的快速归档对话框](media/ON15Con_quick_filing_dialog.jpg "无自定义的快速归档对话框")
  
在对话框中，用户可以导航要查找特定位置，或通过在文本框中键入搜索 OneNote 树状结构中的所有笔记本层次结构。可以自定义的对话框中的方面包括标题、 说明、 最近的结果列表、 复选框文本和状态、 树深度、 按钮和可选位置类型。

您可以通过两个OneNote 2013接口访问快速归档对话框功能。 **IQuickFilingDialog**界面允许用户实例化，设置，并运行对话框。关闭对话框后，调用 **IQuickFilingDialogCallback**接口。在 OneNote 过程中，运行对话框中，因此保持运行对话框的线程所需的一种机制，然后关闭时捕获用户的选择和对话框中的状态。 
  
## <a name="iquickfilingdialog-interface"></a>IQuickFilingDialog 接口
<a name="odc_IQuickFilingDialog"> </a>

此接口允许用户自定义和运行对话框。用户可以通过使用 **Application.QuickFilingDialog**方法实例化一个对话框，通过 **Application**类。该方法返回对话框的实例。一旦设置对话框中的属性， **IQuickFilingDialog.Run**方法用于运行对话框。此方法在新的线程上运行的对话框。 
  
**属性**

|**Name**|**Type**|**说明**|
|:-----|:-----|:-----|
|**Title** <br/> |字符串  <br/> |获取或设置对话框窗口的标题栏中显示的标题文本。  <br/> |
|**Description** <br/> |字符串  <br/> |获取或设置以指示要选择的内容有关用户的文本说明。此值可以是多行文本。  <br/> |
|**CheckboxText** <br/> |字符串  <br/> |获取或设置如下所示的复选框的文本。如果此值设置为非空字符串，在对话框中将显示一个复选框。如果值为空字符串，将显示没有复选框。  <br/> |
|**CheckboxState** <br/> |bool  <br/> |获取或设置状态的复选框。如果值设置为 **false**，启动的对话框时，将清除复选框。如果值设置为 **true**，复选框处于选中状态，当对话框中启动时，只要 **CheckboxText**是一个非空字符串。 <br/> |
|**WindowHandle** <br/> |ulong  <br/> |获取快速归档对话框窗口的句柄 ID。  <br/> |
|**TreeDepth** <br/> |**HierarchyElement** <br/> |获取或设置 OneNote 树应显示在所有笔记本节的深度。默认情况下，最多为各节显示的树。此属性不会影响可选择哪种类型的元素。 <br/> 如果 **TreeDepth**设置为一个元素中的 OneNote 层次结构不是可由任何按钮选择较低，显示的树深度将最低可能可选元素。也就是说，如果树深度设置为显示下页，但的最低的可选元素是部分，部分下显示的树。 <br/> |
|**ParentWindowHandle** <br/> |ulong  <br/> |获取或设置对话框中的父窗口的句柄 ID。如果设置此属性，快速归档对话框中将在分配的父窗口模式时打开的对话框。即，用户将无法访问父窗口，直到关闭快速归档对话框。  <br/> |
|**Position** <br/> |tagPOINT  <br/> |获取或设置与屏幕窗口的位置。默认情况下，在父窗口或桌面的中间显示对话框。  <br/> |
|**SelectedItem** <br/> |string  <br/> |获取 OneNote 位置时关闭对话框，用户选择的对象 ID。如果用户单击 **取消**按钮，该对象将设置为 null。 <br/> |
|**PressedButton** <br/> |ulong  <br/> |获取时关闭对话框中单击了哪个按钮。如果单击 **取消**按钮，此属性返回值-1。所有其他按钮分配整数值从 0 增加 1 添加到对话框中的每个按钮。默认值 **确定**按钮的整数值为 0。 <br/> |
   
### <a name="methods"></a>方法

**SetRecentResults**

|||
|:-----|:-----|
|**说明** <br/> |设置哪些最近的结果列表将显示在快速归档对话框中，并指示是否在列表中包括一些特殊归档位置。用户可以选择[RecentResultType](enumerations-onenote-developer-reference.md#odc_RecentResultType)枚举中的最新的结果列表。用户还可以选择以下选项添加到列表: 当前节、 当前页或未归档笔记。如果 **RecentResultType.rrtNone**处于选中状态，将不显示任何新的结果列表。 <br/> |
|**语法** <br/> | `HRESULT SetRecentResults (`<br/>`[in]RecentResultType recentResults,`<br/>`[in]VARIANT_BOOL fShowCurrentSection,`<br/>`[in]VARIANT_BOOL fShowCurrentPage,`<br/>`[in]VARIANT_BOOL fShowUnfiledNotes);` <br/> |
|**参数** <br/> | _recentResults_&ndash;一个**RecentResultType**类型的对象, 该对象指示应显示的最近结果列表 (如果有)。 如果 **rrtNone**处于选中状态，没有最新的结果列表将显示在对话框中。<br/><br/>  _fShowCurrentSection_&ndash;一个布尔值, 指示当前节是否应包含在最近的结果列表中。<br/><br/>  _fShowCurrentPage_&ndash;一个布尔值, 指示当前页面是否应包含在最近的结果列表中。<br/><br/>  _fShowUnfiledNotes_&ndash;一个布尔值, 该值指示是否应在最近的结果列表中包含未归档笔记部分。  <br/> |
   
> [!NOTE]
> [!注释] 如果无法使用任一按钮的对话框中选中的特殊归档位置，则不将其显示在列表中。如果不找到了最近的结果列表中的任何可选项，将显示没有最新的结果列表。 
  
下面的示例使用 **SetRecentResults**方法在最近的结果列表中显示当前节、 当前页和未归档的注释部分。 
  
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

**AddButton**

|||
|:-----|:-----|
|**说明** <br/> |允许用户添加和自定义对话框中的按钮。用户可以指定的按钮和 OneNote 层次结构的元素可选择通过每个按钮上的文本。  <br/> |
|**语法** <br/> | `HRESULT AddButton (`<br/>`[in]BSTR bstrText,`<br/>`[in]HierarchyElement allowedElements,`<br/>`[in]HierarchyElement allowedReadOnlyElements,`<br/>`[in]VARIANT_BOOL fDefault);` <br/> |
|**参数** <br/> | _bstrText_&ndash;一个字符串, 指定要在按钮上显示的文本。 要自定义的默认 **确定**按钮，将作为 **bstrText**传递中 null 值。  <br/><br/>_allowedElements_&ndash;一个**HierarchyElement** , 指示允许用户通过使用按钮选择的非只读 OneNote 层次结构元素。 选择多个项目，用户应通过 **OR**运算符中的所有 **HierarchyElement**类型允许作为 **HierarchyElement**uint 等效值。<br/><br/>  _allowedReadOnlyElements_&ndash;一个**HierarchyElement** , 指示允许用户使用按钮选择的 OneNote 只读层次结构元素。 选择多个项目，用户应通过在 **OR**运算符 **HierarchyElement**类型允许作为 **HierarchyElement**的所有 **uint** 等效值。<br/><br/>  _fDefault_&ndash;一个布尔值, 该值指定此按钮是否应为默认按钮。 如果多个按钮设置为默认值，最后一个指定的按钮将成为默认按钮。  <br/> |
   
下面的示例将三个按钮添加到快速归档对话框。第一个， **所有**，可以选择通过 OneNote 层次结构树中的所有元素。仅当选择其相应的元素，笔记本和页面，可以选择其他， **笔记本**和 **页面**。
  
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

**运行**

|||
|:-----|:-----|
|**说明** <br/> |在新线程中的快速归档对话框中显示。计 **IQuickFilingDialogCallback**接口，关闭该对话框后，将调用其 **OnDialogClosed**方法的引用。 <br/> |
|**语法** <br/> | `HRESULT Run (`<br/>`[in]IQuickFilingDialogCallback piCallback);` <br/> |
|**参数** <br/> | _piCallback_&ndash;对**IQuickFilingDialogCallback**接口的引用, 该引用将在对话框关闭后实例化。  <br/> |
   
下面的示例使用 **Run**方法显示新线程中的快速归档对话框。 
  
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

**TreeCollapsedState**

|||
|:-----|:-----|
|**说明** <br/> |指示是否应展开或折叠的层次结构树。  <br/> |
|**语法** <br/> | `HRESULT TreeCollapsedState(`<br/>`[in] TreeCollapsedStateType tcs);` <br/> |
|**参数** <br/> | _tcs_ -指定是否展开或折叠树。  <br/> |
   
**NotebookFilterOut**

|||
|:-----|:-----|
|**说明** <br/> |筛选器的显示类型的笔记本的列表。  <br/> |
|**语法** <br/> | `HRESULT NotebookFilterOut(`<br/>`[in] NotebookFilterOutType nfo);` <br/> |
|**参数** <br/> | _nfo_ -指定一组的是要从列表中筛选的笔记本  <br/> |
   
**ShowCreateNewNotebook**

|||
|:-----|:-----|
|**说明** <br/> |在对话框中显示新建笔记本选项。  <br/> |
|**语法** <br/> | `HRESULT ShowCreateNewNotebook ();` <br/> |
|**参数** <br/> |无  <br/> |
   
**AddInitialEditor**

|||
|:-----|:-----|
|**说明** <br/> |到笔记本中的快速归档对话框中，作为初始编辑器中添加用户。  <br/> |
|**语法** <br/> | `HRESULT AddInitialEditor (BSTR initialEditor);` <br/> |
|**参数** <br/> | _initialEditor_ -要将作为编辑器添加到笔记本的用户的电子邮件地址。通过快速归档对话框中创建笔记本后，会自动共享与所有初始编辑器中。  <br/> |
   
**ClearInitialEditors**

|||
|:-----|:-----|
|**说明** <br/> |从快速归档对话框中删除所有的初始编辑器。  <br/> |
|**语法** <br/> | `HRESULT ClearInitialEditors ();` <br/> |
|**参数** <br/> |无  <br/> |
   
**ShowSharingHyperlink**

|||
|:-----|:-----|
|**说明** <br/> |在快速归档对话框中显示共享帮助主题超链接。  <br/> |
|**语法** <br/> | `HRESULT ShowSharingHyperlink();` <br/> |
|**参数** <br/> |无  <br/> |
   
## <a name="iquickfilingdialogcallback-interface"></a>IQuickFilingDialogCallback 接口
<a name="odc_IQuickFilingDialog"> </a>

此接口允许用户访问对话框属性后将关闭对话框。一旦对话框关闭， OneNote 2013此接口中调用 **IQuickFilingDialogCallback.OnDialogClose**方法。 
  
继承此接口的类必须定义。
  
### <a name="methods"></a>方法

以下部分介绍与前面详细介绍的接口关联的方法。
  
**OnDialogClosed**

|||
|:-----|:-----|
|**描述** <br/> |使用户可以添加捕获并从该对话框中使用用户选择的功能。关闭快速归档对话框中后，调用此方法。此方法是 **IQuickFilingDialogCallback**接口具有定义的函数。 <br/> |
|**语法** <br/> | `HRESULT OnDialogClosed (`<br/>`[in]IQuickFilingDialog dialog);` <br/> |
|**参数** <br/> | _对话框_&ndash;调用**OnDialogClose**方法的**IQuickFilingDialog**对象。  <br/> |
   
下面的示例是一个示例 **IQuickFilingDialogCallback**接口。 **OnDialogClose**方法将从快速归档对话框中的用户的选择打印到控制台。 
  
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

## <a name="example"></a>示例
<a name="odc_IQuickFilingDialog"> </a>

下面的代码示例打开一个快速归档对话框具有自定义的标题、 说明、 最近的结果列表、 树深度、 复选框和按钮。用户的已选定项目，按下按钮，并关闭对话框时将在控制台窗口中显示复选框状态。若要查看已启用页面按钮，用户将具有搜索页面并选择它，因为树深度设置为各节。对话框中不是任何窗口的子级。
  
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

## <a name="see-also"></a>另请参阅

- [OneNote 开发人员参考](onenote-developer-reference.md)

