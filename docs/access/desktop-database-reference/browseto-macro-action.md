---
title: BrowseTo 宏操作
TOCTitle: BrowseTo Macro Action
ms:assetid: b25e1cc6-c4ed-abd6-0285-94fc7dae0bdf
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822020(v=office.15)
ms:contentKeyID: 48547167
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm35083
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 15009ca039d5df06bc732f4b58c066ad8f8d67c9
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25603761"
---
# <a name="browseto-macro-action"></a><span data-ttu-id="c464a-102">BrowseTo 宏操作</span><span class="sxs-lookup"><span data-stu-id="c464a-102">BrowseTo Macro Action</span></span>

<span data-ttu-id="c464a-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="c464a-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="c464a-p101">您可以使用 **BrowseTo** 操作在适当位置上的对象之间进行导航，还可通过指定子窗体控件参数的路径来更改子窗体控件的源对象。使用 **BrowseTo** 可从窗体 1 导航到窗体 2，而无需打开新窗口。</span><span class="sxs-lookup"><span data-stu-id="c464a-p101">You can use the **BrowseTo** action to navigate between objects in place. You can also change the source object of a subform control by specifying the Path to Subform Control argument. Use **BrowseTo** to navigate from form1 to form2 without opening up a new window.</span></span>

## <a name="setting"></a><span data-ttu-id="c464a-107">设置</span><span class="sxs-lookup"><span data-stu-id="c464a-107">Setting</span></span>

<span data-ttu-id="c464a-108">**BrowseTo** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="c464a-108">The **BrowseTo** action has the following argument.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c464a-109">操作参数</span><span class="sxs-lookup"><span data-stu-id="c464a-109">Action argument</span></span></p></th>
<th><p><span data-ttu-id="c464a-110">说明</span><span class="sxs-lookup"><span data-stu-id="c464a-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c464a-111">对象类型</span><span class="sxs-lookup"><span data-stu-id="c464a-111">Object Type</span></span></p></td>
<td><p><span data-ttu-id="c464a-112">要浏览的对象类型。</span><span class="sxs-lookup"><span data-stu-id="c464a-112">The object type to which to browse.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c464a-113">对象名称</span><span class="sxs-lookup"><span data-stu-id="c464a-113">Object Name</span></span></p></td>
<td><p><span data-ttu-id="c464a-114">在子窗体控件路径参数所引用的子窗体控件内部加载的对象。</span><span class="sxs-lookup"><span data-stu-id="c464a-114">The object that loads inside the subform control referenced by the Path to Subform Control argument.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c464a-115">Path to Subform Control</span><span class="sxs-lookup"><span data-stu-id="c464a-115">Path to Subform Control</span></span></p></td>
<td><p><span data-ttu-id="c464a-116">如果指定，从主窗体的目标子窗体将应用程序的路径控制该加载对象名称参数指定的对象。</span><span class="sxs-lookup"><span data-stu-id="c464a-116">If specified, the path from the main form of the application to the target subform control that loads the object specified by the Object Name argument.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c464a-117">Where Condition</span><span class="sxs-lookup"><span data-stu-id="c464a-117">Where Condition</span></span></p></td>
<td><p><span data-ttu-id="c464a-118">如果指定，则将替换对象记录源的 Where 条件。</span><span class="sxs-lookup"><span data-stu-id="c464a-118">If specified, replaces the Where condition of the object record source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c464a-119">Page</span><span class="sxs-lookup"><span data-stu-id="c464a-119">Page</span></span></p></td>
<span data-ttu-id="c464a-120"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="c464a-120"><<<<<<< HEAD</span></span>
<td><p><span data-ttu-id="c464a-p102">如果指定，将设置连续窗体中将成为当前页面的页面。该参数仅适用于 Web。</span><span class="sxs-lookup"><span data-stu-id="c464a-p102">If specified, sets the page of the continuous form that will be made the current page. This argument is Web only.</span></span></p></td>
=======
<td><p><span data-ttu-id="c464a-123">如果指定，将设置连续窗体中将成为当前页面的页面。</span><span class="sxs-lookup"><span data-stu-id="c464a-123">If specified, sets the page of the continuous form that will be made the current page.</span></span> <span data-ttu-id="c464a-124">此参数是仅 web。</span><span class="sxs-lookup"><span data-stu-id="c464a-124">This argument is web only.</span></span></p></td><span data-ttu-id="c464a-125">
>>>>>>>主控形状</span><span class="sxs-lookup"><span data-stu-id="c464a-125">
>>>>>>> master</span></span>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c464a-126">Data Mode</span><span class="sxs-lookup"><span data-stu-id="c464a-126">Data Mode</span></span></p></td>
<td><p><span data-ttu-id="c464a-127">如果指定，则为窗体的数据输入模式。</span><span class="sxs-lookup"><span data-stu-id="c464a-127">If specified, the data entry mode of the form.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="c464a-128">注解</span><span class="sxs-lookup"><span data-stu-id="c464a-128">Remarks</span></span>

<span data-ttu-id="c464a-129">必须使用以下代码示例中的语法来指定 PathToSubFormControl 参数：</span><span class="sxs-lookup"><span data-stu-id="c464a-129">The PathToSubFormControl argument must be specified using the syntax in the following code example:</span></span>

```vb
    Main Form.SubForm Ctrl 1>Form 2.SubForm Ctrl 2>Form 3.SubFormCtrl3
```

<span data-ttu-id="c464a-p104">在该示例中，Main Form 是 Access 客户端应用程序中的顶层窗体。"Path to Sub Form Control"参数必须依次指定窗体和子窗体控件的名称，以便从主窗体导航到子窗体控件（该控件是 Object Name 参数指定的对象的容器）。指定的每个子窗体控件必须是它前面的窗体上的控件。该路径必须以子窗体控件结尾。</span><span class="sxs-lookup"><span data-stu-id="c464a-p104">In this example, the Main Form is the top level form in the Access client application. The Path to Sub Form Control argument must alternately specify form and subform control names leading from the main form to the subform control that is the container of the object specified by the Object Name argument. Each subform control specified must be a control on the form that precedes it. The path must end with a subform control.</span></span>

## <a name="example"></a><span data-ttu-id="c464a-134">示例</span><span class="sxs-lookup"><span data-stu-id="c464a-134">Example</span></span>

<span data-ttu-id="c464a-135">下面的示例演示如何使用 BrowseTo 操作在子窗体控件或导航控件中打开报表。</span><span class="sxs-lookup"><span data-stu-id="c464a-135">The following example shows how to use the BrowseTo action to open a report in a subform control or within a navigation control.</span></span>

<span data-ttu-id="c464a-136">**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="c464a-136">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

```vb
    OnError
        Go to Next
        Macro Name
    
    /* Try to load the report in the host form (frmAuthorsParameter)    */
    BrowseTo
        Object Type Report
        Object Name rptChapters
        Path to Subform Control frmAuthorsParameter.sfrmChild
        Where Condition
        Page
        Data Mode Edit
    
    Parameters
        SelectedAuthor =[cboAuthor]
    
    /* if this fails, try to load it in the navigation subform     */
    BrowseTo
        Object Type Report
        Object Name rptChapters
        Path to Subform Control frmMain.NavigationSubform>frmAuthorsParameter.sfrmChild
        Where Condition
        Page
        Data Mode Edit
    
    Parameters
        SelectedAuthor =[cboAuthor]
```



