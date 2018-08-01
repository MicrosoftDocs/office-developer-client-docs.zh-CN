---
title: 演练： 创建和调试使用 InfoPath 对象模型的基本表单模板
manager: soliver
ms.date: 01/13/2015
ms.audience: Developer
keywords:
- form templates [infopath 2007], walkthroughs,form templates [InfoPath 2007], creating InfoPath 2003-compatible,InfoPath 2003-compatible form templates, walkthroughs
localization_priority: Normal
ms.assetid: 7658705f-c062-49a1-bea6-837737df2425
description: 本主题演练如何创建基本 InfoPath 托管代码表单模板，该模板用来处理由 Microsoft.Office.Interop.InfoPath.SemiTrust 命名空间提供的与 InfoPath 2003 兼容对象模型。
ms.openlocfilehash: 3939cfcfdf2a8683fe614c5f49cc8b2719484ff7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774088"
---
# <a name="walkthrough-create-and-debug-a-basic-form-template-using-the-infopath-object-model"></a>演练： 创建和调试使用 InfoPath 对象模型的基本表单模板

本主题演练如何创建基本 InfoPath 托管代码表单模板，该模板用来处理由 [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) 命名空间提供的与 InfoPath 2003 兼容对象模型。 
  
## <a name="hello-world"></a>Hello World

在下面的示例中，您将了解如何通过使用 InfoPath 2003 兼容对象模型的 [Alert](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.Alert.aspx) 方法来显示简单的警告对话框。 
  
### <a name="create-a-new-infopath-form-template-that-works-with-the-infopath-2003-compatible-object-model"></a>新建使用 InfoPath 2003 兼容对象模型的 InfoPath 表单模板

1. 创建新的表单模板使用 InfoPath 2003 兼容对象模型，[创建一个表单模板使用 InfoPath 2003 对象模型](how-to-create-a-form-template-using-the-infopath-2003-object-model.md)中所述。
    
2. 将该表单模板项目命名为 HelloWorld 并保存它。 
    
   项目系统会创建代码文件和项目文件，然后在 InfoPath 设计模式下打开一个空白的表单模板。现在可以添加事件处理程序了。
    
### <a name="add-a-button-with-an-onclick-event-handler"></a>添加包含 OnClick 事件处理程序的按钮

1. 在“主页”**** 选项卡的“控件”**** 部分，单击“按钮”**** 控件以将其插入视图中。 
    
2. 右键单击该控件，然后单击“按钮属性”****。
    
3. **标签**更改为 Alert。
    
4. 将**ID**更改为 AlertID。
    
5. 单击“编辑表单代码”****。
    
   此时会创建 [OnClick](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._ButtonEventSink_Event.OnClick.aspx) 事件的事件处理程序框架，同时焦点将移至 Visual Studio 2008 中的代码编辑器。 使用事件处理程序的详细信息，请参阅[添加事件处理程序使用的 InfoPath 2003 对象模型](how-to-add-an-event-handler-using-the-infopath-2003-object-model.md)。 
    
   现在可以向该按钮的事件处理程序中添加表单代码了。
    
### <a name="add-form-code-to-the-event-handler"></a>向事件处理程序中添加表单代码

1. 在 **OnClick** 事件处理程序中，键入下面的代码： 
    
   ```cs
    thisXDocument.UI.Alert("Hello World!");
   ```

   ```vb
    thisXDocument.UI.Alert("Hello World!")
   ```

   请注意，在代码行中每键入一个句点之后，都会显示一个 Microsoft IntelliSense 下拉列表。整个事件处理程序看上去应当如下所示：
    
   ```cs
    [InfoPathEventHandler(MatchPath="AlertID", EventType=InfoPathEventType.OnClick)]
    public void AlertID_OnClick(DocActionEvent e)
    {
        thisXDocument.UI.Alert("Hello World!");
    }
   ```

   ```vb
    <InfoPathEventHandler(MatchPath:="AlertID", EventType:=InfoPathEventType.OnClick)>
    Public Sub AlertID_OnClick(ByVal e As DocActionEvent)
        thisXDocument.UI.Alert("Hello World!")
    End Sub
   ```

   > [!NOTE]
   > [!注释] 除了 **Alert** 方法，还可以使用 **System.Windows.Forms** 命名空间的 **MessageBox.Show** 方法来显示消息框。为此，必须添加一个对 System.Windows.Forms 程序集的引用，在代码文件开头的指令中添加  `using System.Windows.Forms;` 或  `Imports System.Windows.Forms`，然后键入一行如下所示的代码： `MessageBox.Show("Hello World!); or MessageBox.Show("Hello World!)`
  
