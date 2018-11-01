---
title: SelectObject 宏操作
TOCTitle: SelectObject Macro Action
ms:assetid: a90539a0-c5a0-e997-9c25-e0972d28f2a6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821420(v=office.15)
ms:contentKeyID: 48546914
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm41840
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 655b5c9273e84be3365116c2e7b93c657c0d732f
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25884056"
---
# <a name="selectobject-macro-action"></a>SelectObject 宏操作


**适用于**： Access 2013、 Office 2013

可以使用 **SelectObject** 操作选择指定的数据库对象。

## <a name="setting"></a>设置

**SelectObject** 操作具有下列参数。

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
<td><p><strong>对象类型</strong></p></td>
<td><p>要选择的数据库对象的类型。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“对象类型”</strong>框中单击<strong>“表”</strong>、<strong>“查询”</strong>、<strong>“窗体”</strong>、<strong>“报表”</strong>、<strong>“宏”</strong>、<strong>“模块”</strong>、<strong>“数据访问页”</strong>、<strong>“服务器视图”</strong>、<strong>“图表”</strong>、<strong>“存储过程”</strong>或<strong>“函数”</strong>。这是一个必选参数。</p></td>
</tr>
<tr class="even">
<td><p><strong>对象名称</strong></p></td>
<td><p>要选择的对象的名称。 <strong>对象名称</strong>框中显示<strong>对象类型</strong>参数所选类型的数据库中的所有对象。 这是一个必需的参数，除非您将在导航窗格中参数设置为<strong>是</strong>。</p>

> [!NOTE]
> <P><STRONG>“服务器视图”</STRONG>、<STRONG>“图表”</STRONG>或<STRONG>“存储过程”</STRONG>对象的对象名称不会显示在 Microsoft Access 项目 (.adp) 的<STRONG>“对象名称”</STRONG>框中。</P>


<p></p></td>
</tr>
<tr class="odd">
<td><p><strong>在导航窗格中</strong></p></td>
<td><p>指定 Microsoft Access 是否选择导航窗格中的对象。请单击<strong>“是”</strong>（选择导航窗格中的对象）或<strong>“否”</strong>（不选择导航窗格中的对象）。默认值为<strong>“否”</strong>。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

**SelectObject**操作适用于可接收焦点任何访问对象。 此操作使指定的对象获得焦点，显示对象如果它处于隐藏状态。 如果对象是窗体， **SelectObject**操作将窗体的**Visible**属性设置为**是**，并让窗体返回其窗体属性 （例如，为模式或弹出式窗体） 设置的模式。

如果在一个其他 Access 窗口中，该对象未打开，您可以通过**在导航窗格中**参数设置为**是**导航窗格中选择它。 如果将**在导航窗格中**参数设置为**否**，，当您尝试选择未打开对象时，但未出现错误消息。

通常，您可能会使用此操作来选择要对其执行其他操作的对象。例如，如果您将 Access 配置为使用重叠窗口，而不是使用选项卡式文档，您可能需要还原已经最小化的对象（使用 **RestoreWindow** 操作）或最大化包含您要使用的对象的窗口（使用 **MaximizeWindow** 操作）。

如果您选择了窗体，则可以使用 **GoToControl** 、 **GoToRecord** 和 **GoToPage** 操作移动至窗体上的特定区域。 **GoToRecord** 操作也适用于数据表。

要在 Visual Basic for Applications (VBA) 模块中运行 **SelectObject** 操作，请使用 **DoCmd** 对象的 **SelectObject** 方法。

