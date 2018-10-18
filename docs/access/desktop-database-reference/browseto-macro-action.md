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
# <a name="browseto-macro-action"></a>BrowseTo 宏操作

**适用于**： Access 2013 |Office 2013

您可以使用 **BrowseTo** 操作在适当位置上的对象之间进行导航，还可通过指定子窗体控件参数的路径来更改子窗体控件的源对象。使用 **BrowseTo** 可从窗体 1 导航到窗体 2，而无需打开新窗口。

## <a name="setting"></a>设置

**BrowseTo** 操作具有以下参数。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>操作参数</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>对象类型</p></td>
<td><p>要浏览的对象类型。</p></td>
</tr>
<tr class="even">
<td><p>对象名称</p></td>
<td><p>在子窗体控件路径参数所引用的子窗体控件内部加载的对象。</p></td>
</tr>
<tr class="odd">
<td><p>Path to Subform Control</p></td>
<td><p>如果指定，从主窗体的目标子窗体将应用程序的路径控制该加载对象名称参数指定的对象。</p></td>
</tr>
<tr class="even">
<td><p>Where Condition</p></td>
<td><p>如果指定，则将替换对象记录源的 Where 条件。</p></td>
</tr>
<tr class="odd">
<td><p>Page</p></td>
<<<<<<< 标头
<td><p>如果指定，将设置连续窗体中将成为当前页面的页面。该参数仅适用于 Web。</p></td>
=======
<td><p>如果指定，将设置连续窗体中将成为当前页面的页面。 此参数是仅 web。</p></td>
>>>>>>>主控形状
</tr>
<tr class="even">
<td><p>Data Mode</p></td>
<td><p>如果指定，则为窗体的数据输入模式。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

必须使用以下代码示例中的语法来指定 PathToSubFormControl 参数：

```vb
    Main Form.SubForm Ctrl 1>Form 2.SubForm Ctrl 2>Form 3.SubFormCtrl3
```

在该示例中，Main Form 是 Access 客户端应用程序中的顶层窗体。"Path to Sub Form Control"参数必须依次指定窗体和子窗体控件的名称，以便从主窗体导航到子窗体控件（该控件是 Object Name 参数指定的对象的容器）。指定的每个子窗体控件必须是它前面的窗体上的控件。该路径必须以子窗体控件结尾。

## <a name="example"></a>示例

下面的示例演示如何使用 BrowseTo 操作在子窗体控件或导航控件中打开报表。

**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。

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



