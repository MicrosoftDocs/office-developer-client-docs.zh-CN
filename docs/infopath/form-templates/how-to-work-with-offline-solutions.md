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
ms.openlocfilehash: fcdaae31dd6a0c76cf1c453f267be430a2b34bba
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773993"
---
# <a name="work-with-offline-solutions"></a><span data-ttu-id="df5f3-105">使用脱机解决方案</span><span class="sxs-lookup"><span data-stu-id="df5f3-105">Work with Offline Solutions?</span></span>

<span data-ttu-id="df5f3-p102">InfoPath 对象模型提供 [Application](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.MachineOnlineState.aspx) 类的 [MachineOnlineState](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.aspx) 属性，该属性使您的表单代码能够检查用户的计算机是否已连接至网络。通过检查 **MachineOnlineState** 属性的值，您的表单代码可以根据连接状态执行不同的操作。</span><span class="sxs-lookup"><span data-stu-id="df5f3-p102">The InfoPath object model provides the [MachineOnlineState](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.MachineOnlineState.aspx) property of the [Application](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.aspx) class that enables your form code to check whether the user's computer is connected to the network. By checking the value of **MachineOnlineState** property, your form code can perform different actions depending on the state of the connection.</span></span> 
  
## <a name="using-the-machineonlinestate-property"></a><span data-ttu-id="df5f3-108">使用 MachineOnlineState 属性</span><span class="sxs-lookup"><span data-stu-id="df5f3-108">Using the MachineOnlineState Property</span></span>

<span data-ttu-id="df5f3-109">以下示例显示了如何在表单代码中添加逻辑，以确定如何根据用户计算机处于联机还是脱机状态来提交表单。</span><span class="sxs-lookup"><span data-stu-id="df5f3-109">The following example shows how you can add logic to your form code that determines how to submit a form based on whether the user's computer is online or offline.</span></span>
  
<span data-ttu-id="df5f3-p103">该示例假定您已创建了一个表单，用于提交包含名为 period 的域（指定报表所涵盖的月份和年份）的销售报表。还假定您已定义了数据连接以及当用户联机时用于提交报表的逻辑。</span><span class="sxs-lookup"><span data-stu-id="df5f3-p103">This example assumes that you have created a form for submitting a sales report that contains a field named period that specifies the month and year covered in the report. It also assumes that you have already defined a data connection and the logic for submitting the report when the user is online.</span></span> 
  
### <a name="add-a-data-connection-that-submits-the-form-as-an-attachment-to-an-email-message"></a><span data-ttu-id="df5f3-112">添加将表单作为电子邮件附件提交的数据连接</span><span class="sxs-lookup"><span data-stu-id="df5f3-112">Add a data connection that submits the form as an attachment to an e-mail message</span></span>

1. <span data-ttu-id="df5f3-113">使用“空白(InfoPath 编辑器)”**** 模板创建 InfoPath 表单模板。</span><span class="sxs-lookup"><span data-stu-id="df5f3-113">Create an InfoPath form template using the **Blank (InfoPath Editor)** template.</span></span> 
    
2. <span data-ttu-id="df5f3-114">在 InfoPath 设计模式下，单击“数据”**** 选项卡上的“数据连接”****。</span><span class="sxs-lookup"><span data-stu-id="df5f3-114">In InfoPath design mode, click **Data Connections** on the **Data** tab.</span></span> 
    
3. <span data-ttu-id="df5f3-115">在“数据连接”**** 对话框中，单击“添加”****。</span><span class="sxs-lookup"><span data-stu-id="df5f3-115">In the **Data Connections** dialog box, click **Add**.</span></span>
    
