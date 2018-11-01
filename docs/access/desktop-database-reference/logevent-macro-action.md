---
title: LogEvent 宏操作
TOCTitle: LogEvent Macro Action
ms:assetid: 3578c725-64b9-385e-ef73-a15cdf751c33
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192460(v=office.15)
ms:contentKeyID: 48544148
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 093313028822bebea26fbf86dfc94063e5512e14
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25873374"
---
# <a name="logevent-macro-action"></a>LogEvent 宏操作


**适用于**： Access 2013、 Office 2013

**LogEvent** 操作可向 **USysApplicationLog** 系统表中写入信息。


> [!NOTE]
> <P>[!注释] <STRONG>LogEvent</STRONG> 操作仅适用于数据宏。</P>



## <a name="setting"></a>设置

**LogEvent** 操作具有以下参数。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>参数</p></th>
<th><p>是否必需</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>否</p></td>
<td><p>一个用于描述要记录的条件的字符串表达式。该描述不能超过 255 个字符。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注释

**LogEvent** 操作可用于向不应使用 [**RaiseError**](raiseerror-macro-action.md) 操作引发错误的 **USysApplicationLog** 系统表中写入状态信息。例如，您可以记录对特定字段的更改，或使用写入 **USysApplicationLog** 的项来帮助您调试宏。

当您使用**LogEvent**操作写入**USysApplicationLog**表时，**类别**列会自动设置给**用户**。

若要查看 **USysApplicationLog** 表，请执行以下步骤：

1.  单击 **"文件"** 菜单，然后单击 **"选项"**。

2.  在 **"Access 选项"** 对话框中，单击 **"当前数据库"** 选项卡。

3.  在 **"导航"** 部分，单击 **"导航选项"**。

4.  在 **"导航选项"** 对话框中，单击 **"显示系统对象"**，然后单击 **"确定"**。

5.  单击 **"确定"** 关闭 **"Access 选项"** 对话框。

