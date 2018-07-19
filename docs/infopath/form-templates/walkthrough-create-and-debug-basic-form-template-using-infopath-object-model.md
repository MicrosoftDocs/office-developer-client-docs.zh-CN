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
# <a name="walkthrough-create-and-debug-a-basic-form-template-using-the-infopath-object-model"></a><span data-ttu-id="6871a-104">演练： 创建和调试使用 InfoPath 对象模型的基本表单模板</span><span class="sxs-lookup"><span data-stu-id="6871a-104">Walkthrough: Create and debug a basic form template using the InfoPath object model</span></span>

<span data-ttu-id="6871a-105">本主题演练如何创建基本 InfoPath 托管代码表单模板，该模板用来处理由 [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) 命名空间提供的与 InfoPath 2003 兼容对象模型。</span><span class="sxs-lookup"><span data-stu-id="6871a-105">This topic provides a walkthrough of creating a basic InfoPath managed code form template that works with the InfoPath 2003-compatible object model provided by the [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) namespace.</span></span> 
  
## <a name="hello-world"></a><span data-ttu-id="6871a-106">Hello World</span><span class="sxs-lookup"><span data-stu-id="6871a-106">Hello World</span></span>

<span data-ttu-id="6871a-107">在下面的示例中，您将了解如何通过使用 InfoPath 2003 兼容对象模型的 [Alert](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.Alert.aspx) 方法来显示简单的警告对话框。</span><span class="sxs-lookup"><span data-stu-id="6871a-107">In the following example, you will learn how to display a simple alert dialog box by using the [Alert](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.Alert.aspx) method of the InfoPath 2003-compatible object model.</span></span> 
  
### <a name="create-a-new-infopath-form-template-that-works-with-the-infopath-2003-compatible-object-model"></a><span data-ttu-id="6871a-108">新建使用 InfoPath 2003 兼容对象模型的 InfoPath 表单模板</span><span class="sxs-lookup"><span data-stu-id="6871a-108">Create a new InfoPath form template that works with the InfoPath 2003-compatible object model</span></span>

