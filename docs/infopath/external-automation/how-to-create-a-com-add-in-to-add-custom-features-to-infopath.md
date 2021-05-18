---
title: 创建 COM 加载项以将自定义功能添加到 InfoPath
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
keywords:
- infopath 2007， creating com add-ins，InfoPath 2007， adding custom features，COM add-ins [InfoPath 2007]
localization_priority: Normal
ms.assetid: af0b0bc9-20ef-4503-8b3b-8f2a97b671a2
description: 为了扩展表单编辑的用户体验，Microsoft InfoPath 支持 COM 加载项。 尽管首先在 InfoPath 中添加了对 COM 加载项的支持，但自 2000 Office 以来，其他 Office 应用程序（如 Microsoft Office Word 和 Microsoft Office Excel）也支持 COM 加载项。
ms.openlocfilehash: f8dd16b161c4ea862cf3b15e56e26a2547c1fc4c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303785"
---
# <a name="create-a-com-add-in-to-add-custom-features-to-infopath"></a>创建 COM 加载项以将自定义功能添加到 InfoPath

为了扩展表单编辑的用户体验，Microsoft InfoPath 支持 COM 加载项。 尽管首先在 InfoPath 中添加了对 COM 加载项的支持，但自 2000 Office 以来，其他 Office 应用程序（如 Microsoft Office Word 和 Microsoft Office Excel）也支持 COM 加载项。
  
InfoPath 中的 COM 加载项支持适用于表单编辑环境。 无法使用 COM 加载项扩展表单设计环境。
  
## <a name="the-idtextensibility2-interface"></a>IDTExtensibility2 接口

InfoPath 编辑环境支持 **IDTExtensibility2** 接口，该接口必须由 COM 加载项的开发人员实现。 **IDTExtensibility2** 是一个双接口对象，提供五个方法，这些方法在编辑环境中充当事件。 这些方法允许 COM 加载项响应环境启动和关闭条件，如下表所列。 
  
|**接口**|**说明**|
|:-----|:-----|
|**OnAddInsUpdate (ByVal 自定义 () As Variant)** <br/> |在环境中加载或卸载加载项时发生。  <br/> |
|**OnBeginShutdown (ByVal 自定义 () 作为变量)** <br/> |在关闭环境时发生。  <br/> |
|**OnConnection (ByVal Application As Object， ByVal ConnectMode As ext_ConnectMode， ByVal AddInInst As Object， ByVal custom () As Variant)** <br/> |在环境中加载加载项时发生。  <br/> |
|**OnDisconnection (ByVal RemoveMode As ext_DisconnectMode， ByVal custom () As Variant)** <br/> |从环境中卸载外接程序时发生。  <br/> |
|**OnStartupComplete (ByVal 自定义 () 作为变量)** <br/> |在环境完成启动时发生。  <br/> |
   
## <a name="registering-com-add-ins"></a>注册 COM 加载项

所有 Office 应用程序（包括 InfoPath）都使用注册表在 COM Add-Ins 集合中列出加载项，存储连接状态，并存储启动或需求加载信息。 对于 InfoPath COM 加载项，每个加载项的名称都显示在以下项下：
  
