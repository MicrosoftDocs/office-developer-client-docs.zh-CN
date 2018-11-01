---
title: DBEngine Object (DAO)
TOCTitle: DBEngine Object
ms:assetid: ceaeb505-615e-37ba-4633-27240ef8c5de
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834506(v=office.15)
ms:contentKeyID: 48547792
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 86c14ef0e9443965b2e80af329d4cca6023d1467
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25873627"
---
# <a name="dbengine-object-dao"></a>DBEngine Object (DAO)

**适用于**： Access 2013、 Office 2013

**DBEngine** 对象是数据访问对象 (DAO) 对象模型中的顶层对象。

## <a name="remarks"></a>注解

**DBEngine** 对象包含和控制 DAO 对象层次结构中的所有其他对象。不能创建额外的 **DBEngine** 对象，并且 **DBEngine** 对象不是任何集合的元素。

对于任何类型的数据库或连接，您可以进行下列操作：

  - 使用 **Version** 属性获取 DAO 版本号。

  - 使用 **LoginTimeout** 属性获取或设置开放式数据库连接 (ODBC) 登录超时时间，使用 **RegisterDatabase** 方法为 Microsoft Access 数据库引擎提供 ODBC 信息。

  - 使用 **DefaultPassword** 和 **DefaultUser** 属性为默认的 **Workspace** 对象设置用户标识和密码。

  - 使用 **CreateWorkspace** 方法创建新的 **Workspace** 对象。可使用可选参数替代 **DefaultType**、 **DefaultPassword** 和 **DefaultUser** 属性的设置。

  - 使用 **OpenDatabase** 方法在默认的 **Workspace** 中打开一个数据库，使用 **BeginTrans**、 **Commit** 和 **Rollback** 方法控制默认 **Workspace** 上的事务。

  - 使用 **Workspaces** 集合引用特定的 **Workspace** 对象。

  - 使用 **Errors** 集合检查数据访问错误详细信息。

只有将 DAO 与 Microsoft Access 数据库引擎一起使用时，才可以使用其他属性和方法。可以使用这些属性和方法来控制 Microsoft Access 数据库引擎，操作该数据库引擎的属性，以及对那些不是集合元素的临时对象执行任务。例如，您可以进行下列操作：

  - 使用 **CreateDatabase** 方法创建新的 Microsoft Access 数据库引擎 **Database** 对象。

  - 使用 **Idle** 方法使 Microsoft Access 数据库引擎能够完成任何待定的任务。

  - 使用 **CompactDatabase** 和 **RepairDatabase** 方法维护数据库文件。

  - 分别使用 **IniPath** 和 **SystemDB** 属性指定 Microsoft Access 数据库引擎的 Windows 注册表信息文件的位置和 Microsoft Access 工作组信息文件的位置。 **SetOption** 方法允许您替代 Microsoft Access 数据库引擎的 Windows 注册表设置。

更改 **DefaultType** 和 **IniPath** 属性设置之后，只有后续的 **Workspace** 对象才会反映这些更改。

要引用一个属于 **DBEngine** 对象的集合，或引用一个应用到该对象的方法或属性，请使用以下语法：

\[**DBEngine**。\]\[集合 |方法 |属性\]

## <a name="example"></a>示例

以下示例枚举 **DBEngine** 对象的集合。

```vb
    Sub DBEngineX() 
     
     Dim wrkLoop As Workspace 
     Dim prpLoop As Property 
     
     With DBEngine 
     Debug.Print "DBEngine Properties" 
     
     ' Enumerate Properties collection of DBEngine, 
     ' trapping for properties whose values are 
     ' invalid in this context. 
     For Each prpLoop In .Properties 
     On Error Resume Next 
     Debug.Print " " & prpLoop.Name & " = " _ 
     & prpLoop 
     On Error GoTo 0 
     Next prpLoop 
     
     Debug.Print "Workspaces collection of DBEngine" 
     
     ' Enumerate Workspaces collection of DBEngine. 
     For Each wrkLoop In .Workspaces 
     Debug.Print " " & wrkLoop.Name 
     
     ' Enumerate Properties collection of each 
     ' Workspace object, trapping for properties 
     ' whose values are invalid in this context. 
     For Each prpLoop In wrkLoop.Properties 
     On Error Resume Next 
     Debug.Print " " & prpLoop.Name & _ 
     " = " & prpLoop 
     On Error GoTo 0 
     Next prpLoop 
     
     Next wrkLoop 
     
     End With 
     
    End Sub
```
