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
ms.openlocfilehash: 858b5d317cf5245dbfb447fa9e118a11ecbe7eb3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773989"
---
# <a name="work-with-offline-solutions-using-the-infopath-object-model"></a><span data-ttu-id="ca20f-105">使用 InfoPath 对象模型处理脱机解决方案</span><span class="sxs-lookup"><span data-stu-id="ca20f-105">Work with offline solutions using the InfoPath object model</span></span>

<span data-ttu-id="ca20f-p102">InfoPath 2003 兼容对象模型提供了 [Application](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._Application2.MachineOnlineState.aspx) 对象的 [MachineOnlineState](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Application.aspx) 属性，该属性使您的表单代码可以检查用户的计算机是否已连接至网络。根据连接状态的不同，表单代码可以执行不同的操作。</span><span class="sxs-lookup"><span data-stu-id="ca20f-p102">The InfoPath 2003-compatible object model provides the [MachineOnlineState](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._Application2.MachineOnlineState.aspx) property of the [Application](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Application.aspx) object which enables your form code to check whether the user's computer is connected to the network. Your form code can perform different actions depending on the state of the connection.</span></span> 
  
## <a name="using-the-machineonlinestate-property"></a><span data-ttu-id="ca20f-108">使用 MachineOnlineState 属性</span><span class="sxs-lookup"><span data-stu-id="ca20f-108">Using the MachineOnlineState Property</span></span>

<span data-ttu-id="ca20f-109">以下示例显示了如何在表单代码中添加逻辑，以确定如何根据用户计算机处于联机还是脱机状态来提交表单。</span><span class="sxs-lookup"><span data-stu-id="ca20f-109">The following example shows how you can add logic to your form code that determines how to submit a form based on whether the user's computer is online or offline.</span></span>
  
<span data-ttu-id="ca20f-p103">此示例假定您已创建了一个表单，用于提交包含名为"period"的域（该域指定报表所涵盖的月份和年份）的销售报表。还假定您已定义了数据连接以及当用户联机时用于提交报表的逻辑。</span><span class="sxs-lookup"><span data-stu-id="ca20f-p103">This example assumes that you have created a form for submitting a sales report that contains a field named "period" that specifies the month and year covered in the report. It also assumes that you have already defined a data connection and the logic for submitting the report when the user is online.</span></span>
  
### <a name="add-a-data-connection-that-submits-the-form-as-an-attachment-to-an-email-message"></a><span data-ttu-id="ca20f-112">添加将表单作为电子邮件附件提交的数据连接</span><span class="sxs-lookup"><span data-stu-id="ca20f-112">Add a data connection that submits the form as an attachment to an e-mail message</span></span>

1. <span data-ttu-id="ca20f-113">创建或打开 InfoPath 托管代码表单模板。</span><span class="sxs-lookup"><span data-stu-id="ca20f-113">Create or open an InfoPath managed-code form template.</span></span>
    
2. <span data-ttu-id="ca20f-114">在 InfoPath 设计模式下，在“数据”**** 选项卡上，单击“数据连接”****。</span><span class="sxs-lookup"><span data-stu-id="ca20f-114">In InfoPath design mode, on the **Data** tab, click **Data Connections**.</span></span>
    
3. <span data-ttu-id="ca20f-115">在“数据连接”**** 对话框中，单击“添加”****。</span><span class="sxs-lookup"><span data-stu-id="ca20f-115">In the **Data Connections** dialog box, click **Add**.</span></span>
    
4. <span data-ttu-id="ca20f-116">在“数据连接向导”**** 中，单击“提交数据”****，然后单击“下一步”****。</span><span class="sxs-lookup"><span data-stu-id="ca20f-116">In the **Data Connection Wizard**, click **Submit data**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="ca20f-117">在向导的下一页，单击“作为电子邮件消息提交”****，再单击“下一步”****。</span><span class="sxs-lookup"><span data-stu-id="ca20f-117">On the next page of the wizard, click **As an e-mail message**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="ca20f-118">在向导下一页的“收件人”**** 框中，键入你的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="ca20f-118">On the next page of the wizard, type your e-mail address in the **To** box.</span></span> 
    
7. <span data-ttu-id="ca20f-119">在“主题”**** 框中，执行下列操作以将销售时期与文本销售报表组合：</span><span class="sxs-lookup"><span data-stu-id="ca20f-119">In the **Subject** box, do the following to combine the sales period with the text Sales Report:</span></span> 
    
   1. <span data-ttu-id="ca20f-120">单击“主题”**** 框旁边的“公式”**** 按钮。</span><span class="sxs-lookup"><span data-stu-id="ca20f-120">Click the **Formula **button next to the **Subject** box.</span></span> 
      
   2. <span data-ttu-id="ca20f-121">在“插入公式”**** 对话框中，单击“插入函数”****。</span><span class="sxs-lookup"><span data-stu-id="ca20f-121">In the **Insert Formula** dialog box, click **Insert Function**.</span></span>
      
   3. <span data-ttu-id="ca20f-122">在“插入函数”**** 对话框中，单击“类别”**** 列表中的“文本”****，然后双击“函数”**** 列表中的“concat”****。</span><span class="sxs-lookup"><span data-stu-id="ca20f-122">In the **Insert Function** dialog box, click **Text** in the **Categories** list, and then double-click **concat** in the **Functions** list.</span></span> 
      
   4. <span data-ttu-id="ca20f-123">将”双击以插入字段“**** 的第一个实例替换为以下内容（包括单引号）：'Sales Report: '</span><span class="sxs-lookup"><span data-stu-id="ca20f-123">Replace the first instance of **double click to insert field** with the following (include the single quotes): 'Sales Report: '</span></span> 
      
   5. <span data-ttu-id="ca20f-124">双击“双击以插入字段”**** 的第二个实例。</span><span class="sxs-lookup"><span data-stu-id="ca20f-124">Double-click the second instance of **double click to insert field**.</span></span>
      
   6. <span data-ttu-id="ca20f-125">在“选择字段或组”**** 对话框中，选择销售时期字段。</span><span class="sxs-lookup"><span data-stu-id="ca20f-125">In the **Select a Field or Group** dialog box, select the period field.</span></span> 
      
   7. <span data-ttu-id="ca20f-126">删除“双击以插入字段”**** 的最后一个实例，然后单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="ca20f-126">Delete the final instance of **double click to insert field**, and then click **OK**.</span></span>
    
