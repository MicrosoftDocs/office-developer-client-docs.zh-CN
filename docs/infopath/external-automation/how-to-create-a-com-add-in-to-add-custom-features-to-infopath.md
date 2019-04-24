---
title: 创建 COM 加载项以向 InfoPath 添加自定义功能
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
keywords:
- infopath 2007, 创建 com 加载项, InfoPath 2007, 添加自定义功能, com 加载项 [InfoPath 2007]
localization_priority: Normal
ms.assetid: af0b0bc9-20ef-4503-8b3b-8f2a97b671a2
description: 为了扩展表单编辑的用户体验，Microsoft InfoPath 支持 COM 加载项。 虽然在 InfoPath 中首次添加了对 COM 外接程序的支持, 但其他 office 应用程序 (如 microsoft office Word 和 microsoft office Excel) 自 office 2000 起支持的 com 加载项。
ms.openlocfilehash: f8dd16b161c4ea862cf3b15e56e26a2547c1fc4c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303785"
---
# <a name="create-a-com-add-in-to-add-custom-features-to-infopath"></a>创建 COM 加载项以向 InfoPath 添加自定义功能

为了扩展表单编辑的用户体验，Microsoft InfoPath 支持 COM 加载项。 虽然在 InfoPath 中首次添加了对 COM 外接程序的支持, 但其他 office 应用程序 (如 microsoft office Word 和 microsoft office Excel) 自 office 2000 起支持的 com 加载项。
  
InfoPath 中的 COM 外接程序支持可用于表单编辑环境。 无法使用 COM 加载项扩展表单设计环境。
  
## <a name="the-idtextensibility2-interface"></a>IDTExtensibility2 接口

InfoPath 编辑环境为**IDTExtensibility2**接口提供支持, 该接口必须由 COM 加载项的开发人员实现。 **IDTExtensibility2**是一个双接口对象, 提供了五个作为事件的方法在编辑环境中。 这些方法允许 COM 加载项响应下表中列出的环境启动和关闭条件。 
  
|**接口**|**说明**|
|:-----|:-----|
|**OnAddInsUpdate (ByVal custom () 作为 Variant)** <br/> |在环境中加载或卸载外接程序时发生。  <br/> |
|**OnBeginShutdown (ByVal custom () 作为 Variant)** <br/> |在环境关闭时发生。  <br/> |
|**OnConnection (byval Application as object, byval ConnectMode as ext_ConnectMode, byval AddInInst as Object, byval custom () as Variant)** <br/> |在环境中加载外接程序时发生。  <br/> |
|**OnDisconnection (byval RemoveMode As ext_DisconnectMode, byval custom () as Variant)** <br/> |当外接程序从环境中卸载时发生。  <br/> |
|**OnStartupComplete (ByVal custom () 作为 Variant)** <br/> |在环境已完成启动时发生。  <br/> |
   
## <a name="registering-com-add-ins"></a>注册 COM 加载项

所有 Office 应用程序 (包括 InfoPath) 都使用注册表列出 COM 加载项集合中的外接程序, 以存储连接状态, 并存储启动或需求加载信息。 对于 InfoPath COM 加载项, 每个加载项的名称显示在以下项下面:
  
