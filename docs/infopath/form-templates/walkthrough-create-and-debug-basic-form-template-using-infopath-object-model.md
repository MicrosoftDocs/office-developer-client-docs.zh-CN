---
title: Walkthrough： Create and debug a basic 表单模板 using the InfoPath object model
manager: soliver
ms.date: 01/13/2015
ms.audience: Developer
keywords:
- form templates [infopath 2007]， walkthroughs，form templates [InfoPath 2007]， creating InfoPath 2003-compatible，InfoPath 2003-compatible form templates， walkthroughs
localization_priority: Normal
ms.assetid: 7658705f-c062-49a1-bea6-837737df2425
description: 本主题演示了如何创建与 Microsoft 提供的 InfoPath 2003 兼容表单模板 InfoPath 托管代码模型。Office.Interop.InfoPath.SemiTrust 命名空间。
ms.openlocfilehash: c559aedad5c62134c796196c63c1a84f70c4dc3e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414338"
---
# <a name="walkthrough-create-and-debug-a-basic-form-template-using-the-infopath-object-model"></a><span data-ttu-id="9ad9c-104">Walkthrough： Create and debug a basic 表单模板 using the InfoPath object model</span><span class="sxs-lookup"><span data-stu-id="9ad9c-104">Walkthrough: Create and debug a basic form template using the InfoPath object model</span></span>

<span data-ttu-id="9ad9c-105">本主题演示了如何创建与[Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx)命名空间提供的 InfoPath 2003 兼容对象模型兼容的基本 InfoPath 托管代码 表单模板。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-105">This topic provides a walkthrough of creating a basic InfoPath managed code form template that works with the InfoPath 2003-compatible object model provided by the [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) namespace.</span></span> 
  
## <a name="hello-world"></a><span data-ttu-id="9ad9c-106">Hello World</span><span class="sxs-lookup"><span data-stu-id="9ad9c-106">Hello World</span></span>

<span data-ttu-id="9ad9c-107">在下面的示例中，您将了解如何使用 InfoPath 2003 兼容对象模型的 [Alert](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.Alert.aspx) 方法显示简单的警报对话框。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-107">In the following example, you will learn how to display a simple alert dialog box by using the [Alert](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.Alert.aspx) method of the InfoPath 2003-compatible object model.</span></span> 
  
### <a name="create-a-new-infopath-form-template-that-works-with-the-infopath-2003-compatible-object-model"></a><span data-ttu-id="9ad9c-108">新建使用 InfoPath 2003 兼容对象模型的 InfoPath 表单模板</span><span class="sxs-lookup"><span data-stu-id="9ad9c-108">Create a new InfoPath form template that works with the InfoPath 2003-compatible object model</span></span>

1. <span data-ttu-id="9ad9c-109">创建一表单模板 InfoPath 2003 兼容对象模型的新模板，如使用 [InfoPath 2003](how-to-create-a-form-template-using-the-infopath-2003-object-model.md)对象模型创建表单模板中所述。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-109">Create a new form template that works with the InfoPath 2003-compatible object model, as described in [Create a Form Template Using the InfoPath 2003 Object Model](how-to-create-a-form-template-using-the-infopath-2003-object-model.md).</span></span>
    
2. <span data-ttu-id="9ad9c-110">将该表单模板项目命名为 HelloWorld 并保存它。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-110">Name the form template project HelloWorld and save it.</span></span> 
    
   <span data-ttu-id="9ad9c-p101">项目系统会创建代码文件和项目文件，然后在 InfoPath 设计模式下打开一个空白的表单模板。现在可以添加事件处理程序了。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-p101">The project system creates code and project files, and then opens a blank form template in InfoPath design mode. You are now ready to add event handlers.</span></span>
    
### <a name="add-a-button-with-an-onclick-event-handler"></a><span data-ttu-id="9ad9c-113">添加包含 OnClick 事件处理程序的按钮</span><span class="sxs-lookup"><span data-stu-id="9ad9c-113">Add a button with an OnClick event handler</span></span>