2. 切换到 InfoPath 设计模式窗口，然后单击“主页”**** 选项卡上的“预览”**** 按钮。 
    
3. 在“预览”**** 窗口中，单击“Alert”**** 按钮。 
    
   将显示一个消息框，其中包含"Hello World!"文本。
    
   下一个过程演示如何向表单代码中添加调试断点。
    
### <a name="debug-form-code"></a>调试表单代码

1. 在代码编辑器中，单击该行左侧的灰条：
    
   ```cs
    thisXDocument.UI.Alert("Hello World!");
   ```

   ```vb
    thisXDocument.UI.Alert("Hello World!")
   ```

   将显示一个红色圆圈，并且该代码行突出显示，指示运行时将在表单代码中的此断点处暂停。
    
2. 在“调试”**** 菜单上，单击“启动调试”****（或按 F5）。 
    
3. 在 InfoPath 的“预览”**** 窗口中，单击“Alert”**** 按钮。 
    
   代码编辑器将获得焦点，并且断点行突出显示。
    
4. 在“调试”**** 菜单上，单击“逐步执行”****（或按 Shift+F8）以继续逐步执行代码。 
    
   将执行 **Alert** 方法代码，并在 InfoPath 的“预览”**** 窗口中显示“Hello World!”警告。 
    
## <a name="getting-the-current-users-name"></a>获取当前用户的名称

通过使用 .NET Framework 类，可以访问不便通过脚本使用的功能。在此示例中，您将了解如何使用 .NET Framework 类来检索当前用户的名称。
  
### <a name="add-an-onload-event-handler"></a>添加 OnLoad 事件处理程序

1. 打开前面创建的 InfoPath HelloWorld 项目。
    
2. 在“视图”**** 选项卡上，单击“显示域”****。
    
3. 右键单击“myFields”**** 节点，然后单击“添加”****。
    
4. 在“名称”**** 中，键入“employee”****，然后单击“确定”****。
    
5. 将“employee”**** 节点拖到视图中。 
    
6. 在“开发工具”**** 选项卡上，单击“OnLoad 事件”****。
    
   这将为 [OnLoad](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnLoad.aspx) 事件创建事件处理程序，并且焦点将移到代码编辑器。每次加载表单时，都将调用该事件处理程序中的代码。下一个过程演示如何将检索用户名的表单代码添加到事件处理程序中。 
    
### <a name="add-form-code"></a>添加表单代码

1. 在 **OnLoad** 事件处理程序中，键入下面的代码： 
    
   ```cs
    // Store an XML DOM node as a local variable.
    IXMLDOMNode nodeEmployee = thisXDocument.DOM.selectSingleNode("my:myFields/my:employee");
    if(nodeEmployee != null)
    {
        if(nodeEmployee.text == "")
        {
        // If the employee name is blank when the form is loaded, 
        // populate the employee node with the current user name.
        nodeEmployee.text = System.Environment.UserName;
        }
    }
   ```

   ```vb
    // Store an XML DOM node as a local variable.
    Dim nodeEmployee As IXMLDOMNode
    nodeEmployee = thisXDocument.DOM.selectSingleNode("my:myFields/my:employee");
    If Not(nodeEmployee Is Nothing) Then
        If(nodeEmployee.text = "") Then
        // If the employee name is blank when the form is loaded, 
        // populate the employee node with the current user name.
        nodeEmployee.text = System.Environment.UserName
        End If
    End If
   ```

2. 编译和预览该表单。
    
   employee 文本框现在应当填写了您的用户名。 
    
有关如何部署托管的代码表单模板的信息，请参阅[替换代码中部署 InfoPath 表单模板](how-to-deploy-infopath-form-templates-with-code.md)。 有关 InfoPath 对象模型以及创建使用 InfoPath 2003 兼容对象模型的托管代码表单模板的常见编程任务的信息，请参阅[了解 InfoPath 2003 对象模型](understanding-the-infopath-2003-object-model.md)。 
  
## <a name="see-also"></a>另请参阅

- [使用 InfoPath 2003 对象模型初始化和清理代码](initialization-and-clean-up-code-using-infopath-2003-object-model.md)
- [InfoPath 2003 兼容对象模型](infopath-2003-compatible-object-models.md)
- [使用 InfoPath 2003 对象模型添加事件处理程序](how-to-add-an-event-handler-using-the-infopath-2003-object-model.md)

