---
title: 示例沙盒解决方案
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 415fa0fa-b7b7-4acb-a437-f54c34064004
description: 本主题提供了两个示例，演示您可在 InfoPath 沙盒解决方案 中编写的代码种类，以及如何发布表单模板。
ms.openlocfilehash: 56a9a2a765100ef327790265c7cf734903268bed
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439336"
---
# <a name="sample-sandboxed-solutions"></a><span data-ttu-id="0cfd4-103">示例沙盒解决方案</span><span class="sxs-lookup"><span data-stu-id="0cfd4-103">Sample sandboxed solutions</span></span>

<span data-ttu-id="0cfd4-p101">可以从 InfoPath 设计器中将包含托管代码的 InfoPath 表单发布到 SharePoint 沙盒解决方案 基础结构。本主题提供了两个示例，演示您可在 InfoPath 沙盒解决方案 中编写的代码种类，以及如何发布表单模板。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-p101">InfoPath forms with managed code can be published to the SharePoint sandboxed solution infrastructure from the InfoPath Designer. This topic provides two examples that show the kind of code that you can write in an InfoPath sandboxed solution, and how to publish the form template.</span></span>
  
## <a name="example-1-sorting-data-in-an-order-form"></a><span data-ttu-id="0cfd4-106">示例 1：按订单对数据进行排序</span><span class="sxs-lookup"><span data-stu-id="0cfd4-106">Example 1: Sorting data in an order form</span></span>

<span data-ttu-id="0cfd4-p102">可通过使用 InfoPath 表单中的代码执行的一个有用的任务是对重复表中的数据进行排序。为此，代码将对 InfoPath 表单中显示的基础 XML 文档中的节点进行重新排序。尽管本主题中描述的方案针对的是直接从 InfoPath 中以 沙盒解决方案 的形式发布，但也可将其部署为管理员批准的表单模板。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-p102">A useful task that you can perform by using code in an InfoPath form is to sort data in a repeating table. To do this, the code reorders the nodes in underlying XML document that is displayed in the InfoPath form. Although the scenario described in this topic is targeted for publishing directly from InfoPath as a sandboxed solution, it can also be deployed as an administrator-approved form template.</span></span>
  
<span data-ttu-id="0cfd4-110">在开始之前，请确保满足以下要求。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-110">Before you start, make sure that you meet the following requirements.</span></span>
  
- <span data-ttu-id="0cfd4-111">您是要在其中发布表单的 SharePoint Server 2010 或 SharePoint Foundation 2010 网站的网站集管理员。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-111">You are a site collection administrator on the SharePoint Server 2010 or SharePoint Foundation 2010 site where you want to publish the form.</span></span>
    
- <span data-ttu-id="0cfd4-p103">与服务器场管理员核实，以确保服务器上正在运行 Microsoft SharePoint Foundation 沙盒代码服务。有关详细信息，请参阅[发布包含代码的表单](publishing-forms-with-code.md)。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-p103">Check with the farm administrator to make sure that the Microsoft SharePoint Foundation Sandboxed Code Service is running on the server. For more information, see [Publishing Forms with Code](publishing-forms-with-code.md).</span></span>
    
- <span data-ttu-id="0cfd4-114">所选的表单模板编程语言为 \*\* C#\*\* 或 \*\* Visual Basic \*\*，其后不含任何早期版本名称。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-114">The programming language that you have selected for the form template is either **C#** or **Visual Basic** without any earlier version name after it.</span></span> <span data-ttu-id="0cfd4-115">InfoPath 2007 兼容以及 InfoPath 2003 兼容版本的编程语言和对象模型不支持沙盒解决方案。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-115">The InfoPath 2007-compatible and InfoPath 2003-compatible versions of the programming languages and object models are not supported for sandboxed solutions.</span></span> <span data-ttu-id="0cfd4-116">有关如何指定编程语言的详细信息，请参阅[使用 Visual studio 进行开发](how-to-develop-with-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-116">For more information about how to specify the programming language, see [Develop with Visual Studio](how-to-develop-with-visual-studio.md).</span></span>
    
<span data-ttu-id="0cfd4-117">执行以下步骤以创建表单模板，该模板将对表单上的“重复表”\*\*\*\* 控件中的数据进行排序。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-117">Perform the following steps to create a form template that sorts the data in a **Repeating Table** control on the form.</span></span> 
  