`HKEY_CURRENT_USER\Software\Microsoft\Office\InfoPath\AddIns\`
  
对于安装供客户端计算机的每个用户使用的 COM 加载项, 该注册表项位于 HKLM 注册表配置单元中:
  
`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\InfoPath\AddIns\`
  
注册表项名称对应于加载项的**ProgIdAttribute** , 并包含以下值。 
  
|**Name**|**Type**|**说明**|
|:-----|:-----|:-----|
|**FriendlyName** <br/> |**String** <br/> |显示在 " **COM 加载项**" 对话框中并在 "**信任中心**" 的 "**加载项**" 页中列出的名称。  <br/> |
|**说明** <br/> |**字符串** <br/> |在**信任中心**中选择外接程序时显示的字符串。  <br/> |
|**LoadBehavior** <br/> |**DWORD** <br/> |指定 COM 加载项的加载方式。 该值可以是0、1、2、8和16的组合。 有关详细信息, 请参阅下表。  <br/> |
   
**LoadBehavior**的**DWORD**值应包含一个值, 该值描述 COM 加载项在编辑环境中的加载方式。 值可以是下表中的值, 也可以是表中的值的组合。 例如, 在 Visual Studio 2005 中创建的 COM 加载项将在应用程序启动时加载**LoadBehavior** "3", 并进行连接。 
  
|**Value**|**说明**|
|:-----|:-----|
|0  <br/> |被. 加载项在 " **COM 加载项**" 对话框中显示为 "非活动"。  <br/> |
|1  <br/> |连. 加载项在 " **COM 加载项**" 对话框中显示为 "活动"。  <br/> |
|双面  <br/> |启动时加载。 在主机应用程序启动时加载并连接加载项。  <br/> |
|utf-8  <br/> |按需加载。 加载项在主机应用程序需要时加载和连接, 例如, 当用户单击使用加载项中的功能的按钮时。  <br/> |
|位  <br/> |第一次运行时连接。 注册加载项后, 用户首次运行主机应用程序时, 将加载并连接加载项。  <br/> |
   
## <a name="creating-a-managed-com-add-in-with-visual-studio-2005-or-visual-studio-2008"></a>使用 visual studio 2005 或 visual studio 2008 创建托管 COM 加载项

若要使用 Microsoft Visual Studio 2005 或 Visual studio 2008 创建托管 COM 加载项, 请创建共享的加载项项目, 如下所示: 
  
1. 启动 Visual Studio。
    
2. 在“文件”**** 菜单上，单击“新建项目”****。
    
3. 在 "**新建项目**" 对话框的 "**项目类型**" 窗格中, 单击 "**其他项目类型**" 文件夹, 然后单击 "可**扩展性**"。
    
4. 在 "**模板**" 窗格中, 单击 "**共享加载项**"。
    
5. 在 "**名称**" 框中, 键入项目的名称。 
    
6. 在 "**位置**" 框中, 键入文件夹路径或单击 "**浏览**" 并选择文件夹路径, 然后单击 **"确定"**。 将显示 "**共享加载项" 向导**。 
    
7. 单击 "**共享加载项向导**" 中的 "**下一步**"。 将显示 "**选择编程语言**" 页面。 
    
8. 单击 "**使用 Visual Basic 创建外接程序**", 然后单击 "**下一步**"。 将显示 "**选择应用程序主机**" 页。 
    
9. 取消选中除**Microsoft InfoPath**之外的每个应用程序旁边的复选框, 然后单击 "**下一步**"。 将显示 "**输入名称和说明**" 页。 
    
10. 在 "**您的外接程序的名称是什么？** " 框中, 键入您的 COM 加载项的名称。 
    
11. 在 "**外接程序的说明是什么**" 框中, 键入 COM 加载项的说明, 然后单击 "**下一步**"。 将显示 "**选择外接加载项选项**" 页。 
    
12. 选中 "**我希望我的外接程序在主机应用程序加载时加载**", 而我的外接程序**应对安装它的计算机上的所有用户可用, 而不只是安装它的人**。 
    
13. 单击 "**下一步**" 查看**摘要**页, 然后单击 "**完成**"。
    
在 Visual Studio 中创建项目后, 您将在 "解决方案资源管理器" 窗口中看到两个项目。 第一个项目是 COM 加载项的项目;第二个项目是用于部署 COM 加载项的安装项目。 **共享加载项向导**仅插入对**Microsoft Office 14.0 对象库**的引用, 因此必须使用以下步骤插入对 InfoPath 对象库的引用:
  
1. 双击 **"我的项目**" 以显示加载项项目属性。 单击 "**引用**" 选项卡以显示自动添加到项目中的引用。 
    
2. 单击 "**添加**" 按钮以显示 "**添加引用**" 对话框。 
    
3. 在 " **COM** " 选项卡上, 双击 " **Microsoft"。 InfoPath 2.0 类型库**, 然后单击 **"确定"**。
    
4. 添加对**Microsoft InfoPath 3.0 类型库**的引用时, 还会添加对必须删除的三个程序集的引用: **ADODB**、 **MSHTML**和**MSXML2**。 在 "**解决方案资源管理器**" 中的 "**引用**" 下, 右键单击每个引用, 然后单击 "**删除**"。
    
## <a name="viewing-the-registry-settings"></a>查看注册表设置

若要查看在安装 COM 加载项时将创建的注册表设置, 请按照以下步骤操作:
  
1. 在 "**解决方案资源管理器**" 中右键单击安装项目的根节点, 单击 "**视图**", 然后单击 "**编辑**", 然后单击 "**注册表**"。
    
2. 在左侧窗格中, 单击加号以展开 " **HKEY_LOCAL_MACHINE**"、"**软件**"、" **Microsoft**"、" **InfoPath**" 和 " **AddIns**"。
    
3. 单击与共享的外接程序项目的**ProgID**相对应的名称。
    
若要更改这些属性中的任何属性, 请右键单击该属性, 单击 "**属性" 窗口**, 然后在 "**属性" 窗口**中更改 "**值**" 框。
  
## <a name="compiling-and-distributing-the-shared-add-in"></a>编译和分发共享加载项

若要在开发共享外接程序项目的计算机上编译托管 COM 加载项以进行测试, 请在 "解决方案资源管理器" 中右键单击共享外接程序项目的根节点, 然后单击 "生成"。 如果项目生成时没有任何错误, 则可以启动 InfoPath 编辑环境并开始使用托管 COM 加载项。 如果有一个 InfoPath 实例正在运行, 请在生成项目之前将其关闭。 可能还需要打开 "com 加载项" 对话框, 以验证 com 加载项是否已注册。 若要打开 "COM 加载项" 对话框, 请按照下列步骤操作:
  
1. 打开 InfoPath 编辑环境。 执行此操作最简单的方法是打开现有表单模板, 该模板将基于该表单模板创建新表单。
    
2. 单击 "**工具**" 菜单上的 "**信任中心**"。 
    
3. 单击左侧的 "**外接程序**" 类别。 
    
4. 在靠近 "**信任中心**" 对话框底部的 "**管理**" 部分中, 从列表中选择 " **COM 加载项**", 然后单击 "**转到**" 按钮。 
    
5. 在 " **COM 加载项**" 对话框中, 您将看到最近生成的外接程序的名称, 并且旁边应有一个复选框。 如果旁边没有复选框, 则 COM 加载项由于出现错误而无法加载, 这将在对话框的 "**加载行为**" 部分列出。 
    
若要编译托管 COM 加载项以供在开发共享外接程序项目的计算机以外的计算机上使用, 您必须执行其他步骤来保护您的代码。 有关保护共享的外接程序项目以在其他计算机上使用的信息, 请参阅以下三篇文章:
  
- [Office XP 中托管 COM 加载项的部署](https://go.microsoft.com/fwlink/?LinkID=73473)
  
- [使用 COM 加载项填充解决方案在 Office XP 中部署托管 COM 加载项](https://go.microsoft.com/fwlink/?LinkID=73474)
  
- [使用 COM 填充程序向导隔离 Office 扩展](https://go.microsoft.com/fwlink/?LinkID=73475)
  
> [!IMPORTANT]
> 不隔离 COM 加载项可能会导致内存泄漏和应用程序不稳定。 
  
> [!NOTE]
> 如果 .net Framework 或安装程序项目中的其他必需程序集尚未安装在目标计算机上, 则 .msi 文件可能无法正确安装。 此外, 您还不能分发 .msi 文件, 然后尝试安装 .msi 文件。 此外, 还必须将其他支持文件与 Visual Studio 生成的原始 .msi 文件分发在同一文件夹中。 
  
## <a name="coding-in-the-com-add-in"></a>COM 加载项中的编码

在 InfoPath 表单编辑环境中发生的应用程序事件可以由 COM 加载项捕获。 COM 加载项可以使用[ApplicationEvents](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.ApplicationEvents.aspx)对象的以下事件来响应用户操作: 
  
|**Event**|**Description**|
|:-----|:-----|
|[NewXDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.NewXDocument.aspx)事件  <br/> |新建表单时发生。  <br/> |
|[Quit](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.Quit.aspx)事件  <br/> |用户退出 InfoPath 时发生。  <br/> |
|[WindowActivate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.WindowActivate.aspx)事件  <br/> |在激活文档窗口时发生。  <br/> |
|[WindowDeactivate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.WindowDeactivate.aspx)事件  <br/> |在文档窗口成为非活动窗口时发生。  <br/> |
|[WindowSize](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.WindowSize.aspx)事件  <br/> |当调整任一文档窗口大小或移动该窗口时发生。  <br/> |
|[XDocumentBeforeClose](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentBeforeClose.aspx)事件  <br/> |在打开的文档即将关闭之前发生。  <br/> |
|[XDocumentBeforePrint](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentBeforePrint.aspx)事件  <br/> |在即将打印任一打开文档时发生。  <br/> |
|[XDocumentBeforeSave](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentBeforeSave.aspx)事件  <br/> |在即将保存任一打开文档时发生。  <br/> |
|[XDocumentChange](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentChange.aspx)事件  <br/> |新建表单、打开现有表单或另一个表单变为激活状态时发生。  <br/> |
|[XDocumentOpen](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentOpen.aspx)事件  <br/> |在打开文档时发生。  <br/> |
   
若要在 COM 加载项中捕获这些事件, 必须在**Connect**类中声明以下类级别变量: 
  
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

第一条线将外接程序接收到的通用 application**对象**转换为[_Application3](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._Application3.aspx)对象。 第二行将 **_Application3**对象 (由**InfoPathApplication**变量表示) 的[Events](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath._Application3.Events.aspx)属性转换为[ApplicationEvents](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.ApplicationEvents.aspx)对象。 
  
若要创建事件处理程序, 请从 visual Studio 窗口顶部的 "**类名**" 下拉框中选择 " **InfoPathApplicationEvents** ", 然后在可视对象顶部的 "**方法名称**" 下拉框中选择要处理的事件。Studio 窗口。 例如, 如果您需要控制何时保存窗体, 则处理**XDocumentBeforeSave**事件。 从 "**方法名称**" 下拉选项中选择 " **XDocumentBeforeSave** " 将自动插入以下过程: 
  
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

可以使用相同的方法, 由 COM 加载项处理**ApplicationEvents**对象的任何事件。 
  
## <a name="see-also"></a>另请参阅

- [创建 Microsoft Office 2000 COM 加载项](https://go.microsoft.com/fwlink/?LinkID=73468) 
- [使用 Visual Studio .net 创建 Office 托管 COM 加载项](https://go.microsoft.com/fwlink/?LinkID=73470)
- [使用 IDTExtensibility2 事件过程](https://go.microsoft.com/fwlink/?LinkID=73471)
- [使用 Visual Basic .net 生成 Office COM 加载项](https://go.microsoft.com/fwlink/?LinkID=73469)
- [使用 Visual c # .net 生成 Office COM 加载项](https://support.microsoft.com/en-us/help/302901/how-to-build-an-office-com-add-in-by-using-visual-c-net)
- [使用 Visual Studio 2005 Tools for Office System SE 创建 InfoPath 2007 外接程序](https://msdn.microsoft.com/library/bb968857%28office.12%29.aspx)

