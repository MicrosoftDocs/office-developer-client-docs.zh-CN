---
title: NewPassword 方法 (DAO)
TOCTitle: NewPassword Method
ms:assetid: 01c1c454-d651-222c-225a-2b02734a1b7a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff844754(v=office.15)
ms:contentKeyID: 48542941
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052943
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 20f09dbfba50526409472f7eb804ba2c47e4d1d5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294853"
---
# <a name="databasenewpassword-method-dao"></a>NewPassword 方法 (DAO)

**适用于**：Access 2013、Office 2013

更改现有 Microsoft Access 数据库引擎数据库的密码（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式*。NewPassword (***bstrOld***, ***bstrNew***)

*表达式*一个返回**Database**对象的表达式。

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
<td><p><em>bstrOld</em></p></td>
<td><p>必需</p></td>
<td><p><strong>String</strong></p></td>
<td><p><strong>Database</strong> 对象的 <strong>Password</strong> 属性的当前设置。</p></td>
</tr>
<tr class="even">
<td><p><em>bstrNew</em></p></td>
<td><p>必需</p></td>
<td><p><strong>String</strong></p></td>
<td><p><strong>Database</strong>对象的<strong>Password</strong>属性的新设置。</p>
<p><strong>注意</strong>: 请使用组合了大小写字母、数字和符号的强密码。 弱密码不会混合这些元素。 强密码：Y6dh!et5。 弱密码：House27。 请使用可以记住的强密码，这样就不必记录密码了。</p>
</td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

bstrOld 和 bstrNew 字符串的长度最多为20个字符, 并且可以包含除 ASCII 字符 0 (null) 以外的任何字符。 若要清除密码, 请对 bstrNew 使用零长度字符串 ("")。

密码区分大小写。

如果数据库没有密码，Microsoft Access 数据库引擎将通过传递旧密码的零长度字符串 ("") 自动创建一个密码。


> [!IMPORTANT]
> [!重要信息] 如果丢失了密码，则永远不能再次打开数据库。


