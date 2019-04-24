---
title: 通过在 Access 应用程序中使用宏来筛选视图
manager: kelbow
ms.date: 08/18/2017
ms.audience: Developer
ms.topic: overview
ms.assetid: db4dbb71-1b22-4dfd-bc07-5f7d694fc038
description: 了解如何在 Access 应用程序中使用 RequeryRecords 宏操作和数据宏来筛选视图。
localization_priority: Priority
ms.openlocfilehash: 861851a3497f290fe0bcda38e51794194fbe7bbe
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32302662"
---
# <a name="filter-a-view-by-using-a-macro-in-an-access-app"></a><span data-ttu-id="92391-103">通过在 Access 应用程序中使用宏来筛选视图</span><span class="sxs-lookup"><span data-stu-id="92391-103">Filter a view by using a macro in an Access app</span></span>

<span data-ttu-id="92391-104">了解如何在 Access 应用程序中使用 RequeryRecords 宏操作和数据宏来筛选视图。</span><span class="sxs-lookup"><span data-stu-id="92391-104">Learn how to filter a view in an Access app by using the RequeryRecords macro action and a data macro.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="92391-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/zh-CN/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="92391-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/zh-CN/) to build no-code business solutions for the web and mobile devices.</span></span> 

<span data-ttu-id="92391-107">通过 Access 应用程序中的默认列表视图，你可以筛选字段中包含的值问题。</span><span class="sxs-lookup"><span data-stu-id="92391-107">The default list view in an Access app enables you to filter the issues on values that are contained in the fields.</span></span> <span data-ttu-id="92391-108">在某些情况下，你可能希望根据一组条件来筛选视图，而不是通过匹配值来进行筛选。</span><span class="sxs-lookup"><span data-stu-id="92391-108">There may be instances where you'd like to filter a view based on a set of conditions instead of by matching a value.</span></span> <span data-ttu-id="92391-109">为此，你必须创建一个宏。</span><span class="sxs-lookup"><span data-stu-id="92391-109">To do that you must create a macro.</span></span> <span data-ttu-id="92391-110">本文介绍如何创建用于筛选视图的宏，以显示将在未来 7 天内过期或到期的任务。</span><span class="sxs-lookup"><span data-stu-id="92391-110">This article shows you how to create a macro that filter a view to display tasks that are past due or due in the next 7 days.</span></span>
  
## <a name="prerequisites-for-building-an-app-with-access"></a><span data-ttu-id="92391-111">使用 Access 构建应用程序的先决条件</span><span class="sxs-lookup"><span data-stu-id="92391-111">Prerequisites for building an app with Access</span></span>
<span data-ttu-id="92391-112"><a name="Access2013FilterViewByUsingMacro_Prerequisites"> </a></span><span class="sxs-lookup"><span data-stu-id="92391-112"></span></span>

<span data-ttu-id="92391-113">若要按照此示例中的步骤操作，你需要：</span><span class="sxs-lookup"><span data-stu-id="92391-113">To follow the steps in this example, you need:</span></span>
  
- <span data-ttu-id="92391-114">Access 2013</span><span class="sxs-lookup"><span data-stu-id="92391-114">Access 2013</span></span>
- <span data-ttu-id="92391-115">SharePoint 2013 开发环境</span><span class="sxs-lookup"><span data-stu-id="92391-115">A SharePoint 2013 development environment</span></span>
    
