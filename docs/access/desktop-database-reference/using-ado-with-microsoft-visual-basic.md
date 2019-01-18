---
title: 在 Microsoft Visual Basic 中使用 ADO
TOCTitle: Using ADO with Microsoft Visual Basic
ms:assetid: 5e0fb2ec-42aa-e181-386f-099607ac7400
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249338(v=office.15)
ms:contentKeyID: 48545130
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 26eaa93a1abbb3778a2735d50dd5022edb3023d9
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28705237"
---
# <a name="using-ado-with-microsoft-visual-basic"></a>在 Microsoft Visual Basic 中使用 ADO

**适用于**： Access 2013、 Office 2013

无论是使用 Visual Basic 还是使用 Visual Basic for Applications，在设置 ADO 项目和编写 ADO 代码时都类似。本主题介绍了如何在 Visual Basic 和 Visual Basic for Applications 中使用 ADO，并注明了二者之间的区别。

## <a name="referencing-the-ado-library"></a>引用 ADO 库

ADO 库必须由项目引用。

### <a name="to-reference-ado-from-microsoft-visual-basic"></a>从 Microsoft Visual Basic 中引用 ADO

1. 在 Visual Basic 中，从**项目**菜单中，选择**引用...**。

2. 从列表中选择**Microsoft ActiveX 数据对象 x.x 库**。 至少验证以下库也将被选中：
   
   - Visual Basic for Applications
   - Visual Basic 运行时对象和过程
   - Visual Basic 对象和过程
   - OLE 自动化

3. 单击“**确定**”。

在 Visual Basic for Applications（如使用 Microsoft Access 时）中可以同样轻松地使用 ADO。

### <a name="to-reference-ado-from-microsoft-access"></a>从 Microsoft Access 中引用 ADO

1. 在 Microsoft Access 中，选择或创建一个模块，从**数据库**窗口中的**模块**选项卡。

2. 从**工具**菜单中，选择**引用...**。

3. 从列表中选择**Microsoft ActiveX 数据对象 x.x 库**。 至少验证以下库也将被选中：
    
   - Visual Basic for Applications
   - Microsoft Access 11.0 对象库（或更高版本）

4. 单击“**确定**”。

## <a name="creating-ado-objects-in-visual-basic"></a>在 Visual Basic 中创建 ADO 对象

若要创建自动化变量以及该变量的对象实例，可以使用以下两个方法： **Dim** 或 **CreateObject** 。

### <a name="dim"></a>Dim

可以使用 **New** 关键字和 **Dim** ，在一个步骤中同时声明和实例化 ADO 对象：

```vb 
 
Dim conn As New ADODB.Connection 
```

或者，也可以将 **Dim** 语句声明和对象实例化分为两个步骤：

```vb 
 
Dim conn As ADODB.Connection 
Set conn = New ADODB.Connection 
```

> [!NOTE]
> 不需要明确用**Dim**语句，假定您正确引用 ADO 库项目中使用 progid ADODB。 不过，使用它可以确保不会与其他库产生命名冲突。
> 
> 例如，如果同一个项目中同时包括针对 ADO 和 DAO 的引用，那么，您可以使用限定符来指定在实例化 **Recordset** 对象时所使用的对象模型，如以下代码所示：  
> 
> `Dim adoRS As ADODB.Recordset`  
>   
> `Dim daoRS As DAO.Recordset`

### <a name="createobject"></a>CreateObject

采用 **CreateObject** 方法时，声明和对象实例化必须是两个独立的步骤：

```vb 
 
Dim conn1 
Set conn1 = CreateObject("ADODB.Connection") As Object 
```

用 **CreateObject** 实例化的对象是后期绑定的，这表明这些对象不是强类型的，且命令行完成被禁用。不过，允许您在项目中跳过对 ADO 库的引用，并实例化对象的特定版本。例如：

```vb 
 
Set conn1 = CreateObject("ADODB.Connection.2.0") As Object 
```

您也可以通过专门创建一个针对 ADO 版本 2.0 类型库的引用并创建对象来完成此操作。

用 **CreateObject** 方法实例化对象通常要比用 **Dim** 语句慢。

## <a name="handling-events"></a>处理事件

若要处理 ADO 事件在 Microsoft Visual Basic 中，您必须声明模块级变量使用**WithEvents**关键字。 该变量可以只声明为类模块的一部分，但必须在模块级进行声明。 处理 ADO 事件的更完整讨论，请参阅[第 7 章： 处理 ADO 事件](chapter-7-handling-ado-events.md)。

## <a name="visual-basic-examples"></a>Visual Basic 示例

ADO 文档中附带了许多 Visual Basic 示例。 有关详细信息，请参阅[Microsoft Visual Basic 中的 ADO 代码示例](ado-code-examples-in-microsoft-visual-basic.md)。

