---
title: DBEngine.CreateWorkspace 方法 (DAO)
TOCTitle: CreateWorkspace Method
ms:assetid: a7d73771-9420-0448-99e6-d6c4aa78683a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821374(v=office.15)
ms:contentKeyID: 48546888
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052966
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 9cd84b6b5441edda2042ce0a63ae25b2cf399bd2
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28699882"
---
# <a name="dbenginecreateworkspace-method-dao"></a>DBEngine.CreateWorkspace 方法 (DAO)

**适用于**： Access 2013、 Office 2013

创建新的 **[Workspace](workspace-object-dao.md)** 对象。

## <a name="syntax"></a>语法

*表达式*。CreateWorkspace （***名称***、***用户名***、***密码***、 ***UseType***）

*表达式*一个代表**DBEngine**对象的变量。

## <a name="parameters"></a>Parameters

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Name</p></th>
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
<td><p>一个 <strong>String</strong>，对新的 <strong>Workspace</strong> 对象进行唯一命名。有关有效 <strong>Workspace</strong> 名称的详细信息，请参阅 <strong><a href="connection-name-property-dao.md">Name</a></strong> 属性。</p></td>
</tr>
<tr class="even">
<td><p><em>UserName</em></p></td>
<td><p>必需</p></td>
<td><p><strong>String</strong></p></td>
<td><p>一个 <strong>String</strong> 类型的值，用于标识新的 <strong>Workspace</strong> 对象的所有者。有关详细信息，请参阅 <strong>UserName</strong> 属性。</p></td>
</tr>
<tr class="odd">
<td><p><em>Password</em></p></td>
<td><p>必需</p></td>
<td><p><strong>String</strong></p></td>
<td><p>包含新的<strong>Workspace</strong>对象的密码的<strong>字符串</strong>。 密码长度最多为 20 个字符，并且可以包括除 ASCII 字符 0 (null) 的任何字符。</p>
<p><strong>注意</strong>： 使用合并和小写字母、 数字和符号的强密码。 弱密码不混合使用这些元素。 例如，强密码：Y6dh!et5。 弱密码：House27。 请使用可以记住的强密码，这样就不必记录密码了。</p>
</td>
</tr>
<tr class="even">
<td><p><em>UseType</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p><strong><a href="workspacetypeenum-enumeration-dao.md">WorkspaceTypeEnum</a></strong>值之一。</p>
<p><strong>注意</strong>： Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</p>
</td>
</tr>
</tbody>
</table>


## <a name="return-value"></a>返回值

Workspace

## <a name="remarks"></a>注解

一旦使用 **CreateWorkspace** 方法来创建新的 **Workspace** 对象，将启动一个 **Workspace** 会话，并且您可以在应用程序中引用该 **Workspace** 对象。

**Workspace** 对象不是永久性的，不能保存到磁盘中。一旦创建了 **Workspace** 对象，就不能改动此对象的任何属性设置，但在将 **Workspace** 对象追加到 [**Workspaces**](workspaces-collection-dao.md) 集合之前，可以修改 **Name** 属性。

您不必将新的 **Workspace** 对象追加到集合就可以使用该对象。仅当需要通过 **Workspaces** 集合引用新创建的 **Workspace** 对象时，才需要追加该对象。

要从 **Workspaces** 集合中删除 **Workspace** 对象，请关闭所有打开的数据库和连接，然后对 [Workspace](connection-close-method-dao.md) 对象使用 ****Close**** 方法。

## <a name="example"></a>示例

以下示例使用 **CreateWorkspace** 方法创建 Microsoft Access 工作区，并随后列出该工作区的属性。

```vb 
Sub CreateWorkspaceX() 
 
   Dim wrkAcc As Workspace 
   Dim wrkLoop As Workspace 
   Dim prpLoop As Property 
 
   DefaultType = dbUseJet 
   ' Create an unnamed Workspace object of the type  
   ' specified by the DefaultType property of DBEngine  
   ' (dbUseJet). 
   Set wrkAcc = CreateWorkspace("", "admin", "") 
 
   ' Enumerate Workspaces collection. 
   Debug.Print "Workspace objects in Workspaces collection:" 
   For Each wrkLoop In Workspaces 
      Debug.Print "  " & wrkLoop.Name 
   Next wrkLoop 
 
   With wrkAcc 
      ' Enumerate Properties collection of Microsoft Access  
      ' workspace. 
      Debug.Print _ 
         "Properties of unnamed Microsoft Access workspace" 
      On Error Resume Next 
      For Each prpLoop In .Properties 
         Debug.Print "  " & prpLoop.Name & " = " & prpLoop 
      Next prpLoop 
      On Error GoTo 0 
   End With 
 
   wrkAcc.Close 
 
End Sub 
 
```