8. <span data-ttu-id="ca20f-127">在向导中，单击“下一步”****。</span><span class="sxs-lookup"><span data-stu-id="ca20f-127">In the wizard, click **Next**.</span></span>
    
9. <span data-ttu-id="ca20f-128">在向导下一页的“输入该数据连接的名称”**** 框中键入“E-mail Submit”，然后单击“完成”****。</span><span class="sxs-lookup"><span data-stu-id="ca20f-128">On the next page of the wizard, type 'E-mail Submit' in the **Enter a name for this data connection** box, and then click **Finish**.</span></span>
    
### <a name="add-logic-for-submitting-the-form-depending-on-the-connected-state-of-a-users-computer"></a><span data-ttu-id="ca20f-129">添加用于提交表单的逻辑，具体取决于用户计算机的连接状态</span><span class="sxs-lookup"><span data-stu-id="ca20f-129">Add logic for submitting the form depending on the connected state of a user's computer</span></span>

1. <span data-ttu-id="ca20f-130">在 InfoPath 设计模式下，在“数据”**** 选项卡上，单击“提交选项”****。</span><span class="sxs-lookup"><span data-stu-id="ca20f-130">In InfoPath design mode, on the **Data** tab, click **Submit Options**.</span></span>
    
2. <span data-ttu-id="ca20f-131">在“提交选项”**** 对话框中，单击“允许用户提交此表单”****，然后选择“使用代码执行自定义操作”****。</span><span class="sxs-lookup"><span data-stu-id="ca20f-131">In the **Submit Options** dialog box, click **Allow users to submit this form**, and then select **Perform custom action using Code**.</span></span>
    
3. <span data-ttu-id="ca20f-132">单击“编辑代码”**** 按钮。</span><span class="sxs-lookup"><span data-stu-id="ca20f-132">Click the **Edit Code** button.</span></span> 
    
4. <span data-ttu-id="ca20f-133">在 [OnSubmitRequest](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnSubmitRequest.aspx) 事件处理程序下添加以下两个函数：</span><span class="sxs-lookup"><span data-stu-id="ca20f-133">Add the following two functions below the [OnSubmitRequest](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnSubmitRequest.aspx) event handler:</span></span> 
    
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

5. <span data-ttu-id="ca20f-134">将下面的 **if** 语句添加到 **OnSubmitRequest** 事件处理程序函数中。</span><span class="sxs-lookup"><span data-stu-id="ca20f-134">Add the following **if** statement to the **OnSubmitRequest** event handler function.</span></span> 
    
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

### <a name="test-the-code"></a><span data-ttu-id="ca20f-135">测试代码</span><span class="sxs-lookup"><span data-stu-id="ca20f-135">Test the code</span></span>

1. <span data-ttu-id="ca20f-136">在 InfoPath 设计器中，单击“主页”**** 选项卡上的“预览”****。</span><span class="sxs-lookup"><span data-stu-id="ca20f-136">In the InfoPath designer, click **Preview** on the **Home** tab.</span></span> 
    
2. <span data-ttu-id="ca20f-137">填写表单。</span><span class="sxs-lookup"><span data-stu-id="ca20f-137">Fill out the form.</span></span>
    
3. <span data-ttu-id="ca20f-138">启动 Microsoft Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="ca20f-138">Start Microsoft Internet Explorer.</span></span>
    
4. <span data-ttu-id="ca20f-139">在 Internet Explorer 中，单击“文件”**** 菜单上的“脱机工作”****。</span><span class="sxs-lookup"><span data-stu-id="ca20f-139">In Internet Explorer, click **Work offline** on the **File** menu.</span></span> 
    
5. <span data-ttu-id="ca20f-140">在 InfoPath 中，单击“提交”****。</span><span class="sxs-lookup"><span data-stu-id="ca20f-140">In InfoPath, click **Submit**.</span></span> <span data-ttu-id="ca20f-141">你应当看到一条消息，指出表单将作为电子邮件提交。</span><span class="sxs-lookup"><span data-stu-id="ca20f-141">In InfoPath, click Submit. You should see a message that the form will be submitted as an e-mail message.</span></span>
    
6. <span data-ttu-id="ca20f-142">单击“发送”****。</span><span class="sxs-lookup"><span data-stu-id="ca20f-142">Click **Send**.</span></span> <span data-ttu-id="ca20f-143">你应当看到一条指出表单已脱机提交的消息。</span><span class="sxs-lookup"><span data-stu-id="ca20f-143">Click Send. You should see a message stating that the form has been submitted offline.</span></span>
    