> [!NOTE]
> <span data-ttu-id="92391-116">有关设置 SharePoint 开发环境的详细信息，请参阅[设置 SharePoint 2013 的常规开发环境](https://msdn.microsoft.com/library/08e4e4e1-d960-43fa-85df-f3c279ed6927%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="92391-116">For more information about setting up your SharePoint development environment, see [Set up a general development environment for SharePoint 2013](https://msdn.microsoft.com/library/08e4e4e1-d960-43fa-85df-f3c279ed6927%28Office.15%29.aspx).</span></span> <span data-ttu-id="92391-117">有关获取 Access 2013 和 SharePoint 2013 的详细信息，请参阅[下载](https://msdn.microsoft.com/office/apps/fp123627)。</span><span class="sxs-lookup"><span data-stu-id="92391-117">For more information about obtaining Access 2013 and SharePoint 2013, see [Downloads](https://msdn.microsoft.com/office/apps/fp123627).</span></span> 
  
## <a name="create-the-app"></a><span data-ttu-id="92391-118">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="92391-118">Create the app</span></span>
<span data-ttu-id="92391-119"><a name="Access2013FilterViewByUsingMacro_CreateApp"> </a></span><span class="sxs-lookup"><span data-stu-id="92391-119"></span></span>

<span data-ttu-id="92391-120">假设你想创建一个 Access 应用程序，用于跟踪企业的任务。</span><span class="sxs-lookup"><span data-stu-id="92391-120">Suppose you want to create an Access app that tracks tasks for your business.</span></span> <span data-ttu-id="92391-121">在开始创建表和视图之前，你应该搜索一个架构模板。</span><span class="sxs-lookup"><span data-stu-id="92391-121">Before you start creating the tables and view, you should search for a schema template.</span></span>
  
### <a name="to-create-the-task-tracking-app"></a><span data-ttu-id="92391-122">创建任务跟踪应用程序</span><span class="sxs-lookup"><span data-stu-id="92391-122">To create the task tracking app</span></span>

1. <span data-ttu-id="92391-123">打开 Access 并选择“**自定义 Web 应用程序**”。</span><span class="sxs-lookup"><span data-stu-id="92391-123">Open Access and choose **Custom web app**.</span></span>
    
2. <span data-ttu-id="92391-p105">输入一个名称和您的应用程序的 Web 位置。您也可以从“位置”列表中选择一个位置并选择“创建”。</span><span class="sxs-lookup"><span data-stu-id="92391-p105">Enter a name and the web location for your app. You can also choose a location from the **Locations** list and choose **Create**.</span></span>
    
3. <span data-ttu-id="92391-126">在“**搜索**”框中键入**任务**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="92391-126">Type **tasks** into the **Search** box and then press ENTER.</span></span> 
    
    <span data-ttu-id="92391-127">图 1 显示了一个可能对跟踪任务有用的模板列表。</span><span class="sxs-lookup"><span data-stu-id="92391-127">A list of templates that might be useful for tracking tasks is displayed in Figure 1.</span></span>
    
   <span data-ttu-id="92391-128">**图 1. 与任务搜索相匹配的模板**</span><span class="sxs-lookup"><span data-stu-id="92391-128">**Figure 1. Templates that match the search for tasks**</span></span>

   <span data-ttu-id="92391-129">![与问题搜索相匹配的模板](media/odc_Access15_CreateAndCustomizeWebApp_Figure01.JPG "与问题搜索相匹配的模板")</span><span class="sxs-lookup"><span data-stu-id="92391-129">![Templates that match the search for issues](media/odc_Access15_CreateAndCustomizeWebApp_Figure01.JPG "Templates that match the search for issues")</span></span>
  
4. <span data-ttu-id="92391-130">选择“**任务**”。</span><span class="sxs-lookup"><span data-stu-id="92391-130">Choose **Tasks**.</span></span>
    
<span data-ttu-id="92391-131">Access 将创建一组表和视图。</span><span class="sxs-lookup"><span data-stu-id="92391-131">Access creates a set of tables and views.</span></span>
  
<span data-ttu-id="92391-132">在你的应用程序中输入几个示例任务和员工。</span><span class="sxs-lookup"><span data-stu-id="92391-132">Enter several sample tasks and employees in your app.</span></span> <span data-ttu-id="92391-133">为此，单击“**启动应用程序**”以在 Web 浏览器中打开应用程序。</span><span class="sxs-lookup"><span data-stu-id="92391-133">To do this, choose **Launch App** to open the app in your web browser.</span></span> <span data-ttu-id="92391-134">在每个任务的“**截止日期**”字段中输入一个值。</span><span class="sxs-lookup"><span data-stu-id="92391-134">Enter a value in the **Due Date** field for each task.</span></span> <span data-ttu-id="92391-135">完成后返回到 Access。</span><span class="sxs-lookup"><span data-stu-id="92391-135">Return to Access when you're done.</span></span> 
  
## <a name="plan-the-customizations"></a><span data-ttu-id="92391-136">计划自定义项</span><span class="sxs-lookup"><span data-stu-id="92391-136">Plan the customizations</span></span>
<span data-ttu-id="92391-137"><a name="Access2013FilterViewByUsingMacro_PlanCustomizations"> </a></span><span class="sxs-lookup"><span data-stu-id="92391-137"></span></span>

<span data-ttu-id="92391-138">现在，你拥有包含多个任务的应用程序。</span><span class="sxs-lookup"><span data-stu-id="92391-138">You now have an app that contains several tasks.</span></span> <span data-ttu-id="92391-139">通过默认视图，你可以使用在视图所示字段中存储的条目来搜索任何任务。</span><span class="sxs-lookup"><span data-stu-id="92391-139">The default view enables you to search for any tasks using items that are stored in the fields displayed in the view.</span></span> <span data-ttu-id="92391-140">例如，你可以搜索高优先级问题或正在处理的问题。</span><span class="sxs-lookup"><span data-stu-id="92391-140">For example, you can search for high-priority issues or issues in progress.</span></span> <span data-ttu-id="92391-141">假设你希望通过显示将于下周到期的活动问题来确定工作的优先级。</span><span class="sxs-lookup"><span data-stu-id="92391-141">Suppose you want to prioritize your work by displaying active issues that are due in the coming week.</span></span> <span data-ttu-id="92391-142">为此，你应该创建用户界面 (UI) 宏。</span><span class="sxs-lookup"><span data-stu-id="92391-142">To do this, you should create a user interface (UI) macro.</span></span>
  
<span data-ttu-id="92391-143">可用于筛选视图的 UI 宏命令是 [RequeryRecords 宏操作（Access 自定义 Web 应用程序）](requeryrecords-macro-action-access-custom-web-app.md)。</span><span class="sxs-lookup"><span data-stu-id="92391-143">The UI macro command that you can use to filter the view is the [RequeryRecords Macro Action (Access custom web app)](requeryrecords-macro-action-access-custom-web-app.md).</span></span> <span data-ttu-id="92391-144">**RequeryRecords** 宏操作根据 *Where* 参数筛选视图，该参数以 SQL WHERE 子句的形式提供。</span><span class="sxs-lookup"><span data-stu-id="92391-144">The **RequeryRecords** macro action filters the view based on the  *Where*  argument, which is provided in the form of a SQL WHERE clause.</span></span> <span data-ttu-id="92391-145">若要筛选视图，你必须提供特定格式的多个事实来过滤视图。</span><span class="sxs-lookup"><span data-stu-id="92391-145">To filter the view, you must supply several facts in a specific format to filter the view.</span></span> 
  
<span data-ttu-id="92391-146">相关事实包括：</span><span class="sxs-lookup"><span data-stu-id="92391-146">The relevant facts are:</span></span>
  
- <span data-ttu-id="92391-147">要比较的字段</span><span class="sxs-lookup"><span data-stu-id="92391-147">The field or fields to compare</span></span>
    
- <span data-ttu-id="92391-148">如何引用当天日期</span><span class="sxs-lookup"><span data-stu-id="92391-148">How to refer to today's date</span></span>
    
- <span data-ttu-id="92391-149">如何引用相对于当天日期的特定日期</span><span class="sxs-lookup"><span data-stu-id="92391-149">How to refer to a particular day relative to today's date</span></span>
    
- <span data-ttu-id="92391-150">如何确定正在执行的任务</span><span class="sxs-lookup"><span data-stu-id="92391-150">How to determine which on tasks are in progress</span></span>
    
<span data-ttu-id="92391-151">“**截止日期**”字段提供了有关任务截止日期的信息。</span><span class="sxs-lookup"><span data-stu-id="92391-151">The **Due Date** field provides information about when a task is due.</span></span> <span data-ttu-id="92391-152">“**状态**”字段提供了有关每个任务的状态信息。</span><span class="sxs-lookup"><span data-stu-id="92391-152">The **Status** field provides status information about each task.</span></span> <span data-ttu-id="92391-153">若要引用宏中的字段，请使用格式 **[*TableName*].[*FieldName*]**。</span><span class="sxs-lookup"><span data-stu-id="92391-153">To refer to a field in a macro, use the format **[*TableName*].[*FieldName*]**.</span></span> <span data-ttu-id="92391-154">使用 **[Tasks].[Due Date]** 引用“**截至日期**”字段，并使用“**[Tasks].[Status]**”引用“**状态**”字段。</span><span class="sxs-lookup"><span data-stu-id="92391-154">Use **[Tasks].[Due Date]** to refer to the **Due Date** field and **[Tasks].[Status]** to refer to the **Status** field.</span></span> 
  
<span data-ttu-id="92391-155">[Today 函数（Access 自定义 Web 应用程序）](today-function-access-custom-web-app.md)函数将返回当天日期。</span><span class="sxs-lookup"><span data-stu-id="92391-155">The [Today Function (Access custom web app)](today-function-access-custom-web-app.md) function returns today's date.</span></span> <span data-ttu-id="92391-156">[DateAdd 函数（Access 自定义 Web 应用程序）](dateadd-function-access-custom-web-app.md)函数可用于计算在指定日期之后的特定天数的日期。</span><span class="sxs-lookup"><span data-stu-id="92391-156">The [DateAdd Function (Access custom web app)](dateadd-function-access-custom-web-app.md) function can be used to calculate a date that's a certain number of days after a specified date.</span></span> 
  
<span data-ttu-id="92391-157">“**状态**”字段包含几个可能的值。</span><span class="sxs-lookup"><span data-stu-id="92391-157">The **Status** field contains several possible values.</span></span> <span data-ttu-id="92391-158">值“**已完成**”表示任务不再处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="92391-158">A value of **Completed** indicates that the task is no longer active.</span></span> 
  
<span data-ttu-id="92391-159">这些事实可以组合到以下 SQL WHERE 子句中。</span><span class="sxs-lookup"><span data-stu-id="92391-159">These facts can be combined into the following SQL WHERE clause.</span></span>
  
```sql
[Tasks].[Due Date]<DateAdd(Day,7,Today()) AND [Tasks].[Status]<>"Completed"
```

<span data-ttu-id="92391-160">在宏中使用此 SQL WHERE 子句来筛选视图，以显示将在未来 7 天内到期或过期的活动问题。</span><span class="sxs-lookup"><span data-stu-id="92391-160">This SQL WHERE clause is used in the macro to filter the view to display active issues that are due in the next 7 days or are past due.</span></span>
  
<span data-ttu-id="92391-161">若要运行 UI 宏，必须将其附加到视图中出现的项目或事件。</span><span class="sxs-lookup"><span data-stu-id="92391-161">To run the UI macro, it must be attached to an item or an event that occurs in the view.</span></span> <span data-ttu-id="92391-162">**操作栏**是向视图添加自定义命令的便捷位置。</span><span class="sxs-lookup"><span data-stu-id="92391-162">The **Action Bar** is a convenient place to add a custom command to the view.</span></span> <span data-ttu-id="92391-163">**操作栏**是可自定义的工具栏，显示在每个视图的顶部。</span><span class="sxs-lookup"><span data-stu-id="92391-163">The **Action Bar** is a customizable toolbar that appears at the top of each view.</span></span> <span data-ttu-id="92391-164">默认情况下，**操作栏**包含用于添加、编辑、保存、删除和取消编辑的按钮。</span><span class="sxs-lookup"><span data-stu-id="92391-164">By default, the **Action Bar** contains buttons to add, edit, save, delete, and cancel edits.</span></span> <span data-ttu-id="92391-165">你可以添加用于执行自定义操作的按钮，例如筛选视图。</span><span class="sxs-lookup"><span data-stu-id="92391-165">You can add buttons that perform custom actions, such as filtering the view.</span></span> 
  
<span data-ttu-id="92391-166">如果视图包含符合指定条件的记录，则 **RequeryRecords** 会筛选该视图。</span><span class="sxs-lookup"><span data-stu-id="92391-166">If the view contains records that meet the specified criteria, then **RequeryRecords** filters the view.</span></span> <span data-ttu-id="92391-167">但是，如果视图不包含符合条件的记录，则会显示新的空白记录。</span><span class="sxs-lookup"><span data-stu-id="92391-167">However, if the view doesn't contain any records that meet the criteria, than a new, blank record is displayed.</span></span> <span data-ttu-id="92391-168">如果你希望在没有将于下周到期的任务时不要显示空白记录，则必须在调用 **RequeryRecords** 宏操作之前找到检查任务的方法。</span><span class="sxs-lookup"><span data-stu-id="92391-168">If you don't want a blank record to be displayed if no tasks are due in the next week, then you must find a method to check the tasks before you call the **RequeryRecords** macro action.</span></span> <span data-ttu-id="92391-169">为此，请创建数据宏以检查符合条件的记录。</span><span class="sxs-lookup"><span data-stu-id="92391-169">To do this, create a data macro to check for records that meet the criteria.</span></span> 
  
<span data-ttu-id="92391-170">UI 宏将调用数据宏，后者会尝试查找将于下周到期的任务。</span><span class="sxs-lookup"><span data-stu-id="92391-170">The UI macro will call the data macro, which will try to find a task that's due in the next week.</span></span> <span data-ttu-id="92391-171">如果数据宏找到任务，则会自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="92391-171">If the data macro finds the task then customize the app.</span></span>
  
## <a name="customize-the-app"></a><span data-ttu-id="92391-172">自定义应用程序</span><span class="sxs-lookup"><span data-stu-id="92391-172">Customize the app</span></span>
<span data-ttu-id="92391-173"><a name="Access2013FilterViewByUsingMacro_CustomizeApp"> </a></span><span class="sxs-lookup"><span data-stu-id="92391-173"></span></span>

<span data-ttu-id="92391-174">现在，你已确定自定义项，请实现它们。</span><span class="sxs-lookup"><span data-stu-id="92391-174">Now that you've determined the customizations, implement them.</span></span> <span data-ttu-id="92391-175">应该先创建数据宏。</span><span class="sxs-lookup"><span data-stu-id="92391-175">The data macro should be created first.</span></span> <span data-ttu-id="92391-176">某些数据宏将直接附加到表。</span><span class="sxs-lookup"><span data-stu-id="92391-176">Some data macros are attached directly to tables.</span></span> <span data-ttu-id="92391-177">但是，此数据宏是独立的数据宏。</span><span class="sxs-lookup"><span data-stu-id="92391-177">However, this data macro is a stand-alone data macro.</span></span>
  
### <a name="to-create-the-data-macro"></a><span data-ttu-id="92391-178">创建数据宏</span><span class="sxs-lookup"><span data-stu-id="92391-178">To create the data macro</span></span>

1. <span data-ttu-id="92391-179">在 Access 中打开应用程序。</span><span class="sxs-lookup"><span data-stu-id="92391-179">Open the app in Access.</span></span>
    
2. <span data-ttu-id="92391-180">在“**创建**”组中，依次选择“**高级**”、“**数据宏**”。</span><span class="sxs-lookup"><span data-stu-id="92391-180">In the **Create** group, choose **Advanced**, and then choose **Data Macro**.</span></span>
    
    <span data-ttu-id="92391-181">此时将在宏设计视图中打开一个空白数据宏。</span><span class="sxs-lookup"><span data-stu-id="92391-181">A blank data macro is opened in macro Design View.</span></span>
    
3. <span data-ttu-id="92391-182">从“**添加新操作**”列表框中，选择 **LookupRecord**。</span><span class="sxs-lookup"><span data-stu-id="92391-182">From the **Add New Action** list box, choose **LookupRecord**.</span></span>
    
4. <span data-ttu-id="92391-183">在“**查找所选对象中的记录**”列表框中，选择“**任务**”。</span><span class="sxs-lookup"><span data-stu-id="92391-183">In the **Look Up A Record In** list box, choose **Tasks**.</span></span>
    
5. <span data-ttu-id="92391-184">在“**Where 条件**”框中，输入 **[Tasks].[Due Date]\<DateAdd(Day,7,Today()) AND [Tasks].[Status]\<\>"Completed"**。</span><span class="sxs-lookup"><span data-stu-id="92391-184">In the **Where Condition** box, enter **[Tasks].[Due Date]\<DateAdd(Day,7,Today()) AND [Tasks].[Status]\<\>"Completed"**.</span></span> 
    
6. <span data-ttu-id="92391-185">从“**添加新操作**”列表框中选择 **SetReturnVar**。</span><span class="sxs-lookup"><span data-stu-id="92391-185">Choose **SetReturnVar** from the **Add New Action** list box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="92391-186">你将看到两个“**添加新操作**”列表框，一个在 **LookupRecord** 块之内，另一个在 **LookupRecord** 块之外。</span><span class="sxs-lookup"><span data-stu-id="92391-186">You'll see two **Add New Action** list boxes, one within the **LookupRecord** block, and another outside the **LookupRecord** block.</span></span> <span data-ttu-id="92391-187">你应该选择 **LookupRecord** 块之内的“**添加新操作**”列表框，如图 1 所示。</span><span class="sxs-lookup"><span data-stu-id="92391-187">You should choose the **Add New Action** list box within the **LookupRecord** block, as shown in Figure 1.</span></span> 
  
   <span data-ttu-id="92391-188">**图 1.“添加新操作”列表框**</span><span class="sxs-lookup"><span data-stu-id="92391-188">**Figure 1. Add New Action list box**</span></span>

   <span data-ttu-id="92391-189">![“添加新操作”下拉列表](media/odc_Access2013_FilterFormByUsingMacro_Figure01.jpg "“添加新操作”下拉列表")</span><span class="sxs-lookup"><span data-stu-id="92391-189">![Add New Action dropdown](media/odc_Access2013_FilterFormByUsingMacro_Figure01.jpg "Add New Action dropdown")</span></span>
  
7. <span data-ttu-id="92391-190">在“**名称**”框中，输入 **TaskFound**。</span><span class="sxs-lookup"><span data-stu-id="92391-190">In the **Name** box, enter **TaskFound**.</span></span> 
    
8. <span data-ttu-id="92391-191">在“**表达式**”框中，输入“**是**”。</span><span class="sxs-lookup"><span data-stu-id="92391-191">In the **Expression** box, enter **"Yes"**.</span></span> 
    
9. <span data-ttu-id="92391-192">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="92391-192">Choose **Save**.</span></span> <span data-ttu-id="92391-193">在“**宏名称**”框中输入 **TasksDueSoon**，然后选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="92391-193">Enter **TasksDueSoon** in the **Macro Name** box and then choose **OK**.</span></span>
    
    <span data-ttu-id="92391-194">宏应类似于图 2 中所示的宏。</span><span class="sxs-lookup"><span data-stu-id="92391-194">The macro should resemble the macro shown in Figure 2.</span></span>
    
   <span data-ttu-id="92391-195">**图 2. TasksDueSoon 数据宏**</span><span class="sxs-lookup"><span data-stu-id="92391-195">**Figure 2. TasksDueSoon data macro**</span></span>

   <span data-ttu-id="92391-196">![TasksDueSoon 数据宏](media/odc_Access2013_FilterFormByUsingMacro_Figure02.jpg "TasksDueSoon 数据宏")</span><span class="sxs-lookup"><span data-stu-id="92391-196">![TasksDueSoon data macro](media/odc_Access2013_FilterFormByUsingMacro_Figure02.jpg "TasksDueSoon data macro")</span></span>
  
10. <span data-ttu-id="92391-197">关闭宏设计视图。</span><span class="sxs-lookup"><span data-stu-id="92391-197">Close macro Design View.</span></span>
    
<span data-ttu-id="92391-198">现在，我们已准备好向操作栏添加自定义按钮。</span><span class="sxs-lookup"><span data-stu-id="92391-198">Now, we're ready to add a custom button to the Action Bar.</span></span>
  
### <a name="to-add-a-custom-button-to-the-action-bar"></a><span data-ttu-id="92391-199">向操作栏添加自定义按钮</span><span class="sxs-lookup"><span data-stu-id="92391-199">To add a custom button to the Action Bar</span></span>

1. <span data-ttu-id="92391-200">选择“**任务**”表。</span><span class="sxs-lookup"><span data-stu-id="92391-200">Choose the **Tasks** table.</span></span> <span data-ttu-id="92391-201">此操作会选择任务列表表单。</span><span class="sxs-lookup"><span data-stu-id="92391-201">This chooses the Tasks List form.</span></span> 
    
2. <span data-ttu-id="92391-202">在视图选择器中，依次选择“**列表**”、“**设置/操作**”图标、“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="92391-202">In the View selector, choose **List**, choose the **Settings/Action** icon, and then choose **Edit**.</span></span>
    
    <span data-ttu-id="92391-203">视图将在“设计视图”中打开。</span><span class="sxs-lookup"><span data-stu-id="92391-203">The view is opened in Design View.</span></span>
    
3. <span data-ttu-id="92391-204">现在，我们已准备好向操作栏添加自定义按钮。</span><span class="sxs-lookup"><span data-stu-id="92391-204">Now, we're ready to add a custom button to the Action Bar.</span></span> <span data-ttu-id="92391-205">若要执行此操作，请选择“**添加自定义操作**”，如图 3 中所示。</span><span class="sxs-lookup"><span data-stu-id="92391-205">To do this, choose **Add custom action** as shown in Figure 3.</span></span> 
    
   <span data-ttu-id="92391-206">**图 3. 添加自定义操作按钮**</span><span class="sxs-lookup"><span data-stu-id="92391-206">**Figure 3. Add custom action button**</span></span>

   <span data-ttu-id="92391-207">![添加自定义操作按钮](media/odc_Access2013_FilterFormByUsingMacro_Figure03.jpg "添加自定义操作按钮")</span><span class="sxs-lookup"><span data-stu-id="92391-207">![Add custom action button](media/odc_Access2013_FilterFormByUsingMacro_Figure03.jpg "Add custom action button")</span></span>
  
    <span data-ttu-id="92391-208">新操作显示为带有星形图标的按钮，如图 4 中所示。</span><span class="sxs-lookup"><span data-stu-id="92391-208">The new action is displayed as a button with a star icon as shown in Figure 4.</span></span>
    
   <span data-ttu-id="92391-209">**图 4. 新的操作栏按钮**</span><span class="sxs-lookup"><span data-stu-id="92391-209">**Figure 4. New Action Bar button**</span></span>

   <span data-ttu-id="92391-210">![新的操作栏按钮](media/odc_Access2013_FilterFormByUsingMacro_Figure04.jpg "新的操作栏按钮")</span><span class="sxs-lookup"><span data-stu-id="92391-210">![New Action Bar button](media/odc_Access2013_FilterFormByUsingMacro_Figure04.jpg "New Action Bar button")</span></span>
  
4. <span data-ttu-id="92391-211">选择自定义操作栏按钮，然后选择“**数据**”图标。</span><span class="sxs-lookup"><span data-stu-id="92391-211">Choose the custom Action Bar Button, and then choose the **Data** icon.</span></span> 
    
    <span data-ttu-id="92391-212">此时将显示“**数据**”对话框。</span><span class="sxs-lookup"><span data-stu-id="92391-212">The **Data** dialog box appears.</span></span> 
    
5. <span data-ttu-id="92391-213">在“**控件名称**”框中，输入 **FilterTasks**。</span><span class="sxs-lookup"><span data-stu-id="92391-213">In the **Control Name** box, enter **FilterTasks**.</span></span> 
    
6. <span data-ttu-id="92391-214">在“**工具提示**”框中，输入“**显示将于下周过期或到期的任务**”。</span><span class="sxs-lookup"><span data-stu-id="92391-214">In the **Tooltip** box, enter **Display tasks past due or due in the next week**.</span></span> 
    
<span data-ttu-id="92391-215">现在，我们已准备好创建用于筛选视图的 UI 宏。</span><span class="sxs-lookup"><span data-stu-id="92391-215">Now, we're ready to create the UI macro that will filter the view.</span></span>
  
### <a name="to-create-the-ui-macro-to-filter-the-view"></a><span data-ttu-id="92391-216">创建用于筛选视图的 UI 宏</span><span class="sxs-lookup"><span data-stu-id="92391-216">To create the UI macro to filter the view</span></span>

1. <span data-ttu-id="92391-217">在“**数据**”对话框中，选择 **On Click**，如图 5 中所示。</span><span class="sxs-lookup"><span data-stu-id="92391-217">In the **Data** dialog box, choose **On Click** as shown in Figure 5.</span></span> 
    
   <span data-ttu-id="92391-218">**图 5.“数据”对话框**</span><span class="sxs-lookup"><span data-stu-id="92391-218">**Figure 5. Data dialog box**</span></span>

   <span data-ttu-id="92391-219">![“数据”对话框](media/odc_Access2013_FilterFormByUsingMacro_Figure05.jpg "“数据”对话框")</span><span class="sxs-lookup"><span data-stu-id="92391-219">![Data dialog box](media/odc_Access2013_FilterFormByUsingMacro_Figure05.jpg "Data dialog box")</span></span>
  
    <span data-ttu-id="92391-220">将在宏设计视图中打开一个空白 UI 宏。</span><span class="sxs-lookup"><span data-stu-id="92391-220">A blank UI macro is opened in macro Design View.</span></span>
    
2. <span data-ttu-id="92391-221">从“**添加新操作**”列表框中，选择 **RunDataMacro**。</span><span class="sxs-lookup"><span data-stu-id="92391-221">From the **Add New Action** list box, choose **RunDataMacro**.</span></span> 
    
3. <span data-ttu-id="92391-222">在“宏名称”框中，输入 **TasksDueSoon**。</span><span class="sxs-lookup"><span data-stu-id="92391-222">In the Macro Name box, enter **TasksDueSoon**.</span></span> 
    
    <span data-ttu-id="92391-223">在 **SetLocalVar** 框中，输入 **FilterRecords**。</span><span class="sxs-lookup"><span data-stu-id="92391-223">In the **SetLocalVar** box, enter **FilterRecords**.</span></span> 
    
    <span data-ttu-id="92391-224">**RunDataMacro** 操作将调用我们之前创建的 **TasksDueSoon** 数据宏，并将其结果存储在名为 **FilterRecords** 的变量中。</span><span class="sxs-lookup"><span data-stu-id="92391-224">The **RunDataMacro** action calls the **TasksDueSoon** data macro we created earlier and stores its result in a variable named **FilterRecords**.</span></span> 
    
4. <span data-ttu-id="92391-225">从“**添加新操作**”列表框中，选择 **If**。</span><span class="sxs-lookup"><span data-stu-id="92391-225">From the **Add New Action** list box, choose **If**.</span></span> 
    
5. <span data-ttu-id="92391-226">在 **If** 框中，输入 **[FilterRecords]="Yes"**。</span><span class="sxs-lookup"><span data-stu-id="92391-226">In the **If** box, enter **[FilterRecords]="Yes"**.</span></span> 
    
6. <span data-ttu-id="92391-227">从“**添加新操作**”列表框中，选择 **RequeryRecords**。</span><span class="sxs-lookup"><span data-stu-id="92391-227">From the **Add New Action** list box, choose **RequeryRecords**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="92391-228">你将看到两个“**添加新操作**”列表框，一个在 **If** 块之内，另一个在 **If** 块之外。</span><span class="sxs-lookup"><span data-stu-id="92391-228">You'll see two **Add New Action** list boxes, one within the **If** block, and another outside the **If** block.</span></span> <span data-ttu-id="92391-229">你应该选择 **If** 块之内的“**添加新操作**”列表框，如图 6 中所示。</span><span class="sxs-lookup"><span data-stu-id="92391-229">You should choose the **Add New Action** list box within the **If** block, as shown in Figure 6.</span></span> 
  
   <span data-ttu-id="92391-230">**图 6.“添加新操作”列表框**</span><span class="sxs-lookup"><span data-stu-id="92391-230">**Figure 6. Add New Action list box**</span></span>

   <span data-ttu-id="92391-231">![“添加新操作”下拉列表](media/odc_Access2013_FilterFormByUsingMacro_Figure06.jpg "“添加新操作”下拉列表")</span><span class="sxs-lookup"><span data-stu-id="92391-231">![Add New Action dropdown](media/odc_Access2013_FilterFormByUsingMacro_Figure06.jpg "Add New Action dropdown")</span></span>
  
7. <span data-ttu-id="92391-232">在 **Where** 框中，输入 **[Tasks].[Due Date]\<DateAdd(Day,7,Today()) AND [Tasks].[Status]\<\>"Completed"**。</span><span class="sxs-lookup"><span data-stu-id="92391-232">In the **Where** box, enter **[Tasks].[Due Date]\<DateAdd(Day,7,Today()) AND [Tasks].[Status]\<\>"Completed"**.</span></span> 
    
8. <span data-ttu-id="92391-233">在“**排序依据**”框中，输入 **[Due Date]**。</span><span class="sxs-lookup"><span data-stu-id="92391-233">In the **Order By** box, enter **[Due Date]**.</span></span> 
    
9. <span data-ttu-id="92391-234">选择“**添加新操作**”框右侧显示的“**添加 Else**”链接，如图 7 中所示。</span><span class="sxs-lookup"><span data-stu-id="92391-234">Choose the **Add Else** link that appears to the right side of the **Add New Action** box as shown in Figure 7.</span></span> 
    
   <span data-ttu-id="92391-235">**图 7. 添加 Else 链接**</span><span class="sxs-lookup"><span data-stu-id="92391-235">**Figure 7. Add Else link**</span></span>

   <span data-ttu-id="92391-236">![添加 Else 链接](media/odc_Access2013_FilterFormByUsingMacro_Figure07.jpg "添加 Else 链接")</span><span class="sxs-lookup"><span data-stu-id="92391-236">![Add Else link](media/odc_Access2013_FilterFormByUsingMacro_Figure07.jpg "Add Else link")</span></span>
  
    <span data-ttu-id="92391-237">一个 Else 子句将添加到 If 块。</span><span class="sxs-lookup"><span data-stu-id="92391-237">An Else clause is added to the If block.</span></span>
    
10. <span data-ttu-id="92391-238">从“**添加新操作**”列表框中，选择 **MessageBox**。</span><span class="sxs-lookup"><span data-stu-id="92391-238">From the **Add New Action** list box, choose **MessageBox**.</span></span> 
    
11. <span data-ttu-id="92391-239">在“**消息**”框中，输入“**在未来 7 天内没有过期或到期的任务！**”。</span><span class="sxs-lookup"><span data-stu-id="92391-239">In the **Message** box, enter **No tasks are overdue or due in the next 7 days!**.</span></span> 
    
12. <span data-ttu-id="92391-240">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="92391-240">Choose **Save**.</span></span>
    
    <span data-ttu-id="92391-241">宏应类似于图 8 中所示的宏。</span><span class="sxs-lookup"><span data-stu-id="92391-241">The macro should resemble the macro shown in Figure 8.</span></span>
    
    <span data-ttu-id="92391-242">**图 8. 用于筛选视图的 UI 宏**</span><span class="sxs-lookup"><span data-stu-id="92391-242">**Figure 8. UI macro to filter the view**</span></span>

    <span data-ttu-id="92391-243">![用于筛选视图的 UI 宏](media/odc_Access2013_FilterFormByUsingMacro_Figure08.jpg "用于筛选视图的 UI 宏")</span><span class="sxs-lookup"><span data-stu-id="92391-243">![UI macro to filter the view](media/odc_Access2013_FilterFormByUsingMacro_Figure08.jpg "UI macro to filter the view")</span></span>
  
13. <span data-ttu-id="92391-244">关闭宏设计视图。</span><span class="sxs-lookup"><span data-stu-id="92391-244">Close macro Design View.</span></span>
    
<span data-ttu-id="92391-245">此时，我们已经创建了 UI 宏，用于筛选“任务列表”视图以显示紧急任务。</span><span class="sxs-lookup"><span data-stu-id="92391-245">At this point, we've created the UI macro that filters the Tasks List view to display the urgent tasks.</span></span> <span data-ttu-id="92391-246">让视图保持筛选状态而不提供删除筛选器的方法似乎有些不妥。</span><span class="sxs-lookup"><span data-stu-id="92391-246">It wouldn't be polite to leave the view in a filtered state without providing a method to remove the filter.</span></span> <span data-ttu-id="92391-247">为此，请添加另一个操作栏按钮和 UI 宏。</span><span class="sxs-lookup"><span data-stu-id="92391-247">To do this, add another Action Bar button and UI Macro.</span></span>
  
### <a name="to-add-an-action-bar-button-to-remove-the-filter"></a><span data-ttu-id="92391-248">添加操作栏按钮以删除筛选器</span><span class="sxs-lookup"><span data-stu-id="92391-248">To add an Action Bar Button to remove the filter</span></span>

1. <span data-ttu-id="92391-249">选择“**添加自定义操作**”。</span><span class="sxs-lookup"><span data-stu-id="92391-249">Choose **Add custom action**.</span></span>
    
    <span data-ttu-id="92391-250">新操作显示为带有星形图标的按钮</span><span class="sxs-lookup"><span data-stu-id="92391-250">The new action is displayed as a button with a star icon</span></span>
    
2. <span data-ttu-id="92391-251">选择自定义操作栏按钮，然后选择“**数据**”图标。</span><span class="sxs-lookup"><span data-stu-id="92391-251">Choose the custom Action Bar button, and then choose the **Data** icon.</span></span> 
    
    <span data-ttu-id="92391-252">此时将显示“**数据**”对话框。</span><span class="sxs-lookup"><span data-stu-id="92391-252">The **Data** dialog box appears.</span></span> 
    
3. <span data-ttu-id="92391-253">在“**控件名称**”框中，输入 **RemoveFilter**。</span><span class="sxs-lookup"><span data-stu-id="92391-253">In the **Control Name** box, enter **RemoveFilter**.</span></span> 
    
4. <span data-ttu-id="92391-254">在“**工具提示**”框中，输入“**删除应用于视图的所有筛选器**”。</span><span class="sxs-lookup"><span data-stu-id="92391-254">In the **Tooltip** box, enter **Remove all filter applied to the view**.</span></span> 
    
<span data-ttu-id="92391-255">现在，我们已准备好创建将从视图中删除筛选器的 UI 宏。</span><span class="sxs-lookup"><span data-stu-id="92391-255">Now, we're ready to create the UI macro that will remove the filter form the view.</span></span>
  
### <a name="to-create-the-ui-macro-to-remove-the-filter-from-the-view"></a><span data-ttu-id="92391-256">创建用于从视图中删除筛选器的 UI 宏</span><span class="sxs-lookup"><span data-stu-id="92391-256">To create the UI macro to remove the filter from the view</span></span>

1. <span data-ttu-id="92391-257">在“**数据**”对话框中，选择 **On Click**。</span><span class="sxs-lookup"><span data-stu-id="92391-257">In the **Data** dialog box, choose **On Click**.</span></span>
    
    <span data-ttu-id="92391-258">将在宏设计视图中打开一个空白 UI 宏。</span><span class="sxs-lookup"><span data-stu-id="92391-258">A blank UI macro is opened in macro Design View.</span></span>
    
2. <span data-ttu-id="92391-259">从“**添加新操作**”列表框中，选择 **RequeryRecords**。</span><span class="sxs-lookup"><span data-stu-id="92391-259">From the **Add New Action** list box, choose **RequeryRecords**.</span></span> 
    
    <span data-ttu-id="92391-260">此时，我们会将 **Where** 和“**排序依据**”框留空。</span><span class="sxs-lookup"><span data-stu-id="92391-260">This time, we'll leave the **Where** and **Order By** boxes empty.</span></span> <span data-ttu-id="92391-261">然后在没有任何参数的情况下调用 **RequeryRecords** 操作，所有筛选器都将从视图中删除。</span><span class="sxs-lookup"><span data-stu-id="92391-261">Then the **RequeryRecords** action is called without any parameters, all filters are removed from the view.</span></span> 
    
3. <span data-ttu-id="92391-262">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="92391-262">Choose **Save**.</span></span>
    
4. <span data-ttu-id="92391-263">关闭宏设计视图。</span><span class="sxs-lookup"><span data-stu-id="92391-263">Close macro Design View.</span></span>
    
5. <span data-ttu-id="92391-264">关闭“任务列表”视图。</span><span class="sxs-lookup"><span data-stu-id="92391-264">Close the Tasks List view.</span></span> <span data-ttu-id="92391-265">当你收到保存更改的提示时，选择“**是**”。</span><span class="sxs-lookup"><span data-stu-id="92391-265">Choose **Yes** when you are prompted to save your changes.</span></span> 
    
<span data-ttu-id="92391-266">现在，我们已准备好发布自定义文本。</span><span class="sxs-lookup"><span data-stu-id="92391-266">Now, we're ready to text the customization.</span></span> <span data-ttu-id="92391-267">选择“**启动应用程序**”以在 Web 浏览器中打开应用程序，然后选择自定义 FilterTasks 操作栏按钮。</span><span class="sxs-lookup"><span data-stu-id="92391-267">Choose **Launch App** to open the app in your web browser and then choose the custom FilterTasks Action Bar button.</span></span> <span data-ttu-id="92391-268">此时将显示将在未来 7 天内过期或到期的任何任务。</span><span class="sxs-lookup"><span data-stu-id="92391-268">Any tasks past due or due in the next 7 days are displayed.</span></span> <span data-ttu-id="92391-269">如果应用程序不包含紧急任务，则会显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="92391-269">A message is displayed if the app contains no urgent tasks.</span></span> 
  
## <a name="conclusion"></a><span data-ttu-id="92391-270">结论</span><span class="sxs-lookup"><span data-stu-id="92391-270">Conclusion</span></span>

<span data-ttu-id="92391-271">你可以在 UI 宏中使用 **RequeryRecords** 宏操作，以根据你选择的条件来筛选视图。</span><span class="sxs-lookup"><span data-stu-id="92391-271">You can use the **RequeryRecords** macro action in a UI macro to filter the view based on the criteria that you choose.</span></span> <span data-ttu-id="92391-272">根据所需的行为，你可能需要创建数据宏以在使用 **RequeryRecords** 宏操作之前验证记录是否符合条件。</span><span class="sxs-lookup"><span data-stu-id="92391-272">Depending on the behavior that you want, you may want to create a data macro to verify that a record meets the criteria before you use the **RequeryRecords** macro action.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="92391-273">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92391-273">See also</span></span>

- [<span data-ttu-id="92391-274">面向 Access 2013 开发人员的新增功能</span><span class="sxs-lookup"><span data-stu-id="92391-274">What's new for Access 2013 developers</span></span>](https://msdn.microsoft.com/library/df778f51-d65e-4c30-b618-65003ceb39b3%28Office.15%29.aspx)
    

