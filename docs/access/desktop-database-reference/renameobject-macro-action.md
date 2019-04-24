---
title: RenameObject 宏操作
TOCTitle: RenameObject macro action
ms:assetid: fee04eb0-23c0-5d57-b903-e1ae54f2d25e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837293(v=office.15)
ms:contentKeyID: 48548948
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm165893
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: ce16b86ea06e041d490d0c68917daf18bd80dbb6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306718"
---
# <a name="renameobject-macro-action"></a>RenameObject 宏操作

**适用于**：Access 2013、Office 2013

可以使用 **RenameObject** 操作重命名指定的数据库对象。

> [!NOTE]
> [!注释] 如果数据库不受信任，将不允许此操作。

## <a name="setting"></a>设置

**RenameObject** 操作具有下列参数。

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
<td><p><strong>新名称</strong></p></td>
<td><p>数据库对象的新名称。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“新名称”</strong>框中输入对象名称。这是一个必选参数。</p></td>
</tr>
<tr class="even">
<td><p><strong>对象类型</strong></p></td>
<td><p>要重命名的对象的类型。请单击<strong>“表”</strong>、<strong>“查询”</strong>、<strong>“窗体”</strong>、<strong>“报表”</strong>、<strong>“宏”</strong>、<strong>“模块”</strong>、<strong>“数据访问页”</strong>、<strong>“服务器视图”</strong>、<strong>“图表”</strong>、<strong>“存储过程”</strong>或<strong>“函数”</strong>。要重命名导航窗格中选定的对象，请将此参数留空。</p></td>
</tr>
<tr class="odd">
<td><p><strong>旧名称</strong></p></td>
<td><p>要重命名的对象的名称。 <strong>“旧名称”</strong>框显示数据库中属于“对象类型”<strong></strong>参数所选的类型的所有对象。 如果将“对象类型”<strong></strong>参数留空，则也要将此参数留空。</p><p><strong>注意</strong>: 如果在类库数据库中运行包含<STRONG>Rename</STRONG>操作的宏, Microsoft Access 将先在该类库数据库中查找具有此名称的对象, 然后再在当前数据库中查找。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

数据库对象的新名称必须遵循 Access 对象的标准命名约定。

无法重命名打开的对象。

If you leave the **Object Type** and **Old Name** arguments blank, Access renames the object selected in the Navigation Pane. To select an object in the Navigation Pane, you can use the **SelectObject** action with the **In Navigation Pane** argument set to **Yes**.

还可以通过以下方法重命名对象：在导航窗格中右键单击对象，单击 **"重命名"**，然后输入一个新名称。使用 **RenameObject** 操作时，您不必先在导航窗格中选择对象，也不必停止宏的运行来输入新名称。

此操作与 **CopyObject** 操作不同，CopyObject 操作是用新名称创建对象的一个副本。

若要在 Visual Basic for Applications (VBA) 模块中运行 **RenameObject** 操作，请使用 **DoCmd** 对象的 **Rename** 方法。

