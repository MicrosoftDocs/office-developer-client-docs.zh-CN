---
title: DBEngine.OpenDatabase Method (DAO)
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
ms.openlocfilehash: 311481a83c25df29a26610a979a67ceb38124470
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25860418"
---
# <a name="dbengineopendatabase-method-dao"></a>DBEngine.OpenDatabase Method (DAO)


**适用于**： Access 2013 |Office 2013

打开指定的数据库，并返回一个指向代表该数据库的 **[Database](database-object-dao.md)** 对象的引用。

## <a name="syntax"></a>语法

*表达式*。OpenDatabase （***名称***、***选项***、 ***ReadOnly***、***连接***）

*表达式*一个代表**DBEngine**对象的变量。

### <a name="parameters"></a>参数

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
<td><p>名称</p></td>
<td><p>必需</p></td>
<td><p><strong>字符串</strong></p></td>
<td><p>现有 Microsoft Access 数据库文件的名称，或者 ODBC 数据源的数据源名称 (DSN)。有关设置此值的详细信息，请参阅 <strong><a href="connection-name-property-dao.md">Name</a></strong> 属性。</p></td>
</tr>
<tr class="even">
<td><p>选项</p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>根据“说明”中的指定设置数据库的各个选项。</p></td>
</tr>
<tr class="odd">
<td><p>ReadOnly</p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>						如果要使用只读访问权限打开数据库，此值为 <strong>True</strong>；如果要使用可读写访问权限打开数据库，此值为 <strong>False</strong>（默认值）。</p></td>
</tr>
<tr class="even">
<td><p>在浏览器中</p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>指定包括密码在内的各种连接信息。</p></td>
</tr>
</tbody>
</table>


<<<<<<< 头
### <a name="return-value"></a>返回值
=======
### <a name="return-value"></a>返回值
>>>>>>> 母版

Database

## <a name="remarks"></a>注解

可以为 options 参数使用以下值。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>设置</p></th>
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
<td><p>（默认值）以共享模式打开数据库。</p></td>
</tr>
</tbody>
</table>


打开一个数据库后，该数据库将自动添加到 **Databases** 连接。

使用 dbname 时，一些事项：

  - 如果它引用了已打开以便由其他用户访问的数据库，则会发生错误。

  - 如果它没有引用现有数据库或有效的 ODBC 数据源名称，则会发生错误。

  - 如果它是零长度字符串 ("") 并且*连接*是"ODBC;"，以便用户可以选择数据库，则显示一个对话框，列出所有已注册的 ODBC 数据源名称。

若要关闭数据库，以便从 **Databases** 集合中删除 **Database** 对象，请对该对象使用 **[Close](connection-close-method-dao.md)** 方法。


> [!NOTE]
> [!注释] 在访问 Microsoft Access 数据库引擎连接的 ODBC 数据源时，可通过打开连接到 ODBC 数据源的 **Database** 对象改善应用程序的性能，这样不需要将单个 [TableDef](tabledef-object-dao.md) 对象链接到 ODBC 数据源中的特定表。