### <a name="to-create-a-form-template-that-programmatically-sorts-data-in-the-form"></a><span data-ttu-id="0cfd4-118">创建以编程方式对表单中的数据进行排序的表单模板</span><span class="sxs-lookup"><span data-stu-id="0cfd4-118">To create a form template that programmatically sorts data in the form</span></span>

1. <span data-ttu-id="0cfd4-p105">Create a new form template in the InfoPath designer, and add a **Repeating Table** control to the form. The sample code for this example sorts the rows based on the first column in the table, but you can easily modify the code to work with any column.</span><span class="sxs-lookup"><span data-stu-id="0cfd4-p105">Create a new form template in the InfoPath designer, and add a **Repeating Table** control to the form. The sample code for this example sorts the rows based on the first column in the table, but you can easily modify the code to work with any column.</span></span> 
    
2. <span data-ttu-id="0cfd4-p106">Add a **Button** control to the form. The code to sort the table will be added to the event handler for the button's **Clicked** event, but you could also use another event for this purpose.</span><span class="sxs-lookup"><span data-stu-id="0cfd4-p106">Add a **Button** control to the form. The code to sort the table will be added to the event handler for the button's **Clicked** event, but you could also use another event for this purpose.</span></span> 
    
3. <span data-ttu-id="0cfd4-p107">Select the button, click the **Properties** tab, and then click **Custom Code**. If your form hasn't been saved yet, you are prompted to save it, and then the Code Editor will open with the cursor in the button's event handler.</span><span class="sxs-lookup"><span data-stu-id="0cfd4-p107">Select the button, click the **Properties** tab, and then click **Custom Code**. If your form hasn't been saved yet, you are prompted to save it, and then the Code Editor will open with the cursor in the button's event handler.</span></span>
    
4. <span data-ttu-id="0cfd4-p108">将以下代码粘贴到按钮的事件处理程序中。该代码会将第一个列中的元素置于一个数组中，对该数组进行排序，然后基于经过排序的数组对表进行重新排序。此代码假定所排序的数据是字符串数据。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-p108">Paste the following code into the button's event handler. The code puts the elements from the first column into an array, sorts the array, and then reorders the table based on the sorted array. This code assumes that the data being sorted is string data.</span></span>
    
   ```cs
    // Put the elements from the first column into an array.
    XPathNavigator root = this.CreateNavigator();
        
    // Create a node iterator which contains only the values that you want to sort.
    // For this form, the entire table is in "group1", each row is a "group2"
    // and the rows are "field1", "field2" and "field3" respectively.
    XPathNodeIterator nodeIterator = root.Select(
        "/my:myFields/my:group1/my:group2/my:field1", this.NamespaceManager);
        
    // Create arrays to use for sorting.
    string[] sortArrayWords = new string[nodeIterator.Count + 1];
    int[] sortArrayKeys = new int[nodeIterator.Count + 1];
    int arrayPosition = 1;
        
    // Populate the arrays for sorting.
    while (nodeIterator.MoveNext()) 
    {
        // Loop until there are no more elements
        sortArrayWords[arrayPosition] = nodeIterator.Current.Value;
        sortArrayKeys[arrayPosition] = arrayPosition;
        arrayPosition += 1;
    }
        
    // Sort the array.
    Array.Sort(sortArrayWords, sortArrayKeys);
    arrayPosition = 0;
        
    // Create new XML to update the table.
    string newTableXML = "";
    // Iterate through the sorted array of keys.
    for (int i = 1; i <= sortArrayWords.Length - 1; i++) 
    {
        nodeIterator = root.Select(
            "/my:myFields/my:group1/my:group2", this.NamespaceManager);
            
        // Go to the right position in the table.
        for (int j = 1; j <= sortArrayKeys[i]; j++) 
        {
            nodeIterator.MoveNext();
        }
            
        // Add the row to the XML.
        newTableXML += nodeIterator.Current.OuterXml;
    }
        
    // Set the table to use the new XML.
    root.SelectSingleNode(
        "/my:myFields/my:group1", this.NamespaceManager).InnerXml = newTableXML;
    
   ```

   ```vb
    ' Put the elements from the first column into an array.
    Dim root As XPathNavigator = Me.CreateNavigator
    ' Create a node iterator which contains only the values that you want to sort
    ' For this form, the entire table is in "group1",
    ' each row is a "group2"
    ' and the rows are "field1", "field2" and "field3" respectively.
    Dim nodeIterator As XPathNodeIterator = root.Select( _
        "/my:myFields/my:group1/my:group2/my:field1", Me.NamespaceManager)
    ' Create arrays to use for sorting.
    Dim sortArrayWords(nodeIterator.Count) As String
    Dim sortArrayKeys(nodeIterator.Count) As Integer
    Dim arrayPosition As Integer = 1
    ' Populate the arrays for sorting.
    While nodeIterator.MoveNext() ' Loop until there are no more elements
        sortArrayWords(arrayPosition) = nodeIterator.Current.Value
        sortArrayKeys(arrayPosition) = arrayPosition
        arrayPosition += 1
    End While
    ' Sort the array.
    Array.Sort(sortArrayWords, sortArrayKeys)
    arrayPosition = 0
    ' Create new XML to update the table.
    Dim newTableXML As String = ""
    ' Iterate through the sorted array of keys.
    For i As Integer = 1 To sortArrayWords.Length - 1
        nodeIterator = root.Select( _
            "/my:myFields/my:group1/my:group2", Me.NamespaceManager)
        ' Go to the right position in the table.
        For j As Integer = 1 To sortArrayKeys(i)
        nodeIterator.MoveNext()
        Next
    ' Add the row to the XML.
    newTableXML &amp;= nodeIterator.Current.OuterXml
    Next
    ' Set the table to use the new XML.
    root.SelectSingleNode("/my:myFields/my:group1", _
        Me.NamespaceManager).InnerXml = newTableXML
   ```