1. <span data-ttu-id="9ad9c-114">在“主页”选项卡的“控件”部分，单击“按钮”控件以将其插入视图中。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-114">In the **Controls** section on the **Home** tab, click the **Button** control to insert it into the view.</span></span> 
    
2. <span data-ttu-id="9ad9c-115">右键单击该控件，然后单击“按钮属性”。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-115">Right-click the control, and then click **Button Properties**.</span></span>
    
3. <span data-ttu-id="9ad9c-116">将" **标签"** 更改为"警报"。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-116">Change the **Label** to Alert.</span></span>
    
4. <span data-ttu-id="9ad9c-117">将 **ID 更改为** AlertID。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-117">Change the **ID** to AlertID.</span></span>
    
5. <span data-ttu-id="9ad9c-118">单击“编辑表单代码”。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-118">Click **Edit Form Code**.</span></span>
    
   <span data-ttu-id="9ad9c-119">将创建[OnClick](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._ButtonEventSink_Event.OnClick.aspx)事件的事件处理程序框架，并且焦点将移动到 Visual Studio 2012 中的代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-119">An event handler skeleton for the [OnClick](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._ButtonEventSink_Event.OnClick.aspx) event is created and the focus moves to the code editor in Visual Studio 2012.</span></span> <span data-ttu-id="9ad9c-120">有关使用事件处理程序的信息，请参阅 [使用 InfoPath 2003 对象模型添加事件处理程序](how-to-add-an-event-handler-using-the-infopath-2003-object-model.md)。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-120">For more information on working with event handlers, see [Add an Event Handler Using the InfoPath 2003 Object Model](how-to-add-an-event-handler-using-the-infopath-2003-object-model.md).</span></span> 
    
   <span data-ttu-id="9ad9c-121">现在可以向该按钮的事件处理程序中添加表单代码了。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-121">You are now ready to add form code to the event handler for the button.</span></span>
    
### <a name="add-form-code-to-the-event-handler"></a><span data-ttu-id="9ad9c-122">向事件处理程序中添加表单代码</span><span class="sxs-lookup"><span data-stu-id="9ad9c-122">Add form code to the event handler</span></span>

