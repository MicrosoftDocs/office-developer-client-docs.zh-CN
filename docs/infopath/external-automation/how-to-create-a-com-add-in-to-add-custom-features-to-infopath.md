---
title: 创建 COM 加载项自定义功能添加到 InfoPath
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
keywords:
- infopath 2007 中，创建 com 加载项，InfoPath 2007 添加自定义功能，COM 加载项 [InfoPath 2007]
localization_priority: Normal
ms.assetid: af0b0bc9-20ef-4503-8b3b-8f2a97b671a2
description: Microsoft InfoPath 支持 COM 加载项扩展窗体编辑的用户体验。 尽管支持的如 Microsoft Office Word 和 Microsoft Office Excel 具有 Office 2000 以来支持 COM 加载项首先 COM 加载项添加 InfoPath，其他 Office 应用程序中。
ms.openlocfilehash: 4c70dfb71cf7b15a0978b4567ffac02a8ba524c3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773882"
---
# <a name="create-a-com-add-in-to-add-custom-features-to-infopath"></a>创建 COM 加载项自定义功能添加到 InfoPath

Microsoft InfoPath 支持 COM 加载项扩展窗体编辑的用户体验。 尽管支持的如 Microsoft Office Word 和 Microsoft Office Excel 具有 Office 2000 以来支持 COM 加载项首先 COM 加载项添加 InfoPath，其他 Office 应用程序中。
  
可用于表单环境寄宿在 InfoPath 中的 COM 加载项支持。 无法使用 COM 加载项扩展窗体设计环境。
  
## <a name="the-idtextensibility2-interface"></a>IDTExtensibility2 接口

编辑环境提供支持**IDTExtensibility2**接口，必须由开发人员的 COM 加载宏**IDTExtensibility2**实现 InfoPath 是一个双接口对象，提供了五种用作事件的方法在编辑的环境。 COM 加载项以响应环境启动和关机条件下, 表中列出允许这些方法。 
  
|**接口**|**说明**|
|:-----|:-----|
|**OnAddInsUpdate (ByVal custom() 为 Variant)** <br/> |外接程序是加载或卸载环境中时，发生此事件。  <br/> |
|**OnBeginShutdown (ByVal custom() 为 Variant)** <br/> |正在关闭环境时，发生此事件。  <br/> |
|**OnConnection （ByVal 应用程序作为对象，ByVal ConnectMode As ext_ConnectMode，ByVal AddInInst As Object，ByVal custom() 为 Variant）** <br/> |加载在环境中的外接程序时，发生此事件。  <br/> |
|**OnDisconnection (ByVal 如果 RemoveMode As ext_DisconnectMode，ByVal custom() 为 Variant)** <br/> |外接程序是从环境中卸载时发生。  <br/> |
|**OnStartupComplete (ByVal custom() 为 Variant)** <br/> |当环境已完成启动时，发生此事件。  <br/> |
   
## <a name="registering-com-add-ins"></a>注册 COM 加载项

所有 Office 应用程序，包括 InfoPath 都使用到列表中的加载项的 COM 加载项集合，注册表用于存储连接状态，并存储启动或需求加载信息。 为 InfoPath COM 加载项，每一加载项的名称将出现在以下项下：
  
