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
ms.openlocfilehash: 8c98d71c26f8e56c532b2a4467218c366072b2ce
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774106"
---
# <a name="walkthrough-create-a-basic-form-template-with-code"></a><span data-ttu-id="f362f-104">演练：创建包含代码的基本表单模板</span><span class="sxs-lookup"><span data-stu-id="f362f-104">Walkthrough: Create a basic form template with code</span></span>

<span data-ttu-id="f362f-p101">在 Microsoft InfoPath 中，您可以使用 Visual Basic 或 C# 编写业务逻辑，方法是在 InfoPath 设计器中打开表单模板，然后使用某个用户界面命令添加事件处理程序。这将打开 Visual Studio 2008 开发环境供您编写代码。默认情况下，使用 Visual Studio 2008 创建的表单模板项目依据 [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 命名空间所提供的托管代码对象模型进行工作。</span><span class="sxs-lookup"><span data-stu-id="f362f-p101">In Microsoft InfoPath, you can write business logic in Visual Basic or C# by opening a form template in the InfoPath designer, and then using one of the user interface commands to add an event handler, which will open the Visual Studio 2012 development environment for writing your code. By default, form template projects created using Visual Studio 2012 work against the managed code object model provided by the [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) namespace.</span></span> 
  
<span data-ttu-id="f362f-107">此演练首先演示了如何在 Visual Studio 2012 开发环境中使用 C# 或 Visual Basic 创建简单的 Hello World 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f362f-107">This walkthrough first shows you how to create a simple Hello World application using C# or Visual Basic in the Visual Studio 2012 development environment.</span></span> <span data-ttu-id="f362f-108">最后用代码示例演示了如何使用 [User](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.User.aspx) 类的 [UserName](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.User.UserName.aspx) 属性检索当前用户的名称以及如何使用该值填充“文本框”****。</span><span class="sxs-lookup"><span data-stu-id="f362f-108">This walkthrough first shows you how to create a simple Hello World application using C# or Visual Basic in the vsta14 development environment. The walkthrough concludes with a code sample that shows you how to use the [P:Microsoft.Office.InfoPath.User.UserName](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.User.UserName.aspx) property of the [T:Microsoft.Office.InfoPath.User](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.User.aspx) class to retrieve the current user's name and populate a **Text Box** control with that value.</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="f362f-109">必备组件</span><span class="sxs-lookup"><span data-stu-id="f362f-109">Prerequisites</span></span>

<span data-ttu-id="f362f-110">为了使用 Visual Studio 2008 开发环境完成此演练，您需要：</span><span class="sxs-lookup"><span data-stu-id="f362f-110">In order to complete this walkthrough using the Visual Studio 2012 development environment, you will need:</span></span>
  
- <span data-ttu-id="f362f-111">Microsoft InfoPath（安装了 Visual Studio 2008）。</span><span class="sxs-lookup"><span data-stu-id="f362f-111">Microsoft InfoPath with Visual Studio 2012 installed.</span></span>
    
## <a name="hello-world-in-visual-studio-tools-for-applications"></a><span data-ttu-id="f362f-112">Visual Studio Tools for Applications 中的 Hello World</span><span class="sxs-lookup"><span data-stu-id="f362f-112">Hello World in Visual Studio Tools for Applications</span></span>

<span data-ttu-id="f362f-113">在以下演练中，你将学习如何为 [ButtonEvent](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ButtonEvent.aspx) 类的 [Clicked](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ButtonEvent.Clicked.aspx) 事件编写一个与“按钮”**** 控件关联的事件处理程序，从而在 Visual Studio 2012 开发环境中编写代码以显示一个简单的警报对话框。</span><span class="sxs-lookup"><span data-stu-id="f362f-113">In the following walkthrough, you will learn how to write code in the vsta14 development environment to display a simple alert dialog box by writing an event handler for the E:Microsoft.Office.InfoPath.ButtonEvent.Clicked event of the T:Microsoft.Office.InfoPath.ButtonEvent class, which is associated with the Button control.</span></span> 
  
