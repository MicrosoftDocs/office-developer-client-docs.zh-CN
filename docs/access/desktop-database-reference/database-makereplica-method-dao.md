---
title: Database.MakeReplica 方法 (DAO)
TOCTitle: MakeReplica Method
ms:assetid: b6bf4982-0804-12ce-849f-d2b4ac2e48a5
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822413(v=office.15)
ms:contentKeyID: 48547286
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053371
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 45aa005b7c8337a4c5541ea7217cbdb520bb1725
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25997733"
---
# <a name="databasemakereplica-method-dao"></a>Database.MakeReplica 方法 (DAO)

**适用于**： Access 2013、 Office 2013

根据另一个数据库副本制作一个新的副本（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式*。MakeReplica （***路径名***，在***说明***中，***选项***）

*表达式*一个代表**Database**对象的变量。

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
<td><p><em>PathName</em></p></td>
<td><p>必需</p></td>
<td><p><strong>字符串</strong></p></td>
<td><p>新副本的路径和文件名。如果 replica 是一个现有的文件名，则会发生错误。</p></td>
</tr>
<tr class="even">
<td><p><em>说明</em></p></td>
<td><p>必需</p></td>
<td><p><strong>字符串</strong></p></td>
<td><p>一个 <strong>String</strong>，用于描述所创建的副本</p></td>
</tr>
<tr class="odd">
<td><p><em>Options</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>一个<strong><a href="replicatypeenum-enumeration-dao.md">ReplicaTypeEnum</a></strong>常量，指定要创建的副本的特征。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

新建部分副本的所有 **[ReplicaFilter](tabledef-replicafilter-property-dao.md)** 属性都将设置为 **False**，表示不会将任何数据放入表中。

## <a name="example"></a>示例

此函数使用 **MakeReplica** 方法创建现有设计母版的附加副本。 IntOptions 参数可以是组合的常量**dbRepMakeReadOnly**和**dbRepMakePartial**，也可以是 0。 例如，若要创建只读的部分副本，您应传递值**dbRepMakeReadOnly** + **dbRepMakePartial**作为 intOptions 的值。

```vb 
Function MakeAdditionalReplica(strReplicableDB As _ 
 String, strNewReplica As String, intOptions As _ 
 Integer) As Integer 
 
 Dim dbsTemp As Database 
 On Error GoTo ErrorHandler 
 
 Set dbsTemp = OpenDatabase(strReplicableDB) 
 
 ' If no options are passed to 
 ' MakeAdditionalReplica, omit the 
 ' options argument, which defaults to 
 ' a full, read/write replica. Otherwise, 
 ' use the value of intOptions. 
 
 If intOptions = 0 Then 
 dbsTemp.MakeReplica strNewReplica, _ 
 "Replica of " & strReplicableDB 
 Else 
 dbsTemp.MakeReplica strNewReplica, _ 
 "Replica of " & strReplicableDB, _ 
 intOptions 
 End If 
 
 dbsTemp.Close 
 
ErrorHandler: 
 Select Case Err 
 Case 0: 
 MakeAdditionalReplica = 0 
 Exit Function 
 Case Else: 
 MsgBox "Error " & Err & " : " & Error 
 MakeAdditionalReplica = Err 
 Exit Function 
 End Select 
 
End Function 
 
```