4. <span data-ttu-id="df5f3-116">在“数据连接向导”**** 中，单击“提交数据”****，然后单击“下一步”****。</span><span class="sxs-lookup"><span data-stu-id="df5f3-116">In the **Data Connection Wizard**, click **Submit data**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="df5f3-117">在向导的下一页，单击“作为电子邮件消息提交”****，再单击“下一步”****。</span><span class="sxs-lookup"><span data-stu-id="df5f3-117">On the next page of the wizard, click **As an e-mail message**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="df5f3-118">在向导下一页的“收件人”**** 框中，键入你的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="df5f3-118">On the next page of the wizard, type your e-mail address in the **To** box.</span></span> 
    
7. <span data-ttu-id="df5f3-119">在“主题”**** 框中，执行下列操作以将销售时期与文本销售报表组合：</span><span class="sxs-lookup"><span data-stu-id="df5f3-119">In the **Subject** box, do the following to combine the sales period with the text Sales Report:</span></span> 
    
   1. <span data-ttu-id="df5f3-120">单击“主题”**** 框旁边的“公式”**** 按钮。</span><span class="sxs-lookup"><span data-stu-id="df5f3-120">Click the **Formula **button next to the **Subject** box.</span></span> 
      
   2. <span data-ttu-id="df5f3-121">在“插入公式”**** 对话框中，单击“插入函数”****。</span><span class="sxs-lookup"><span data-stu-id="df5f3-121">In the **Insert Formula** dialog box, click **Insert Function**.</span></span>
      
   3. <span data-ttu-id="df5f3-122">在“插入函数”**** 对话框中，单击“类别”**** 列表中的“文本”****，然后双击“函数”**** 列表中的“concat”****。</span><span class="sxs-lookup"><span data-stu-id="df5f3-122">In the **Insert Function** dialog box, click **Text** in the **Categories** list, and then double-click **concat** in the **Functions** list.</span></span> 
      
   4. <span data-ttu-id="df5f3-123">将”双击以插入字段“**** 的第一个实例替换为以下内容（包括单引号）：'Sales Report: '</span><span class="sxs-lookup"><span data-stu-id="df5f3-123">Replace the first instance of **double click to insert field** with the following (include the single quotes): 'Sales Report: '</span></span> 
      
   5. <span data-ttu-id="df5f3-124">双击“双击以插入字段”**** 的第二个实例。</span><span class="sxs-lookup"><span data-stu-id="df5f3-124">Double-click the second instance of **double click to insert field**.</span></span>
      
   6. <span data-ttu-id="df5f3-125">在“选择字段或组”**** 对话框中，选择销售时期字段。</span><span class="sxs-lookup"><span data-stu-id="df5f3-125">In the **Select a Field or Group** dialog box, select the period field.</span></span> 
      
   7. <span data-ttu-id="df5f3-126">删除“双击以插入字段”**** 的最后一个实例，然后单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="df5f3-126">Delete the final instance of **double click to insert field**, and then click **OK**.</span></span>
    
8. <span data-ttu-id="df5f3-127">在向导中，单击“下一步”****。</span><span class="sxs-lookup"><span data-stu-id="df5f3-127">In the wizard, click **Next**.</span></span>
    
9. <span data-ttu-id="df5f3-128">在向导的下一页，单击“附件名称”**** 框旁边的“公式”**** 按钮，然后重复上述步骤创建公式 concat("Sales Report - ", period)，然后单击“下一步”****。</span><span class="sxs-lookup"><span data-stu-id="df5f3-128">On the next page of the wizard, click the Formula button next to the Attachment Name box, and then repeat the steps above to create the formula concat("Sales Report - ", period), and then click Next.</span></span>
    
10. <span data-ttu-id="df5f3-129">在向导最后一页的“输入该数据连接的名称”**** 框中，键入“E-mail Submit”，然后单击“完成”****。</span><span class="sxs-lookup"><span data-stu-id="df5f3-129">On the last page of the wizard, type E-mail Submit in the **Enter a name for this data connection** box, and then click **Finish**.</span></span>
    