`HKEY_CURRENT_USER\Software\Microsoft\Office\InfoPath\AddIns\`
  
COM 加载项以供客户端计算机的每个用户安装注册表项位于 HKLM 注册表配置单元中：
  
`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\InfoPath\AddIns\`
  
注册表项名称对应于**ProgIdAttribute**的外接程序，并包含以下值。 
  
|**名称**|**类型**|**说明**|
|:-----|:-----|:-----|
|**FriendlyName** <br/> |**字符串** <br/> |显示在**COM 加载项**对话框和**加载项**页上的**信任中心**中列出的名称。  <br/> |
|**说明** <br/> |**字符串** <br/> |**信任中心**中所选加载项时显示的字符串。  <br/> |
|**LoadBehavior** <br/> |**DWORD** <br/> |指定 COM 加载项已加载的方式。 值可以是 0、 1、 2、 8 和 16 的组合。 请参阅下表的详细信息。  <br/> |
   
**LoadBehavior**的**DWORD**值应包含一个描述如何 COM 加载项加载在编辑环境中的值。 值可以是从下，表或表中的值的组合。 例如，COM 加载项创建 Visual Studio 2005 中将在应用程序启动具有"3"加载**LoadBehavior**和连接。 
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |断开连接。 外接程序显示作为**COM 加载项**对话框中的非活动。  <br/> |
|1  <br/> |连接。 外接程序显示为**COM 加载项**对话框中的活动。  <br/> |
|2  <br/> |在启动时加载。 加载项已加载并连接主机应用程序启动时。  <br/> |
|8  <br/> |按需加载。 加载项已加载并连接时主机应用程序需要它，例如，当用户单击按钮用外接程序中的功能。  <br/> |
|16  <br/> |连接第一次。 外接程序将加载和连接第一次用户运行外接程序注册后的主机应用程序。  <br/> |
   
## <a name="creating-a-managed-com-add-in-with-visual-studio-2005-or-visual-studio-2008"></a>使用 Visual Studio 2005 或 Visual Studio 2008 创建托管的 COM 加载项

若要创建托管的 COM 加载项程序使用 Microsoft Visual Studio 2005 或 Visual Studio 2008、 创建共享的加载项项目，如下所示： 
  
1. 启动 Visual Studio。
    
2. 在**文件**菜单中，单击**新建项目**。
    
3. 在**新建项目**对话框的**项目类型**窗格中，单击**其他项目类型**文件夹，然后单击**扩展性**。
    
4. 在**模板**窗格中，单击**共享外接程序**。
    
5. 在**名称**框中，键入项目的名称。 
    
6. 在**位置**框中，键入文件夹路径或单击**浏览**选择文件夹路径，然后单击**确定**。 将显示**共享外接程序向导**。 
    
7. 单击**下一步**中**共享外接程序向导**。 将出现**选择编程语言**页。 
    
8. 单击**使用 Visual Basic 加载项的创建**，然后单击**下一步**。 将显示**选择应用程序主机**页。 
    
9. 取消选中除**Microsoft InfoPath**，每个应用程序旁边的框，然后单击**下一步**。 将显示**输入名称和说明**页。 
    
10. 在**什么是外接程序的名称**框中，键入的 COM 加载项的名称。 
    
11. 在**什么是外接程序的说明**框中，键入 COM 加载项的说明，，然后单击**下一步**。 将出现**选择外接程序选项**页。 
    
12. 选中**我希望我的外接程序时加载主机应用程序加载**和**我的加载项应为可供安装在不只是用户安装此人的计算机的所有用户**框。 
    
13. 单击**下一步**以查看**摘要**页中，然后单击**完成时间**。
    
Visual studio 创建项目后，您将看到解决方案资源管理器窗口中的两个项目。 第一个项目是的 COM 加载项; 项目第二个项目是用于部署 COM 加载项的安装程序项目。 **共享外接程序向导**仅插入对**Microsoft Office 14.0 对象库**的引用，因此必须要插入到使用以下步骤 InfoPath 对象库的引用：
  
1. 双击**我的项目**显示外接程序项目属性。 单击**引用**选项卡以显示自动添加到项目的引用。 
    
2. 单击**添加**按钮以显示**添加引用**对话框。 
    
3. 在**COM**选项卡上，双击**Microsoft.InfoPath 2.0 类型库**，并单击**确定**。
    
4. 添加对**Microsoft InfoPath 3.0 类型库**的引用也将引用添加到三个程序集，则必须删除： **ADODB**、 **MSHTML**和**MSXML2**。 在**引用**下的**解决方案资源管理器**中，右键单击其中每个引用，，然后单击**删除**。
    
## <a name="viewing-the-registry-settings"></a>查看的注册表设置

若要查看安装 COM 加载项时将创建的注册表设置，请按照下列步骤：
  
1. 右键单击安装项目在**解决方案资源管理器**中的根节点，单击**视图**，然后为**编辑器**，然后单击**注册表**。
    
2. 在左侧窗格中，单击加号以展开**HKEY_LOCAL_MACHINE**、**软件**、 **Microsoft**、 **InfoPath**，然后**加载项**。
    
3. 单击共享外接程序项目的**ProgID**与对应的名称。
    
若要更改其中的任何属性，右键单击该属性，单击**属性窗口**中，更改**属性窗口**中的**值**框。
  
## <a name="compiling-and-distributing-the-shared-add-in"></a>编译和分发共享的加载项

若要用于测试开发了共享加载项项目的计算机上编译托管 COM 加载项，右键单击解决方案资源管理器中的共享外接程序项目的根节点，然后单击生成。 如果将生成项目，并且没有错误，您可以启动 InfoPath 编辑环境并开始使用托管 COM 加载项。 如果您有运行的 InfoPath 实例，它构建项目之前将其关闭。 可能还需要打开 COM 加载项对话框中，若要验证 COM 加载项已注册。 要打开 COM 加载项对话框，请执行以下步骤：
  
1. 打开 InfoPath 编辑环境。 执行此操作的最简单方法是打开现有的表单模板，将创建基于该表单模板的新表单。
    
2. 在**工具**菜单上，单击**信任中心**。 
    
3. 单击左侧的**加载项**类别。 
    
4. 在**信任中心**对话框的底部附近的**管理**部分中，从列表中选择**COM 加载项**，然后单击**转**按钮。 
    
5. 在**COM 加载项**对话框，您将看到您最近生成加载项的名称和应该有一个它旁边的复选框。 如果没有它旁边的复选框，COM 加载项无法加载由于错误，将在对话框中的**加载行为**部分中列出。 
    
编译托管 COM 加载项用于共享的加载项项目开发所在计算机以外的计算机上，您必须执行额外的步骤来保护您的代码。 保护共享加载项项目的其他计算机上使用的信息，请参阅下面的三篇文章：
  
- [部署的托管 COM 加载项中 Office XP](http://go.microsoft.com/fwlink/?LinkID=73473)
  
- [使用 COM 加载项填充码解决方案部署托管 COM 加载项中 Office XP](http://go.microsoft.com/fwlink/?LinkID=73474)
  
- [隔离 Office 扩展 COM 填充码向导](http://go.microsoft.com/fwlink/?LinkID=73475)
  
> [!IMPORTANT]
> 如果不隔离 COM 加载项可能会导致内存泄漏和应用程序不稳定。 
  
> [!NOTE]
> .NET Framework 或其他所需的程序集从安装项目尚未安装在目标计算机上，如果.msi 文件可能无法正确安装。 此外，您不能分发的.msi 文件，然后尝试安装该.msi 文件。 您还必须分发 Visual Studio 生成的原始.msi 文件所在的文件夹中的其他支持文件。 
  
## <a name="coding-in-the-com-add-in"></a>编码的 COM 加载项

InfoPath 表单编辑环境中发生的事件，可以捕获由 COM 加载项。 [ApplicationEvents](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.ApplicationEvents.aspx)对象的以下事件可由 COM 加载项，用于响应用户操作： 
  
|**事件**|**说明**|
|:-----|:-----|
|[NewXDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.NewXDocument.aspx)事件  <br/> |新建表单时发生。  <br/> |
|[退出](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.Quit.aspx)事件  <br/> |用户退出 InfoPath 时发生。  <br/> |
|[WindowActivate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.WindowActivate.aspx)事件  <br/> |在激活文档窗口时发生。  <br/> |
|[WindowDeactivate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.WindowDeactivate.aspx)事件  <br/> |在文档窗口成为非活动窗口时发生。  <br/> |
|[WindowSize](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.WindowSize.aspx)事件  <br/> |当调整任一文档窗口大小或移动该窗口时发生。  <br/> |
|[XDocumentBeforeClose](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentBeforeClose.aspx)事件  <br/> |在打开的文档即将关闭之前发生。  <br/> |
|[XDocumentBeforePrint](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentBeforePrint.aspx)事件  <br/> |在即将打印任一打开文档时发生。  <br/> |
|[XDocumentBeforeSave](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentBeforeSave.aspx)事件  <br/> |在即将保存任一打开文档时发生。  <br/> |
|[XDocumentChange](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentChange.aspx)事件  <br/> |新建表单、打开现有表单或另一个表单变为激活状态时发生。  <br/> |
|[XDocumentOpen](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentOpen.aspx)事件  <br/> |在打开文档时发生。  <br/> |
   
要捕获 COM 加载项中的这些事件，您必须在**Connect**类中声明的以下类级变量： 
  
```vb
InfoPathApplication = DirectCast( _
   application, Microsoft.Office.Interop.InfoPath._Application3)
