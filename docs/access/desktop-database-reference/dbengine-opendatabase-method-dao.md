---
title: DBEngine.OpenDatabase 方法 (DAO)
TOCTitle: OpenDatabase Method
ms:assetid: 49fca321-5955-3e69-64ea-da191536eadb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193474(v=office.15)
ms:contentKeyID: 48544654
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052979
f1_categories:
- Office.Version=v15
localization_priority: Priority
ms.openlocfilehash: 1cd4188931999284a6454064a0906b64cf1f519a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294251"
---
# <a name="dbengineopendatabase-method-dao"></a>DBEngine.OpenDatabase 方法 (DAO)

**适用于**：Access 2013、Office 2013

打开指定的数据库并返回对表示该数据库的 **[Database](database-object-dao.md)** 对象的引用。

## <a name="syntax"></a>语法

*表达式* .OpenDatabase(***Name***, ***Options***, ***ReadOnly***, ***Connect***)

*表达式* 一个表示 **DBEngine** 对象的变量。

## <a name="parameters"></a>参数

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>名称</p></th>
<th><p>必需/可选</p></th>
<th><p>数据类型</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Name</em></p></td>
<td><p>必需</p></td>
<td><p><strong>String</strong></p></td>
<td><p>现有 Microsoft Access 数据库文件的名称或 ODBC 数据源的数据源名称 (DSN)。 有关设置此值的详细信息，请参阅 <strong><a href="connection-name-property-dao.md">Name</a></strong> 属性。</p></td>
</tr>
<tr class="even">
<td><p><em>选项</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>设置数据库的各种选项（如“说明”中所述）。</p></td>
</tr>
<tr class="odd">
<td><p><em>ReadOnly</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>如果要使用只读访问权限打开数据库，此值为 <strong>True</strong>；如果要使用可读写访问权限打开数据库，此值为 <strong>False</strong>（默认值）。</p></td>
</tr>
<tr class="even">
<td><p><em>Connect</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>指定各种连接信息，包括密码。</p></td>
</tr>
</tbody>
</table>


## <a name="return-value"></a>返回值

Database

## <a name="remarks"></a>说明

可以为 Options 参数使用如下值。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Setting</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>True</strong></p></td>
<td><p>以独占模式打开数据库。</p></td>
</tr>
<tr class="even">
<td><p><strong>False</strong></p></td>
<td><p>（默认）以共享模式打开数据库。</p></td>
</tr>
</tbody>
</table>


打开数据库时会自动将该数据库添加到 **Databases** 集合。

使用 dbname 时有以下适用的注意事项：

- 如果它引用了已打开以便由其他用户访问的数据库，则会发生错误。

- 如果它没有引用现有数据库或有效的 ODBC 数据源名称，则会发生错误。

- 如果它是零长度字符串 ("")，并且 *connect* 为 "ODBC;"，则会显示列出所有已注册 ODBC 数据源名称的对话框，以便用户能够选择数据库。

若要关闭一个数据库，并因此从 **Databases** 集合中删除 **Database** 对象，请对该对象使用 **[Close](connection-close-method-dao.md)** 方法。

> [!NOTE]
> [!注释] 在访问 Microsoft Access 数据库引擎连接的 ODBC 数据源时，可通过打开连接到 ODBC 数据源的 **Database** 对象改善应用程序的性能，这样不需要将单个 [TableDef](tabledef-object-dao.md) 对象链接到 ODBC 数据源中的特定表。