5. <span data-ttu-id="0cfd4-128">使用以下步骤发布表单：</span><span class="sxs-lookup"><span data-stu-id="0cfd4-128">Publish your form by using the following steps:</span></span>
    
    1. <span data-ttu-id="0cfd4-129">单击 Backstage 中“发布”\*\*\*\* 选项卡上的“SharePoint Server”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-129">Click **SharePoint Server** on the **Publish** tab in the Backstage.</span></span> 
        
    2. <span data-ttu-id="0cfd4-130">输入要发布 SharePoint 站点的 URL，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-130">Enter the URL of the SharePoint site to publish to, and then click **Next**.</span></span> 
        
       > [!IMPORTANT]
       > <span data-ttu-id="0cfd4-131">您必须是此网站上的网站集管理员才能以 沙盒解决方案 的形式发布此表单模板。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-131">You must be a site collection administrator on this site to publish this form template as a sandboxed solution.</span></span> 
    
    3. <span data-ttu-id="0cfd4-132">选择“表单库”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-132">Select **Form Library**, and then click **Next**.</span></span>
        
    4. <span data-ttu-id="0cfd4-133">选择“**创建新的表单库**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-133">Select **Create a new form library**, and then click **Next**.</span></span>
        
    5. <span data-ttu-id="0cfd4-134">输入表单库的名称和描述，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-134">Enter the name and descriptions for your form library, and then click **Next**.</span></span>
        
    6. <span data-ttu-id="0cfd4-135">单击“**发布**”。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-135">Click **Publish**.</span></span>
    
## <a name="example-2-managing-vendors-in-a-sharepoint-list"></a><span data-ttu-id="0cfd4-136">示例 2：在 SharePoint 列表中管理供应商</span><span class="sxs-lookup"><span data-stu-id="0cfd4-136">Example 2: Managing vendors in a SharePoint list</span></span>

<span data-ttu-id="0cfd4-p109">此示例涉及到针对 Microsoft SharePoint Foundation 2010 对象模型进行编程。为此，您必须建立对 Microsoft.SharePoint.dll 程序集的引用，该程序集随 SharePoint Server 2010 的许可副本一起安装。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-p109">This example involves programming against the Microsoft SharePoint Foundation 2010 object model. To do that, you must establish a reference to the Microsoft.SharePoint.dll assembly which is installed with a licensed copy of SharePoint Server 2010.</span></span>
  
<span data-ttu-id="0cfd4-p110">Microsoft.SharePoint.Server.dll is installed in C:\Program Files\Common Files\Microsoft Shared\Web Server Extensions\14\ISAPI by default. This DLL must be included in projects where you program against the SharePoint object model. To establish a reference to the Microsoft.SharePoint.dll in a Visual Studio 2012 project, open the **Code Editor**, and then click **Add Reference** on the **Tools** menu. In the **Add Reference** dialog box, click the **Browse** tab, specify the location of the Microsoft.SharePoint.dll file, and then click **OK**. This will copy the Microsoft.SharePoint.dll into the project directory so that you can use SharePoint Foundation 2010 object model members in your InfoPath solution.</span><span class="sxs-lookup"><span data-stu-id="0cfd4-p110">Microsoft.SharePoint.Server.dll is installed in C:\Program Files\Common Files\Microsoft Shared\Web Server Extensions\14\ISAPI by default. This DLL must be included in projects where you program against the SharePoint object model. To establish a reference to the Microsoft.SharePoint.dll in a Visual Studio 2012 project, open the **Code Editor**, and then click **Add Reference** on the **Tools** menu. In the **Add Reference** dialog box, click the **Browse** tab, specify the location of the Microsoft.SharePoint.dll file, and then click **OK**. This will copy the Microsoft.SharePoint.dll into the project directory so that you can use SharePoint Foundation 2010 object model members in your InfoPath solution.</span></span>
  
