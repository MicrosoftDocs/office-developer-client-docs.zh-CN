---
title: DBEngine.CompactDatabase 方法 (DAO)
TOCTitle: CompactDatabase Method
ms:assetid: 03f3a156-005a-4b71-81b0-598f326f7d42
ms:mtpsurl: https://msdn.microsoft.com/library/Ff844821(v=office.15)
ms:contentKeyID: 48542997
ms.date: 10/24/2016
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052936
f1_categories:
- Office.Version=v15
localization_priority: Priority
ms.openlocfilehash: b50cb0453df1fa357fbd0b089af2e74fdd4b4c1e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294335"
---
# <a name="dbenginecompactdatabase-method-dao"></a>DBEngine.CompactDatabase 方法 (DAO)

**适用于：** Access 2013 | Access 2016

复制并压缩关闭的数据库，使您可以选择更改其版本、整理顺序和加密设置。 （仅适用于 Microsoft Access 工作区。

> [!NOTE]
> 使用加密链接的表来执行操作、更新和 SQL 查询 [例如 SQL UPDATE 语句 (CurrentDb.Execute "UPDATE...")] 时，您必须提供加密密钥。 此外，链接的表有加密密钥的 19 字符限制。 请参阅本主题结尾的**加密链接的表**部分。

## <a name="syntax"></a>语法

*expression* .CompactDatabase(***SrcName***, ***DstName***, ***DstLocale***, ***Options***, ***password***)

*expression*一个返回 **DBEngine** 对象的表达式。

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
<td><p><em>SrcName</em></p></td>
<td><p>必需</p></td>
<td><p><strong>String</strong></p></td>
<td><p>识别现有的已关闭数据库。 可以是完整路径和文件名，例如 &quot;C:\db1.mdb&quot;。 如果文件名称有扩展名，必须指定。 如果网络支持的话，还可以指定网络路径，例如&quot;\\server1\share1\dir1\db1.mdb&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>DstName</em></p></td>
<td><p>必需</p></td>
<td><p><strong>String</strong></p></td>
<td><p>您要创建的压缩数据库的文件名（和路径）。 还可以指定网络路径。 不能使用此参数指定与 SrcName 相同的数据库文件。</p></td>
</tr>
<tr class="odd">
<td><p><em>DstLocale</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>指定用于创建 DstName 整理顺序的字符串表达式，如“备注”中指定。</p>
<ul>
<li><p>如果省略此参数，则 DstName 区域设置与 SrcName 相同。</p></li>
<li><p>还可以通过将密码字符串（以&quot;;pwd=&quot;开头）与 DstLocale 参数中的常量相连（例如 dbLangSpanish &amp; &quot;;pwd=NewPassword&quot;）创建 DstName 的密码。</p></li>
<li><p>如果要使用与 SrcName 相同的 DstLocale（默认值），但指定新密码，只需输入 DstLocale 的密码字符串：&quot;;pwd=NewPassword&quot;</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><em>选项</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>可选。一个常量或常量的组合，用于指示一个或多个选项（根据“说明”中的指定）。可通过对相应的常量求和来组合选项。</p></td>
</tr>
<tr class="odd">
<td><p><em>password</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>包含加密密钥的字符串表达式（若数据库加密）。 字符串&quot;; pwd =&quot;必须位于实际密码之前。 如果在 DstLocale 中包括密码设置，则忽略此设置。</p><p><strong>注释</strong>：这是已弃用的参数, 不支持 .ACCDB 格式。 要加密 .ACCDB 文件，请使用 "pwd =" 选项字符串。 使用混合大小写字母、数字和符号的强密码。 弱密码不混合使用这些元素。 例如，强密码：Y6dh!et5。 弱密码：House27。 请使用可以记住的强密码，这样就不必记录密码了。</p>
</td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

可以使用 DstLocale 参数的下列常量之一来指定文本字符串比较的**CollatingOrder**属性。

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

<br/>

可以在 options 参数中使用以下常量之一来指定在压缩数据库时对数据库进行加密还是解密。

> [!NOTE]
> 常量 dbEncrypt 和 dbDecrypt 已弃用，不支持 .ACCDB 文件格式。

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
<td><p>压缩时加密数据库。</p></td>
</tr>
<tr class="even">
<td><p><strong>dbDecrypt</strong></p></td>
<td><p>压缩操作时解密数据库。</p></td>
</tr>
</tbody>
</table>

<br/>

如果省略加密常量或同时包括 **dbDecrypt** 和 **dbEncrypt**，DstName 将与 SrcName 具有相同的加密。

