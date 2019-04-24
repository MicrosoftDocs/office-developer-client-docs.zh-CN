---
title: 演练：创建包含代码的基本表单模板
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
keywords:
- form templates [infopath 2007], creating managed code,managed code form templates [InfoPath 2007], creating,form templates [InfoPath 2007], walkthroughs,InfoPath 2007, walkthroughs
localization_priority: Normal
ms.assetid: 0f55c8be-8641-476a-b0c8-c88adb2ac2b9
description: 在 Microsoft InfoPath 中，可以使用 Visual Basic 或 C# 编写业务逻辑，方法是在 InfoPath 设计器中打开表单模板，然后使用某个用户界面命令添加事件处理程序。这将打开 Visual Studio 2012 开发环境供你编写代码。
ms.openlocfilehash: cc09856750ced28d35c8da172a08a31c4e3cd4a2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299732"
---
# <a name="walkthrough-create-a-basic-form-template-with-code"></a>演练：创建包含代码的基本表单模板

在 Microsoft InfoPath 中，您可以使用 Visual Basic 或 C# 编写业务逻辑，方法是在 InfoPath 设计器中打开表单模板，然后使用某个用户界面命令添加事件处理程序。这将打开 Visual Studio 2008 开发环境供您编写代码。默认情况下，使用 Visual Studio 2008 创建的表单模板项目依据 [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 命名空间所提供的托管代码对象模型进行工作。 
  
This walkthrough first shows you how to create a simple Hello World application using C# or Visual Basic in the Visual Studio 2012 development environment. The walkthrough concludes with a code sample that shows you how to use the [UserName](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.User.UserName.aspx) property of the [User](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.User.aspx) class to retrieve the current user's name and populate a **Text Box** control with that value. 
  
## <a name="prerequisites"></a>必备组件

为了使用 Visual Studio 2008 开发环境完成此演练，您需要：
  
- Microsoft InfoPath（安装了 Visual Studio 2008）。
    
## <a name="hello-world-in-visual-studio-tools-for-applications"></a>Visual Studio Tools for Applications 中的 Hello World

在以下演练中，你将学习如何为 [ButtonEvent](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ButtonEvent.aspx) 类的 [Clicked](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ButtonEvent.Clicked.aspx) 事件编写一个与“按钮”**** 控件关联的事件处理程序，从而在 Visual Studio 2012 开发环境中编写代码以显示一个简单的警报对话框。 
  
### <a name="create-a-new-project-and-specify-the-programming-language"></a>创建一个新项目并指定编程语言

1. 启动 InfoPath 设计器，然后双击“空白(InfoPath 编辑器)”**** 表单模板。 
    
2. 若要指定要使用的编程语言，请依次单击“Office 按钮”****、“表单选项”**** 和“类别”**** 列表中的“编程”****，然后从“表单模板代码语言”**** 下拉列表中选择“Visual Basic”**** 或“C#”****。 
    
   > [!NOTE]
   > The other programming language options in the **Form template code language** drop-down list provide compatibility with previous versions of InfoPath. The **C# (InfoPath 2007 Compatible)** and **Visual Basic (InfoPath 2007 Compatible)** options will work with the procedures in this topic. However, to use the **C# (InfoPath 2003 Compatible)** and **Visual Basic (InfoPath 2003 Compatible)** options, see [Walkthrough: Creating and Debugging a Basic Form Template Using the InfoPath 2003 Object Model](walkthrough-create-and-debug-basic-form-template-using-infopath-object-model.md). 
  
    现在可以添加“按钮”**** 控件并创建其事件处理程序了。 
    
### <a name="add-a-button-control-and-event-handler"></a>添加一个按钮控件和事件处理程序

1. 在“控件”**** 组中，单击“按钮”**** 控件以添加表单。 
    
