---
title: 在 Access 中创建和自定义 Web 应用
manager: kelbow
ms.date: 08/18/2017
ms.audience: Developer
ms.topic: reference
ms.assetid: 628745f4-82e9-4838-9726-6f3e506a654f
localization_priority: Priority
ms.openlocfilehash: d7d27e98189a5b6784e4db48c81a545b85f01fc1
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28716815"
---
# <a name="create-and-customize-a-web-app-in-access"></a><span data-ttu-id="14164-102">在 Access 中创建和自定义 Web 应用</span><span class="sxs-lookup"><span data-stu-id="14164-102">Create and customize a web app in Access</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14164-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="14164-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
<span data-ttu-id="14164-p102">Access 2013 采用新的应用程序模型，使主题专家可以快速创建基于 Web 的应用程序。Access 中包含一系列模板，您可用于开始创建应用程序。</span><span class="sxs-lookup"><span data-stu-id="14164-p102">Access 2013 features a new application model that enables subject matter experts to quickly create web-based applications. Included with Access are a set of templates that you can use to jump start creating your application.</span></span>

<span data-ttu-id="14164-107"><a name="ac15_CreateAndCustomizeWebApp_Prerequisites"> </a></span><span class="sxs-lookup"><span data-stu-id="14164-107"><a name="ac15_CreateAndCustomizeWebApp_Prerequisites"> </a></span></span>

## <a name="prerequisites-for-building-an-app-with-access-2013"></a><span data-ttu-id="14164-108">使用 Access 2013 构建应用程序的先决条件</span><span class="sxs-lookup"><span data-stu-id="14164-108">Prerequisites for building an app with Access 2013</span></span>

<span data-ttu-id="14164-109">若要按照此示例中的步骤操作，需要：</span><span class="sxs-lookup"><span data-stu-id="14164-109">To follow the steps in this example, you need the following:</span></span>
  
- <span data-ttu-id="14164-110">Access</span><span class="sxs-lookup"><span data-stu-id="14164-110">Access</span></span>
    
- <span data-ttu-id="14164-111">SharePoint 开发环境</span><span class="sxs-lookup"><span data-stu-id="14164-111">A SharePoint development environment</span></span>
    