1. <span data-ttu-id="9ad9c-123">在 **OnClick** 事件处理程序中，键入下面的代码：</span><span class="sxs-lookup"><span data-stu-id="9ad9c-123">In the **OnClick** event handler, type the following code:</span></span> 
    
   ```cs
    thisXDocument.UI.Alert("Hello World!");
   ```

   ```vb
    thisXDocument.UI.Alert("Hello World!")
   ```

   <span data-ttu-id="9ad9c-p103">请注意，在代码行中每键入一个句点之后，都会显示一个 Microsoft IntelliSense 下拉列表。整个事件处理程序看上去应当如下所示：</span><span class="sxs-lookup"><span data-stu-id="9ad9c-p103">Note that a Microsoft IntelliSense drop-down list is displayed after you type each period in the line of code. The entire event handler should look like the following:</span></span>
    
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
   > <span data-ttu-id="9ad9c-126">除了 **Alert** 方法，还可以使用 **System.Windows.Forms** 命名空间的 **MessageBox.Show** 方法来显示消息框。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-126">As an alternative to using the **Alert** method, you can use the **MessageBox.Show** method of the **System.Windows.Forms** namespace to display a message box.</span></span> <span data-ttu-id="9ad9c-127">为此，您必须添加对 System 的引用。Windows。表单程序集，在代码文件的开头添加或添加到指令，然后键入一行代码 `using System.Windows.Forms;` `Imports System.Windows.Forms` ，如下所示：`MessageBox.Show("Hello World!); or MessageBox.Show("Hello World!)`</span><span class="sxs-lookup"><span data-stu-id="9ad9c-127">To do so, you must add a reference to the System.Windows.Forms assembly, add  `using System.Windows.Forms;` or  `Imports System.Windows.Forms` to the directives at the beginning of your code file, and then type a line of code such as the following:  `MessageBox.Show("Hello World!); or MessageBox.Show("Hello World!)`</span></span>
  
2. <span data-ttu-id="9ad9c-128">切换到 InfoPath 设计模式窗口，然后单击“主页”选项卡上的“预览”按钮。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-128">Switch to the InfoPath design mode window, and then click the **Preview** button on the **Home** tab.</span></span> 
    
3. <span data-ttu-id="9ad9c-129">在“预览”窗口中，单击“Alert”按钮。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-129">In the **Preview** window, click the **Alert** button.</span></span> 
    
   <span data-ttu-id="9ad9c-130">将显示一个消息框，其中包含“Hello World!”文本。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-130">A message box will be displayed with the text "Hello World!"</span></span>
    
   <span data-ttu-id="9ad9c-131">下一个过程演示如何向表单代码中添加调试断点。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-131">The next procedure shows how to add debugging breakpoints to your form code.</span></span>
    
### <a name="debug-form-code"></a><span data-ttu-id="9ad9c-132">调试表单代码</span><span class="sxs-lookup"><span data-stu-id="9ad9c-132">Debug form code</span></span>

1. <span data-ttu-id="9ad9c-133">在代码编辑器中，单击该行左侧的灰条：</span><span class="sxs-lookup"><span data-stu-id="9ad9c-133">In the code editor, click the grey bar to the left of the line:</span></span>
    
   ```cs
    thisXDocument.UI.Alert("Hello World!");
   ```

   ```vb
    thisXDocument.UI.Alert("Hello World!")
   ```

   <span data-ttu-id="9ad9c-134">将显示一个红色圆圈，并且该代码行突出显示，指示运行时将在表单代码中的此断点处暂停。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-134">A red circle is displayed and the line of code is highlighted to indicate that the runtime will pause at this breakpoint in your form code.</span></span>
    
2. <span data-ttu-id="9ad9c-135">在“调试”菜单上，单击“启动调试”（或按 F5）。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-135">On the **Debug** menu, click **Start Debugging** (or press F5).</span></span> 
    
3. <span data-ttu-id="9ad9c-136">在 InfoPath 的“预览”窗口中，单击“Alert”按钮。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-136">In the InfoPath **Preview** window, click the **Alert** button.</span></span> 
    
   <span data-ttu-id="9ad9c-137">代码编辑器将获得焦点，并且断点行突出显示。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-137">The code editor is given focus, and the breakpoint line is highlighted.</span></span>
    
4. <span data-ttu-id="9ad9c-138">在“调试”菜单上，单击“单步执行(跳过过程)”（或按 Shift+F8）继续单步执行代码。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-138">On the **Debug** menu, click **Step Over** (or press Shift+F8) to continue stepping through the code.</span></span> 
    
   <span data-ttu-id="9ad9c-139">将执行 **Alert** 方法代码，并运行"Hello World！"</span><span class="sxs-lookup"><span data-stu-id="9ad9c-139">The **Alert** method code is executed, and the "Hello World!"</span></span> <span data-ttu-id="9ad9c-140">警报显示在 InfoPath 预览 **窗口中** 。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-140">alert is displayed in the InfoPath **Preview** window.</span></span> 
    
## <a name="getting-the-current-users-name"></a><span data-ttu-id="9ad9c-141">获取当前用户的名称</span><span class="sxs-lookup"><span data-stu-id="9ad9c-141">Getting the Current User's Name</span></span>

<span data-ttu-id="9ad9c-p106">通过使用 .NET Framework 类，可以访问不便通过脚本使用的功能。在此示例中，您将了解如何使用 .NET Framework 类来检索当前用户的名称。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-p106">By using the .NET Framework classes, you can get access to functionality that was not easily available in script. In this example, you will learn how use the .NET Framework classes to retrieve the name of the current user.</span></span>
  
### <a name="add-an-onload-event-handler"></a><span data-ttu-id="9ad9c-144">添加 OnLoad 事件处理程序</span><span class="sxs-lookup"><span data-stu-id="9ad9c-144">Add an OnLoad event handler</span></span>

1. <span data-ttu-id="9ad9c-145">打开前面创建的 InfoPath HelloWorld 项目。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-145">Open the InfoPath HelloWorld project that you created earlier.</span></span>
    
2. <span data-ttu-id="9ad9c-146">在“视图”选项卡上，单击“显示域”。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-146">On the **View** tab, click **Show Fields**.</span></span>
    
3. <span data-ttu-id="9ad9c-147">右键单击“myFields”节点，然后单击“添加”。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-147">Right-click the **myFields** node, and then click **Add**.</span></span>
    
4. <span data-ttu-id="9ad9c-148">在“名称”中，键入“employee”，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-148">In **Name**, type **employee**, then click **OK**.</span></span>
    
5. <span data-ttu-id="9ad9c-149">将“employee”节点拖到视图中。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-149">Drag the **employee** node into the view.</span></span> 
    
6. <span data-ttu-id="9ad9c-150">在“开发工具”选项卡上，单击“OnLoad 事件”。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-150">On the **Developer** tab, click **On Load Event**.</span></span>
    
   <span data-ttu-id="9ad9c-151">这将为 [OnLoad](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnLoad.aspx) 事件创建事件处理程序，并且焦点将移动到代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-151">This will create an event handler for the [OnLoad](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnLoad.aspx) event, and focus moves to the code editor.</span></span> <span data-ttu-id="9ad9c-152">每次加载表单时，都将调用该事件处理程序中的代码。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-152">The code in this event handler will be called each time the form is loaded.</span></span> <span data-ttu-id="9ad9c-153">下一个过程演示如何将检索用户名的表单代码添加到事件处理程序中。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-153">The next procedure shows how to add form code that retrieves the user's name to the event handler.</span></span> 
    
### <a name="add-form-code"></a><span data-ttu-id="9ad9c-154">添加表单代码</span><span class="sxs-lookup"><span data-stu-id="9ad9c-154">Add form code</span></span>

1. <span data-ttu-id="9ad9c-155">在 **OnLoad** 事件处理程序中，键入下面的代码：</span><span class="sxs-lookup"><span data-stu-id="9ad9c-155">In the **OnLoad** event handler, type the following code:</span></span> 
    
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

2. <span data-ttu-id="9ad9c-156">编译和预览该表单。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-156">Compile and preview the form.</span></span>
    
   <span data-ttu-id="9ad9c-157">employee 文本框现在应当填写了您的用户名。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-157">The employee text box should now be populated with your username.</span></span> 
    
<span data-ttu-id="9ad9c-158">若要了解如何部署托管代码模板表单模板，请参阅部署包含代码的 [InfoPath 表单模板](how-to-deploy-infopath-form-templates-with-code.md)。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-158">For information about how to deploy a managed code form template, see [Deploy InfoPath Form Templates with Code](how-to-deploy-infopath-form-templates-with-code.md).</span></span> <span data-ttu-id="9ad9c-159">有关 InfoPath 对象模型以及使用 InfoPath 2003 兼容对象模型的托管代码表单模板中的常见编程任务的信息，请参阅了解 [InfoPath 2003 对象模型](understanding-the-infopath-2003-object-model.md)。</span><span class="sxs-lookup"><span data-stu-id="9ad9c-159">For information on the InfoPath object model and common programming tasks in managed code form templates that work with the InfoPath 2003-compatible object model, see [Understanding the InfoPath 2003 Object Model](understanding-the-infopath-2003-object-model.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9ad9c-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9ad9c-160">See also</span></span>

- [<span data-ttu-id="9ad9c-161">使用 InfoPath 2003 对象模型初始化和清理代码</span><span class="sxs-lookup"><span data-stu-id="9ad9c-161">Initialization and Clean-up Code Using InfoPath 2003 Object Model</span></span>](initialization-and-clean-up-code-using-infopath-2003-object-model.md)
- [<span data-ttu-id="9ad9c-162">InfoPath 2003 兼容对象模型</span><span class="sxs-lookup"><span data-stu-id="9ad9c-162">InfoPath 2003 Compatible Object Models</span></span>](infopath-2003-compatible-object-models.md)
- [<span data-ttu-id="9ad9c-163">使用 InfoPath 2003 对象模型添加事件处理程序</span><span class="sxs-lookup"><span data-stu-id="9ad9c-163">Add an Event Handler Using the InfoPath 2003 Object Model</span></span>](how-to-add-an-event-handler-using-the-infopath-2003-object-model.md)

