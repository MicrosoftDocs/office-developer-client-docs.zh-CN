---
title: 将值记录到域中进行调试
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 5874dc28-1b10-48a3-8287-9474db0b7435
description: 当调试 InfoPath 表单模板时，将值直接记录到表单中的某个域以创建表单测试会话期间的调试数据记录，这种做法通常会很有用。下面的过程演示如何创建一个多行域，然后将帮助程序函数添加到表单代码以便使您能够将调试数据记录到该域中。
ms.openlocfilehash: 28f2a1ad3c13aefd9f898bdf397c9103df98d3c9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431811"
---
# <a name="log-values-to-a-field-for-debugging"></a><span data-ttu-id="69380-104">将值记录到域中进行调试</span><span class="sxs-lookup"><span data-stu-id="69380-104">Log values to a field for debugging</span></span>

<span data-ttu-id="69380-p102">当调试 InfoPath 表单模板时，将值直接记录到表单中的某个域以创建表单测试会话期间的调试数据记录，这种做法通常会很有用。下面的过程演示如何创建一个多行域，然后将帮助程序函数添加到表单代码以便使您能够将调试数据记录到该域中。</span><span class="sxs-lookup"><span data-stu-id="69380-p102">When debugging an InfoPath form template, it is often useful to log values directly into a field in the form to create a record of debug data during a session of testing the form. The following procedures show how to create a multi-line field, and then add helper functions to the form code that enable you log debug data into that field.</span></span>
  
## <a name="create-a-multi-line-text-field"></a><span data-ttu-id="69380-107">创建多行文本域</span><span class="sxs-lookup"><span data-stu-id="69380-107">Create a multi-line text field</span></span>

1. <span data-ttu-id="69380-108">向表单中添加\*\*\*\*“文本框”控件，然后调整其大小以便可以显示多行。</span><span class="sxs-lookup"><span data-stu-id="69380-108">Add a **Text Box** control to the form, and then resize it so that it can display multiple lines.</span></span> 
    
2. <span data-ttu-id="69380-109">右键单击文本框，单击“文本框属性”\*\*\*\*，然后单击“显示”\*\*\*\* 选项卡上的“多行”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="69380-109">Right-click the text box, click **Text Box Properties**, and then click the **Multi-line** check box on the **Display** tab.</span></span> 
    
## <a name="add-helper-functions-to-log-debug-information-to-the-field"></a><span data-ttu-id="69380-110">添加帮助程序函数将调试信息记录到域中</span><span class="sxs-lookup"><span data-stu-id="69380-110">Add helper functions to log debug information to the field</span></span>

1. <span data-ttu-id="69380-111">在“开发人员”\*\*\*\* 选项卡上，单击“代码编辑器”\*\*\*\*，然后在出现提示时保存表单模板。</span><span class="sxs-lookup"><span data-stu-id="69380-111">On the **Developer** tab, click **Code Editor**, and then save the form template if you are prompted.</span></span>
    