InfoPathApplicationEvents = DirectCast( _
   InfoPathApplication.Events, _
   Microsoft.Office.Interop.InfoPath.ApplicationEvents)
```

```cs
InfoPathApplication =
   (Microsoft.Office.Interop.InfoPath._Application3)application;
InfoPathApplicationEvents =
   (Microsoft.Office.Interop.InfoPath.ApplicationEvents)
   InfoPathApplication.Events;
```

第一行投射**对象**接收的外接程序对[_Application3](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._Application3.aspx)对象的常规应用程序。 第二行将 （由**InfoPathApplication**变量） **_Application3**对象的[事件](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._Application3.Events.aspx)属性强制转换为[ApplicationEvents](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.ApplicationEvents.aspx)对象。 
  
要创建事件处理程序，请从**类名**下拉列表框顶部的 Visual Studio 窗口中，选择**InfoPathApplicationEvents** ，然后选择您想要在可视顶部的**方法名称**下拉列表框中处理的事件Studio 窗口。 例如，如果您需要控制保存表单时，您可以处理**XDocumentBeforeSave**事件。 自动从**方法名称**下拉列表中选择**XDocumentBeforeSave**插入下面的过程： 
  
```vb
Private Sub InfoPathApplicationEvents_XDocumentBeforeSave( _
   ByVal pDocument As Microsoft.Office.Interop.InfoPath._XDocument, _
   ByRef pfCancel As Boolean) _
   Handles InfoPathApplicationEvents.XDocumentBeforeSave
End Sub
```

```cs
private void InfoPathApplicationEvents_XDocumentBeforeSave(
   Microsoft.Office.Interop.InfoPath._XDocument pDocument, ref bool pfCancel)
{
}

```

任一**ApplicationEvents**对象的事件可以处理由 COM 加载项使用相同的方法。 
  
## <a name="see-also"></a>另请参阅

- [创建 Microsoft Office 2000 COM 加载项](http://go.microsoft.com/fwlink/?LinkID=73468) 
- [创建 Office 托管 COM 加载项使用 Visual Studio.NET](http://go.microsoft.com/fwlink/?LinkID=73470)
- [使用 IDTExtensibility2 事件过程](http://go.microsoft.com/fwlink/?LinkID=73471)
- [构建 Office COM 加载项与 Visual Basic.NET](http://go.microsoft.com/fwlink/?LinkID=73469)
- [构建 Office COM 加载项使用 Visual C#.NET](http://go.microsoft.com/fwlink/?LinkID=73472)
- [使用 Visual Studio 2005 Tools for the Office System SE 创建 InfoPath 2007 加载项](http://msdn.microsoft.com/en-us/library/bb968857%28office.12%29.aspx)

