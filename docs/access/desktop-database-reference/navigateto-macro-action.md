---
title: NavigateTo 宏操作
TOCTitle: NavigateTo macro action
ms:assetid: 6594d614-3ea6-7851-b70e-1661d24f8ba0
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195165(v=office.15)
ms:contentKeyID: 48545324
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm119055
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 1c37e798e0624a5655b63a76332073e5b57c0823
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288600"
---
# <a name="navigateto-macro-action"></a>NavigateTo 宏操作

**适用于**：Access 2013、Office 2013

可以使用 **NavigateTo** 操作控制在导航窗格中显示的数据库对象。例如，可以更改数据库对象的分类方式，并可通过筛选对象来仅显示特定的对象。

## <a name="setting"></a>Setting

**NavigateTo** 操作具有下列参数。

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
<td><p><strong>类别</strong></p></td>
<td><p>必选。要让导航窗格在显示对象时依据的类别。请在<strong>“类别”</strong>框中单击<strong>“对象类型”</strong>、<strong>“表和视图”</strong>、<strong>“修改日期”</strong>、<strong>“创建日期”</strong>或<strong>“自定义”</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong>组</strong></p></td>
<td><p>可选。 “组”<strong></strong>参数限制类别中可显示在导航窗格中的对象。 如果将<strong>Group</strong>参数保留为空, 则导航窗格将显示按照您在<strong>Category</strong>参数中指定的条件进行分类的所有数据库对象。 下表中显示了各个“类别”参数<strong></strong>的有效“组”<strong></strong>参数的示例。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

- 此操作类似于从导航窗格的标题栏中选择类别和组。

- Valid **Group** arguments depend on which **Category** argument is used. If you enter an invalid **Group** argument, an error message appears.The following table contains examples of valid **Group** arguments for each **Category** argument.
    
  <table>
  <colgroup>
  <col style="width: 50%" />
  <col style="width: 50%" />
  </colgroup>
  <thead>
  <tr class="header">
  <th><p>Category 参数</p></th>
  <th><p>Group 参数的示例</p></th>
  </tr>
  </thead>
  <tbody>
  <tr class="odd">
  <td><p>对象类型</p></td>
  <td><p>表；窗体；查询；页；宏；模块</p></td>
  </tr>
  <tr class="even">
  <td><p>表和视图</p></td>
  <td><p>数据库中特定表的名称</p></td>
  </tr>
  <tr class="odd">
  <td><p>修改日期</p></td>
  <td><p>今天；昨天；上个月；更早</p></td>
  </tr>
  <tr class="even">
  <td><p>创建日期</p></td>
  <td><p>今天、昨天、上个月、更早</p></td>
  </tr>
  <tr class="odd">
  <td><p>自定义类别</p></td>
  <td><p>为指定的自定义类别创建的组名</p></td>
  </tr>
  </tbody>
  </table>

- 要在 VBA 模块中运行 **NavigateTo** 操作，请使用 **DoCmd** 对象的 **NavigateTo** 方法。

> [!NOTE]
> To navigate to the top level of a category (for example, **All Tables**, **All Access Objects**, or **All Dates**), you must leave the Group argument blank. For example, when the **Category** argument is **Object Type**, entering **All Access Objects** as a **Group** argument results in an error.


