---
title: CopyObject 宏操作
TOCTitle: CopyObject macro action
ms:assetid: 746f61df-d5db-284a-0897-75820c2be11f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195876(v=office.15)
ms:contentKeyID: 48545661
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm12836
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 79f4e59309a4f224498421f2407df187d3b9e728
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25998063"
---
# <a name="copyobject-macro-action"></a>CopyObject 宏操作

**适用于**： Access 2013、 Office 2013

可以使用 **CopyObject** 操作将指定的数据库对象复制到另一个数据库中，或使用新名称将其复制到同一个数据库或 Microsoft Access 项目中。例如，您可以将现有对象复制或备份到另一个数据库中，也可以快速创建略有更改的类似对象。

> [!NOTE]
> [!注释] 如果数据库不受信任，将不允许此操作。 

## <a name="setting"></a>设置

**CopyObject** 操作具有下列参数。

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
<td><p><strong>目标数据库</strong></p></td>
<td><p>目标数据库的有效路径和文件名。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“目标数据库”</strong>框中输入路径和文件名。如果要选择当前数据库，请将此参数留空。 

</p><p><strong>注意</strong>： 此参数才 Access 数据库环境中可用。 在 Access 项目 (.adp) 环境中使用此操作时，目标数据库参数必须为空。</p>
<p>如果在类库数据库中运行包含 <strong>CopyObject</strong> 操作的宏并将此参数留空，Microsoft Office Access 2007 就会将该对象复制到类库数据库中。</p></td>
</tr>
<tr class="even">
<td><p><strong>新名称</strong></p></td>
<td><p>对象的新名称。在将对象复制到另一个数据库中时，将此参数留空可使名称保持不变。</p></td>
</tr>
<tr class="odd">
<td><p><strong>源对象类型</strong></p></td>
<td><p>要复制的对象类型。请单击<strong>“表”</strong>、<strong>“查询”</strong>、<strong>“窗体”</strong>、<strong>“报表”</strong>、<strong>“宏”</strong>、<strong>“模块”</strong>、<strong>“数据访问页”</strong>、<strong>“服务器视图”</strong>、<strong>“图表”</strong>、<strong>“存储过程”</strong>或<strong>“函数”</strong>。要复制在导航窗格中选择的对象，请将此参数留空。</p></td>
</tr>
<tr class="even">
<td><p><strong>源对象名称</strong></p></td>
<td><p>要复制的对象的名称。 <strong>源对象名称</strong>框中显示的<strong>源对象类型</strong>参数所选类型的数据库中的所有对象。 在<strong>源对象名称</strong>框中，单击要复制的对象。 如果将<strong>源对象类型</strong>参数留空，还应将此参数留空。 如果在类库数据库中运行包含 <strong>CopyObject</strong> 操作的宏，Access 将先在该类库数据库中查找具有此名称的对象，然后再在当前数据库中查找。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

您必须输入的一个或两个**目标数据库**和**新名称**的参数，此操作的值。

如果将**源对象类型**和**源对象名称**参数留空，Access 将复制的导航窗格中选择的对象。 若要在导航窗格中选择一个对象，可以在导航窗格中参数设置为**是**使用**SelectObject**操作。

**CopyObject** 操作类似于手动执行下列步骤：

1. 在导航窗格中选择对象。

2. 在 Home 选项卡上，在 Clipboard 组中，单击 Copy。

3. 在同一个选项卡上，单击 **"粘贴"**。此时将出现 **"粘贴为"** 对话框，以便您为对象指定一个新名称。 **CopyObject** 操作会自动执行所有这些步骤。

> [!NOTE]
> [!注释] 复制数据访问页时， **CopyObject** 操作将仅复制相关 .htm 文件的链接，而不复制该文件本身。

在宏运行 **CopyObject** 操作之前，目标数据库的路径和文件名必须已经存在。如果不存在，Access 将显示错误消息。

要在 Visual Basic for Applications (VBA) 模块中运行 **CopyObject** 操作，请使用 **DoCmd** 对象的 **CopyObject** 方法。

也可以通过单击 **"文件"** 选项卡，然后单击 **"另存为"**，手动复制在导航窗格中选择的对象或当前打开的对象。此命令将仅在当前数据库中创建对象的副本。在 **"另存为"** 对话框中，输入副本的名称，然后选择要将该对象另存为哪种对象类型。如果原始对象已经保存，而且您使用新名称将其保存在当前数据库中，则原来的版本仍以其旧名称存在。

要将对象手动复制到另一个 Access 数据库中，请执行下列操作：

1. 在 **"外部数据"** 选项卡上的 **"导出"** 组中，单击 **"其他"**，然后单击 **"Access 数据库"**。

2. 在 **"导出 - Access 数据库"** 对话框中，输入目标数据库的文件名。-或者-单击 **"浏览"** 以显示 **"保存文件"** 对话框，找到目标数据库，然后单击 **"保存"**。

3. 在 **"导出 - Access 数据库"** 对话框中，单击 **"确定"**。此时将出现 **"导出"** 对话框。

4. 在 **"导出"** 对话框中，输入目标数据库中的对象的名称。选择任何适用的选项，例如表的 **"导出定义和数据"** 或 **"只导出定义"**。完成后，请单击 **"确定"**。

