---
title: 将值记录到域中进行调试
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 5874dc28-1b10-48a3-8287-9474db0b7435
description: 当调试 InfoPath 表单模板时，将值直接记录到表单中的某个域以创建表单测试会话期间的调试数据记录，这种做法通常会很有用。下面的过程演示如何创建一个多行域，然后将帮助程序函数添加到表单代码以便使您能够将调试数据记录到该域中。
ms.openlocfilehash: 28f2a1ad3c13aefd9f898bdf397c9103df98d3c9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303575"
---
# <a name="log-values-to-a-field-for-debugging"></a>将值记录到域中进行调试

当调试 InfoPath 表单模板时，将值直接记录到表单中的某个域以创建表单测试会话期间的调试数据记录，这种做法通常会很有用。下面的过程演示如何创建一个多行域，然后将帮助程序函数添加到表单代码以便使您能够将调试数据记录到该域中。
  
## <a name="create-a-multi-line-text-field"></a>创建多行文本域

1. 向表单中添加****“文本框”控件，然后调整其大小以便可以显示多行。 
    
2. 右键单击文本框，单击“文本框属性”****，然后单击“显示”**** 选项卡上的“多行”**** 复选框。 
    
## <a name="add-helper-functions-to-log-debug-information-to-the-field"></a>添加帮助程序函数将调试信息记录到域中

1. 在“开发人员”**** 选项卡上，单击“代码编辑器”****，然后在出现提示时保存表单模板。
    
2. 在代码编辑器中，将以下三个帮助程序函数添加到表单代码文件中的公共类。
    
   > [!IMPORTANT]
   > 对于绑定到您在第一步创建的控件的域，确保将为  `debugFieldXpath` 函数中的  `AddToDebugField` 变量设置的值更新为正确的 XPath 表达式。 
  
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
> 如果使用 Visual Basic，则将 `Imports Microsoft.VisualBasic.Constants` 添加到表单代码文件顶部的指令。 
  
## <a name="test-the-addtodebugfield-function"></a>测试 AddToDebugField 函数

1. 在“开发人员”**** 选项卡上，单击“加载事件”****，然后将以下代码行添加到事件处理程序。
    
   ```cs
    AddToDebugField("Form loaded");
   ```

   ```vb
    AddToDebugField("Form loaded")
   ```

2. 在“开发人员”**** 选项卡上，单击“ViewSwitched 事件”****，然后将以下代码行添加到事件处理程序。
    
   ```cs
    AddToDebugField("View switched: " + this.CurrentView.ViewInfo.Name);
   ```

   ```vb
    AddToDebugField("View switched: " &amp; Me.CurrentView.ViewInfo.Name)
   ```

3. 在“主页”**** 选项卡上，单击“预览”****。
    
   调试域应显示两项：一项指示加载了表单，另一项指示视图的名称。这些示例使用针对打开表单时发生的事件的事件处理程序。但是，在加载表单之后，除了在表单上下文中运行的其他任何代码以外，您还可以从其他事件处理程序调用  `AddToDebugField` 函数。 
  

