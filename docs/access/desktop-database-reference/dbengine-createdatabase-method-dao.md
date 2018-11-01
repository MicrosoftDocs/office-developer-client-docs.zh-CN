---
title: DBEngine.CreateDatabase Method (DAO)
TOCTitle: CreateDatabase Method
ms:assetid: d5821a4b-483a-b8fa-e929-5f036057d8c4
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835033(v=office.15)
ms:contentKeyID: 48547966
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052972
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 65a32b2b7e884e2b5957f435df0592549062b7ed
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25868013"
---
# <a name="dbenginecreatedatabase-method-dao"></a>DBEngine.CreateDatabase Method (DAO)


**适用于**： Access 2013、 Office 2013

创建一个新的 **[Database](database-object-dao.md)** 对象，将数据库保存到磁盘，然后返回一个打开的 **Database** 对象（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式*。CreateDatabase （***名称***、***区域设置***，***选项***）

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
<td><p>一个最长 255 个字符的字符串，是正在创建的数据库文件的名称。 它可以是完整路径和文件名称。 如果您的网络支持，您还可以指定一个网络路径，如&quot; \\server1\share1\dir1\db1&quot;。 仅可以使用此方法来创建 Microsoft Access 数据库文件。</p></td>
</tr>
<tr class="even">
<td><p>Locale</p></td>
<td><p>必需</p></td>
<td><p><strong>字符串</strong></p></td>
<td><ul>
<li><p>一个字符串表达式，根据“设置”中的定义指定创建数据库时使用的整理顺序。必须提供此参数，否则会发生错误。</p></li>
<li><p>您还可以通过将密码字符串创建新的<strong>Database</strong>对象的密码 (开头&quot;; pwd =&quot; ) 与<em>locale</em>参数，如下所示中的一个常量：</p></li>
<li><p>dbLangSpanish &amp; &quot;; pwd = NewPassword&quot;</p></li>
<li><p>如果需要使用默认的 <em>locale</em>，但又要指定密码，只需要为 <em>locale</em> 参数输入密码字符串：</p></li>
<li><p>&quot;pwd = NewPassword&quot;</p></li>
<li><p>[!注释] 使用同时包含大小写字母、数字和符号的强密码。弱密码不混合使用这些元素。例如，强密码：Y6dh!et5。弱密码：House27。请使用可以记住的强密码，这样就不必记录密码了。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>选项</p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>一个常量或常量组合，根据“设置”中的指定指示一个或多个选项。可通过对相应的常量求和来组合选项。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

可以使用 locale 参数的下列常量之一，指定用于字符串比较的文本的 **[CollatingOrder](database-collatingorder-property-dao.md)** 属性。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
<th><p>整理顺序</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>dbLangGeneral</strong></p></td>
<td><p>英语、德语、法语、葡萄牙语、意大利语和现代西班牙语</p></td>
</tr>
<tr class="even">
<td><p><strong>dbLangArabic</strong></p></td>
<td><p>阿拉伯语</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbLangChineseSimplified</strong></p></td>
<td><p>简体中文</p></td>
</tr>
<tr class="even">
<td><p><strong>dbLangChineseTraditional</strong></p></td>
<td><p>繁体中文</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbLangCyrillic</strong></p></td>
<td><p>俄语</p></td>
</tr>
<tr class="even">
<td><p><strong>dbLangCzech</strong></p></td>
<td><p>捷克语</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbLangDutch</strong></p></td>
<td><p>荷兰语</p></td>
</tr>
<tr class="even">
<td><p><strong>dbLangGreek</strong></p></td>
<td><p>希腊语</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbLangHebrew</strong></p></td>
<td><p>希伯来语</p></td>
</tr>
<tr class="even">
<td><p><strong>dbLangHungarian</strong></p></td>
<td><p>匈牙利语</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbLangIcelandic</strong></p></td>
<td><p>冰岛语</p></td>
</tr>
<tr class="even">
<td><p><strong>dbLangJapanese</strong></p></td>
<td><p>日语</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbLangKorean</strong></p></td>
<td><p>朝鲜语</p></td>
</tr>
<tr class="even">
<td><p><strong>dbLangNordic</strong></p></td>
<td><p>北欧语言（仅适用于 Microsoft Jet 数据库引擎 1.0 版）</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbLangNorwDan</strong></p></td>
<td><p>挪威语和丹麦语</p></td>
</tr>
<tr class="even">
<td><p><strong>dbLangPolish</strong></p></td>
<td><p>波兰语</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbLangSlovenian</strong></p></td>
<td><p>斯洛文尼亚语</p></td>
</tr>
<tr class="even">
<td><p><strong>dbLangSpanish</strong></p></td>
<td><p>传统西班牙语</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbLangSwedFin</strong></p></td>
<td><p>瑞典语和芬兰语</p></td>
</tr>
<tr class="even">
<td><p><strong>dbLangThai</strong></p></td>
<td><p>泰语</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbLangTurkish</strong></p></td>
<td><p>土耳其语</p></td>
</tr>
</tbody>
</table>


可以在 options 参数中使用下列一个或多个常量，以指定数据格式应使用的版本，以及是否对数据库加密。

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
<td><p><strong>dbEncrypt</strong></p></td>
<td><p>创建加密的数据库。</p></td>
</tr>
<tr class="even">
<td><p><strong>dbVersion10</strong></p></td>
<td><p>创建一个使用 Microsoft Jet 数据库引擎 1.0 版文件格式的数据库。</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbVersion11</strong></p></td>
<td><p>创建一个使用 Microsoft Jet 数据库引擎 1.1 版文件格式的数据库。</p></td>
</tr>
<tr class="even">
<td><p><strong>dbVersion20</strong></p></td>
<td><p>创建一个使用 Microsoft Jet 数据库引擎 2.0 版文件格式的数据库。</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbVersion30</strong></p></td>
<td><p>创建一个使用 Microsoft Jet 数据库引擎 3.0 版文件格式的数据库（与 3.5 版兼容）。</p></td>
</tr>
<tr class="even">
<td><p><strong>dbVersion40</strong></p></td>
<td><p>创建一个使用 Microsoft Jet 数据库引擎 4.0 版文件格式的数据库。</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbVersion120</strong></p></td>
<td><p>创建一个使用 Microsoft Access 数据库引擎 12.0 版文件格式的数据库。</p></td>
</tr>
</tbody>
</table>


如果省略加密常量， **CreateDatabase** 将创建一个不加密的数据库。

可使用 **CreateDatabase** 方法创建和打开一个新的空数据库，然后返回 **Database** 对象。必须通过使用其他 DAO 对象完成该数据库的结构和内容。如果要对现有的数据库制作一个部分副本或完整副本，可以使用 **[CompactDatabase](dbengine-compactdatabase-method-dao.md)** 方法制作一个能够自定义的副本。