<span data-ttu-id="14164-112">有关设置 SharePoint 开发环境的详细信息，请参阅[设置 SharePoint 的常规开发环境](https://docs.microsoft.com/sharepoint/dev/general-development/set-up-a-general-development-environment-for-sharepoint)。</span><span class="sxs-lookup"><span data-stu-id="14164-112">For more information about setting up your SharePoint development environment, see [Set up a general development environment for SharePoint](https://docs.microsoft.com/sharepoint/dev/general-development/set-up-a-general-development-environment-for-sharepoint).</span></span> 
  
<span data-ttu-id="14164-113">有关获取 Access 和 SharePoint 的详细信息，请参阅[下载](https://msdn.microsoft.com/office/apps/fp123627)。</span><span class="sxs-lookup"><span data-stu-id="14164-113">For more information about obtaining Access and SharePoint, see [Downloads](https://msdn.microsoft.com/office/apps/fp123627).</span></span>

<span data-ttu-id="14164-114"><a name="ac15_CreateAndCustomizeWebApp_CreateTheApp"> </a></span><span class="sxs-lookup"><span data-stu-id="14164-114"><a name="ac15_CreateAndCustomizeWebApp_CreateTheApp"> </a></span></span>

## <a name="create-the-app"></a><span data-ttu-id="14164-115">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="14164-115">Create the app</span></span>

<span data-ttu-id="14164-p103">假设您想创建一个 Access 应用程序，用于跟踪企业的问题，则在从头开始创建表和视图之前，您应该搜索一个满足您需求的架构模板。</span><span class="sxs-lookup"><span data-stu-id="14164-p103">Suppose you want to create an Access app that tracks issues for your business. Before you start creating the tables and view from scratch, you should search for a schema template that meets your needs.</span></span>
  
### <a name="to-create-the-issue-tracking-app"></a><span data-ttu-id="14164-118">创建问题跟踪应用程序</span><span class="sxs-lookup"><span data-stu-id="14164-118">To create the issue tracking app</span></span>

1. <span data-ttu-id="14164-119">打开 Access 并选择 **"自定义 Web 应用程序"**。</span><span class="sxs-lookup"><span data-stu-id="14164-119">Open Access and choose **Custom web app**.</span></span>
    
2. <span data-ttu-id="14164-120">输入你的应用的名称和 Web 位置。</span><span class="sxs-lookup"><span data-stu-id="14164-120">Enter a name and the web location for your app.</span></span> <span data-ttu-id="14164-121">你也可以从“位置”\*\*\*\* 列表中选择一个位置并选择“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="14164-121">You can also choose a location from the **Locations** list and choose **Create**.</span></span>
    
3. <span data-ttu-id="14164-122">在“你想跟踪什么?”\*\*\*\* 框中键入 **Issues**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="14164-122">Type **Issues** into the **What would you like to track?** box and then press ENTER.</span></span> 
    
   <span data-ttu-id="14164-123">图 1 显示了一个可能对跟踪问题有用的模板列表。</span><span class="sxs-lookup"><span data-stu-id="14164-123">A list of templates that might be useful for tracking issues is displayed in Figure 1.</span></span>
    
   <span data-ttu-id="14164-124">**图 1. 与问题搜索相匹配的模板**</span><span class="sxs-lookup"><span data-stu-id="14164-124">**Figure 1. Templates that match the search for issues**</span></span>

   <span data-ttu-id="14164-125">![与问题搜索相匹配的模板](media/odc_Access15_CreateAndCustomizeWebApp_Figure01.JPG "与问题搜索相匹配的模板")</span><span class="sxs-lookup"><span data-stu-id="14164-125">![Templates that match the search for issues](media/odc_Access15_CreateAndCustomizeWebApp_Figure01.JPG "Templates that match the search for issues")</span></span>
  
4. <span data-ttu-id="14164-126">选择“问题”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="14164-126">Choose **Issues**.</span></span>
    
<span data-ttu-id="14164-127">Access 创建一系列表和视图。</span><span class="sxs-lookup"><span data-stu-id="14164-127">Access creates a set of tables and views.</span></span>
  
## <a name="explore-the-app"></a><span data-ttu-id="14164-128">浏览应用程序</span><span class="sxs-lookup"><span data-stu-id="14164-128">Explore the app</span></span>
<span data-ttu-id="14164-129"><a name="ac15_CreateAndCustomizeWebApp_ExploreTheApp"> </a></span><span class="sxs-lookup"><span data-stu-id="14164-129"><a name="ac15_CreateAndCustomizeWebApp_ExploreTheApp"> </a></span></span>

<span data-ttu-id="14164-130">若要了解架构和视图是否满足您的需求，您应该对其进行检查。</span><span class="sxs-lookup"><span data-stu-id="14164-130">To understand whether the schema and views meet your needs, you should examine them.</span></span>
  
<span data-ttu-id="14164-p105">平铺窗格中显示了通过选择“问题”架构创建的表。“问题”、“客户”和“员工”表是应用程序的重心所在。“问题”表存储关于每个问题的信息。每个问题由员工代表客户创建并分配给某个员工。“相关问题”和“问题注释”表在应用程序中起支持作用。“相关问题”表使您可以将一个问题链接到另一个。“问题注释”表存储对一个问题的多个注释。</span><span class="sxs-lookup"><span data-stu-id="14164-p105">The tables created by selecting the Issues schema are displayed in the Tile Pane. The Issues, Customer, and Employees tables are the main focus of the app. The Issues table stores information about each issue. Each issue is opened by and assigned to an employee on behalf of a customer. The Related Issues and Issue Comments tables play a supporting role in the app. The Related Issues table enables you to link one issue to another. The Issue Comments table stores multiple comments for a single issue.</span></span>
  
<span data-ttu-id="14164-138">在 Access 桌面 (.accdb) 数据库中，在“关系”\*\*\*\* 窗口中管理表之间的关系。</span><span class="sxs-lookup"><span data-stu-id="14164-138">In an Access desktop (.accdb) database, the relationships between tables are managed in the **Relationships** window.</span></span> <span data-ttu-id="14164-139">Access 2013 应用使用设置为 **Lookup** 数据类型的字段来管理关系。</span><span class="sxs-lookup"><span data-stu-id="14164-139">Access 2013 apps manage relationships by using fields set to the **Lookup** data type.</span></span> <span data-ttu-id="14164-140">让我们通过右键单击“问题”\*\*\*\* 窗格并选择“编辑表”\*\*\*\* 来检查问题表的关系。</span><span class="sxs-lookup"><span data-stu-id="14164-140">Let's examine the relationships for the Issues table by right-clicking the **Issues** tile and selecting **Edit Table**.</span></span>
  
<span data-ttu-id="14164-141">“客户”\*\*\*\* 字段与“客户”\*\*\*\* 表相关。</span><span class="sxs-lookup"><span data-stu-id="14164-141">The **Customer** field is related to the **Customers** table.</span></span> <span data-ttu-id="14164-142">若要检查关系，请选择“客户”\*\*\*\* 字段，然后选择“修改查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="14164-142">To examine the relationship, select the **Customer** field and then select **Modify Lookups**.</span></span> <span data-ttu-id="14164-143">将显示“查找向导”\*\*\*\*，如图 2 所示。</span><span class="sxs-lookup"><span data-stu-id="14164-143">The **Lookup Wizard** is displayed, as shown in Figure 2.</span></span> 
  
<span data-ttu-id="14164-144">**图 2. 显示与“客户”表的关系的“查找向导”**</span><span class="sxs-lookup"><span data-stu-id="14164-144">**Figure 2. Lookup Wizard displaying the relationship to the Customers table**</span></span>

<span data-ttu-id="14164-145">![显示关系的“查找向导”](media/odc_Access15_CreateAndCustomizeWebApp_Figure02.jpg "显示关系的“查找向导”")</span><span class="sxs-lookup"><span data-stu-id="14164-145">![Lookup Wizard displaying the relationship](media/odc_Access15_CreateAndCustomizeWebApp_Figure02.jpg "Lookup Wizard displaying the relationship")</span></span>
  
<span data-ttu-id="14164-146">“查找向导”对话框显示“客户”\*\*\*\* 字段链接到“客户”\*\*\*\* 表，并从“客户”\*\*\*\* 表中返回“显示名字和姓氏”\*\*\*\* 字段。</span><span class="sxs-lookup"><span data-stu-id="14164-146">The Lookup Wizard dialog box shows that the **Customer** field is linked to the **Customers** table and to return the **Display Name First Last** field from the **Customers** table.</span></span> 
  
<span data-ttu-id="14164-147">“打开者”\*\*\*\*、“分配到”\*\*\*\* 和“更改者”\*\*\*\* 字段与“员工”\*\*\*\* 表相关。</span><span class="sxs-lookup"><span data-stu-id="14164-147">The **Opened By**, **Assigned To**, and **Changed By** fields are related to the **Employees** table.</span></span> <span data-ttu-id="14164-148">其他几个字段也被设置为 **Lookup** 数据类型。</span><span class="sxs-lookup"><span data-stu-id="14164-148">Several other fields are also set to the **Lookup** data type.</span></span> <span data-ttu-id="14164-149">在这些情况下，Lookup 数据类型用于指定字段中允许的特定值。</span><span class="sxs-lookup"><span data-stu-id="14164-149">In these cases, the Lookup data type is used to specify the specific values to allow for in the field.</span></span> 
  
<span data-ttu-id="14164-150">关闭“问题”\*\*\*\* 表并检查平铺窗格。</span><span class="sxs-lookup"><span data-stu-id="14164-150">Close the **Issues** table and examine the Tile Pane.</span></span> <span data-ttu-id="14164-151">“问题”\*\*\*\*、“客户”\*\*\*\* 和“员工”\*\*\*\* 表的顶部三个窗格与“相关问题”\*\*\*\* 和“问题注释”\*\*\*\* 表的底部两个窗格的显示有所不同，如图 3 中所示。</span><span class="sxs-lookup"><span data-stu-id="14164-151">The top three tiles, for the **Issues**, **Customers**, and **Employees** tables, are displayed differently than the bottom two tiles for the **Related Issues** and **Issue Comments** table, as shown in Figure 3.</span></span> 
  
<span data-ttu-id="14164-152">**图 3.“问题”架构的平铺窗格**</span><span class="sxs-lookup"><span data-stu-id="14164-152">**Figure 3. Tile Pane for the Issues schema**</span></span>

<span data-ttu-id="14164-153">![“问题”架构的平铺窗格](media/odc_Access15_CreateAndCustomizeWebApp_Figure03.jpg "“问题”架构的平铺窗格")</span><span class="sxs-lookup"><span data-stu-id="14164-153">![Tile Pane for the Issues schema](media/odc_Access15_CreateAndCustomizeWebApp_Figure03.jpg "Tile Pane for the Issues schema")</span></span>
  
<span data-ttu-id="14164-154">“相关问题”\*\*\*\* 和“问题注释”\*\*\*\* 表显示为灰色，因为它们将对 Web 浏览器中的用户隐藏。</span><span class="sxs-lookup"><span data-stu-id="14164-154">The **Related Issues** and **Issue Comments** tables are dimmed because they are to be hidden from the user in the web browser.</span></span> 
  
<span data-ttu-id="14164-155">现在我们使用该应用来跟踪某些问题。</span><span class="sxs-lookup"><span data-stu-id="14164-155">Let's use the app to track some issues.</span></span> <span data-ttu-id="14164-156">为此，单击“启动应用”\*\*\*\* 在 Web 浏览器中打开应用。</span><span class="sxs-lookup"><span data-stu-id="14164-156">To do this, click **Launch App** to open the app in your web browser.</span></span> 
  
<span data-ttu-id="14164-157">该应用打开“问题”表的“问题列表”\*\*\*\* 视图。</span><span class="sxs-lookup"><span data-stu-id="14164-157">The app opens the **Issues List** view of the Issues table.</span></span> <span data-ttu-id="14164-158">在添加问题之前，可添加一些客户和员工。</span><span class="sxs-lookup"><span data-stu-id="14164-158">Before adding an issue, it would be a good idea to add some customers and employees.</span></span> <span data-ttu-id="14164-159">单击“客户”\*\*\*\* 窗格以开始添加客户。</span><span class="sxs-lookup"><span data-stu-id="14164-159">Click the **Customers** tile to start adding customers.</span></span> 
  
<span data-ttu-id="14164-160">使用视图选择器从“客户”\*\*\*\* 表的三个可用视图（即“列表”\*\*\*\*、“数据表”\*\*\*\* 和“组”\*\*\*\*）中选择一个，如图 4 中所示。</span><span class="sxs-lookup"><span data-stu-id="14164-160">Use the View Selector to choose one of three views available for the **Customers** table, labeled **List**, **Datasheet**, and **Groups** as shown in Figure 4.</span></span> 
  
<span data-ttu-id="14164-161">**图 4. 视图选择器**</span><span class="sxs-lookup"><span data-stu-id="14164-161">**Figure 4. View Selector**</span></span>

<span data-ttu-id="14164-162">![视图选择器](media/odc_Access15_CreateAndCustomizeWebApp_Figure04.jpg "视图选择器")</span><span class="sxs-lookup"><span data-stu-id="14164-162">![View Selector](media/odc_Access15_CreateAndCustomizeWebApp_Figure04.jpg "View Selector")</span></span>
  
<span data-ttu-id="14164-163">选择“列表”\*\*\*\* 会激活“客户列表”\*\*\*\* 视图，该视图是“列表详细信息”视图。</span><span class="sxs-lookup"><span data-stu-id="14164-163">Choosing **List** activates the **Customers List** view, which is a List Details view.</span></span> <span data-ttu-id="14164-164">列表详细信息是创建表时 Access 自动生成的一种视图。</span><span class="sxs-lookup"><span data-stu-id="14164-164">List Details is one of the views Access automatically generates when you create a table.</span></span> <span data-ttu-id="14164-165">用于区分“列表详细信息”视图的主要功能是视图左侧显示的列表窗格。</span><span class="sxs-lookup"><span data-stu-id="14164-165">The main feature that distinguishes a List Details view is the list pane that appears on the left side of the view.</span></span> <span data-ttu-id="14164-166">列表窗格用于筛选和导航视图中包含的记录。</span><span class="sxs-lookup"><span data-stu-id="14164-166">The list pane is used to filter and navigate the records contained in the view.</span></span> <span data-ttu-id="14164-167">在 Access 桌面数据库中，实现可搜索的列表视图将需要编写自定义代码。</span><span class="sxs-lookup"><span data-stu-id="14164-167">In an Access desktop database, implementing a searchable list view would require writing custom code.</span></span> 
  
<span data-ttu-id="14164-168">选择“数据表”\*\*\*\* 将打开“客户数据表”\*\*\*\* 视图。</span><span class="sxs-lookup"><span data-stu-id="14164-168">Choosing **Datasheet** opens the **Customers Datasheet** view.</span></span> <span data-ttu-id="14164-169">“数据表”是创建表时 Access 自动生成的另一种视图。</span><span class="sxs-lookup"><span data-stu-id="14164-169">Datasheet is the other kind of view Access automatically generates when you create a table.</span></span> <span data-ttu-id="14164-170">“数据表”视图对于更习惯以类似电子表格的方式输入、排序和筛选数据的用户而言非常有帮助。</span><span class="sxs-lookup"><span data-stu-id="14164-170">Datasheet views are useful for those who find it easier to enter, sort, and filter data in a spreadsheet-like manner.</span></span> 
  
<span data-ttu-id="14164-p114">选择“组”将打开“摘要”视图。“摘要”视图可用于根据字段对记录进行分组，并（可选）计算总和或平均值。</span><span class="sxs-lookup"><span data-stu-id="14164-p114">Choosing Groups opens a Summary view. Summary views can be used to group records based on a field and optionally calculate a sum or average.</span></span>
  
<span data-ttu-id="14164-p115">添加客户时，可使用操作栏添加、编辑、保存和删除记录或取消编辑。操作栏是每个视图顶部的 可自定义 工具栏，如图 5 中所示。</span><span class="sxs-lookup"><span data-stu-id="14164-p115">As you're adding customers, use the Action Bar to add records, edit records, save records, delete records, and cancel edits. The Action Bar is a customizable toolbar that appears at the top of each view, as shown in Figure 5.</span></span>
  
<span data-ttu-id="14164-175">**图 5. 操作栏**</span><span class="sxs-lookup"><span data-stu-id="14164-175">**Figure 5. Action Bar**</span></span>

<span data-ttu-id="14164-176">![操作栏](media/odc_Access15_CreateAndCustomizeWebApp_Figure05.jpg "操作栏")</span><span class="sxs-lookup"><span data-stu-id="14164-176">![Action Bar](media/odc_Access15_CreateAndCustomizeWebApp_Figure05.jpg "Action Bar")</span></span>
  
<span data-ttu-id="14164-p116">添加一些客户和员工后，打开"问题列表"视图并开始添加问题。在"客户"框中键入客户的名称时，将出现一个或多个客户名称，如图 6 中所示。</span><span class="sxs-lookup"><span data-stu-id="14164-p116">Once you've added some customers and employees open the Issues List view and start adding an issue. As you type the name of a customer into the into the Customer box, one or more of the customer names will appear, as shown in Figure 6.</span></span>
  
<span data-ttu-id="14164-179">**图 6. 自动完成控件**</span><span class="sxs-lookup"><span data-stu-id="14164-179">**Figure 6. AutoComplete control**</span></span>

<span data-ttu-id="14164-180">![自动完成控件](media/odc_Access15_CreateAndCustomizeWebApp_Figure06.jpg "自动完成控件")</span><span class="sxs-lookup"><span data-stu-id="14164-180">![AutoComplete control](media/odc_Access15_CreateAndCustomizeWebApp_Figure06.jpg "AutoComplete control")</span></span>
  
<span data-ttu-id="14164-p117">"客户"框是一个自动完成控件。自动完成控件显示与您在框中所键入内容匹配的记录的列表。这有助于确保数据输入的准确性。</span><span class="sxs-lookup"><span data-stu-id="14164-p117">The Customer box is an AutoComplete control. The AutoComplete control displays a list of records that match what you're typing into the box. This helps ensure the accuracy of data entry.</span></span>
  
## <a name="customize-the-app"></a><span data-ttu-id="14164-184">自定义应用程序</span><span class="sxs-lookup"><span data-stu-id="14164-184">Customize the app</span></span>
<span data-ttu-id="14164-185"><a name="ac15_CreateAndCustomizeWebApp_CustomizeTheApp"> </a></span><span class="sxs-lookup"><span data-stu-id="14164-185"><a name="ac15_CreateAndCustomizeWebApp_CustomizeTheApp"> </a></span></span>

<span data-ttu-id="14164-p118">现在您已浏览了整个应用程序，您注意到"问题列表"视图不包含客户的任何联系信息。现在我们来对应用程序进行自定义，在创建问题时在问题表中添加客户的工作电话。</span><span class="sxs-lookup"><span data-stu-id="14164-p118">Now that you've taken a tour of the app, you notice that the Issues List view doesn't contain contact information for the customer. Let's customize the app to add the customer's work phone to the Issues table as the issue is being created.</span></span>
  
### <a name="to-add-a-field-to-the-issues-table"></a><span data-ttu-id="14164-188">向问题表添加字段</span><span class="sxs-lookup"><span data-stu-id="14164-188">To add a field to the Issues table</span></span>

1. <span data-ttu-id="14164-189">在 Access 中打开应用程序。</span><span class="sxs-lookup"><span data-stu-id="14164-189">Open the app in Access.</span></span>
    
2. <span data-ttu-id="14164-190">依次选择“问题”\*\*\*\* 窗格、“设置/操作”\*\*\*\* 图标和“编辑表”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="14164-190">Choose the **Issues** tile, choose the **Settings/Action** icon, and then choose **Edit Table**.</span></span>
    
3. <span data-ttu-id="14164-191">在“字段名称”\*\*\*\* 列的第一个空白单元格中输入“联系人号码”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="14164-191">Enter **Contact Number** in the first blank cell in the **Field Name** column.</span></span> 
    
4. <span data-ttu-id="14164-192">在“数据类型”\*\*\*\* 列中选择“短文本”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="14164-192">Choose **Short Text** in the **Data Type** column.</span></span> 
    
5. <span data-ttu-id="14164-193">选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="14164-193">Choose **Save**.</span></span>
    
6. <span data-ttu-id="14164-194">关闭问题表。</span><span class="sxs-lookup"><span data-stu-id="14164-194">Close the Issues table.</span></span>
    
<span data-ttu-id="14164-195">现在我们已有字段来存储电话号码，让我们创建一个数据宏来查找联系信息。</span><span class="sxs-lookup"><span data-stu-id="14164-195">Now that we have field in which to store the phone number, let's create a data macro to look up the contact information.</span></span>
  
### <a name="to-create-the-data-macro-to-look-up-contact-information"></a><span data-ttu-id="14164-196">创建数据宏以查找联系信息</span><span class="sxs-lookup"><span data-stu-id="14164-196">To create the data macro to look up contact information</span></span>

1. <span data-ttu-id="14164-197">在“创建”\*\*\*\* 组中，依次选择“高级”\*\*\*\*、“数据宏”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="14164-197">In the **Create** group, choose **Advanced**, and then choose **Data Macro**.</span></span>
    
2. <span data-ttu-id="14164-198">选择“创建参数”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="14164-198">Choose **Create Parameter**.</span></span>
    
3. <span data-ttu-id="14164-199">在“名称”\*\*\*\* 框中，输入 **CustID**。</span><span class="sxs-lookup"><span data-stu-id="14164-199">In the **Name** box, enter **CustID**.</span></span> <span data-ttu-id="14164-200">在“类型”\*\*\*\* 下拉列表中，选择“数字(浮点十进制数)”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="14164-200">In the **Type** dropdown, choose **Number (Floating Decimal).**</span></span>
    
4. <span data-ttu-id="14164-201">从“添加新操作”\*\*\*\* 下拉列表中，选择“LookupRecord”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="14164-201">From the **Add New Action** dropdown, choose **LookupRecord**.</span></span> 
    
5. <span data-ttu-id="14164-202">在“在其中查找 A 记录”\*\*\*\* 下拉列表中，选择“客户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="14164-202">In the **Look Up A Record In** dropdown, choose **Customers**.</span></span> 
    
6. <span data-ttu-id="14164-203">在“Where 条件”\*\*\*\* 框中，输入 **[Customers].[ID]=[CustID]**。</span><span class="sxs-lookup"><span data-stu-id="14164-203">In the **Where Condition** box, enter **[Customers].[ID]=[CustID]**.</span></span> 
    
7. <span data-ttu-id="14164-204">从“添加新操作”\*\*\*\* 下拉列表中选择“SetReturnVar”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="14164-204">Choose **SetReturnVar** from the **Add New Action** dropdown.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="14164-205">你将看到两个“添加新操作”\*\*\*\* 下拉列表，一个在 **LookupRecord** 块之内，另一个在 **LookupRecord** 块之外。</span><span class="sxs-lookup"><span data-stu-id="14164-205">You'll see two **Add New Action** dropdowns, one within the **LookupRecord** block, and another outside the **LookupRecord** block.</span></span> <span data-ttu-id="14164-206">你应该在 **LookupRecord** 块中选择“添加新操作”\*\*\*\* 下拉列表，如图 7 所示。</span><span class="sxs-lookup"><span data-stu-id="14164-206">You should choose the **Add New Action** dropdown within the **LookupRecord** block, as shown in Figure 7.</span></span> 
  
   <span data-ttu-id="14164-207">**图 7.“添加新操作”下拉列表**</span><span class="sxs-lookup"><span data-stu-id="14164-207">**Figure 7. Add New Action dropdown**</span></span>

   <span data-ttu-id="14164-208">![“添加新操作”下拉列表](media/odc_Access15_CreateAndCustomizeWebApp_Figure07.jpg "“添加新操作”下拉列表")</span><span class="sxs-lookup"><span data-stu-id="14164-208">![Add New Action dropdown](media/odc_Access15_CreateAndCustomizeWebApp_Figure07.jpg "Add New Action dropdown")</span></span>
  
8. <span data-ttu-id="14164-209">在“名称”\*\*\*\* 框中，输入 **ContactPhone**。</span><span class="sxs-lookup"><span data-stu-id="14164-209">In the **Name** box, enter **ContactPhone**.</span></span> 
    
9. <span data-ttu-id="14164-210">在“表达式”\*\*\*\* 框中，输入 **[Customers].[Work Phone]**。</span><span class="sxs-lookup"><span data-stu-id="14164-210">In the **Expression** box, enter **[Customers].[Work Phone]**.</span></span> 
    
10. <span data-ttu-id="14164-211">选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="14164-211">Choose **Save**.</span></span> <span data-ttu-id="14164-212">在“宏名称”\*\*\*\* 框中输入 **GetContactPhone**，然后选择“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="14164-212">Enter **GetContactPhone** in the **Macro Name** box and then choose **OK**.</span></span>
    
    <span data-ttu-id="14164-213">宏应类似于图 8 中所示的宏。</span><span class="sxs-lookup"><span data-stu-id="14164-213">The macro should resemble the macro shown in Figure 8.</span></span>
    
    <span data-ttu-id="14164-214">**图 8. GetContactPhone 数据宏**</span><span class="sxs-lookup"><span data-stu-id="14164-214">**Figure 8. GetContactPhone data macro**</span></span>

    <span data-ttu-id="14164-215">![GetContactPhone 数据宏](media/odc_Access15_CreateAndCustomizeWebApp_Figure08.jpg "GetContactPhone 数据宏")</span><span class="sxs-lookup"><span data-stu-id="14164-215">![GetContactPhone data macro](media/odc_Access15_CreateAndCustomizeWebApp_Figure08.jpg "GetContactPhone data macro")</span></span>
  
11. <span data-ttu-id="14164-216">关闭宏设计视图。</span><span class="sxs-lookup"><span data-stu-id="14164-216">Close macro Design View.</span></span>
    
<span data-ttu-id="14164-217">现在我们已准备好将“联系人号码”\*\*\*\* 字段添加到问题列表窗体中。</span><span class="sxs-lookup"><span data-stu-id="14164-217">Now we're ready to add the **Contact Number** field to the Issues List form.</span></span> 
  
### <a name="to-add-the-contact-number-field-to-the-issues-list-form"></a><span data-ttu-id="14164-218">将“联系人号码”字段添加到问题列表窗体中</span><span class="sxs-lookup"><span data-stu-id="14164-218">To add the Contact Number field to the Issues List form</span></span>

1. <span data-ttu-id="14164-219">选择“问题”\*\*\*\* 表。</span><span class="sxs-lookup"><span data-stu-id="14164-219">Choose the **Issues** table.</span></span> <span data-ttu-id="14164-220">此操作会选择问题列表表单。</span><span class="sxs-lookup"><span data-stu-id="14164-220">This chooses the Issues list form.</span></span> 
    
2. <span data-ttu-id="14164-221">在视图选择器中，依次选择“列表”\*\*\*\*、“设置/操作”图标\*\*\*\*、“编辑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="14164-221">In the View selector, choose **List**, choose the **Settings/Action** icon, and then choose **Edit**.</span></span>
    
3. <span data-ttu-id="14164-222">将“联系人号码”\*\*\*\* 字段从“字段列表”\*\*\*\* 窗格拖动到你希望联系人号码显示的窗体上的位置。</span><span class="sxs-lookup"><span data-stu-id="14164-222">Drag the **Contact Number** field form the **Field List** pane to the location on the form where you want the contact number to be displayed.</span></span> 
    
4. <span data-ttu-id="14164-223">选择“联系人号码”\*\*\*\* 文本框，然后单击“数据”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="14164-223">Choose the **Contact Number** text box, and then click **Data**.</span></span> 
    
5. <span data-ttu-id="14164-224">在“控件名称”\*\*\*\* 框中，输入 **CustomerContact**，然后关闭“数据”\*\*\*\* 弹出框。</span><span class="sxs-lookup"><span data-stu-id="14164-224">In the **Control Name** box, enter **CustomerContact** and then close the **Data** popup.</span></span> 
    
6. <span data-ttu-id="14164-225">选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="14164-225">Choose **Save**.</span></span>
    
<span data-ttu-id="14164-226">现在我们应编写一个用户界面 (UI) 宏，将“工作电话”\*\*\*\* 字段从“客户”\*\*\*\* 表复制到“问题”\*\*\*\* 表的“联系人电话”\*\*\*\* 字段中。</span><span class="sxs-lookup"><span data-stu-id="14164-226">Now we should write a user interface (UI) macro that copies the **Work Phone** field from the **Customers** table into the **Contact Phone** field of the **Issues** table.</span></span> <span data-ttu-id="14164-227">“CustomerAutocomplete”\*\*\*\* 控件的“更新后”\*\*\*\* 事件是该宏的一个理想位置。</span><span class="sxs-lookup"><span data-stu-id="14164-227">The **After Update** event of the **CustomerAutocomplete** control is a good location for the macro.</span></span> 
  
### <a name="to-create-the-afterupdate-macro"></a><span data-ttu-id="14164-228">创建 AfterUpdate 宏</span><span class="sxs-lookup"><span data-stu-id="14164-228">To create the AfterUpdate macro</span></span>

1. <span data-ttu-id="14164-229">依次选择“CustomerAutocomplete”\*\*\*\* 控件、“操作”\*\*\*\* 按钮、“更新后”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="14164-229">Choose the **CustomerAutocomplete** control, choose the **Actions** button, and then choose **After Update**.</span></span> 
    
    <span data-ttu-id="14164-230">将在宏设计视图中打开一个空宏。</span><span class="sxs-lookup"><span data-stu-id="14164-230">A blank macro is opened in macro Design View.</span></span>
    
2. <span data-ttu-id="14164-231">从“添加新操作”\*\*\*\* 下拉列表中，选择“RunDataMacro”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="14164-231">From the **Add New Action** dropdown, choose **RunDataMacro**.</span></span> 
    
3. <span data-ttu-id="14164-232">在“宏名称”\*\*\*\* 下拉列表中，选择“GetContactPhone”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="14164-232">In the **Macro Name** dropdown, choose **GetContactPhone**.</span></span> 
    
4. <span data-ttu-id="14164-233">在" **CustID**"框中，输入" **[CustomerAutocomplete]** "。</span><span class="sxs-lookup"><span data-stu-id="14164-233">In the **CustID** box, enter **[CustomerAutocomplete]**.</span></span> 
    
5. <span data-ttu-id="14164-234">在“SetLocalVar”\*\*\*\* 框中，输入**电话**。</span><span class="sxs-lookup"><span data-stu-id="14164-234">In the **SetLocalVar** box, enter **Phone**.</span></span> 
    
    <span data-ttu-id="14164-235">当您选择之前创建的 GetContactPhone 数据宏时，Access 自动填充参数名称并返回宏的变量。</span><span class="sxs-lookup"><span data-stu-id="14164-235">When you chose the GetContactPhone data macro that was created earlier, Access automatically filled in the parameter name and return variable for the macro.</span></span>
    
    <span data-ttu-id="14164-236">客户的电话号码存储在名为 Phone 的变量中。</span><span class="sxs-lookup"><span data-stu-id="14164-236">The phone number for the customer is stored in a variable named Phone.</span></span>
    
6. <span data-ttu-id="14164-237">从“添加新操作”\*\*\*\* 下拉列表中，选择“SetProperty”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="14164-237">From the **Add New Action** dropdown, choose **SetProperty**.</span></span> 
    
7. <span data-ttu-id="14164-238">在“控件名称”\*\*\*\* 框中，输入 **CustomerContact**。</span><span class="sxs-lookup"><span data-stu-id="14164-238">In the **Control Name** box, enter **CustomerContact**.</span></span> 
    
8. <span data-ttu-id="14164-239">在“属性”\*\*\*\* 下拉列表中，选择“值”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="14164-239">In the **Property** dropdown, choose **Value**.</span></span> 
    
9. <span data-ttu-id="14164-240">在“值”\*\*\*\* 框中，输入 **=[Phone]**。</span><span class="sxs-lookup"><span data-stu-id="14164-240">In the **Value** box, enter **=[Phone]**.</span></span> 
    
10. <span data-ttu-id="14164-241">选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="14164-241">Choose **Save**.</span></span>
    
    <span data-ttu-id="14164-242">宏应类似于图 9 中所示的宏。</span><span class="sxs-lookup"><span data-stu-id="14164-242">The macro should resemble the macro shown in Figure 9.</span></span>
    
    <span data-ttu-id="14164-243">**图 9.“更新后”宏**</span><span class="sxs-lookup"><span data-stu-id="14164-243">**Figure 9. After Update macro**</span></span>

    <span data-ttu-id="14164-244">![“更新后”宏](media/odc_Access15_CreateAndCustomizeWebApp_Figure09.jpg "“更新后”宏")</span><span class="sxs-lookup"><span data-stu-id="14164-244">![After Update macro](media/odc_Access15_CreateAndCustomizeWebApp_Figure09.jpg "After Update macro")</span></span>
  
11. <span data-ttu-id="14164-245">关闭宏设计视图。</span><span class="sxs-lookup"><span data-stu-id="14164-245">Close macro Design View.</span></span>
    
12. <span data-ttu-id="14164-p124">关闭“问题列表”视图。当看到更改保存提示时，选择“是”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="14164-p124">Close the Issues List view. Choose **Yes** when you are prompted to save your changes.</span></span> 
    
<span data-ttu-id="14164-248">现在我们准备好发布自定义文本了。</span><span class="sxs-lookup"><span data-stu-id="14164-248">Now we're ready to text the customization.</span></span> <span data-ttu-id="14164-249">单击“启动应用”\*\*\*\* 在 Web 浏览器中打开应用，然后添加新问题。</span><span class="sxs-lookup"><span data-stu-id="14164-249">Click **Launch App** to open the app in your web browser and then add a new issue.</span></span> <span data-ttu-id="14164-250">输入客户名称后，“联系人号码”\*\*\*\* 框会自动更新，如图 10 所示。</span><span class="sxs-lookup"><span data-stu-id="14164-250">The **Contact Number** box updates automatically after the customer name is entered,  as shown in Figure 10.</span></span> 
  
<span data-ttu-id="14164-251">**图 10. 已更新电话号码的问题视图**</span><span class="sxs-lookup"><span data-stu-id="14164-251">**Figure 10. Issues view updated with phone number**</span></span>

<span data-ttu-id="14164-252">![已更新电话号码的问题视图](media/odc_Access15_CreateAndCustomizeWebApp_Figure10.jpg "已更新电话号码的问题视图")</span><span class="sxs-lookup"><span data-stu-id="14164-252">![Issues view updated with phone number](media/odc_Access15_CreateAndCustomizeWebApp_Figure10.jpg "Issues view updated with phone number")</span></span>
  
## <a name="conclusion"></a><span data-ttu-id="14164-253">结论</span><span class="sxs-lookup"><span data-stu-id="14164-253">Conclusion</span></span>

<span data-ttu-id="14164-p126">使用 中包含的架构模板之一是开始创建 Access Web 应用程序的好办法。为您自动创建的视图包含高级功能，这需要在 Access 桌面数据库中实施的自定义代码。</span><span class="sxs-lookup"><span data-stu-id="14164-p126">Using one of the schema templates included with is a good way to jump start the creation of an Access web app. The views that are automatically created for you contain advanced functionally that requires custom code to implement in a Access desktop database.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="14164-256">另请参阅</span><span class="sxs-lookup"><span data-stu-id="14164-256">See also</span></span>

- [<span data-ttu-id="14164-257">面向 Access 2013 开发人员的新增功能</span><span class="sxs-lookup"><span data-stu-id="14164-257">What's new for Access 2013 developers</span></span>](https://msdn.microsoft.com/library/df778f51-d65e-4c30-b618-65003ceb39b3%28Office.15%29.aspx) 
- [<span data-ttu-id="14164-258">Access custom web app reference</span><span class="sxs-lookup"><span data-stu-id="14164-258">Access custom web app reference</span></span>](access-custom-web-app-reference.md)
  