### <a name="create-a-new-project-and-specify-the-programming-language"></a><span data-ttu-id="f362f-114">创建一个新项目并指定编程语言</span><span class="sxs-lookup"><span data-stu-id="f362f-114">Create a new project and specify the programming language</span></span>

1. <span data-ttu-id="f362f-115">启动 InfoPath 设计器，然后双击“空白(InfoPath 编辑器)”**** 表单模板。</span><span class="sxs-lookup"><span data-stu-id="f362f-115">Start the InfoPath designer, and then double-click the **Blank (InfoPath Editor)** form template.</span></span> 
    
2. <span data-ttu-id="f362f-116">若要指定要使用的编程语言，请依次单击“Office 按钮”****、“表单选项”**** 和“类别”**** 列表中的“编程”****，然后从“表单模板代码语言”**** 下拉列表中选择“Visual Basic”**** 或“C#”****。</span><span class="sxs-lookup"><span data-stu-id="f362f-116">To specify which programming language to use, click the **Office Button**, click **Form Options**, click **Programming** in the **Category** list, and then select either **Visual Basic** or **C#** from the **Form template code language** drop-down list.</span></span> 
    
   > [!NOTE]
   > <span data-ttu-id="f362f-117">****“表单模板代码语言”下拉列表中的其他编程语言选项提供与早期版本的 InfoPath 的兼容性。</span><span class="sxs-lookup"><span data-stu-id="f362f-117">The other programming language options in the **Form template code language** drop-down list provide compatibility with previous versions of InfoPath.</span></span> <span data-ttu-id="f362f-118">“C# (InfoPath 2007 兼容)”**** 和“Visual Basic (InfoPath 2007 兼容)”**** 选项将适用于本主题中的过程。</span><span class="sxs-lookup"><span data-stu-id="f362f-118">The **C# (InfoPath 2007 Compatible)** and **Visual Basic (InfoPath 2007 Compatible)** options will work with the procedures in this topic.</span></span> <span data-ttu-id="f362f-119">但是，若要使用“C# (InfoPath 2003 兼容)”**** 和“Visual Basic (InfoPath 2003 兼容)”**** 选项，请参阅[演练：使用 InfoPath 2003 对象模型创建和调试基本表单模板](walkthrough-create-and-debug-basic-form-template-using-infopath-object-model.md)。</span><span class="sxs-lookup"><span data-stu-id="f362f-119">The other programming language options in the **Form template code language** drop-down list provide compatibility with previous versions of InfoPath. The **C# (InfoPath 2007 Compatible)** and Visual Basic (InfoPath 2007 Compatible) options will work with the procedures in this topic. However, to use the C# (InfoPath 2003 Compatible) and Visual Basic (InfoPath 2003 Compatible) options, see [Walkthrough: Creating and Debugging a Basic Form Template Using the InfoPath 2003 Object Model](walkthrough-create-and-debug-basic-form-template-using-infopath-object-model.md).</span></span> 
  
    <span data-ttu-id="f362f-120">现在可以添加“按钮”**** 控件并创建其事件处理程序了。</span><span class="sxs-lookup"><span data-stu-id="f362f-120">You are now ready to add a **Button** control and create its event handler.</span></span> 
    
### <a name="add-a-button-control-and-event-handler"></a><span data-ttu-id="f362f-121">添加一个按钮控件和事件处理程序</span><span class="sxs-lookup"><span data-stu-id="f362f-121">Add a Button control and event handler</span></span>

1. <span data-ttu-id="f362f-122">在“控件”**** 组中，单击“按钮”**** 控件以添加表单。</span><span class="sxs-lookup"><span data-stu-id="f362f-122">In the **Controls** group, click the **Button** control to add it the form.</span></span> 
    
