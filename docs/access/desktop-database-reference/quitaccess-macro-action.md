---
title: QuitAccess 宏操作
TOCTitle: QuitAccess Macro Action
ms:assetid: af063f65-d3b1-fa9a-4bc1-04b0d21d62b9
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821759(v=office.15)
ms:contentKeyID: 48547089
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm96777
f1_categories:
- Office.Version=v15
ms.openlocfilehash: d26f8d32e0df350c52ea22dfec44ac7a24c9ecc9
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25870749"
---
# <a name="quitaccess-macro-action"></a>QuitAccess 宏操作


**适用于**： Access 2013、 Office 2013

可以使用 **QuitAccess** 操作退出 Microsoft Access。 **QuitAccess** 操作还可以指定在退出 Access 之前用于保存数据库对象的若干选项之一。


> [!NOTE]
> <P>[!注释] 如果数据库不受信任，将不允许此操作。有关启用宏的详细信息，请参阅本文 See Also 一节中的链接。</P>



## <a name="setting"></a>设置

**QuitAccess** 操作具有以下参数。

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
<td><p><strong>Options</strong></p></td>
<td><p>指定在退出 Access 时未保存的对象会出现什么情况。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“选项”</strong>对话框中单击<strong>“提示”</strong>（显示询问是否保存每个对象的对话框）、<strong>“全部保存”</strong>（直接保存所有对象而不使用对话框提示）或<strong>“退出”</strong>（退出而不保存任何对象）。默认值为<strong>“全部保存”</strong>。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

Access 不运行宏的 **QuitAccess** 操作后的任何操作。

您可以使用此操作退出 Access 不提示**保存**对话框通过使用窗体上的自定义菜单命令或按钮。 例如，您可能必须使用您的自定义工作区中显示的对象的主窗体。 此窗体无法有运行的宏的**QuitAccess**操作包含**选项**参数设置为**全部保存****退出**按钮。

此操作具有相同的效果，然后单击**退出**打开**文件**选项卡。 如果您有任何未保存的对象，当您单击此命令时，显示对话框是显示使用**提示**的**QuitAccess**操作在**Options**参数时的相同。

可以使用宏中的 **SaveObject** 操作保存指定的对象，而不必退出 Access 或者关闭该对象。

若要在 Visual Basic for Applications (VBA) 模块中运行 **QuitAccess** 操作，请使用 **DoCmd** 对象的 **Quit** 方法。

