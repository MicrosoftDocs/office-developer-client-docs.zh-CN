---
title: HelloData： 简单 ADO 应用程序
TOCTitle: 'HelloData: A simple ADO application'
ms:assetid: c271abeb-8865-81f9-db8e-47d3db87ad30
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249950(v=office.15)
ms:contentKeyID: 48547554
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 359816f828191a8643941a21ac520ba7b3231e6b
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25998201"
---
# <a name="hellodata-a-simple-ado-application"></a>HelloData： 简单 ADO 应用程序

**适用于**： Access 2013、 Office 2013

若要奠定探索 ADO 库的基础，可以考虑使用名"HelloData"的简单 ADO 应用程序。HelloData 分步介绍了四种主要 ADO 操作（获取数据、检查数据、编辑数据和更新数据）中的每一种。为了注重 ADO 基础并避免出现代码混乱，示例中进行了最少错误处理。

该应用程序查询 Microsoft SQL Server 2000 中包含的罗斯文示例数据库。

**运行 HelloData**

1.  新建一个引用 ADO 2.5 库的标准可执行 Visual Basic 项目。

2.  在窗体顶部创建四个命令按钮，将 **Name** 和 **Caption** 属性设置为下表中所示的值。

3.  按钮，下面添加一个**Microsoft DataGrid 控件**(Msdatgrd.ocx)。 Msdatgrd.ocx 文件附带了 Visual Basic 和位于您\\windows\\system32 或\\可以对\\system32 目录。 若要将 DataGrid 控件添加到 Visual Basic 工具箱窗格中，从**项目**菜单中选择**组件...** 。 然后单击复选框"Microsoft DataGrid 控件 6.0 (SP3) (OLEDB)"，然后单击**确定**。 将控件添加到项目中，将 DataGrid 控件从工具箱拖动到 Visual Basic 窗体中。

4.  在网格下方的窗体上创建一个 **文本框** ，按表中所示设置其属性。完成时，该窗体的外观应如下图所示。

5.  最后，复制[HelloData 代码](hellodata-code.md)中列出的代码并将其粘贴到窗体的代码编辑器窗口。 按 **F5** 运行代码。

> [!NOTE]
> [!注释] 在以下示例和整个指南中，将以用户 ID"MyId"和密码"123aBc"来向服务器进行身份验证。应当用您的服务器的有效登录凭据来替换这些值，并用您的服务器的名称替换"MyServer"值。

代码的详细说明，请参阅[HelloData 详细信息](hellodata-details.md)。

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
<td><p>高度</p></td>
<td><p>6500</p></td>
</tr>
<tr class="odd">
<td><p><br />
</p></td>
<td><p>宽度</p></td>
<td><p>6500</p></td>
</tr>
<tr class="even">
<td><p>MS 数据网格</p></td>
<td><p>名称</p></td>
<td><p>grdDisplay1</p></td>
</tr>
<tr class="odd">
<td><p>文本框</p></td>
<td><p>名称</p></td>
<td><p>txtDisplay1</p></td>
</tr>
<tr class="even">
<td><p><br />
</p></td>
<td><p>多行</p></td>
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
<td><p>标题</p></td>
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
<td><p>标题</p></td>
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
<td><p>标题</p></td>
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
<td><p>标题</p></td>
<td><p>更新数据</p></td>
</tr>
</tbody>
</table>



