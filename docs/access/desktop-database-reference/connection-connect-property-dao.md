---
title: Connection 属性 (DAO)
TOCTitle: Connect Property
ms:assetid: 58b514a2-91cd-7918-cba5-15d71c2457a6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194335(v=office.15)
ms:contentKeyID: 48545001
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e44ce5b4acf58f3f9d9e887d0136baed64c8e227
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295924"
---
# <a name="connectionconnect-property-dao"></a>Connection 属性 (DAO)


**适用于**：Access 2013、Office 2013

设置或返回一个值，该值提供与已打开连接的源有关的信息。 可读/写 **String** 类型。

## <a name="syntax"></a>语法

*表达式*。连接

*表达式*一个代表**Connection**对象的变量。

## <a name="remarks"></a>注解

**Connect** 属性设置是一个 **String**，由一个数据库类型说明符以及由分号分隔的零个或更多个参数组成。 **Connect** 属性根据需要将其他信息传递给 ODBC 和某些 ISAM 驱动程序。

若要对链接到 Microsoft Access 数据库文件的表执行 SQL 传递查询，必须首先将链接表的数据库的 **Connect** 属性设置为有效的 ODBC 连接字符串。

对于代表链接表的 **TableDef** 对象， **Connect** 属性设置由一个或两个部分（数据库类型说明符和指向该数据库的路径）组成，其中每个部分都以分号结尾。

下表中所示的路径是包含数据库文件的目录的完整路径，它的前面必须是标识符 DATABASE=。 在某些情况下（如使用 Microsoft Excel 和 Microsoft Access 数据库引擎数据库时），应该在数据库路径参数中包括特定的文件名。

下表显示适用于 **Connect** 属性设置的可能的数据库类型及其相应的数据库说明符和路径。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>数据库类型</p></th>
<th><p>分类</p></th>
<th><p>示例</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microsoft Access 数据库</p></td>
<td><p>[数据库];</p></td>
<td><p>驱动器: \ path\filename</p></td>
</tr>
<tr class="even">
<td><p>dBASE III</p></td>
<td><p>dBASE III;</p></td>
<td><p>驱动器: \ 路径</p></td>
</tr>
<tr class="odd">
<td><p>dBASE IV</p></td>
<td><p>dBASE IV;</p></td>
<td><p>驱动器: \ 路径</p></td>
</tr>
<tr class="even">
<td><p>dBASE 5</p></td>
<td><p>dBASE 5.0;</p></td>
<td><p>驱动器: \ 路径</p></td>
</tr>
<tr class="odd">
<td><p>Paradox 3.x</p></td>
<td><p>Paradox 3.x;</p></td>
<td><p>驱动器: \ 路径</p></td>
</tr>
<tr class="even">
<td><p>Paradox 4.x</p></td>
<td><p>Paradox 4.x;</p></td>
<td><p>驱动器: \ 路径</p></td>
</tr>
<tr class="odd">
<td><p>Paradox 5.x</p></td>
<td><p>Paradox 5.x;</p></td>
<td><p>驱动器: \ 路径</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Excel 3.0</p></td>
<td><p>Excel 3.0;</p></td>
<td><p>驱动器: \ path\filename.xls</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Excel 4.0</p></td>
<td><p>Excel 4.0;</p></td>
<td><p>驱动器: \ path\filename.xls</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Excel 5.0 或 Microsoft Excel 95</p></td>
<td><p>Excel 5.0;</p></td>
<td><p>驱动器: \ path\filename.xls</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Excel 97</p></td>
<td><p>Excel 8.0;</p></td>
<td><p>驱动器: \ path\filename.xls</p></td>
</tr>
<tr class="even">
<td><p>Lotus 1-2-3 WKS 和 WK1</p></td>
<td><p>Lotus WK1;</p></td>
<td><p>驱动器: \ path\filename.wk1</p></td>
</tr>
<tr class="odd">
<td><p>Lotus 1-2-3 WK3</p></td>
<td><p>Lotus WK3;</p></td>
<td><p>驱动器: \ path\filename.wk3</p></td>
</tr>
<tr class="even">
<td><p>Lotus 1-2-3 WK4</p></td>
<td><p>Lotus WK4;</p></td>
<td><p>驱动器: \ path\filename.wk4</p></td>
</tr>
<tr class="odd">
<td><p>HTML Import</p></td>
<td><p>HTML Import;</p></td>
<td><p>驱动器: \ path\filename</p></td>
</tr>
<tr class="even">
<td><p>HTML Export</p></td>
<td><p>HTML Export;</p></td>
<td><p>驱动器: \ 路径</p></td>
</tr>
<tr class="odd">
<td><p>文本</p></td>
<td><p>文本框</p></td>
<td><p>驱动器: \ 路径</p></td>
</tr>
<tr class="even">
<td><p>ODBC</p></td>
<td><p>ODBC数据库 = 数据库;UID = user;PWD = 密码;DSN = 值 1;[LOGINTIMEOUT = 秒;]</p></td>
<td><p>无</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Exchange</p></td>
<td><p>Exchange 4.0;MAPILEVEL = folderpath;[TABLETYPE = {0 | 1}];[profile = profile;][PWD = password;][数据库 = 数据库;]</p></td>
<td><p>驱动器: \ path\filename</p></td>
</tr>
</tbody>
</table>


如果说明符只是 "ODBC;"，则 ODBC 驱动程序显示一个对话框，列出所有注册的 ODBC 数据源名称，以便用户可以选择一个数据库。

如果需要密码，但是 **Connect** 属性设置中未提供此密码，那么 ODBC 驱动程序首次访问表时，将显示一个登录对话框，并且在关闭并重新打开连接时，会再次显示该对话框。

对于 Microsoft Exchange 中的数据，应该将必需的 MAPILEVEL 项设置为完全解析的文件夹路径（例如，"Mailbox - Pat SmithIAlpha/Today"）。 路径不包括将作为表格打开的文件夹的名称;应改为将该文件夹的名称指定为**CreateTable**方法的 name 参数。 TABLETYPE 项应设置为"0"以打开文件夹（默认设置），或设置为"1"以打开通讯簿。 PROFILE 项默认为当前使用的配置文件。

对于 Micorosoft Access 数据库中的基表， **Connect** 属性设置为零长度字符串 ("")。

您可以通过为**OpenDatabase**方法提供 source 参数来设置**Database**对象的**Connect**属性。 可以检查设置以确定数据库的类型、路径、用户 ID、密码或 ODBC 数据源。

对于 Microsoft Access 工作区中的 **QueryDef** 对象，可以将 **Connect** 属性与 ReturnsRecords 属性一起使用以创建一个 ODBC SQL 传递查询。 连接字符串的 databasetype 为 "ODBC;"，字符串的其余部分包含用于访问远程数据的 ODBC 驱动程序的特定信息。 有关详细信息，请参阅特定驱动程序的文档。


> [!NOTE]
> - 必须先设置 **Connect** 属性，然后才能设置 **ReturnsRecords** 属性。
> - 您必须有权访问包含您尝试访问的数据库服务器的计算机。


