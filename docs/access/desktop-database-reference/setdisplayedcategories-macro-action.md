---
title: SetDisplayedCategories 宏操作
TOCTitle: SetDisplayedCategories Macro Action
ms:assetid: e8bf39a6-c639-2232-7b21-3b0badf37e4b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836053(v=office.15)
ms:contentKeyID: 48548429
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm20026
f1_categories:
- Office.Version=v15
ms.openlocfilehash: af4b491ff76a28c998e1ec195a861dbf065d36c8
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468263"
---
# <a name="setdisplayedcategories-macro-action"></a>SetDisplayedCategories 宏操作


**适用于**： Access 2013 |Office 2013

可以使用 **SetDisplayedCategories** 操作指定哪些类别在导航窗格标题栏中的 **"浏览类别"** 下显示。例如，如果希望阻止用户切换导航窗格，以便显示按 **"创建日期"** 排序的对象，则可以使用此操作在标题栏的下拉列表中隐藏该选项。

## <a name="setting"></a>设置

**SetDisplayedCategories** 操作具有下列参数。

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
<td><p><strong>Show</strong></p></td>
<td><p>选择<strong>“是”</strong>可显示一个或多个类别。选择<strong>“否”</strong>可隐藏类别。</p></td>
</tr>
<tr class="even">
<td><p><strong>类别</strong></p></td>
<td><p>请输入或选择要显示或隐藏的类别的名称。将此参数留空可显示或隐藏所有类别。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

  - 导航窗格的标题栏中的标题指示哪种筛选（如果有）当前处于活动状态。请单击标题栏的任意位置以显示下拉列表。此宏操作控制的项会在 **"浏览类别"** 下列出。

  - 此操作仅启用或禁用指定的一个或多个类别的显示；它不执行在任何导航窗格显示之间的切换。例如，如果正在显示按 **"创建日期"** 排序的对象并且使用 **SetDisplayedCategories** 操作禁用 **"创建日期"** 选项，则 Access 不会将导航窗格切换到其他类别。

  - 要在 VBA 模块中运行 **SetDisplayedCategories** 操作，请使用 **DoCmd** 对象的 **SetDisplayedCategories** 方法。

