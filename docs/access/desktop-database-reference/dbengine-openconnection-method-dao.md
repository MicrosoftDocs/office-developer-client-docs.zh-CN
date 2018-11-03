---
title: DBEngine.OpenConnection 方法 (DAO)
TOCTitle: OpenConnection Method
ms:assetid: 778a581f-be42-94ee-e5c6-4cbc1843450d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196074(v=office.15)
ms:contentKeyID: 48545729
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053574
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 08e26c4a32e8648eb1833dc493b4e121030d1f1a
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25950032"
---
# <a name="dbengineopenconnection-method-dao"></a>DBEngine.OpenConnection 方法 (DAO)

**适用于**： Access 2013、 Office 2013

## <a name="syntax"></a>语法

*表达式*。OpenConnection （***名称***、***选项***、 ***ReadOnly***、***连接***）

*表达式*一个代表**DBEngine**对象的变量。

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
<td><p><strong>字符串</strong></p></td>
<td><p>一个字符串表达式。请参阅“说明”中的讨论。</p></td>
</tr>
<tr class="even">
<td><p><em>Options</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>根据“说明”中的指定设置连接的各个选项。ODBC 驱动程序管理器根据此值向用户提示有关连接的信息，例如数据源名称 (DSN)、用户名和密码。</p></td>
</tr>
<tr class="odd">
<td><p><em>ReadOnly</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>						如果连接针对只读访问权限打开，则为 <strong>True</strong>；如果连接针对读/写访问权限打开，则为 <strong>False</strong>（默认值）。</p></td>
</tr>
<tr class="even">
<td><p><em>Connect</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>将 ODBC 连接字符串。 请参阅<strong><a href="connection-connect-property-dao.md">Connect</a></strong>属性为特定的元素和此字符串的语法。 预先计算&quot;ODBC;&quot; ，则需要。</p></td>
</tr>
</tbody>
</table>


## <a name="return-value"></a>返回值

Connection

## <a name="remarks"></a>注解

使用 **OpenConnection** 方法可在 ODBCDirect 工作区中建立与 ODBC 数据源的连接。 **OpenConnection** 方法类似于 **OpenDatabase**，但不完全相同。主要差别在于 **OpenConnection** 只在 ODBCDirect 工作区中可用。

如果连接参数中指定注册的 ODBC 数据源名称 (DSN)，然后名称参数可以是任何有效的字符串，并将还提供的**Connection**对象的**Name**属性。 如果在连接参数中不包含有效 DSN，名称必须引用有效的 ODBC DSN，还将**名称**属性。 如果 name 和连接都不包含有效 DSN，ODBC 驱动程序管理器可以设置 （通过在 options 参数），以提示用户输入所需的连接信息。 然后，通过提示而提供的 DSN 将会提供 **Name** 属性。

options 参数确定是否以及何时提示用户建立连接，以及是否异步打开连接。可以使用下列常量之一。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>dbDriverNoPrompt</strong></p></td>
<td><p>ODBC 驱动程序管理器使用 <em>dbname</em> 和 <em>connect</em> 中提供的连接字符串。如果不提供足够的信息，将发生运行时错误。</p></td>
</tr>
<tr class="even">
<td><p><strong>dbDriverPrompt</strong></p></td>
<td><p>ODBC 驱动程序管理器将显示<strong>ODBC 数据源</strong>对话框，其中显示<em>dbname</em>或<em>连接</em>中的任何提供的相关信息。 连接字符串是组成 DSN 用户选择通过对话框框中，或者，如果用户不指定 dsn 以外，则使用默认 DSN。</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbDriverComplete</strong></p></td>
<td><p>默认值。如果 <em>connect</em> 参数包括完成连接所需的所有必要信息，ODBC 驱动程序管理器将使用 <em>connect</em> 中的字符串。否则，其表现与指定了 <strong>dbDriverPrompt</strong> 时相同。</p></td>
</tr>
<tr class="even">
<td><p><strong>dbDriverCompleteRequired</strong></p></td>
<td><p>此选项的表现类似于 <strong>dbDriverComplete</strong>，不同之处在于，ODBC 驱动程序将禁止提示完成连接所不需要的任何信息。</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbRunAsync</strong></p></td>
<td><p>异步执行方法。此常量可以与其他任何 <em>options</em> 常量一起使用。</p></td>
</tr>
</tbody>
</table>


**OpenConnection** 返回包含有关连接的信息的 **Connection** 对象。 **Connection** 对象与 **[Database](database-object-dao.md)** 对象类似。主要差别在于 **Database** 对象通常代表数据库，尽管也可以使用它代表在 Microsoft Access 工作区中与 ODBC 数据源建立的连接。