2. Double-click the **Button** control, type Hello for the **Label** property on the **Properties** tab of the ribbon, and then click **Custom Code**. When prompted, save the form and name it HelloWorld.
    
   这将会打开“Visual Studio Tools for Applications”**** 环境，而且光标出现在“按钮”**** 控件的 [Clicked](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ButtonEvent.Clicked.aspx) 事件的事件处理程序中。 
    
   现在可以向该按钮的事件处理程序中添加表单代码了。 
    
### <a name="add-hello-world-code-to-the-event-handler-and-preview-the-form"></a>向事件处理程序添加"Hello World"代码并预览表单

1. 在事件处理程序的框架中，键入：
    
   ```cs
   MessageBox.Show("Hello World!");
   ```

   ```vb
   MessageBox.Show("Hello World!")
   ```

   表单模板的代码应如下所示：
    
   ```cs
    using Microsoft.Office.InfoPath;
    using System;
    using System.Windows.Forms;
    using System.Xml;
    using System.Xml.XPath;
    namespace HelloWorld
    {
        public partial class FormCode
        {
            public void InternalStartup()
            {
            ((ButtonEvent)EventManager.ControlEvents["CTRL1_5"]).Clicked += new ClickedEventHandler(CTRL1_5_Clicked);
            }
            public void CTRL1_5_Clicked(object sender, ClickedEventArgs e)
            {
            MessageBox.Show("Hello World!");
            }
        }
    }
   ```

   ```vb
    Imports Microsoft.Office.InfoPath
    Imports System
    Imports System.Windows.Forms
    Imports System.Xml
    Imports System.Xml.XPath
    Namespace HelloWorld
        Public Class FormCode
            Private Sub InternalStartup(ByVal sender As Object, ByVal e As EventArgs) Handles Me.Startup
            AddHandler DirectCast(EventManager.ControlEvents("CTRL1_5"), ButtonEvent).Clicked, AddressOf CTRL1_5_Clicked
            End Sub
            Public Sub CTRL1_5_Clicked(ByVal sender As Object, ByVal e As ClickedEventArgs)
            MessageBox.Show("Hello World!")
            End Sub
        End Class
    End Namespace
   ```

2. 切换到 InfoPath 设计器窗口。
    
3. 单击“主页”**** 选项卡上的“预览”**** 按钮。 
    
4. 单击表单上的 Hello 按钮。 
    
   将显示一个消息框，其中包含"Hello World!"文本。
    
   下一个过程演示如何向表单代码中添加调试断点。
    
### <a name="debug-form-code"></a>调试表单代码

1. 切换回 Visual Studio 2008 窗口。
    
2. 单击下面一行左侧的灰色栏：
    
   ```cs
   MessageBox.Show("Hello World!");
   ```

   ```vb
   MessageBox.Show("Hello World!")
   ```

   将显示一个红色圆圈，并且该代码行突出显示，指示运行时将在表单代码中的此断点处暂停。
    
3. 在“调试”**** 菜单上，单击“启动调试”****（或按 F5）。 
    
4. 在 InfoPath 的“预览”**** 窗口中，单击表单上的 Hello 按钮。 
    
5. Visual Studio 2008 代码编辑器将获得焦点，断点行将突出显示。
    
6. 在“调试”**** 菜单上，单击“逐步执行”****（或按 Shift+F8）以继续逐步执行代码。 
    
7. 将执行事件处理程序代码，并显示"Hello World!"消息。 
    
8. 单击“确定”**** 返回到 Visual Studio 2012 代码编辑器，然后在“调试”**** 菜单上单击“停止调试”****（或按 Ctrl+Alt+Break）。 
    
## <a name="getting-the-current-users-name"></a>获取当前用户的名称

在以下示例中，你将学习如何使用 [User](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.User.aspx) 类的 [UserName](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.User.UserName.aspx) 属性来检索当前用户的名称，然后使用 [Loading](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Loading.aspx) 事件的事件处理程序填充“文本框”**** 控件的值。 
  