### <a name="add-logic-for-submitting-the-form-depending-on-the-connected-state-of-a-users-computer"></a><span data-ttu-id="df5f3-130">添加用于提交表单的逻辑，具体取决于用户计算机的连接状态</span><span class="sxs-lookup"><span data-stu-id="df5f3-130">Add logic for submitting the form depending on the connected state of a user's computer</span></span>

1. <span data-ttu-id="df5f3-131">在 InfoPath 设计模式下，单击“数据”**** 选项卡上的“提交选项”****。</span><span class="sxs-lookup"><span data-stu-id="df5f3-131">In InfoPath design mode, click **Submit Options** on the **Data** tab.</span></span> 
    
2. <span data-ttu-id="df5f3-132">在“提交选项”**** 对话框中，单击“允许用户提交此表单”****，选择“使用代码执行自定义操作”****，单击“编辑代码”****。</span><span class="sxs-lookup"><span data-stu-id="df5f3-132">In the **Submit Options** dialog box, click **Allow users to submit this form**, select **Perform custom action using Code**, click **Edit Code**.</span></span>
    
3. <span data-ttu-id="df5f3-133">在 [Submit](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Submit.aspx) 事件处理程序下添加下面两个函数：</span><span class="sxs-lookup"><span data-stu-id="df5f3-133">Add the following two functions below the [Submit](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Submit.aspx) event handler:</span></span> 
    
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

4. <span data-ttu-id="df5f3-134">将下面的 **if** 语句添加到 [Submit](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Submit.aspx) 事件处理程序函数中。</span><span class="sxs-lookup"><span data-stu-id="df5f3-134">Add the following **if** statement to the [Submit](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Submit.aspx) event handler function.</span></span> 
    
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

### <a name="test-the-code"></a><span data-ttu-id="df5f3-135">测试代码</span><span class="sxs-lookup"><span data-stu-id="df5f3-135">Test the code</span></span>

1. <span data-ttu-id="df5f3-136">在“调试”**** 菜单上，单击“启动调试”****。</span><span class="sxs-lookup"><span data-stu-id="df5f3-136">On the **Debug** menu, click **Start Debugging**.</span></span>
    
2. <span data-ttu-id="df5f3-137">填写表单。</span><span class="sxs-lookup"><span data-stu-id="df5f3-137">Fill out the form.</span></span>
    
3. <span data-ttu-id="df5f3-138">启动 Microsoft Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="df5f3-138">Start Microsoft Internet Explorer.</span></span>
    
4. <span data-ttu-id="df5f3-139">在 Internet Explorer 中，单击“文件”**** 菜单上的“脱机工作”****。</span><span class="sxs-lookup"><span data-stu-id="df5f3-139">In Internet Explorer, click **Work offline** on the **File** menu.</span></span> 
    
5. <span data-ttu-id="df5f3-140">在 InfoPath 中，单击“提交”****。</span><span class="sxs-lookup"><span data-stu-id="df5f3-140">In InfoPath, click **Submit**.</span></span> <span data-ttu-id="df5f3-141">你应当看到一条消息，指出表单将作为电子邮件提交。</span><span class="sxs-lookup"><span data-stu-id="df5f3-141">In InfoPath, click Submit. You should see a message that the form will be submitted as an e-mail message.</span></span>
    
6. <span data-ttu-id="df5f3-142">单击“发送”****。</span><span class="sxs-lookup"><span data-stu-id="df5f3-142">Click **Send**.</span></span> <span data-ttu-id="df5f3-143">你应该看到一条消息，指出表单已脱机提交并将在你连接至网络时提交。</span><span class="sxs-lookup"><span data-stu-id="df5f3-143">Click Send. You should see a message stating that the form has been submitted offline and will be submitted when you connect to the network.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="df5f3-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df5f3-144">See also</span></span>

- [<span data-ttu-id="df5f3-145">设计供脱机时使用的表单模板</span><span class="sxs-lookup"><span data-stu-id="df5f3-145">Design a form template for offline use</span></span>](http://office.microsoft.com/en-us/infopath/HA102117391033.aspx?pid=CH100341121033)