2. <span data-ttu-id="f362f-123">双击“按钮”**** 控件，在功能区的“属性”**** 选项卡上，为“标签”**** 属性键入 Hello，然后单击“自定义代码”****。</span><span class="sxs-lookup"><span data-stu-id="f362f-123">Double-click the **Button** control, type Hello for the **Label** property on the **Properties** tab of the ribbon, and then click **Custom Code. When prompted, save the form and name it HelloWorld**.</span></span> <span data-ttu-id="f362f-124">当出现提示时，保存表单并将其命名为 HelloWorld。</span><span class="sxs-lookup"><span data-stu-id="f362f-124">When prompted, save the form and name it HelloWorld.</span></span>
    
   <span data-ttu-id="f362f-125">这将会打开“Visual Studio Tools for Applications”**** 环境，而且光标出现在“按钮”**** 控件的 [Clicked](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ButtonEvent.Clicked.aspx) 事件的事件处理程序中。</span><span class="sxs-lookup"><span data-stu-id="f362f-125">This will open the **Visual Studio Tools for Applications** environment with the cursor in the event handler for the [E:Microsoft.Office.InfoPath.ButtonEvent.Clicked](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ButtonEvent.Clicked.aspx) event of **Button** control.</span></span> 
    
   <span data-ttu-id="f362f-126">现在可以向该按钮的事件处理程序中添加表单代码了。</span><span class="sxs-lookup"><span data-stu-id="f362f-126">You are now ready to add form code to the event handler for the button.</span></span> 
    
### <a name="add-hello-world-code-to-the-event-handler-and-preview-the-form"></a><span data-ttu-id="f362f-127">向事件处理程序添加"Hello World"代码并预览表单</span><span class="sxs-lookup"><span data-stu-id="f362f-127">Add "Hello World" code to the event handler and preview the form</span></span>

1. <span data-ttu-id="f362f-128">在事件处理程序的框架中，键入：</span><span class="sxs-lookup"><span data-stu-id="f362f-128">In the event handler skeleton, type:</span></span>
    
   ```cs
   MessageBox.Show("Hello World!");
   ```

   ```vb
   MessageBox.Show("Hello World!")
   ```

   <span data-ttu-id="f362f-129">表单模板的代码应如下所示：</span><span class="sxs-lookup"><span data-stu-id="f362f-129">The code for your form template should look similar to the following:</span></span>
    
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

2. <span data-ttu-id="f362f-130">切换到 InfoPath 设计器窗口。</span><span class="sxs-lookup"><span data-stu-id="f362f-130">Switch to the InfoPath designer window.</span></span>
    
3. <span data-ttu-id="f362f-131">单击“主页”**** 选项卡上的“预览”**** 按钮。</span><span class="sxs-lookup"><span data-stu-id="f362f-131">Click the **Preview** button on the **Home** tab.</span></span> 
    
4. <span data-ttu-id="f362f-132">单击表单上的 Hello 按钮。</span><span class="sxs-lookup"><span data-stu-id="f362f-132">Click the Hello button on the form.</span></span> 
    
   <span data-ttu-id="f362f-133">将显示一个消息框，其中包含"Hello World!"文本。</span><span class="sxs-lookup"><span data-stu-id="f362f-133">A message box will be displayed with the text "Hello World!"</span></span>
    
   <span data-ttu-id="f362f-134">下一个过程演示如何向表单代码中添加调试断点。</span><span class="sxs-lookup"><span data-stu-id="f362f-134">The next procedure shows how to add debugging breakpoints to your form code.</span></span>
    
### <a name="debug-form-code"></a><span data-ttu-id="f362f-135">调试表单代码</span><span class="sxs-lookup"><span data-stu-id="f362f-135">Debug form code</span></span>

1. <span data-ttu-id="f362f-136">切换回 Visual Studio 2008 窗口。</span><span class="sxs-lookup"><span data-stu-id="f362f-136">Switch back to the Visual Studio 2012 window.</span></span>
    