### <a name="designing-the-form-and-developing-the-code"></a><span data-ttu-id="0cfd4-144">设计表单并开发代码</span><span class="sxs-lookup"><span data-stu-id="0cfd4-144">Designing the form and developing the code</span></span>

<span data-ttu-id="0cfd4-p111">从 InfoPath 表单的代码中，您可以使用 SharePoint 对象模型创建查找列表中的项。当您依据 SharePoint 列表填充下拉框，并且要在不创建单独表单的情况下向下拉框中添加新值时，这一点非常有用。此示例使用组合框来显示当前位于列表中的所有值，并创建编程逻辑来向列表中添加值（如果尚不存在）。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-p111">From code in an InfoPath form, you can use the SharePoint object model to create items in lookup lists. This is useful when you populate a drop-down box from a SharePoint list and want to add new values to it without creating a separate form. This example uses a combo box to show all the values currently in the list and creates programming logic to add the value to the list if it does not already exist.</span></span>
  
### <a name="to-create-a-form-template-that-can-add-new-items-to-a-combo-box-based-on-a-sharepoint-list"></a><span data-ttu-id="0cfd4-148">创建可基于 SharePoint 列表向组合框中添加新项的表单模板</span><span class="sxs-lookup"><span data-stu-id="0cfd4-148">To create a form template that can add new items to a combo box based on a SharePoint list</span></span>

1. <span data-ttu-id="0cfd4-p112">Create a simple custom list on a SharePoint Server 2010 server, and name it MyList. The following example uses a **Combo Box** bound to the **Title** field of this list.</span><span class="sxs-lookup"><span data-stu-id="0cfd4-p112">Create a simple custom list on a SharePoint Server 2010 server, and name it MyList. The following example uses a **Combo Box** bound to the **Title** field of this list.</span></span> 
    
2. <span data-ttu-id="0cfd4-151">在 InfoPath Designer 中新建一个“空白表单”\*\*\*\*，在表单上插入“组合框”\*\*\*\* 控件，并将绑定到组合框的字段重命名为 myCombo。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-151">Create a new **Blank Form** in InfoPath Designer, insert a **Combo Box** control on your form, and rename the field bound to the combo box to myCombo.</span></span>
    
3. <span data-ttu-id="0cfd4-152">通过使用以下步骤，创建与将用于填充组合框的列表的数据连接：</span><span class="sxs-lookup"><span data-stu-id="0cfd4-152">Create the data connection to the list that will be used to populate the combo box by using the following steps:</span></span>
    
    1. <span data-ttu-id="0cfd4-153">在“数据”\*\*\*\* 选项卡上，单击“获取外部数据”\*\*\*\* 组中的“来自 SharePoint 列表”\*\*\*\* 按钮。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-153">On the **Data** tab, click **From SharePoint List** button in the **Get External Data** group.</span></span> 
        
    2. <span data-ttu-id="0cfd4-154">输入包含该列表的站点的 URL，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-154">Enter the URL for the site that contains the list, and then click **Next**.</span></span>
        
    3. <span data-ttu-id="0cfd4-155">选择该列表，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-155">Select the list, and then click **Next**.</span></span>
        
    4. <span data-ttu-id="0cfd4-p113">Select the fields that you want to include, for this example, select Title and ID. Title contains the values for lookup. Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="0cfd4-p113">Select the fields that you want to include, for this example, select Title and ID. Title contains the values for lookup. Click **Next**.</span></span>
        
    5. <span data-ttu-id="0cfd4-159">在以下屏幕中单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-159">Click **Next** on the following screen.</span></span> 
        
    6. <span data-ttu-id="0cfd4-160">将数据连接命名为 LookupList，然后单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-160">Name the data connection LookupList, and then click **Finish**.</span></span>
    