1. <span data-ttu-id="6871a-109">创建新的表单模板使用 InfoPath 2003 兼容对象模型，[创建一个表单模板使用 InfoPath 2003 对象模型](how-to-create-a-form-template-using-the-infopath-2003-object-model.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="6871a-109">Create a new form template that works with the InfoPath 2003-compatible object model, as described in [Create a Form Template Using the InfoPath 2003 Object Model](how-to-create-a-form-template-using-the-infopath-2003-object-model.md).</span></span>
    
2. <span data-ttu-id="6871a-110">将该表单模板项目命名为 HelloWorld 并保存它。</span><span class="sxs-lookup"><span data-stu-id="6871a-110">Name the form template project HelloWorld and save it.</span></span> 
    
   <span data-ttu-id="6871a-p101">项目系统会创建代码文件和项目文件，然后在 InfoPath 设计模式下打开一个空白的表单模板。现在可以添加事件处理程序了。</span><span class="sxs-lookup"><span data-stu-id="6871a-p101">The project system creates code and project files, and then opens a blank form template in InfoPath design mode. You are now ready to add event handlers.</span></span>
    
### <a name="add-a-button-with-an-onclick-event-handler"></a><span data-ttu-id="6871a-113">添加包含 OnClick 事件处理程序的按钮</span><span class="sxs-lookup"><span data-stu-id="6871a-113">Add a button with an OnClick event handler</span></span>

1. <span data-ttu-id="6871a-114">在“主页”**** 选项卡的“控件”**** 部分，单击“按钮”**** 控件以将其插入视图中。</span><span class="sxs-lookup"><span data-stu-id="6871a-114">In the **Controls** section on the **Home** tab, click the **Button** control to insert it into the view.</span></span> 
    
2. <span data-ttu-id="6871a-115">右键单击该控件，然后单击“按钮属性”****。</span><span class="sxs-lookup"><span data-stu-id="6871a-115">Right-click the control, and then click **Button Properties**.</span></span>
    
3. <span data-ttu-id="6871a-116">**标签**更改为 Alert。</span><span class="sxs-lookup"><span data-stu-id="6871a-116">Change the **Label** to Alert.</span></span>
    
4. <span data-ttu-id="6871a-117">将**ID**更改为 AlertID。</span><span class="sxs-lookup"><span data-stu-id="6871a-117">Change the **ID** to AlertID.</span></span>
    
5. <span data-ttu-id="6871a-118">单击“编辑表单代码”****。</span><span class="sxs-lookup"><span data-stu-id="6871a-118">Click **Edit Form Code**.</span></span>
    
   <span data-ttu-id="6871a-119">此时会创建 [OnClick](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._ButtonEventSink_Event.OnClick.aspx) 事件的事件处理程序框架，同时焦点将移至 Visual Studio 2008 中的代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="6871a-119">An event handler skeleton for the [OnClick](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._ButtonEventSink_Event.OnClick.aspx) event is created and the focus moves to the code editor in Visual Studio 2012.</span></span> <span data-ttu-id="6871a-120">使用事件处理程序的详细信息，请参阅[添加事件处理程序使用的 InfoPath 2003 对象模型](how-to-add-an-event-handler-using-the-infopath-2003-object-model.md)。</span><span class="sxs-lookup"><span data-stu-id="6871a-120">For more information on working with event handlers, see [Add an Event Handler Using the InfoPath 2003 Object Model](how-to-add-an-event-handler-using-the-infopath-2003-object-model.md).</span></span> 
    
   <span data-ttu-id="6871a-121">现在可以向该按钮的事件处理程序中添加表单代码了。</span><span class="sxs-lookup"><span data-stu-id="6871a-121">You are now ready to add form code to the event handler for the button.</span></span>
    
### <a name="add-form-code-to-the-event-handler"></a><span data-ttu-id="6871a-122">向事件处理程序中添加表单代码</span><span class="sxs-lookup"><span data-stu-id="6871a-122">Add form code to the event handler</span></span>

1. <span data-ttu-id="6871a-123">在 **OnClick** 事件处理程序中，键入下面的代码：</span><span class="sxs-lookup"><span data-stu-id="6871a-123">In the **OnClick** event handler, type the following code:</span></span> 
    
   ```cs
    thisXDocument.UI.Alert("Hello World!");
   ```

   ```vb
    thisXDocument.UI.Alert("Hello World!")
   ```

   <span data-ttu-id="6871a-p103">请注意，在代码行中每键入一个句点之后，都会显示一个 Microsoft IntelliSense 下拉列表。整个事件处理程序看上去应当如下所示：</span><span class="sxs-lookup"><span data-stu-id="6871a-p103">Note that a Microsoft IntelliSense drop-down list is displayed after you type each period in the line of code. The entire event handler should look like the following:</span></span>
    
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
   > <span data-ttu-id="6871a-p104"> 除了 **Alert** 方法，还可以使用 **System.Windows.Forms** 命名空间的 **MessageBox.Show** 方法来显示消息框。为此，必须添加一个对 System.Windows.Forms 程序集的引用，在代码文件开头的指令中添加  `using System.Windows.Forms;` 或  `Imports System.Windows.Forms`，然后键入一行如下所示的代码： `MessageBox.Show("Hello World!); or MessageBox.Show("Hello World!)`</span><span class="sxs-lookup"><span data-stu-id="6871a-p104">As an alternative to using the **Alert** method, you can use the **MessageBox.Show** method of the **System.Windows.Forms** namespace to display a message box. To do so, you must add a reference to the System.Windows.Forms assembly, add  `using System.Windows.Forms;` or  `Imports System.Windows.Forms` to the directives at the beginning of your code file, and then type a line of code such as the following:  `MessageBox.Show("Hello World!); or MessageBox.Show("Hello World!)`</span></span>
  
2. <span data-ttu-id="6871a-128">切换到 InfoPath 设计模式窗口，然后单击“主页”**** 选项卡上的“预览”**** 按钮。</span><span class="sxs-lookup"><span data-stu-id="6871a-128">Switch to the InfoPath design mode window, and then click the **Preview** button on the **Home** tab.</span></span> 
    
3. <span data-ttu-id="6871a-129">在“预览”**** 窗口中，单击“Alert”**** 按钮。</span><span class="sxs-lookup"><span data-stu-id="6871a-129">In the **Preview** window, click the **Alert** button.</span></span> 
    
   <span data-ttu-id="6871a-130">将显示一个消息框，其中包含"Hello World!"文本。</span><span class="sxs-lookup"><span data-stu-id="6871a-130">A message box will be displayed with the text "Hello World!"</span></span>
    
   <span data-ttu-id="6871a-131">下一个过程演示如何向表单代码中添加调试断点。</span><span class="sxs-lookup"><span data-stu-id="6871a-131">The next procedure shows how to add debugging breakpoints to your form code.</span></span>
    
### <a name="debug-form-code"></a><span data-ttu-id="6871a-132">调试表单代码</span><span class="sxs-lookup"><span data-stu-id="6871a-132">Debug form code</span></span>

1. <span data-ttu-id="6871a-133">在代码编辑器中，单击该行左侧的灰条：</span><span class="sxs-lookup"><span data-stu-id="6871a-133">In the code editor, click the grey bar to the left of the line:</span></span>
    
   ```cs
    thisXDocument.UI.Alert("Hello World!");
   ```

   ```vb
    thisXDocument.UI.Alert("Hello World!")
   ```

   <span data-ttu-id="6871a-134">将显示一个红色圆圈，并且该代码行突出显示，指示运行时将在表单代码中的此断点处暂停。</span><span class="sxs-lookup"><span data-stu-id="6871a-134">A red circle is displayed and the line of code is highlighted to indicate that the runtime will pause at this breakpoint in your form code.</span></span>
    
2. <span data-ttu-id="6871a-135">在“调试”**** 菜单上，单击“启动调试”****（或按 F5）。</span><span class="sxs-lookup"><span data-stu-id="6871a-135">On the **Debug** menu, click **Start Debugging** (or press F5).</span></span> 
    
3. <span data-ttu-id="6871a-136">在 InfoPath 的“预览”**** 窗口中，单击“Alert”**** 按钮。</span><span class="sxs-lookup"><span data-stu-id="6871a-136">In the InfoPath **Preview** window, click the **Alert** button.</span></span> 
    
   <span data-ttu-id="6871a-137">代码编辑器将获得焦点，并且断点行突出显示。</span><span class="sxs-lookup"><span data-stu-id="6871a-137">The code editor is given focus, and the breakpoint line is highlighted.</span></span>
    
4. <span data-ttu-id="6871a-138">在“调试”**** 菜单上，单击“单步执行(跳过过程)”****（或按 Shift+F8）继续单步执行代码。</span><span class="sxs-lookup"><span data-stu-id="6871a-138">On the **Debug** menu, click **Step Over** (or press Shift+F8) to continue stepping through the code.</span></span> 
    
   <span data-ttu-id="6871a-p105">将执行 **Alert** 方法代码，并在 InfoPath 的“预览”**** 窗口中显示“Hello World!”警告。</span><span class="sxs-lookup"><span data-stu-id="6871a-p105">The **Alert** method code is executed, and the "Hello World!" alert is displayed in the InfoPath **Preview** window.</span></span> 
    
## <a name="getting-the-current-users-name"></a><span data-ttu-id="6871a-141">获取当前用户的名称</span><span class="sxs-lookup"><span data-stu-id="6871a-141">Getting the Current User's Name</span></span>

<span data-ttu-id="6871a-p106">通过使用 .NET Framework 类，可以访问不便通过脚本使用的功能。在此示例中，您将了解如何使用 .NET Framework 类来检索当前用户的名称。</span><span class="sxs-lookup"><span data-stu-id="6871a-p106">By using the .NET Framework classes, you can get access to functionality that was not easily available in script. In this example, you will learn how use the .NET Framework classes to retrieve the name of the current user.</span></span>
  
### <a name="add-an-onload-event-handler"></a><span data-ttu-id="6871a-144">添加 OnLoad 事件处理程序</span><span class="sxs-lookup"><span data-stu-id="6871a-144">Add an OnLoad event handler</span></span>

1. <span data-ttu-id="6871a-145">打开前面创建的 InfoPath HelloWorld 项目。</span><span class="sxs-lookup"><span data-stu-id="6871a-145">Open the InfoPath HelloWorld project that you created earlier.</span></span>
    
2. <span data-ttu-id="6871a-146">在“视图”**** 选项卡上，单击“显示域”****。</span><span class="sxs-lookup"><span data-stu-id="6871a-146">On the **View** tab, click **Show Fields**.</span></span>
    
3. <span data-ttu-id="6871a-147">右键单击“myFields”**** 节点，然后单击“添加”****。</span><span class="sxs-lookup"><span data-stu-id="6871a-147">Right-click the **myFields** node, and then click **Add**.</span></span>
    
4. <span data-ttu-id="6871a-148">在“名称”**** 中，键入“employee”****，然后单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="6871a-148">In **Name**, type **employee**, then click **OK**.</span></span>
    
5. <span data-ttu-id="6871a-149">将“employee”**** 节点拖到视图中。</span><span class="sxs-lookup"><span data-stu-id="6871a-149">Drag the **employee** node into the view.</span></span> 
    
6. <span data-ttu-id="6871a-150">在“开发工具”**** 选项卡上，单击“OnLoad 事件”****。</span><span class="sxs-lookup"><span data-stu-id="6871a-150">On the **Developer** tab, click **On Load Event**.</span></span>
    
   <span data-ttu-id="6871a-p107">这将为 [OnLoad](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnLoad.aspx) 事件创建事件处理程序，并且焦点将移到代码编辑器。每次加载表单时，都将调用该事件处理程序中的代码。下一个过程演示如何将检索用户名的表单代码添加到事件处理程序中。</span><span class="sxs-lookup"><span data-stu-id="6871a-p107">This will create an event handler for the [OnLoad](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnLoad.aspx) event, and focus moves to the code editor. The code in this event handler will be called each time the form is loaded. The next procedure shows how to add form code that retrieves the user's name to the event handler.</span></span> 
    
### <a name="add-form-code"></a><span data-ttu-id="6871a-154">添加表单代码</span><span class="sxs-lookup"><span data-stu-id="6871a-154">Add form code</span></span>

1. <span data-ttu-id="6871a-155">在 **OnLoad** 事件处理程序中，键入下面的代码：</span><span class="sxs-lookup"><span data-stu-id="6871a-155">In the **OnLoad** event handler, type the following code:</span></span> 
    
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

2. <span data-ttu-id="6871a-156">编译和预览该表单。</span><span class="sxs-lookup"><span data-stu-id="6871a-156">Compile and preview the form.</span></span>
    
   <span data-ttu-id="6871a-157">employee 文本框现在应当填写了您的用户名。</span><span class="sxs-lookup"><span data-stu-id="6871a-157">The employee text box should now be populated with your username.</span></span> 
    
<span data-ttu-id="6871a-158">有关如何部署托管的代码表单模板的信息，请参阅[替换代码中部署 InfoPath 表单模板](how-to-deploy-infopath-form-templates-with-code.md)。</span><span class="sxs-lookup"><span data-stu-id="6871a-158">For information about how to deploy a managed code form template, see [Deploy InfoPath Form Templates with Code](how-to-deploy-infopath-form-templates-with-code.md).</span></span> <span data-ttu-id="6871a-159">有关 InfoPath 对象模型以及创建使用 InfoPath 2003 兼容对象模型的托管代码表单模板的常见编程任务的信息，请参阅[了解 InfoPath 2003 对象模型](understanding-the-infopath-2003-object-model.md)。</span><span class="sxs-lookup"><span data-stu-id="6871a-159">For information on the InfoPath object model and common programming tasks in managed code form templates that work with the InfoPath 2003-compatible object model, see [Understanding the InfoPath 2003 Object Model](understanding-the-infopath-2003-object-model.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6871a-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6871a-160">See also</span></span>

- [<span data-ttu-id="6871a-161">使用 InfoPath 2003 对象模型初始化和清理代码</span><span class="sxs-lookup"><span data-stu-id="6871a-161">Initialization and Clean-up Code Using InfoPath 2003 Object Model</span></span>](initialization-and-clean-up-code-using-infopath-2003-object-model.md)
- [<span data-ttu-id="6871a-162">InfoPath 2003 兼容对象模型</span><span class="sxs-lookup"><span data-stu-id="6871a-162">InfoPath 2003 Compatible Object Models</span></span>](infopath-2003-compatible-object-models.md)
- [<span data-ttu-id="6871a-163">使用 InfoPath 2003 对象模型添加事件处理程序</span><span class="sxs-lookup"><span data-stu-id="6871a-163">Add an Event Handler Using the InfoPath 2003 Object Model</span></span>](how-to-add-an-event-handler-using-the-infopath-2003-object-model.md)

