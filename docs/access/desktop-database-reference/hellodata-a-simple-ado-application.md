---
title: HelloData：简单 ADO 应用程序
TOCTitle: 'HelloData: A simple ADO application'
ms:assetid: c271abeb-8865-81f9-db8e-47d3db87ad30
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249950(v=office.15)
ms:contentKeyID: 48547554
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 3c7d9be9b91b3f847516eb3c22aa37e46c8a551d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292018"
---
# <a name="hellodata-a-simple-ado-application"></a>HelloData：简单 ADO 应用程序

**适用于**：Access 2013、Office 2013

若要奠定探索 ADO 库的基础，可以考虑使用名"HelloData"的简单 ADO 应用程序。HelloData 分步介绍了四种主要 ADO 操作（获取数据、检查数据、编辑数据和更新数据）中的每一种。为了注重 ADO 基础并避免出现代码混乱，示例中进行了最少错误处理。

该应用程序查询 Microsoft SQL Server 2000 中包含的罗斯文示例数据库。

**运行 HelloData**

1.  新建一个引用 ADO 2.5 库的标准可执行 Visual Basic 项目。

2.  在窗体顶部创建四个命令按钮，将 **Name** 和 **Caption** 属性设置为下表中所示的值。

3.  在按钮下方，添加 **Microsoft DataGrid Control** (Msdatgrd.ocx)。 Msdatgrd 文件包含在 Visual Basic 中, \\位于 windows\\system32 或\\winnt\\system32 目录中。 若要向 Visual Basic 工具箱面板添加 DataGrid 控件，请从“工程”菜单上选择“组件”********。 选中“Microsoft DataGrid Control 6.0 (SP3) (OLEDB)”旁边的复选框，然后单击“确定”****。 若要向工程添加控件，请将 DataGrid 控件从工具箱拖到 Visual Basic 窗体上。

4.  在网格下方的窗体上创建一个 **文本框** ，按表中所示设置其属性。完成时，该窗体的外观应如下图所示。

5.  最后, 将[HelloData 代码](hellodata-code.md)中列出的代码复制并粘贴到窗体的代码编辑器窗口中。 按 **F5** 运行代码。

> [!NOTE]
> [!注释] 在以下示例和整个指南中，将以用户 ID"MyId"和密码"123aBc"来向服务器进行身份验证。应当用您的服务器的有效登录凭据来替换这些值，并用您的服务器的名称替换"MyServer"值。

有关代码的详细说明, 请参阅[HelloData Details](hellodata-details.md)。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>控件类型</p></th>
<th><p>属性</p></th>
<th><p>值</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>窗体</p></td>
<td><p>名称</p></td>
<td><p>Form1</p></td>
</tr>
<tr class="even">
<td><p><br />
</p></td>
<td><p>Height</p></td>
<td><p>6500</p></td>
</tr>
<tr class="odd">
<td><p><br />
</p></td>
<td><p>Width</p></td>
<td><p>6500</p></td>
</tr>
<tr class="even">
<td><p>MS 数据网格</p></td>
<td><p>名称</p></td>
<td><p>grdDisplay1</p></td>
</tr>
<tr class="odd">
<td><p>TextBox</p></td>
<td><p>名称</p></td>
<td><p>txtDisplay1</p></td>
</tr>
<tr class="even">
<td><p><br />
</p></td>
<td><p>适用</p></td>
<td><p>true</p></td>
</tr>
<tr class="odd">
<td><p>命令按钮</p></td>
<td><p>名称</p></td>
<td><p>cmdGetData</p></td>
</tr>
<tr class="even">
<td><p><br />
</p></td>
<td><p>Caption</p></td>
<td><p>获取数据</p></td>
</tr>
<tr class="odd">
<td><p>命令按钮</p></td>
<td><p>名称</p></td>
<td><p>cmdExamineData</p></td>
</tr>
<tr class="even">
<td><p><br />
</p></td>
<td><p>Caption</p></td>
<td><p>检查数据</p></td>
</tr>
<tr class="odd">
<td><p>命令按钮</p></td>
<td><p>名称</p></td>
<td><p>cmdEditData</p></td>
</tr>
<tr class="even">
<td><p><br />
</p></td>
<td><p>Caption</p></td>
<td><p>编辑数据</p></td>
</tr>
<tr class="odd">
<td><p>命令按钮</p></td>
<td><p>名称</p></td>
<td><p>cmdUpdateData</p></td>
</tr>
<tr class="even">
<td><p><br />
</p></td>
<td><p>Caption</p></td>
<td><p>更新数据</p></td>
</tr>
</tbody>
</table>