4. <span data-ttu-id="0cfd4-161">通过使用以下步骤，依据列表在组合框中填充值：</span><span class="sxs-lookup"><span data-stu-id="0cfd4-161">Populate the values in the combo box from the list by using the following steps:</span></span>
    
    1. <span data-ttu-id="0cfd4-162">选择步骤 1 中创建的组合框。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-162">Select the combo box that you created in step 1.</span></span>
        
    2. <span data-ttu-id="0cfd4-163">单击功能区的“控件工具属性”\*\*\*\* 选项卡上的“编辑选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-163">Click **Edit Choices** on the **Control Tools Properties** tab of the ribbon.</span></span> 
        
    3. <span data-ttu-id="0cfd4-164">选择“从外部数据源中获取选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-164">Select **Get choices from an external data source**.</span></span>
        
    4. <span data-ttu-id="0cfd4-165">确保将“数据源”\*\*\*\* 设置为你在步骤 2 中创建的数据连接。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-165">Make sure that **Data source** is set to the data connection that you created in step 2.</span></span> 
        
    5. <span data-ttu-id="0cfd4-166">将值和显示名称设置为 Title。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-166">Set the value and display name to Title.</span></span>
        
    6. <span data-ttu-id="0cfd4-167">在“浏览器表单”\*\*\*\* 选项卡上，选择“回发设置”\*\*\*\* 下的“始终”\*\*\*\*，然后单击“确定”\*\*\*\* 关闭属性对话框。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-167">On the **Browser forms** tab, select **Always** under **Postback settings**, and then click **OK** to close the properties dialog box.</span></span> 
    
5. <span data-ttu-id="0cfd4-168">确保仍然选中组合框，然后单击功能区中“开发人员”\*\*\*\* 选项卡上的“Changed 事件”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-168">Make sure the combo box is still selected, and then click **Changed Event** on the **Developer** tab of the ribbon.</span></span> 
    
    <span data-ttu-id="0cfd4-p114">如果表单尚未保存，则会提示您保存表单。然后，代码编辑器窗口将在  `myCombo_Changed` 事件处理程序中打开并显示游标。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-p114">If your form is not saved yet, you are prompted to save it. And then, the code editor window opens with the cursor in the  `myCombo_Changed` event handler.</span></span> 
    
6. <span data-ttu-id="0cfd4-171">如本主题前面所述，添加对 Microsoft.SharePoint.dll 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-171">Add a reference to the Microsoft.SharePoint.dll assembly as described earlier in this topic.</span></span> <span data-ttu-id="0cfd4-172">有关引用 Microsoft.SharePoint 程序集的详细信息，请参阅[使用 SharePoint 对象模型成员](how-to-use-sharepoint-object-model-members.md)。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-172">For more information about referencing the Microsoft.SharePoint assembly, see [Use SharePoint Object Model Members](how-to-use-sharepoint-object-model-members.md).</span></span>
    
7. <span data-ttu-id="0cfd4-173">将以下代码粘贴到 `myCombo_Changed` 事件处理程序中。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-173">Paste the following code into the  `myCombo_Changed` event handler.</span></span> 
    
   ```cs
    // Use InfoPath OM's ServerInfo.SharePointSiteUrl property to programmatically
    // specify the site where the form is published.
    using (SPSite FormSite = new SPSite(ServerInfo.SharePointSiteUrl.ToString()))
    {
        using (SPWeb FormWeb = FormSite.OpenWeb())
        {
            // Get the SharePoint list.
            SPList LookupList = FormWeb.Lists["MyList"];
            // Query for the item.
            SPQuery MyQuery = new SPQuery();
            // "Title" is the field (column) to search in the SharePoint list.
            // /my:myFields/my:myCombo is the xpath to the field bound to the Combo Box in the form.
            MyQuery.Query = "<Where><Eq><FieldRef Name='Title' /><Value Type='Text'>" + 
                GetDomValue("/my:myFields/my:myCombo") + "</Value></Eq></Where>";
            SPListItemCollection ReturnedItems = LookupList.GetItems(MyQuery);
            // Add the item to the SharePoint list if no items were returned in the query.
            if (ReturnedItems.Count == 0)
            {
                SPListItem NewItem = LookupList.Items.Add();
                // Set the value of the Title field in the list to the value in Combo Box on the form.
                NewItem["Title"] = GetDomValue("/my:myFields/my:myCombo");
                // Set AllowUnsafeUpdates to 'true' to temporarily allow updates to the database.
                FormWeb.AllowUnsafeUpdates = true;
                NewItem.Update();
                // Set AllowUnsafeUpdates back to 'false' to prevent further updates to the database.
                FormWeb.AllowUnsafeUpdates = false;
            }
        }
    }
   ```

   ```vb
    ' Use InfoPath OM's ServerInfo.SharePointSiteUrl property to specify the site where the form is published.
    Using FormSite As New SPSite(ServerInfo.SharePointSiteUrl.ToString())
        Using FormWeb As SPWeb = FormSite.OpenWeb()
            ' Get the SharePoint list.
            Dim LookupList As SPList = FormWeb.Lists("MyList")
            ' Query for the item.
            Dim MyQuery As New SPQuery()
            ' "Title" is the field (column) to search in the SharePoint list.
            ' my:myFields/my:myCombo is the xpath to the field bound to the Combo Box in the form.
            MyQuery.Query = "<Where><Eq><FieldRef Name='Title' /><Value Type='Text'>" &amp; _
                GetDomValue("/my:myFields/my:myCombo") &amp; "</Value></Eq></Where>"
            Dim ReturnedItems As SPListItemCollection = LookupList.GetItems(MyQuery)
            ' Add the item to the lookup list if no items were returned in the query.
            If ReturnedItems.Count = 0 Then
                Dim NewItem As SPListItem = LookupList.Items.Add()
                ' Set the value of the Title field in the list to the value in Combo Box on the form.
                NewItem("Title") = GetDomValue("/my:myFields/my:myCombo")
                ' Set AllowUnsafeUpdates to 'true' to temporarily allow updates to the database.
                FormWeb.AllowUnsafeUpdates = True
                NewItem.Update()
                ' Set AllowUnsafeUpdates back to 'false' to prevent further updates to the database.
                FormWeb.AllowUnsafeUpdates = False
            End If
        End Using
    End Using
   ```