`HKEY_CURRENT_USER\Software\Microsoft\Office\InfoPath\AddIns\`
  
对于已安装供客户端计算机的每个用户使用的 COM 加载项，注册表项位于 HKLM 注册表配置单元中：
  
`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\InfoPath\AddIns\`
  
注册表项名称对应于加载项的 **ProgIdAttribute，** 并包含以下值。 
  
|**名称**|**类型**|**说明**|
|:-----|:-----|:-----|
|**FriendlyName** <br/> |**String** <br/> |显示在 **"COM** 加载项"对话框中，并列在信任中心的"加载项"页 **中的名称**。   <br/> |
|**说明** <br/> |**字符串** <br/> |在信任中心选择加载项时显示的 **字符串**。  <br/> |
|**LoadBehavior** <br/> |**DWORD** <br/> |指定加载 COM 加载项的方式。 该值可以是 0、1、2、8 和 16 的组合。 有关详细信息，请参阅下表。  <br/> |
   
**LoadBehavior** 的 **DWORD** 值应包含一个值，该值描述 COM 加载项在编辑环境中如何加载。 该值可以是下表中的值，也可以来自该表的值的组合。 例如，在 Visual Studio 2005 中创建的 COM 加载项将在应用程序启动时加载 **LoadBehavior"3"** 并连接。 
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |已断开连接。 加载项在"COM 加载项"对话框中 **显示为"非活动** "。  <br/> |
|1  <br/> |已连接。 加载项在"COM 加载项"对话框中 **显示为"活动** "。  <br/> |
|2  <br/> |启动时加载。 主机应用程序启动时加载并连接加载项。  <br/> |
|8   <br/> |按需加载。 当主机应用程序需要加载项时（例如，当用户单击使用加载项中的功能的按钮时）加载并连接加载项。  <br/> |
|16   <br/> |第一次运行时连接。 注册外接程序后，用户首次运行主机应用程序时，将加载并连接外接程序。  <br/> |
   
## <a name="creating-a-managed-com-add-in-with-visual-studio-2005-or-visual-studio-2008"></a>使用 Visual Studio 2005 或 Visual Studio 2008 创建托管 COM 加载项

若要使用 Microsoft Visual Studio 2005 或 Visual Studio 2008 创建托管 COM Add-In项目，如下所示： 
  
1. 启动 Visual Studio。
    
2. 在“文件”菜单上，单击“新建项目”。
    
3. In the **Project Types** pane of the **New Project** dialog box， click the **Other Projects Types** folder， and then click **Extensibility**.
    
4. 在 **"模板"窗格中**，单击"**共享加载项"。**
    
5. 在 **"名称** "框中，键入项目的名称。 
    
6. 在"**位置"** 框中，键入文件夹路径 **或单击"** 浏览"并选择文件夹路径，然后单击"确定 **"。** 将显示 **"共享外接程序向导** "。 
    
7. 单击 **共享** 加载项 **向导中的"下一步"。** 将显示 **"选择编程语言"** 页。 
    
8. 单击 **"使用加载项创建Visual Basic"，** 然后单击"下一 **步"。** 将显示 **"选择应用程序主机"** 页。 
    
9. 取消选中每个应用程序 **（Microsoft InfoPath** 除外）旁边的框，然后单击"下一步 **"。** 将显示 **"输入名称和说明"** 页。 
    
10. 在 **"什么是加载项名称"框中** ，键入 COM 加载项的名称。 
    
11. 在 **"什么是加载项** 说明"框中，键入 COM 加载项的说明，然后单击"下一步 **"。** 将显示 **"Add-In选项"** 页。 
    
12. 选中 **"我希望在加载主机** 应用程序时加载我的外接程序"和"我的外接程序"应可供安装它的计算机的所有用户使用，而不只是将其安装在框中。 
    
13. 单击 **"下** 一步"**查看"摘要"** 页，然后单击"完成 **"。**
    
项目由项目创建Visual Studio，您将在"解决方案资源管理器"窗口中看到两个项目。 第一个项目是 COM 加载项的项目;第二个项目是一个部署 COM 加载项的安装项目。 **共享外接程序向导** 仅插入对 **Microsoft Office 14.0** 对象库的引用，因此有必要使用以下步骤插入对 InfoPath 对象库的引用：
  
1. 双击"**我的Project"** 显示外接程序项目属性。 单击" **引用** "选项卡以显示自动添加到项目中的引用。 
    
2. 单击" **添加** "按钮以显示" **添加引用** "对话框。 
    
3. 在 **"COM"** 选项卡上，双击 **"Microsoft.InfoPath 2.0 类型库"，** 然后单击"确定 **"。**
    
4. 添加对 Microsoft **InfoPath 3.0** 类型库的引用也会添加对必须删除的三个程序集的引用 **：ADODB、MSHTML** 和 **MSXML2。**  在 **"解决方案资源管理器****"中的**"引用"下，右键单击其中每个引用，然后单击"删除 **"。**
    
## <a name="viewing-the-registry-settings"></a>查看注册表设置

若要查看安装 COM 加载项时将创建的注册表设置，请按照以下步骤操作：
  
1. 右键单击"解决方案资源管理器"中安装程序项目的根节点，单击"查看"，再单击"**编辑器****"，然后单击"注册表"。**
    
2. 在左侧窗格中，单击加号以展开 **HKEY_LOCAL_MACHINE、Software、Microsoft、InfoPath** 和 **AddIns。**  
    
3. 单击与共享加载项项目的 **ProgID 对应的名称**。
    
若要更改其中任何属性，请右键单击该属性，单击"属性窗口"，然后更改"属性窗口"中的"值 **"框**。
  
## <a name="compiling-and-distributing-the-shared-add-in"></a>编译和分发共享Add-In

若要编译托管 COM 加载项以在开发共享 Add-In 项目的计算机上进行测试，请在"解决方案资源管理器"中右键单击"共享 Add-In"项目的根节点，然后单击"生成"。 如果生成项目时没有出现错误，您可以启动 InfoPath 编辑环境并开始使用托管 COM 加载项。 如果正在运行 InfoPath 实例，则先关闭它，然后再生成项目。 可能还需要打开"COM 加载项"对话框来验证 COM 加载项是否注册。 若要打开"COM 加载项"对话框，请按照以下步骤操作：
  
1. 打开 InfoPath 编辑环境。 执行此操作的最简单方法是打开现有 表单模板，这将基于该表单创建一表单模板。
    
2. 单击 **"工具"菜单** 上的" **信任中心** "。 
    
3. 单击 **左侧的"** 加载项"类别。 
    
4. 在"**信任** 中心"对话框底部附近的"管理"部分，从列表中选择 **"COM** 加载项"，然后单击"开始 **"** 按钮。 
    
5. 在 **"COM 加载项** "对话框中，你将看到最近构建的加载项的名称，旁边应该有一个复选框。 如果旁边没有复选框，则 COM 加载项因错误而无法加载，该错误将在对话框的"加载行为"部分列出。  
    
若要编译托管 COM 加载项，以用于开发共享 Add-In 项目的计算机，必须执行其他步骤以确保代码安全。 有关保护共享Add-In项目以用于其他计算机的信息，请参阅以下三篇文章：
  
- [在 Office XP 中Add-Ins COM Office](https://go.microsoft.com/fwlink/?LinkID=73473)
  
- [使用 COM 加载项填充程序解决方案在 OFFICE XP 中部署托管 COM 加载项](https://go.microsoft.com/fwlink/?LinkID=73474)
  
- [使用 COM 填充Office隔离扩展](https://go.microsoft.com/fwlink/?LinkID=73475)
  
> [!IMPORTANT]
> 不隔离 COM 加载项可能会导致内存泄漏和应用程序不稳定。 
  
> [!NOTE]
> 如果.NET Framework安装项目中的程序集或其他所需程序集尚未安装在目标计算机上，.msi文件可能无法正确安装。 此外，无法分发.msi文件，然后尝试安装.msi文件。 还必须将其他支持文件分发到由 Visual Studio 生成的原始 .msi 文件夹中。 
  
## <a name="coding-in-the-com-add-in"></a>COM 加载项中的编码

COM 加载项可以捕获 InfoPath 表单编辑环境中发生的应用程序事件。 COM 加载项可以使用 [ApplicationEvents](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.ApplicationEvents.aspx) 对象的以下事件来响应用户操作： 
  
|**Event**|**说明**|
|:-----|:-----|
|[NewXDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.NewXDocument.aspx) 事件  <br/> |新建表单时发生。  <br/> |
|[Quit](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.Quit.aspx) 事件  <br/> |用户退出 InfoPath 时发生。  <br/> |
|[WindowActivate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.WindowActivate.aspx) 事件  <br/> |在激活文档窗口时发生。  <br/> |
|[WindowDeactivate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.WindowDeactivate.aspx) 事件  <br/> |在文档窗口成为非活动窗口时发生。  <br/> |
|[WindowSize](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.WindowSize.aspx) 事件  <br/> |当调整任一文档窗口大小或移动该窗口时发生。  <br/> |
|[XDocumentBeforeClose](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentBeforeClose.aspx) 事件  <br/> |在打开的文档即将关闭之前发生。  <br/> |
|[XDocumentBeforePrint](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentBeforePrint.aspx) 事件  <br/> |在即将打印任一打开文档时发生。  <br/> |
|[XDocumentBeforeSave](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentBeforeSave.aspx) 事件  <br/> |在即将保存任一打开文档时发生。  <br/> |
|[XDocumentChange](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentChange.aspx) 事件  <br/> |新建表单、打开现有表单或另一个表单变为激活状态时发生。  <br/> |
|[XDocumentOpen](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentOpen.aspx) 事件  <br/> |在打开文档时发生。  <br/> |
   
若要在 COM 加载项中捕获这些事件，必须在 连接 类 **中声明以下类级别** 变量： 
  
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

第一行将加载项收到的通用应用程序 **对象** 强制转换到 _Application3 [对象。](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._Application3.aspx) 第二行将 **_Application3** 对象的 [Events](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._Application3.Events.aspx) (由 **InfoPathApplication** 变量) [ApplicationEvents](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.ApplicationEvents.aspx)对象。 
  
若要创建事件处理程序，请从 Visual Studio 窗口顶部的"类名称"下拉框中选择 **InfoPathApplicationEvents，** 然后在 Visual Studio 窗口顶部的"方法名称"下拉框中选择要处理的事件。 例如，如果需要控制窗体保存时间，可以处理 **XDocumentBeforeSave** 事件。 从 **"方法名称"下拉列表中选择"XDocumentBeforeSave"** 将自动插入以下过程：  
  
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

**ApplicationEvents** 对象的任何事件都可以通过 COM 加载项使用相同的方法进行处理。 
  
## <a name="see-also"></a>另请参阅

- [创建 Microsoft Office 2000 COM 加载项](https://go.microsoft.com/fwlink/?LinkID=73468) 
- [使用 .NET Office托管 COM Add-Ins Visual Studio托管 COM 应用程序](https://go.microsoft.com/fwlink/?LinkID=73470)
- [使用 IDTExtensibility2 事件过程](https://go.microsoft.com/fwlink/?LinkID=73471)
- [使用 .NET Office COM 加载项Visual Basic加载项](https://go.microsoft.com/fwlink/?LinkID=73469)
- [使用 Visual Office .NET 生成 C# COM 加载项](https://support.microsoft.com/en-us/help/302901/how-to-build-an-office-com-add-in-by-using-visual-c-net)
- [使用 Add-Ins System Visual Studio 的 Visual Studio 2005 工具创建 InfoPath 2007 Office 标准版](https://msdn.microsoft.com/library/bb968857%28office.12%29.aspx)