2. <span data-ttu-id="f362f-137">单击下面一行左侧的灰色栏：</span><span class="sxs-lookup"><span data-stu-id="f362f-137">Click the grey bar to the left of the line:</span></span>
    
   ```cs
   MessageBox.Show("Hello World!");
   ```

   ```vb
   MessageBox.Show("Hello World!")
   ```

   <span data-ttu-id="f362f-138">将显示一个红色圆圈，并且该代码行突出显示，指示运行时将在表单代码中的此断点处暂停。</span><span class="sxs-lookup"><span data-stu-id="f362f-138">A red circle is displayed and the line of code is highlighted to indicate that the runtime will pause at this breakpoint in your form code.</span></span>
    
3. <span data-ttu-id="f362f-139">在“调试”**** 菜单上，单击“启动调试”****（或按 F5）。</span><span class="sxs-lookup"><span data-stu-id="f362f-139">On the **Debug** menu, click **Start Debugging** (or press F5).</span></span> 
    
4. <span data-ttu-id="f362f-140">在 InfoPath 的“预览”**** 窗口中，单击表单上的 Hello 按钮。</span><span class="sxs-lookup"><span data-stu-id="f362f-140">In the InfoPath **Preview** window, click the Hello button on the form.</span></span> 
    
5. <span data-ttu-id="f362f-141">Visual Studio 2008 代码编辑器将获得焦点，断点行将突出显示。</span><span class="sxs-lookup"><span data-stu-id="f362f-141">The Visual Studio 2012 code editor is given focus, and the breakpoint line is highlighted.</span></span>
    
6. <span data-ttu-id="f362f-142">在“调试”**** 菜单上，单击“逐步执行”****（或按 Shift+F8）以继续逐步执行代码。</span><span class="sxs-lookup"><span data-stu-id="f362f-142">On the **Debug** menu, click **Step Over** (or press Shift+F8) to continue stepping through the code.</span></span> 
    
7. <span data-ttu-id="f362f-p105">将执行事件处理程序代码，并显示"Hello World!"消息。</span><span class="sxs-lookup"><span data-stu-id="f362f-p105">The event handler code is executed, and the "Hello World!" message is displayed.</span></span> 
    
8. <span data-ttu-id="f362f-145">单击“确定”**** 返回到 Visual Studio 2012 代码编辑器，然后在“调试”**** 菜单上单击“停止调试”****（或按 Ctrl+Alt+Break）。</span><span class="sxs-lookup"><span data-stu-id="f362f-145">Click OK to return to the vsta14 code editor, and then click Stop Debugging on the Debug menu (or press Ctrl+Alt+Break).</span></span> 
    
## <a name="getting-the-current-users-name"></a><span data-ttu-id="f362f-146">获取当前用户的名称</span><span class="sxs-lookup"><span data-stu-id="f362f-146">Getting the Current User's Name</span></span>

<span data-ttu-id="f362f-147">在以下示例中，你将学习如何使用 [User](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.User.aspx) 类的 [UserName](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.User.UserName.aspx) 属性来检索当前用户的名称，然后使用 [Loading](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Loading.aspx) 事件的事件处理程序填充“文本框”**** 控件的值。</span><span class="sxs-lookup"><span data-stu-id="f362f-147">In the following example, you will learn how to use the [P:Microsoft.Office.InfoPath.User.UserName](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.User.UserName.aspx) property of the [T:Microsoft.Office.InfoPath.User](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.User.aspx) class to retrieve the name of the current user and populate the value of a **Text Box** control by using an event handler for the [E:Microsoft.Office.InfoPath.FormEvents.Loading](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Loading.aspx) event.</span></span> 
  
