---
title: 使用 InfoPath 对象模型处理脱机解决方案
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- solutions [infopath 2007], offline,offline solutions [InfoPath 2007], InfoPath 2003-compatible form templates,InfoPath 2003-compatible form templates, offline solutions
localization_priority: Normal
ms.assetid: 634ccd8c-0b5f-4161-875c-0e546a517377
description: InfoPath 2003 兼容对象模型提供了 Application 对象的 MachineOnlineState 属性，该属性使您的表单代码可以检查用户的计算机是否已连接至网络。根据连接状态的不同，表单代码可以执行不同的操作。
ms.openlocfilehash: 452eb0d92b09dc0c3f9b2c247f7cda243dc8eb13
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303568"
---
# <a name="work-with-offline-solutions-using-the-infopath-object-model"></a>使用 InfoPath 对象模型处理脱机解决方案

InfoPath 2003 兼容对象模型提供了 [Application](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._Application2.MachineOnlineState.aspx) 对象的 [MachineOnlineState](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Application.aspx) 属性，该属性使您的表单代码可以检查用户的计算机是否已连接至网络。根据连接状态的不同，表单代码可以执行不同的操作。 
  
## <a name="using-the-machineonlinestate-property"></a>使用 MachineOnlineState 属性

以下示例显示了如何在表单代码中添加逻辑，以确定如何根据用户计算机处于联机还是脱机状态来提交表单。
  
此示例假定您已创建了一个表单，用于提交包含名为"period"的域（该域指定报表所涵盖的月份和年份）的销售报表。还假定您已定义了数据连接以及当用户联机时用于提交报表的逻辑。
  
### <a name="add-a-data-connection-that-submits-the-form-as-an-attachment-to-an-email-message"></a>添加将表单作为电子邮件附件提交的数据连接

1. 创建或打开 InfoPath 托管代码表单模板。
    
2. 在 InfoPath 设计模式下，在“数据”**** 选项卡上，单击“数据连接”****。
    
3. 在“数据连接”**** 对话框中，单击“添加”****。
    
4. 在“数据连接向导”**** 中，单击“提交数据”****，然后单击“下一步”****。
    
5. 在向导的下一页，单击“作为电子邮件消息提交”****，再单击“下一步”****。
    
6. 在向导下一页的“收件人”**** 框中，键入你的电子邮件地址。 
    
7. 在“主题”**** 框中，执行下列操作以将销售时期与文本销售报表组合： 
    
   1. 单击“主题”**** 框旁边的“公式”**** 按钮。 
      
   2. 在“插入公式”**** 对话框中，单击“插入函数”****。
      
   3. 在“插入函数”**** 对话框中，单击“类别”**** 列表中的“文本”****，然后双击“函数”**** 列表中的“concat”****。 
      
   4. 将”双击以插入字段“**** 的第一个实例替换为以下内容（包括单引号）：'Sales Report: ' 
      
   5. 双击“双击以插入字段”**** 的第二个实例。
      
   6. 在“选择字段或组”**** 对话框中，选择销售时期字段。 
      
   7. 删除“双击以插入字段”**** 的最后一个实例，然后单击“确定”****。
    
8. 在向导中，单击“下一步”****。
    
9. 在向导下一页的“输入该数据连接的名称”**** 框中键入“E-mail Submit”，然后单击“完成”****。
    
### <a name="add-logic-for-submitting-the-form-depending-on-the-connected-state-of-a-users-computer"></a>添加用于提交表单的逻辑，具体取决于用户计算机的连接状态

1. 在 InfoPath 设计模式下，在“数据”**** 选项卡上，单击“提交选项”****。
    
2. 在“提交选项”**** 对话框中，单击“允许用户提交此表单”****，然后选择“使用代码执行自定义操作”****。
    
3. 单击“编辑代码”**** 按钮。 
    
4. 在 [OnSubmitRequest](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnSubmitRequest.aspx) 事件处理程序下添加以下两个函数： 
    
   ```cs
    public void OnlineSubmit(DocReturnEvent e)
    {
      // Logic for submitting online goes here.
    }
    public void OfflineSubmitX(DocReturnEvent e)
    {
      // Access and submit to the email adapter.
      DataAdaptersCollection myDataAdapters = 
          thisXDocument.DataAdapters;
      EmailAdapterObject submitAdapter = 
          (EmailAdapterObject) myDataAdapters["Email Submit"];
      submitAdapter.Submit();
      // Notify the user that the form was submitted offline.
      System.Text.StringBuilder message = 
      new System.Text.StringBuilder();
      message.Append("You submitted your Sales Report offline. ");
      message.Append("Your Sales Report is in your outbox ");
      message.Append("and will be submitted when you connect to ");
      message.Append("the network.");
        thisXDocument.UI.Alert(message.ToString());
      // The submission was successful.
      e.ReturnStatus = true;
    }
   ```

5. 将下面的 **if** 语句添加到 **OnSubmitRequest** 事件处理程序函数中。 
    
   ```cs
    // Check the computer's connection state.
    if (thisApplication.MachineOnlineState==XdMachineOnlineState.xdOnline)
    {
        OnlineSubmit(e);
    }
    else
    {
        OfflineSubmit(e);
    }
   ```

### <a name="test-the-code"></a>测试代码

1. 在 InfoPath 设计器中，单击“主页”**** 选项卡上的“预览”****。 
    
2. 填写表单。
    
3. 启动 Microsoft Internet Explorer。
    
4. 在 Internet Explorer 中，单击“文件”**** 菜单上的“脱机工作”****。 
    
5. 在 InfoPath 中，单击“提交”****。 应该会看到一条消息，指出表单将作为电子邮件提交。
    
6. Click **Send**. You should see a message stating that the form has been submitted offline.
    

