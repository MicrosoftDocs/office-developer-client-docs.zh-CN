---
title: TableDef.Connect 属性 (DAO)
TOCTitle: Connect Property
ms:assetid: 4fbb324c-a358-8fad-60f2-fb8005cf74d9
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193791(v=office.15)
ms:contentKeyID: 48544782
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053064
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 322b59c6556b73186fe4034e64c75d9104d29560
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25926897"
---
# <a name="tabledefconnect-property-dao"></a>TableDef.Connect 属性 (DAO)


**适用于**： Access 2013、 Office 2013

设置或返回一个值，该值提供有关链接表的信息。可读/写 **String** 类型。

## <a name="syntax"></a>语法

*表达式*。连接

*表达式*一个代表**TableDef**对象的变量。

## <a name="remarks"></a>注解

**Connect** 属性设置是一个 **String**，由一个数据库类型说明符以及由分号分隔的零个或更多个参数组成。 **Connect** 属性根据需要将其他信息传递给 ODBC 和某些 ISAM 驱动程序。

对于代表链接表的 **TableDef** 对象， **Connect** 属性设置由一个或两个部分（数据库类型说明符和指向该数据库的路径）组成，其中每个部分都以分号结尾。

下表中所示的路径是包含数据库文件的目录的完整路径，它的前面必须是标识符 DATABASE=。在某些情况下（如使用 Microsoft Excel 和 Microsoft Access 数据库引擎数据库时），应该在数据库路径参数中包括特定的文件名。

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
<th><p>说明符</p></th>
<th><p>示例</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microsoft Access 数据库</p></td>
<td><p>[数据库;]</p></td>
<td><p>drive:\path\filename</p></td>
</tr>
<tr class="even">
<td><p>dBASE III</p></td>
<td><p>dBASE III;</p></td>
<td><p>驱动器： \path</p></td>
</tr>
<tr class="odd">
<td><p>dBASE IV</p></td>
<td><p>dBASE IV;</p></td>
<td><p>驱动器： \path</p></td>
</tr>
<tr class="even">
<td><p>dBASE 5</p></td>
<td><p>dBASE 5.0;</p></td>
<td><p>驱动器： \path</p></td>
</tr>
<tr class="odd">
<td><p>Paradox 3.x</p></td>
<td><p>Paradox 3.x;</p></td>
<td><p>驱动器： \path</p></td>
</tr>
<tr class="even">
<td><p>Paradox 4.x</p></td>
<td><p>Paradox 4.x;</p></td>
<td><p>驱动器： \path</p></td>
</tr>
<tr class="odd">
<td><p>Paradox 5.x</p></td>
<td><p>Paradox 5.x;</p></td>
<td><p>驱动器： \path</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Excel 3.0</p></td>
<td><p>Excel 3.0;</p></td>
<td><p>drive:\path\filename.xls</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Excel 4.0</p></td>
<td><p>Excel 4.0;</p></td>
<td><p>drive:\path\filename.xls</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Excel 5.0 或 Microsoft Excel 95</p></td>
<td><p>Excel 5.0;</p></td>
<td><p>drive:\path\filename.xls</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Excel 97</p></td>
<td><p>Excel 8.0;</p></td>
<td><p>drive:\path\filename.xls</p></td>
</tr>
<tr class="even">
<td><p>Lotus 1-2-3 WKS 和 WK1</p></td>
<td><p>Lotus WK1;</p></td>
<td><p>drive:\path\filename.wk1</p></td>
</tr>
<tr class="odd">
<td><p>Lotus 1-2-3 WK3</p></td>
<td><p>Lotus WK3;</p></td>
<td><p>drive:\path\filename.wk3</p></td>
</tr>
<tr class="even">
<td><p>Lotus 1-2-3 WK4</p></td>
<td><p>Lotus WK4;</p></td>
<td><p>drive:\path\filename.wk4</p></td>
</tr>
<tr class="odd">
<td><p>HTML Import</p></td>
<td><p>HTML Import;</p></td>
<td><p>drive:\path\filename</p></td>
</tr>
<tr class="even">
<td><p>HTML Export</p></td>
<td><p>HTML Export;</p></td>
<td><p>驱动器： \path</p></td>
</tr>
<tr class="odd">
<td><p>文本</p></td>
<td><p>Text;</p></td>
<td><p>驱动器： \path</p></td>
</tr>
<tr class="even">
<td><p>ODBC</p></td>
<td><p>ODBC;数据库 = 数据库;UID = 用户;PWD = 密码;DSN = 名称;[LOGINTIMEOUT = 秒;]</p></td>
<td><p>无</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Exchange</p></td>
<td><p>Exchange 4.0;MAPILEVEL = folderpath;[TABLETYPE = {0 | 1}];[PROFILE = 配置文件;][PWD = 密码;][数据库 = 数据库;]</p></td>
<td><p>drive:\path\filename</p></td>
</tr>
</tbody>
</table>


如果需要密码，但是 **Connect** 属性设置中未提供此密码，那么 ODBC 驱动程序首次访问表时，将显示一个登录对话框，并且在关闭并重新打开连接时，会再次显示该对话框。

对于 Microsoft Exchange 中的数据，应该将必需的 MAPILEVEL 项设置为完全解析的文件夹路径（例如，"Mailbox - Pat SmithIAlpha/Today"）。 路径不包含将作为表; 打开文件夹的名称而是应用作**CreateTable**方法的名称参数指定该文件夹的名称。 TABLETYPE 项应设置为"0"以打开文件夹（默认设置），或设置为"1"以打开通讯簿。 PROFILE 项默认为当前使用的配置文件。

对于 Micorosoft Access 数据库中的基表， **Connect** 属性设置为零长度字符串 ("")。


> [!NOTE]
> <UL>
> <LI>
> <P>必须先设置 <STRONG>Connect</STRONG> 属性，然后才能设置 <STRONG>ReturnsRecords</STRONG> 属性。</P>
> <LI>
> <P>您必须有权访问包含您尝试访问的数据库服务器的计算机。</P></LI></UL>