2. <span data-ttu-id="69380-112">在代码编辑器中，将以下三个帮助程序函数添加到表单代码文件中的公共类。</span><span class="sxs-lookup"><span data-stu-id="69380-112">In the Code Editor, add the following three helper functions to the public class in the form code file.</span></span>
    
   > [!IMPORTANT]
   > <span data-ttu-id="69380-113">对于绑定到您在第一步创建的控件的域，确保将为  `debugFieldXpath` 函数中的  `AddToDebugField` 变量设置的值更新为正确的 XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="69380-113">Make sure that you update the value set for the  `debugFieldXpath` variable in the  `AddToDebugField` function to the correct XPath expression for the field bound to the control that you created in the first procedure.</span></span> 
  
    ```cs
        private void AddToDebugField(string valueToAdd)
        {
            // Update the value of debugFieldXpath to the XPath of the
            // multi-line field where you want to log debug information.
            string debugFieldXpath = "/my:myFields/my:field1";
            string headerLine = "----------------- " + DateTime.Now + 
                " -----------------" + "\r\n";
            SetDebugFieldValue(debugFieldXpath, headerLine + valueToAdd + 
                "\r\n" + GetDebugFieldValue(debugFieldXpath));
        }
        private string GetDebugFieldValue(string xpath)
        {
            return this.CreateNavigator().SelectSingleNode(xpath, 
                this.NamespaceManager).Value;
        }
        private void SetDebugFieldValue(string xpath, string value)
        {
            this.CreateNavigator().SelectSingleNode(xpath, 
                this.NamespaceManager).SetValue(value);
        }
    ```

    ```vb
        Private Sub AddToDebugField(ByVal valueToAdd As String)
            ' Update the value of debugFieldXpath to the XPath of the 
            ' multi-line field where you want to log debug information.
            Dim debugFieldXpath As String = "/my:myFields/my:field1"
            Dim headerLine As String = "----------------- " _
                &amp; DateTime.Now &amp; " -----------------" &amp; vbCrLf
            SetDebugFieldValue(debugFieldXpath, (headerLine &amp; valueToAdd &amp; vbCrLf) _
                &amp; GetDebugFieldValue(debugFieldXpath))
        End Sub
        Private Function GetDebugFieldValue(ByVal xpath As String) As String
            Return Me.CreateNavigator().SelectSingleNode(xpath, _
                Me.NamespaceManager).Value
        End Function
        Private Sub SetDebugFieldValue(ByVal xpath As String, ByVal value As String)
            Me.CreateNavigator().SelectSingleNode(xpath, _
                Me.NamespaceManager).SetValue(value)
        End Sub
    ```

> [!NOTE] 
> <span data-ttu-id="69380-114">如果使用 Visual Basic，则将 `Imports Microsoft.VisualBasic.Constants` 添加到表单代码文件顶部的指令。</span><span class="sxs-lookup"><span data-stu-id="69380-114">When using Visual Basic, add  `Imports Microsoft.VisualBasic.Constants` to the directives at the top of the form code file.</span></span> 
  
## <a name="test-the-addtodebugfield-function"></a><span data-ttu-id="69380-115">测试 AddToDebugField 函数</span><span class="sxs-lookup"><span data-stu-id="69380-115">Test the AddToDebugField function</span></span>

1. <span data-ttu-id="69380-116">在“开发人员”\*\*\*\* 选项卡上，单击“加载事件”\*\*\*\*，然后将以下代码行添加到事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="69380-116">On the **Developer** tab, click **Loading Event**, and then add the following line of code to the event handler.</span></span>
    
   ```cs
    AddToDebugField("Form loaded");
   ```

   ```vb
    AddToDebugField("Form loaded")
   ```

2. <span data-ttu-id="69380-117">在“开发人员”\*\*\*\* 选项卡上，单击“ViewSwitched 事件”\*\*\*\*，然后将以下代码行添加到事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="69380-117">On the **Developer** tab, click **View Switched Event**, and then add the following line of code to the event handler.</span></span>
    
   ```cs
    AddToDebugField("View switched: " + this.CurrentView.ViewInfo.Name);
   ```

   ```vb
    AddToDebugField("View switched: " &amp; Me.CurrentView.ViewInfo.Name)
   ```

3. <span data-ttu-id="69380-118">在“主页”\*\*\*\* 选项卡上，单击“预览”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="69380-118">On the **Home** tab, click **Preview**.</span></span>
    
   <span data-ttu-id="69380-p103">调试域应显示两项：一项指示加载了表单，另一项指示视图的名称。这些示例使用针对打开表单时发生的事件的事件处理程序。但是，在加载表单之后，除了在表单上下文中运行的其他任何代码以外，您还可以从其他事件处理程序调用  `AddToDebugField` 函数。</span><span class="sxs-lookup"><span data-stu-id="69380-p103">The debug field should display two entries: one indicating that the form is loaded, and another indicating the name of the view. These examples use event handlers for events that occur as the form is opened. However, after the form is loaded, you can call the  `AddToDebugField` function from other event handlers in addition to any other code running in the context of the form.</span></span> 
  