可以在 options 参数中使用下列常量之一来指定压缩数据库的数据格式的版本。 此常量仅影响 DstName 的数据格式的版本，而不会影响任何 Microsoft Access 定义的对象（例如窗体和报表）的版本。

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
<td><p><strong>dbVersion10</strong></p></td>
<td><p>在压缩时创建一个使用 Microsoft Jet 数据库引擎 1.0 版文件格式的数据库。</p></td>
</tr>
<tr class="even">
<td><p><strong>dbVersion11</strong></p></td>
<td><p>在压缩时创建一个使用 Microsoft Jet 数据库引擎 1.1 版文件格式的数据库。</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbVersion20</strong></p></td>
<td><p>在压缩时创建一个使用 Microsoft Jet 数据库引擎 2.0 版文件格式的数据库。</p></td>
</tr>
<tr class="even">
<td><p><strong>dbVersion30</strong></p></td>
<td><p>在压缩时创建一个使用 Microsoft Jet 数据库引擎 3.0 版文件格式的数据库（与 3.5 版兼容）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbVersion40</strong></p></td>
<td><p>在压缩时创建一个使用 Microsoft Jet 数据库引擎 4.0 版文件格式的数据库。</p></td>
</tr>
<tr class="even">
<td><p><strong>dbVersion120</strong></p></td>
<td><p>创建一个压缩时使用 Microsoft Access 数据库引擎版本 12.0 文件格式的数据库。</p></td>
</tr>
</tbody>
</table>

<br/>

只能指定一个版本常量。 如果省略版本常量，DstName 将与 SrcName 具有相同的版本。 只能将 DstName 压缩为等于或高于 SrcName 版本的版本。

更改数据库中的数据时，数据库文件中会产生碎片，并使用多于所需量的磁盘空间。您可以定期使用 **CompactDatabase** 方法来压缩数据库，对数据库文件进行碎片整理。压缩的数据库通常更小且运行速度更快。在复制和压缩数据库时，还可以更改整理顺序、加密或数据格式的版本。

压缩 SrcName 之前，必须关闭它。 在多用户环境中，在您压缩 SrcName 时，其他用户不能打开它。 如果 SrcName 未关闭或者不能被独占使用，将会发生错误。

由于 **CompactDatabase** 会创建数据库的副本，因此您必须为原始数据库和复制数据库提供足够的磁盘空间。 如果没有足够的可用磁盘空间，压缩操作将失败。 DstName 复制数据库不必与 SrcName 位于同一个磁盘上。 在成功压缩数据库之后，可以删除 SrcName 文件，并将压缩的 DstName 文件重命名为原始文件名。

**CompactDatabase** 方法将所有数据和安全权限设置从由 SrcName 指定的数据库复制到由 DstName 指定的数据库。

> [!NOTE]
> 因为**CompactDatabase**方法不能转换 Microsoft Access 对象，所以请不要使用**CompactDatabase**来转换包含此类对象的数据库。

## <a name="encrypted-linked-tables"></a>加密链接的表

加密密码都依赖于正在使用的数据库的文件格式。 如果使用 Access 2003 (.mdb) 或早期数据库，会有一个密码来保护数据库，另一个单独密码来加密数据库。 对于 Access 2007 (.accdb) 和更高版本 (.mdb) 数据库，唯一选项就是使用同一个密码来加密和保护数据库，因为拥有两个单独密码的选项已删除。

> [!NOTE]
> 对于 Access 2007 (.accdb) 数据库，密码就是加密密钥

对于命令按钮可以使用以下示例 VBA 代码：

```vb
    Private Sub Command0_Click()
    
    Dim strSourcePath As String
    Dim strDestPath As String
    
    strSourcePath = "<path>\sourceDb.accdb"
    strDestPath = "<path>\destDb.accdb"
    
    DBEngine.CompactDatabase strSourcePath, strDestPath, dbLangGeneral & ";pwd=Access", dbVersion120, ";pwd=Access"
    
    Set CurrentDatabase = CurrentDb
    Set LinkedTableDef = CurrentDatabase.CreateTableDef 
    ("My Linked Table")
    LinkedTableDef.Connect = "MS Access;pwd=Access";database=" & strDestPath
    LinkedTableDef.RefreshLink
    
    
    MsgBox "Finished"
    
    End Sub 
```

<br/>

下面代码示例演示如何借助密码 （加密密钥） 来使用 CompactDatabase，然后将其链接到该压缩数据库的表中。 请注意必须提供密码。

```vb
    Private Sub CompactAndLink_Click() 
     
    Dim strSourcePath As String
    Dim strDestPath As String
    Dim strSourceTableName As String
    Dim strDestTableName As String
    Dim tdf As TableDef
     
    strSourcePath = "<path>\<database>.accdb"
    strDestPath = "<path>\<database>.accdb"
    strSourceTableName = "<table name in destination database>"
    strDestTableName = "<linked table name>"
     
    ' Compact source database into new destination database with encrypted password
    DBEngine.CompactDatabase strSourcePath, strDestPath, dbLangGeneral & ";pwd=Access", dbVersion120, ";pwd=Access"
     
    ' Link to one of the tables in the destination database
    ' Password must be provided in the Connect property
     
    Set CurrentDatabase = CurrentDb
    Set tdf = CurrentDatabase.CreateTableDef(strDestTableName)
       
        With tdf
            .Connect = ";pwd=Access" & ";DATABASE=" & strDestPath
            .SourceTableName = strSourceTableName
        End With
        
    CurrentDatabase.TableDefs.Append tdf
     
    MsgBox "Database compacted and encrypted password applied. Link to table also completed."
     
    End Sub
```
