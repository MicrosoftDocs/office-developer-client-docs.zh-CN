---
title: 使用脱机解决方案
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- offline solutions [infopath 2007],solutions [InfoPath 2007], offline,InfoPath 2007, offline solutions
localization_priority: Normal
ms.assetid: 108f9bd0-c80f-4790-a572-da2f571a7d85
description: InfoPath 对象模型提供 Application 类的 MachineOnlineState 属性，该属性使您的表单代码能够检查用户的计算机是否已连接至网络。通过检查 MachineOnlineState 属性的值，您的表单代码可以根据连接状态执行不同的操作。
ms.openlocfilehash: eb2903c2445a61be803c0d7a2f5ddd7ac7a912ad
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436137"
---
# <a name="work-with-offline-solutions"></a>使用脱机解决方案

InfoPath 对象模型提供 [Application](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.MachineOnlineState.aspx) 类的 [MachineOnlineState](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.aspx) 属性，该属性使您的表单代码能够检查用户的计算机是否已连接至网络。通过检查 **MachineOnlineState** 属性的值，您的表单代码可以根据连接状态执行不同的操作。 
  
## <a name="using-the-machineonlinestate-property"></a>使用 MachineOnlineState 属性

以下示例显示了如何在表单代码中添加逻辑，以确定如何根据用户计算机处于联机还是脱机状态来提交表单。
  
该示例假定您已创建了一个表单，用于提交包含名为 period 的域（指定报表所涵盖的月份和年份）的销售报表。还假定您已定义了数据连接以及当用户联机时用于提交报表的逻辑。 
  
### <a name="add-a-data-connection-that-submits-the-form-as-an-attachment-to-an-email-message"></a>添加将表单作为电子邮件附件提交的数据连接

1. 使用“空白(InfoPath 编辑器)”模板创建 InfoPath 表单模板。 
    
2. 在 InfoPath 设计模式下，单击“数据”选项卡上的“数据连接”。 
    
3. 在“数据连接”对话框中，单击“添加”。
    
4. 在“数据连接向导”中，单击“提交数据”，然后单击“下一步”。
    
5. 在向导的下一页，单击“作为电子邮件消息提交”，再单击“下一步”。
    
6. 在向导下一页的“收件人”框中，键入你的电子邮件地址。 
    
7. 在“主题”框中，执行下列操作以将销售时期与文本销售报表组合： 
    
   1. 单击“主题”框旁边的“公式”按钮。 
      
   2. 在“插入公式”对话框中，单击“插入函数”。
      
   3. 在“插入函数”对话框中，单击“类别”列表中的“文本”，然后双击“函数”列表中的“concat”。 
      
   4. 将”双击以插入字段“的第一个实例替换为以下内容（包括单引号）：'Sales Report: ' 
      
   5. 双击“双击以插入字段”的第二个实例。
      
   6. 在“选择字段或组”对话框中，选择销售时期字段。 
      
   7. 删除“双击以插入字段”的最后一个实例，然后单击“确定”。
    
8. 在向导中，单击“下一步”。
    
9. 在向导的下一页，单击“附件名称”框旁边的“公式”按钮，然后重复上述步骤创建公式 concat("Sales Report - ", period)，然后单击“下一步”。
    
10. 在向导最后一页的“输入该数据连接的名称”框中，键入“E-mail Submit”，然后单击“完成”。
    
### <a name="add-logic-for-submitting-the-form-depending-on-the-connected-state-of-a-users-computer"></a>添加用于提交表单的逻辑，具体取决于用户计算机的连接状态

1. 在 InfoPath 设计模式下，单击“数据”选项卡上的“提交选项”。 
    
2. 在“提交选项”对话框中，单击“允许用户提交此表单”，选择“使用代码执行自定义操作”，单击“编辑代码”。
    
3. 在 [Submit](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Submit.aspx) 事件处理程序下添加下面两个函数： 
    
   ```cs
    public void OnlineSubmit(SubmitEventArgs e)
    {
      // Logic for submitting online goes here.
    }
    public void OfflineSubmit(SubmitEventArgs e)
    {
      // Access and submit to the email connection.
      DataConnectionCollection myDataConnections =
          this.DataConnections;
      EmailSubmitConnection submitConnection =
          (EmailSubmitConnection)myDataConnections["Email Submit"];
      submitConnection.Execute();
      // Notify the user that the form was submitted offline.
      System.Text.StringBuilder myMessage = 
          new System.Text.StringBuilder();
      myMessage.Append("You submitted your Sales Report offline. ");
      myMessage.Append("Your Sales Report is in your outbox ");
      myMessage.Append("and will be submitted when you connect to ");
      myMessage.Append("the network.");
        MessageBox.Show(myMessage.ToString());
      // The submission was successful.
      e.CancelableArgs.Cancel = false;
    }
   ```

   ```vb
    Public Sub OnlineSubmit(ByVal e As SubmitEventArgs)
      ' Logic for submitting online goes here.
    End Sub
    Public Sub OfflineSubmit(ByVal e As SubmitEventArgs)
      ' Access and submit to the email connection.
      Dim myDataConnections As DataConnectionCollection = _
          Me.DataConnections
      Dim submitConnection As EmailSubmitConnection = _
          DirectCast(myDataConnections("Email Submit"), _
          EmailSubmitConnection)
      submitConnection.Execute
      ' Notify the user that the form was submitted offline.
      Dim myMessage As System.Text.StringBuilder = _
          New System.Text.StringBuilder()
      myMessage.Append("You submitted your Sales Report offline. ")
      myMessage.Append("Your Sales Report is in your outbox ")
      myMessage.Append("and will be submitted when you connect to ")
      myMessage.Append("the network.")
        MessageBox.Show(myMessage.ToString())
      ' The submission was successful.
      e.CancelableArgs.Cancel = False
    End Sub
   ```

4. 将下面的 **if** 语句添加到 [Submit](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Submit.aspx) 事件处理程序函数中。 
    
   ```cs
    // Check the computer's connection state.
    if (this.Application.MachineOnlineState == MachineState.Online)
    {
      OnlineSubmit(e);
    }
    else
    {
      OfflineSubmit(e);
    }
   ```

   ```vb
    ' Check the computer's connection state.
    If (Me.Application.MachineOnlineState = MachineState.Online) Then
      OnlineSubmit(e)
    Else
    {
      OfflineSubmit(e)
    End If
   ```

### <a name="test-the-code"></a>测试代码

1. 在“调试”菜单上，单击“启动调试”。
    
2. 填写表单。
    
3. 启动 Microsoft Internet Explorer。
    
4. 在 Internet Explorer 中，单击“文件”菜单上的“脱机工作”。 
    
5. 在 InfoPath 中，单击“提交”。 应该会看到一条消息，指出表单将作为电子邮件提交。
    
6. 单击“发送”。您应该看到一条消息，指出表单已脱机提交并将在您连接至网络时提交。
    
## <a name="see-also"></a>另请参阅

- [设计供脱机时使用的表单模板](https://support.office.com/en-us/article/design-a-form-template-for-offline-use-3ab8de84-babc-4bd7-9215-66d308546be4)