填充“文本框”**** 控件可通过使用 [XPathNavigator](https://msdn.microsoft.com/library/system.xml.xpath.xpathnavigator%28v=vs.110%29.aspx) 类的实例将当前用户的名称写入与控件绑定的 XML 节点中来实现。 
  
首先，调用 [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.MainDataSource.aspx) 类的 [MainDataSource](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) 属性，以检索代表表单的基础 XML 文档的 [DataSource](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.aspx) 类的一个实例。然后， [DataSource](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.aspx) 对象会调用 [CreateNavigator](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.CreateNavigator.aspx) 方法，该方法会创建 **XPathNavigator** 对象并将其置于表单主要数据源的根节点上。 
  
调用 [XPathNavigator](https://msdn.microsoft.com/library/system.xml.xpath.xpathnavigator.selectsinglenode%28v=vs.100%29.aspx) 类的 **SelectSingleNode** 方法以选择表单数据源中的 employee 域。最后，调用 [SetValue](https://msdn.microsoft.com/library/system.xml.xpath.xpathnavigator.setvalue%28v=vs.100%29.aspx) 方法，用 [UserName](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.User.UserName.aspx) 属性设置该域的值。 
  
有关在托管代码表单模板中使用 **System.Xml** 的详细信息，请参阅[使用 XPathNavigator 和 XPathNodeIterator 类](how-to-work-with-the-xpathnavigator-and-xpathnodeiterator-classes.md)。
  
### <a name="add-a-loading-event-handler"></a>添加 Loading 事件处理程序

1. 在 InfoPath 设计器中打开您在前一个演练中创建的 HelloWorld 表单模板。
    
2. 在“视图”**** 选项卡上，选择“显示域”****。
    
3. 右键单击“myFields”**** 文件夹，然后单击“添加”****。
    
4. 在“名称”**** 中，键入 employee，然后单击“确定”****。
    
5. 将 employee 域拖到视图中。 
    
6. 在“开发人员”**** 选项卡上，单击“Loading 事件”****。
    
   这将为 [Loading](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Loading.aspx) 事件创建事件处理程序，并将焦点移到代码编辑器中的该事件处理程序。 
    
7. 在代码编辑器中，键入以下代码：
    
   ```cs
    public void FormEvents_Loading(object sender, LoadingEventArgs e)
    {
        XPathNavigator dataSource;
        dataSource = this.MainDataSource.CreateNavigator();
        dataSource.SelectSingleNode(
            "/my:myFields/my:employee", NamespaceManager).SetValue(this.User.UserName);
    }
   ```
 
   ```vb
    Public Sub FormEvents_Loading(ByVal sender As Object, ByVal e As LoadingEventArgs)
        Dim dataSource As XPathNavigator
        dataSource = Me.MainDataSource.CreateNavigator
        dataSource.SelectSingleNode( _
            "/my:myFields/my:employee", NamespaceManager).SetValue(Me.User.UserName)
    End Sub
   ```

8. 切换到 InfoPath 表单设计窗口，然后单击“主页”**** 选项卡上的“预览”**** 按钮以预览表单。 
    
   employee 域中应自动填充您的用户名。 
    
## <a name="next-steps"></a>后续步骤

- 有关使用其他控件和事件的事件处理程序的信息，请参阅[添加事件处理程序](how-to-add-an-event-handler.md)。
    
- 有关在表单模板中预览和调试代码的详细信息，请参阅[预览和调试包含代码的 InfoPath 表单模板](how-to-preview-and-debug-infopath-form-templates-with-code.md)。
    
- 有关如何部署托管代码表单模板的信息，请参阅[部署包含代码的 InfoPath 表单模板](how-to-deploy-infopath-form-templates-with-code.md)。
    
- 有关 InfoPath 对象模型和托管代码表单模板中的常见编程任务的信息，请参阅[了解 InfoPath 对象模型和常见开发任务](understanding-the-infopath-object-model-and-common-developer-tasks.md)
    
## <a name="see-also"></a>另请参阅

- [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx)