8. <span data-ttu-id="0cfd4-p116">前面的代码示例取决于 `GetDomValue` 帮助程序函数。在 `myCombo_Changed` 事件处理程序函数下面粘贴 `GetDomValue` 帮助程序函数的以下代码。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-p116">The preceding code example depends on the  `GetDomValue` helper function. Paste the following code for the  `GetDomValue` helper function below the  `myCombo_Changed` event handler function.</span></span> 
    
   ```cs
    private string GetDomValue(string XpathToGet)
    {
        return this.CreateNavigator().SelectSingleNode(XpathToGet, this.NamespaceManager).Value;
    }
   ```

   ```vb
    Private Function GetDomValue(XpathToGet As String) As String
        Return Me.CreateNavigator().SelectSingleNode(XpathToGet, Me.NamespaceManager).Value
    End Function
   ```

9. <span data-ttu-id="0cfd4-176">使用以下步骤发布表单：</span><span class="sxs-lookup"><span data-stu-id="0cfd4-176">Publish your form by using the following steps:</span></span>
    
    1. <span data-ttu-id="0cfd4-177">单击 Backstage 中“发布”\*\*\*\* 选项卡上的“SharePoint Server”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-177">Click **SharePoint Server** on the **Publish** tab in the Backstage.</span></span> 
        
    2. <span data-ttu-id="0cfd4-178">输入要发布 SharePoint 站点的 URL，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-178">Enter the URL of the SharePoint site to publish to, and then click **Next**.</span></span> 
        
       > [!IMPORTANT]
       > <span data-ttu-id="0cfd4-179">您必须是此网站上的网站集管理员才能以 沙盒解决方案 的形式发布此表单模板。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-179">You must be a site collection administrator on this site to publish this form template as a sandboxed solution.</span></span> 
    
    3. <span data-ttu-id="0cfd4-180">选择“表单库”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-180">Select **Form Library**, and then click **Next**.</span></span>
        
    4. <span data-ttu-id="0cfd4-181">选择“新建表单库”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-181">Select **Create a new form library**, and then click **Next**.</span></span>
        
    5. <span data-ttu-id="0cfd4-182">输入表单库的名称和描述，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-182">Enter the name and description for your form library, and then click **Next**.</span></span>
        
    6. <span data-ttu-id="0cfd4-183">单击“发布”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-183">Click **Publish**.</span></span>
        
    7. <span data-ttu-id="0cfd4-p117">成功发布表单后，从表单库中打开该表单，然后向组合框中添加一个新值以测试代码。退出 myCombo 域时，新值将会写入 SharePoint 列表。</span><span class="sxs-lookup"><span data-stu-id="0cfd4-p117">After the form is successfully published, open the form from the form library and add a new value into the combo box to test the code. When you exit the myCombo field, the new value will be written to the SharePoint list.</span></span> 
    