<span data-ttu-id="f362f-148">填充“文本框”**** 控件可通过使用 [XPathNavigator](https://msdn.microsoft.com/library/system.xml.xpath.xpathnavigator%28v=vs.110%29.aspx) 类的实例将当前用户的名称写入与控件绑定的 XML 节点中来实现。</span><span class="sxs-lookup"><span data-stu-id="f362f-148">Populating the **Text Box** control is accomplished by using an instance of the [XPathNavigatorfrlrfSystemXmlXPathXPathNavigatorClassTopic](https://msdn.microsoft.com/library/system.xml.xpath.xpathnavigator%28v=vs.110%29.aspx) class to write the current user's name to the XML node that the control is bound to.</span></span> 
  
<span data-ttu-id="f362f-p106">首先，调用 [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.MainDataSource.aspx) 类的 [MainDataSource](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) 属性，以检索代表表单的基础 XML 文档的 [DataSource](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.aspx) 类的一个实例。然后， [DataSource](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.aspx) 对象会调用 [CreateNavigator](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.CreateNavigator.aspx) 方法，该方法会创建 **XPathNavigator** 对象并将其置于表单主要数据源的根节点上。</span><span class="sxs-lookup"><span data-stu-id="f362f-p106">First, the [MainDataSource](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.MainDataSource.aspx) property of the [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) class is called to retrieve an instance of the [DataSource](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.aspx) class that represents the underlying XML document of the form. The [DataSource](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.aspx) object then calls the [CreateNavigator](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.CreateNavigator.aspx) method, which creates the **XPathNavigator** object and positions it at the root node of the form's main data source.</span></span> 
  
<span data-ttu-id="f362f-p107">调用 [XPathNavigator](https://msdn.microsoft.com/library/system.xml.xpath.xpathnavigator.selectsinglenode%28v=vs.100%29.aspx) 类的 **SelectSingleNode** 方法以选择表单数据源中的 employee 域。最后，调用 [SetValue](https://msdn.microsoft.com/library/system.xml.xpath.xpathnavigator.setvalue%28v=vs.100%29.aspx) 方法，用 [UserName](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.User.UserName.aspx) 属性设置该域的值。</span><span class="sxs-lookup"><span data-stu-id="f362f-p107">The [SelectSingleNode](https://msdn.microsoft.com/library/system.xml.xpath.xpathnavigator.selectsinglenode%28v=vs.100%29.aspx) method of the **XPathNavigator** class is called to select the employee field in the form's data source. Finally, the [SetValue](https://msdn.microsoft.com/library/system.xml.xpath.xpathnavigator.setvalue%28v=vs.100%29.aspx) method is called to set the value of the field with the [UserName](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.User.UserName.aspx) property.</span></span> 
  
<span data-ttu-id="f362f-153">有关在托管代码表单模板中使用 **System.Xml** 的详细信息，请参阅[使用 XPathNavigator 和 XPathNodeIterator 类](how-to-work-with-the-xpathnavigator-and-xpathnodeiterator-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="f362f-153">For more information on working with **System.Xml** in managed code form templates, see [How to: Work with the XPathNavigator and XPathNodeIterator Classes](how-to-work-with-the-xpathnavigator-and-xpathnodeiterator-classes.md).</span></span>
  
### <a name="add-a-loading-event-handler"></a><span data-ttu-id="f362f-154">添加 Loading 事件处理程序</span><span class="sxs-lookup"><span data-stu-id="f362f-154">Add a Loading event handler</span></span>

1. <span data-ttu-id="f362f-155">在 InfoPath 设计器中打开您在前一个演练中创建的 HelloWorld 表单模板。</span><span class="sxs-lookup"><span data-stu-id="f362f-155">Open the HelloWorld form template that you created in the previous walkthrough in the InfoPath designer.</span></span>
    
2. <span data-ttu-id="f362f-156">在“视图”**** 选项卡上，选择“显示域”****。</span><span class="sxs-lookup"><span data-stu-id="f362f-156">On the **View** tab, select **Show Fields**.</span></span>
    
3. <span data-ttu-id="f362f-157">右键单击“myFields”**** 文件夹，然后单击“添加”****。</span><span class="sxs-lookup"><span data-stu-id="f362f-157">Right click the **myFields** folder, and then click **Add**.</span></span>
    
4. <span data-ttu-id="f362f-158">在“名称”**** 中，键入 employee，然后单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="f362f-158">In Name, type employee, and then click OK.</span></span>
    
5. <span data-ttu-id="f362f-159">将 employee 域拖到视图中。</span><span class="sxs-lookup"><span data-stu-id="f362f-159">Drag the employee field onto the view.</span></span> 
    
6. <span data-ttu-id="f362f-160">在“开发人员”**** 选项卡上，单击“Loading 事件”****。</span><span class="sxs-lookup"><span data-stu-id="f362f-160">On the **Developer** tab, click **Loading Event**.</span></span>
    
   <span data-ttu-id="f362f-161">这将为 [Loading](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Loading.aspx) 事件创建事件处理程序，并将焦点移到代码编辑器中的该事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="f362f-161">This will create an event handler for the [Loading](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Loading.aspx) event, and move the focus to that event handler in the code editor.</span></span> 
    
7. <span data-ttu-id="f362f-162">在代码编辑器中，键入以下代码：</span><span class="sxs-lookup"><span data-stu-id="f362f-162">In the code editor, type the following:</span></span>
    
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

8. <span data-ttu-id="f362f-163">切换到 InfoPath 表单设计窗口，然后单击“主页”**** 选项卡上的“预览”**** 按钮以预览表单。</span><span class="sxs-lookup"><span data-stu-id="f362f-163">Switch to the InfoPath form design window, and then click the **Preview** button on the **Home** tab to preview the form.</span></span> 
    
   <span data-ttu-id="f362f-164">employee 域中应自动填充您的用户名。</span><span class="sxs-lookup"><span data-stu-id="f362f-164">The employee field should automatically fill in with your user name.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="f362f-165">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f362f-165">Next steps</span></span>

- <span data-ttu-id="f362f-166">有关使用其他控件和事件的事件处理程序的信息，请参阅[添加事件处理程序](how-to-add-an-event-handler.md)。</span><span class="sxs-lookup"><span data-stu-id="f362f-166">For information about working with event handlers for other controls and events, see [How to: Add an Event Handler](how-to-add-an-event-handler.md).</span></span>
    
- <span data-ttu-id="f362f-167">有关在表单模板中预览和调试代码的详细信息，请参阅[预览和调试包含代码的 InfoPath 表单模板](how-to-preview-and-debug-infopath-form-templates-with-code.md)。</span><span class="sxs-lookup"><span data-stu-id="f362f-167">For more information about previewing and debugging code in form templates, see [How to: Preview and Debug InfoPath Form Templates with Code](how-to-preview-and-debug-infopath-form-templates-with-code.md).</span></span>
    
- <span data-ttu-id="f362f-168">有关如何部署托管代码表单模板的信息，请参阅[部署包含代码的 InfoPath 表单模板](how-to-deploy-infopath-form-templates-with-code.md)。</span><span class="sxs-lookup"><span data-stu-id="f362f-168">For information about how to deploy a managed-code form template, see [How to: Deploy InfoPath Form Templates with Code](how-to-deploy-infopath-form-templates-with-code.md).</span></span>
    
- <span data-ttu-id="f362f-169">有关 InfoPath 对象模型和托管代码表单模板中的常见编程任务的信息，请参阅[了解 InfoPath 对象模型和常见开发任务](understanding-the-infopath-object-model-and-common-developer-tasks.md)</span><span class="sxs-lookup"><span data-stu-id="f362f-169">For information about the InfoPath object model and common programming tasks in managed-code form templates, see [Understanding the InfoPath Object Model and Common Developer Tasks](understanding-the-infopath-object-model-and-common-developer-tasks.md)</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f362f-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f362f-170">See also</span></span>

- <span data-ttu-id="f362f-171">[XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx)</span><span class="sxs-lookup"><span data-stu-id="f362f-171">[XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) property</span></span>

