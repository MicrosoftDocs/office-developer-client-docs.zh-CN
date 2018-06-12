---
title: 访问应用程序中使用宏筛选视图
manager: kelbow
ms.date: 08/18/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: db4dbb71-1b22-4dfd-bc07-5f7d694fc038
description: 了解如何使用 RequeryRecords 宏操作和数据宏筛选 Access 应用程序中的视图。
ms.openlocfilehash: 9cd8c74b3949a0bb496798df663b1b42fb2868d9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773490"
---
# <a name="filter-a-view-by-using-a-macro-in-an-access-app"></a><span data-ttu-id="2ab87-103">访问应用程序中使用宏筛选视图</span><span class="sxs-lookup"><span data-stu-id="2ab87-103">Filter a view by using a macro in an Access app</span></span>

<span data-ttu-id="2ab87-104">了解如何使用 RequeryRecords 宏操作和数据宏筛选 Access 应用程序中的视图。</span><span class="sxs-lookup"><span data-stu-id="2ab87-104">Learn how to filter a view in an Access app by using the RequeryRecords macro action and a data macro.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2ab87-p101">[!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="2ab87-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 

<span data-ttu-id="2ab87-107">Access 应用程序中的默认列表视图，可以筛选的字段中包含的值的问题。</span><span class="sxs-lookup"><span data-stu-id="2ab87-107">The default list view in an Access app enables you to filter the issues on values that are contained in the fields.</span></span> <span data-ttu-id="2ab87-108">可能想要筛选通过匹配值基于一组条件，而不是视图的实例。</span><span class="sxs-lookup"><span data-stu-id="2ab87-108">There may be instances where you'd like to filter a view based on a set of conditions instead of by matching a value.</span></span> <span data-ttu-id="2ab87-109">为此，您必须创建宏。</span><span class="sxs-lookup"><span data-stu-id="2ab87-109">To do that you must create a macro.</span></span> <span data-ttu-id="2ab87-110">本文演示如何创建用于筛选视图以显示位于以前到期或截止随后 7 天的任务的宏。</span><span class="sxs-lookup"><span data-stu-id="2ab87-110">This article shows you how to create a macro that filter a view to display tasks that are past due or due in the next 7 days.</span></span>
  
## <a name="prerequisites-for-building-an-app-with-access"></a><span data-ttu-id="2ab87-111">构建具有访问权限的应用程序的先决条件</span><span class="sxs-lookup"><span data-stu-id="2ab87-111">Prerequisites for building an app with Access</span></span>
<span data-ttu-id="2ab87-112"><a name="Access2013FilterViewByUsingMacro_Prerequisites"> </a></span><span class="sxs-lookup"><span data-stu-id="2ab87-112"></span></span>

<span data-ttu-id="2ab87-113">若要遵循此示例中的步骤，您需要：</span><span class="sxs-lookup"><span data-stu-id="2ab87-113">To follow the steps in this example, you need:</span></span>
  
- <span data-ttu-id="2ab87-114">Access 2013</span><span class="sxs-lookup"><span data-stu-id="2ab87-114">Access 2013</span></span>
- <span data-ttu-id="2ab87-115">SharePoint 2013 开发环境</span><span class="sxs-lookup"><span data-stu-id="2ab87-115">A SharePoint 2013 development environment</span></span>
    
> [!NOTE]
> <span data-ttu-id="2ab87-116">有关设置 SharePoint 开发环境的详细信息，请参阅[设置 SharePoint 2013 的常规开发环境](http://msdn.microsoft.com/library/08e4e4e1-d960-43fa-85df-f3c279ed6927%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2ab87-116">For more information about setting up your SharePoint development environment, see [Set up a general development environment for SharePoint 2013](http://msdn.microsoft.com/library/08e4e4e1-d960-43fa-85df-f3c279ed6927%28Office.15%29.aspx).</span></span> <span data-ttu-id="2ab87-117">> 的有关获取 Access 2013 和 SharePoint 2013 的详细信息，请参阅[下载](http://msdn.microsoft.com/en-US/office/apps/fp123627)。</span><span class="sxs-lookup"><span data-stu-id="2ab87-117">>  For more information about obtaining Access 2013 and SharePoint 2013, see [Downloads](http://msdn.microsoft.com/en-US/office/apps/fp123627).</span></span> 
  
## <a name="create-the-app"></a><span data-ttu-id="2ab87-118">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="2ab87-118">Create the app</span></span>
<span data-ttu-id="2ab87-119"><a name="Access2013FilterViewByUsingMacro_CreateApp"> </a></span><span class="sxs-lookup"><span data-stu-id="2ab87-119"></span></span>

<span data-ttu-id="2ab87-120">假设您想要创建的跟踪任务为您的业务应用程序访问。</span><span class="sxs-lookup"><span data-stu-id="2ab87-120">Suppose you want to create an Access app that tracks tasks for your business.</span></span> <span data-ttu-id="2ab87-121">在开始创建的表和视图之前，您应搜索架构的模板。</span><span class="sxs-lookup"><span data-stu-id="2ab87-121">Before you start creating the tables and view, you should search for a schema template.</span></span>
  
### <a name="to-create-the-task-tracking-app"></a><span data-ttu-id="2ab87-122">若要创建跟踪应用程序的任务</span><span class="sxs-lookup"><span data-stu-id="2ab87-122">To create the task tracking app</span></span>

1. <span data-ttu-id="2ab87-123">打开 Access 并选择 **"自定义 Web 应用程序"**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-123">Open Access and choose **Custom web app**.</span></span>
    
2. <span data-ttu-id="2ab87-124">输入名称和您的应用程序的 web 位置。</span><span class="sxs-lookup"><span data-stu-id="2ab87-124">Enter a name and the web location for your app.</span></span> <span data-ttu-id="2ab87-125">您还可以从**位置**列表中选择一个位置，然后选择**创建**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-125">You can also choose a location from the **Locations** list and choose **Create**.</span></span>
    
3. <span data-ttu-id="2ab87-126">在**搜索**框中键入**任务**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="2ab87-126">Type **tasks** into the **Search** box and then press ENTER.</span></span> 
    
    <span data-ttu-id="2ab87-127">图 1 中显示的可能很有用跟踪任务的模板的列表。</span><span class="sxs-lookup"><span data-stu-id="2ab87-127">A list of templates that might be useful for tracking tasks is displayed in Figure 1.</span></span>
    
   <span data-ttu-id="2ab87-128">**图 1。与任务搜索相匹配的模板**</span><span class="sxs-lookup"><span data-stu-id="2ab87-128">**Figure 1. Templates that match the search for tasks**</span></span>

   <span data-ttu-id="2ab87-129">![与问题搜索相匹配的模板](media/odc_Access15_CreateAndCustomizeWebApp_Figure01.JPG "与问题搜索相匹配的模板")</span><span class="sxs-lookup"><span data-stu-id="2ab87-129">![Templates that match the search for issues](media/odc_Access15_CreateAndCustomizeWebApp_Figure01.JPG "Templates that match the search for issues")</span></span>
  
4. <span data-ttu-id="2ab87-130">选择**任务**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-130">Choose **Tasks**.</span></span>
    
<span data-ttu-id="2ab87-131">Access 创建一系列表和视图。</span><span class="sxs-lookup"><span data-stu-id="2ab87-131">Access creates a set of tables and views.</span></span>
  
<span data-ttu-id="2ab87-132">输入您的应用程序中的几个示例任务和员工。</span><span class="sxs-lookup"><span data-stu-id="2ab87-132">Enter several sample tasks and employees in your app.</span></span> <span data-ttu-id="2ab87-133">若要执行此操作，选择**启动应用程序**在 web 浏览器中打开应用程序。</span><span class="sxs-lookup"><span data-stu-id="2ab87-133">To do this, choose **Launch App** to open the app in your web browser.</span></span> <span data-ttu-id="2ab87-134">在**截止日期**字段中输入一个值，为每项任务。</span><span class="sxs-lookup"><span data-stu-id="2ab87-134">Enter a value in the **Due Date** field for each task.</span></span> <span data-ttu-id="2ab87-135">完成后，返回到 Access。</span><span class="sxs-lookup"><span data-stu-id="2ab87-135">Return to Access when you're done.</span></span> 
  
## <a name="plan-the-customizations"></a><span data-ttu-id="2ab87-136">规划自定义项</span><span class="sxs-lookup"><span data-stu-id="2ab87-136">Plan the customizations</span></span>
<span data-ttu-id="2ab87-137"><a name="Access2013FilterViewByUsingMacro_PlanCustomizations"> </a></span><span class="sxs-lookup"><span data-stu-id="2ab87-137"></span></span>

<span data-ttu-id="2ab87-138">现在，您可以包含多个任务的应用程序。</span><span class="sxs-lookup"><span data-stu-id="2ab87-138">You now have an app that contains several tasks.</span></span> <span data-ttu-id="2ab87-139">默认视图，可搜索的任何任务使用视图中显示的字段中存储的项目。</span><span class="sxs-lookup"><span data-stu-id="2ab87-139">The default view enables you to search for any tasks using items that are stored in the fields displayed in the view.</span></span> <span data-ttu-id="2ab87-140">例如，您可以搜索高优先级的问题或正在进行中的问题。</span><span class="sxs-lookup"><span data-stu-id="2ab87-140">For example, you can search for high-priority issues or issues in progress.</span></span> <span data-ttu-id="2ab87-141">假设您想要设置您的工作，通过显示的未到期在下一周中解决问题的优先级。</span><span class="sxs-lookup"><span data-stu-id="2ab87-141">Suppose you want to prioritize your work by displaying active issues that are due in the coming week.</span></span> <span data-ttu-id="2ab87-142">若要执行此操作，您应创建用户界面 (UI) 宏。</span><span class="sxs-lookup"><span data-stu-id="2ab87-142">To do this, you should create a user interface (UI) macro.</span></span>
  
<span data-ttu-id="2ab87-143">您可用于筛选视图的 UI 宏命令是[RequeryRecords 宏操作 （访问自定义 web 应用程序）](requeryrecords-macro-action-access-custom-web-app.md)。</span><span class="sxs-lookup"><span data-stu-id="2ab87-143">The UI macro command that you can use to filter the view is the [RequeryRecords Macro Action (Access custom web app)](requeryrecords-macro-action-access-custom-web-app.md).</span></span> <span data-ttu-id="2ab87-144">**RequeryRecords**宏操作的筛选器基于*其中*参数，它提供一个 SQL WHERE 子句的窗体中的视图。</span><span class="sxs-lookup"><span data-stu-id="2ab87-144">The **RequeryRecords** macro action filters the view based on the  *Where*  argument, which is provided in the form of a SQL WHERE clause.</span></span> <span data-ttu-id="2ab87-145">筛选的视图，必须提供若干事实以特定格式筛选的视图。</span><span class="sxs-lookup"><span data-stu-id="2ab87-145">To filter the view, you must supply several facts in a specific format to filter the view.</span></span> 
  
<span data-ttu-id="2ab87-146">相关的事实是：</span><span class="sxs-lookup"><span data-stu-id="2ab87-146">The relevant facts are:</span></span>
  
- <span data-ttu-id="2ab87-147">要比较的字段</span><span class="sxs-lookup"><span data-stu-id="2ab87-147">The field or fields to compare</span></span>
    
- <span data-ttu-id="2ab87-148">如何引用今天的日期</span><span class="sxs-lookup"><span data-stu-id="2ab87-148">How to refer to today's date</span></span>
    
- <span data-ttu-id="2ab87-149">如何引用相对于今天的日期某一天</span><span class="sxs-lookup"><span data-stu-id="2ab87-149">How to refer to a particular day relative to today's date</span></span>
    
- <span data-ttu-id="2ab87-150">如何确定其任务正在进行</span><span class="sxs-lookup"><span data-stu-id="2ab87-150">How to determine which on tasks are in progress</span></span>
    
<span data-ttu-id="2ab87-151">**截止日期**字段提供有关时任务的截止日期信息。</span><span class="sxs-lookup"><span data-stu-id="2ab87-151">The **Due Date** field provides information about when a task is due.</span></span> <span data-ttu-id="2ab87-152">**状态**字段提供有关每个任务的状态信息。</span><span class="sxs-lookup"><span data-stu-id="2ab87-152">The **Status** field provides status information about each task.</span></span> <span data-ttu-id="2ab87-153">要引用在宏中的字段，请使用格式 **[*TableName*]。 [*FieldName*]**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-153">To refer to a field in a macro, use the format **[*TableName*].[*FieldName*]**.</span></span> <span data-ttu-id="2ab87-154">使用 **[任务]。 [截止日期]** 指**截止日期**字段和 **[任务]。 [状态]** 来引用**状态**字段。</span><span class="sxs-lookup"><span data-stu-id="2ab87-154">Use **[Tasks].[Due Date]** to refer to the **Due Date** field and **[Tasks].[Status]** to refer to the **Status** field.</span></span> 
  
<span data-ttu-id="2ab87-155">[Today 函数 （访问自定义 web 应用程序）](today-function-access-custom-web-app.md)函数将返回今天的日期。</span><span class="sxs-lookup"><span data-stu-id="2ab87-155">The [Today Function (Access custom web app)](today-function-access-custom-web-app.md) function returns today's date.</span></span> <span data-ttu-id="2ab87-156">[DateAdd 函数 （访问自定义 web 应用程序）](dateadd-function-access-custom-web-app.md)函数可用于计算的日期，则一定数量的指定日期之后的天数。</span><span class="sxs-lookup"><span data-stu-id="2ab87-156">The [DateAdd Function (Access custom web app)](dateadd-function-access-custom-web-app.md) function can be used to calculate a date that's a certain number of days after a specified date.</span></span> 
  
<span data-ttu-id="2ab87-157">**状态**字段包含多个可能的值。</span><span class="sxs-lookup"><span data-stu-id="2ab87-157">The **Status** field contains several possible values.</span></span> <span data-ttu-id="2ab87-158">**已完成**的值表示任务不再处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="2ab87-158">A value of **Completed** indicates that the task is no longer active.</span></span> 
  
<span data-ttu-id="2ab87-159">可以将这些事实结合到下面的 SQL WHERE 子句。</span><span class="sxs-lookup"><span data-stu-id="2ab87-159">These facts can be combined into the following SQL WHERE clause.</span></span>
  
```sql
[Tasks].[Due Date]<DateAdd(Day,7,Today()) AND [Tasks].[Status]<>"Completed"
```

<span data-ttu-id="2ab87-160">在宏中使用此 SQL WHERE 子句筛选的视图，显示在下一步 7 天内到期或已到期解决问题。</span><span class="sxs-lookup"><span data-stu-id="2ab87-160">This SQL WHERE clause is used in the macro to filter the view to display active issues that are due in the next 7 days or are past due.</span></span>
  
<span data-ttu-id="2ab87-161">若要运行的 UI 宏，它必须附加到的项目或在视图中发生的事件。</span><span class="sxs-lookup"><span data-stu-id="2ab87-161">To run the UI macro, it must be attached to an item or an event that occurs in the view.</span></span> <span data-ttu-id="2ab87-162">**操作栏**是方便地向视图中添加自定义命令。</span><span class="sxs-lookup"><span data-stu-id="2ab87-162">The **Action Bar** is a convenient place to add a custom command to the view.</span></span> <span data-ttu-id="2ab87-163">**操作栏**是可自定义工具栏出现在每个视图的顶部。</span><span class="sxs-lookup"><span data-stu-id="2ab87-163">The **Action Bar** is a customizable toolbar that appears at the top of each view.</span></span> <span data-ttu-id="2ab87-164">默认情况下，**操作栏**包含按钮添加、 编辑、 保存、 删除和取消编辑。</span><span class="sxs-lookup"><span data-stu-id="2ab87-164">By default, the **Action Bar** contains buttons to add, edit, save, delete, and cancel edits.</span></span> <span data-ttu-id="2ab87-165">您可以添加执行自定义操作，如筛选视图的按钮。</span><span class="sxs-lookup"><span data-stu-id="2ab87-165">You can add buttons that perform custom actions, such as filtering the view.</span></span> 
  
<span data-ttu-id="2ab87-166">如果视图包含符合指定的条件的记录，然后**RequeryRecords**筛选视图。</span><span class="sxs-lookup"><span data-stu-id="2ab87-166">If the view contains records that meet the specified criteria, then **RequeryRecords** filters the view.</span></span> <span data-ttu-id="2ab87-167">但是，如果视图不包含任何记录符合条件，比一个新的空白记录显示。</span><span class="sxs-lookup"><span data-stu-id="2ab87-167">However, if the view doesn't contain any records that meet the criteria, than a new, blank record is displayed.</span></span> <span data-ttu-id="2ab87-168">如果您不希望如果没有任务的截止下一周显示空白记录，您必须找到检查任务之前调用**RequeryRecords**宏操作的方法。</span><span class="sxs-lookup"><span data-stu-id="2ab87-168">If you don't want a blank record to be displayed if no tasks are due in the next week, then you must find a method to check the tasks before you call the **RequeryRecords** macro action.</span></span> <span data-ttu-id="2ab87-169">若要执行此操作，创建要检查的满足条件的记录的数据宏。</span><span class="sxs-lookup"><span data-stu-id="2ab87-169">To do this, create a data macro to check for records that meet the criteria.</span></span> 
  
<span data-ttu-id="2ab87-170">UI 宏将调用数据宏，将尝试查找的下一周截止任务。</span><span class="sxs-lookup"><span data-stu-id="2ab87-170">The UI macro will call the data macro, which will try to find a task that's due in the next week.</span></span> <span data-ttu-id="2ab87-171">如果数据宏查找任务，则自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="2ab87-171">If the data macro finds the task then customize the app.</span></span>
  
## <a name="customize-the-app"></a><span data-ttu-id="2ab87-172">自定义应用程序</span><span class="sxs-lookup"><span data-stu-id="2ab87-172">Customize the app</span></span>
<span data-ttu-id="2ab87-173"><a name="Access2013FilterViewByUsingMacro_CustomizeApp"> </a></span><span class="sxs-lookup"><span data-stu-id="2ab87-173"></span></span>

<span data-ttu-id="2ab87-174">现在，您已确定自定义项，实现它们。</span><span class="sxs-lookup"><span data-stu-id="2ab87-174">Now that you've determined the customizations, implement them.</span></span> <span data-ttu-id="2ab87-175">应首先创建数据宏。</span><span class="sxs-lookup"><span data-stu-id="2ab87-175">The data macro should be created first.</span></span> <span data-ttu-id="2ab87-176">某些数据宏直接连接到表。</span><span class="sxs-lookup"><span data-stu-id="2ab87-176">Some data macros are attached directly to tables.</span></span> <span data-ttu-id="2ab87-177">但是，此数据宏为独立的数据宏。</span><span class="sxs-lookup"><span data-stu-id="2ab87-177">However, this data macro is a stand-alone data macro.</span></span>
  
### <a name="to-create-the-data-macro"></a><span data-ttu-id="2ab87-178">若要创建数据宏</span><span class="sxs-lookup"><span data-stu-id="2ab87-178">To create the data macro</span></span>

1. <span data-ttu-id="2ab87-179">在 Access 中打开应用程序。</span><span class="sxs-lookup"><span data-stu-id="2ab87-179">Open the app in Access.</span></span>
    
2. <span data-ttu-id="2ab87-180">在**创建**组中，选择**高级**，然后选择**数据宏**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-180">In the **Create** group, choose **Advanced**, and then choose **Data Macro**.</span></span>
    
    <span data-ttu-id="2ab87-181">在宏设计视图中打开一个空白数据宏。</span><span class="sxs-lookup"><span data-stu-id="2ab87-181">A blank data macro is opened in macro Design View.</span></span>
    
3. <span data-ttu-id="2ab87-182">从**添加新操作**列表框中，选择**LookupRecord**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-182">From the **Add New Action** list box, choose **LookupRecord**.</span></span>
    
4. <span data-ttu-id="2ab87-183">在查找 Up A 记录列表框**中**，选择**任务**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-183">In the **Look Up A Record In** list box, choose **Tasks**.</span></span>
    
5. <span data-ttu-id="2ab87-184">在**Where 条件**框中，输入 **[任务]。 [截止日期]\<DateAdd(Day,7,Today()) 和 [任务]。[状态]\< \>"完成"**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-184">In the **Where Condition** box, enter **[Tasks].[Due Date]\<DateAdd(Day,7,Today()) AND [Tasks].[Status]\<\>"Completed"**.</span></span> 
    
6. <span data-ttu-id="2ab87-185">从**添加新操作**列表框中选择**SetReturnVar** 。</span><span class="sxs-lookup"><span data-stu-id="2ab87-185">Choose **SetReturnVar** from the **Add New Action** list box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="2ab87-186">您将看到两个**添加新操作**列表框， **LookupRecord**块，和其他外部**LookupRecord**块内的一个。</span><span class="sxs-lookup"><span data-stu-id="2ab87-186">You'll see two **Add New Action** list boxes, one within the **LookupRecord** block, and another outside the **LookupRecord** block.</span></span> <span data-ttu-id="2ab87-187">图 1 中所示，您应选择在**LookupRecord**块中，**添加新操作**列表框。</span><span class="sxs-lookup"><span data-stu-id="2ab87-187">You should choose the **Add New Action** list box within the **LookupRecord** block, as shown in Figure 1.</span></span> 
  
   <span data-ttu-id="2ab87-188">**图 1。添加新操作列表框**</span><span class="sxs-lookup"><span data-stu-id="2ab87-188">**Figure 1. Add New Action list box**</span></span>

   <span data-ttu-id="2ab87-189">![添加新操作下拉列表](media/odc_Access2013_FilterFormByUsingMacro_Figure01.jpg "添加新操作下拉列表")</span><span class="sxs-lookup"><span data-stu-id="2ab87-189">![Add New Action dropdown](media/odc_Access2013_FilterFormByUsingMacro_Figure01.jpg "Add New Action dropdown")</span></span>
  
7. <span data-ttu-id="2ab87-190">在**名称**框中，输入**TaskFound**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-190">In the **Name** box, enter **TaskFound**.</span></span> 
    
8. <span data-ttu-id="2ab87-191">在**表达式**框中，输入 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-191">In the **Expression** box, enter **"Yes"**.</span></span> 
    
9. <span data-ttu-id="2ab87-192">选择“保存”****。</span><span class="sxs-lookup"><span data-stu-id="2ab87-192">Choose **Save**.</span></span> <span data-ttu-id="2ab87-193">在**宏名称**框中输入**TasksDueSoon** ，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-193">Enter **TasksDueSoon** in the **Macro Name** box and then choose **OK**.</span></span>
    
    <span data-ttu-id="2ab87-194">宏应类似于图 2 所示的宏。</span><span class="sxs-lookup"><span data-stu-id="2ab87-194">The macro should resemble the macro shown in Figure 2.</span></span>
    
   <span data-ttu-id="2ab87-195">**图 2。TasksDueSoon 数据宏**</span><span class="sxs-lookup"><span data-stu-id="2ab87-195">**Figure 2. TasksDueSoon data macro**</span></span>

   <span data-ttu-id="2ab87-196">![TasksDueSoon 数据宏](media/odc_Access2013_FilterFormByUsingMacro_Figure02.jpg "TasksDueSoon 数据宏")</span><span class="sxs-lookup"><span data-stu-id="2ab87-196">![TasksDueSoon data macro](media/odc_Access2013_FilterFormByUsingMacro_Figure02.jpg "TasksDueSoon data macro")</span></span>
  
10. <span data-ttu-id="2ab87-197">关闭宏设计视图。</span><span class="sxs-lookup"><span data-stu-id="2ab87-197">Close macro Design View.</span></span>
    
<span data-ttu-id="2ab87-198">现在，我们已准备好自定义按钮添加到操作栏。</span><span class="sxs-lookup"><span data-stu-id="2ab87-198">Now, we're ready to add a custom button to the Action Bar.</span></span>
  
### <a name="to-add-a-custom-button-to-the-action-bar"></a><span data-ttu-id="2ab87-199">将自定义按钮添加到操作栏</span><span class="sxs-lookup"><span data-stu-id="2ab87-199">To add a custom button to the Action Bar</span></span>

1. <span data-ttu-id="2ab87-200">选择**任务**表。</span><span class="sxs-lookup"><span data-stu-id="2ab87-200">Choose the **Tasks** table.</span></span> <span data-ttu-id="2ab87-201">这会选择的任务列表表单。</span><span class="sxs-lookup"><span data-stu-id="2ab87-201">This chooses the Tasks List form.</span></span> 
    
2. <span data-ttu-id="2ab87-202">视图选择器中选择**列表**，选择**设置中的操作**图标，然后选择**编辑**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-202">In the View selector, choose **List**, choose the **Settings/Action** icon, and then choose **Edit**.</span></span>
    
    <span data-ttu-id="2ab87-203">在设计视图中打开视图。</span><span class="sxs-lookup"><span data-stu-id="2ab87-203">The view is opened in Design View.</span></span>
    
3. <span data-ttu-id="2ab87-204">现在，我们已准备好自定义按钮添加到操作栏。</span><span class="sxs-lookup"><span data-stu-id="2ab87-204">Now, we're ready to add a custom button to the Action Bar.</span></span> <span data-ttu-id="2ab87-205">为此，请选择**添加自定义操作**，如图 3 所示。</span><span class="sxs-lookup"><span data-stu-id="2ab87-205">To do this, choose **Add custom action** as shown in Figure 3.</span></span> 
    
   <span data-ttu-id="2ab87-206">**图 3。添加自定义操作按钮**</span><span class="sxs-lookup"><span data-stu-id="2ab87-206">**Figure 3. Add custom action button**</span></span>

   <span data-ttu-id="2ab87-207">![添加自定义操作按钮](media/odc_Access2013_FilterFormByUsingMacro_Figure03.jpg "添加自定义操作按钮")</span><span class="sxs-lookup"><span data-stu-id="2ab87-207">![Add custom action button](media/odc_Access2013_FilterFormByUsingMacro_Figure03.jpg "Add custom action button")</span></span>
  
    <span data-ttu-id="2ab87-208">新操作显示为具有星形图标的按钮，如图 4 中所示。</span><span class="sxs-lookup"><span data-stu-id="2ab87-208">The new action is displayed as a button with a star icon as shown in Figure 4.</span></span>
    
   <span data-ttu-id="2ab87-209">**图 4。新操作栏按钮**</span><span class="sxs-lookup"><span data-stu-id="2ab87-209">**Figure 4. New Action Bar button**</span></span>

   <span data-ttu-id="2ab87-210">![新操作栏按钮](media/odc_Access2013_FilterFormByUsingMacro_Figure04.jpg "新操作栏按钮")</span><span class="sxs-lookup"><span data-stu-id="2ab87-210">![New Action Bar button](media/odc_Access2013_FilterFormByUsingMacro_Figure04.jpg "New Action Bar button")</span></span>
  
4. <span data-ttu-id="2ab87-211">选择自定义操作栏按钮，，然后选择**数据**图标。</span><span class="sxs-lookup"><span data-stu-id="2ab87-211">Choose the custom Action Bar Button, and then choose the **Data** icon.</span></span> 
    
    <span data-ttu-id="2ab87-212">出现**数据**对话框。</span><span class="sxs-lookup"><span data-stu-id="2ab87-212">The **Data** dialog box appears.</span></span> 
    
5. <span data-ttu-id="2ab87-213">在**控件名称**框中，输入**FilterTasks**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-213">In the **Control Name** box, enter **FilterTasks**.</span></span> 
    
6. <span data-ttu-id="2ab87-214">在**工具提示**框中，输入**显示任务以前到期或截止在下个星期**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-214">In the **Tooltip** box, enter **Display tasks past due or due in the next week**.</span></span> 
    
<span data-ttu-id="2ab87-215">现在，我们已准备好创建将筛选视图的 UI 宏。</span><span class="sxs-lookup"><span data-stu-id="2ab87-215">Now, we're ready to create the UI macro that will filter the view.</span></span>
  
### <a name="to-create-the-ui-macro-to-filter-the-view"></a><span data-ttu-id="2ab87-216">若要创建要筛选的视图的 UI 宏</span><span class="sxs-lookup"><span data-stu-id="2ab87-216">To create the UI macro to filter the view</span></span>

1. <span data-ttu-id="2ab87-217">在**数据**对话框中，选择**在单击**图 5 中所示。</span><span class="sxs-lookup"><span data-stu-id="2ab87-217">In the **Data** dialog box, choose **On Click** as shown in Figure 5.</span></span> 
    
   <span data-ttu-id="2ab87-218">**图 5。数据对话框**</span><span class="sxs-lookup"><span data-stu-id="2ab87-218">**Figure 5. Data dialog box**</span></span>

   <span data-ttu-id="2ab87-219">![数据对话框](media/odc_Access2013_FilterFormByUsingMacro_Figure05.jpg "数据对话框")</span><span class="sxs-lookup"><span data-stu-id="2ab87-219">![Data dialog box](media/odc_Access2013_FilterFormByUsingMacro_Figure05.jpg "Data dialog box")</span></span>
  
    <span data-ttu-id="2ab87-220">在宏设计视图中打开一个空的 UI 宏。</span><span class="sxs-lookup"><span data-stu-id="2ab87-220">A blank UI macro is opened in macro Design View.</span></span>
    
2. <span data-ttu-id="2ab87-221">从**添加新操作**列表框中，选择**RunDataMacro**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-221">From the **Add New Action** list box, choose **RunDataMacro**.</span></span> 
    
3. <span data-ttu-id="2ab87-222">在宏名称框中，输入**TasksDueSoon**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-222">In the Macro Name box, enter **TasksDueSoon**.</span></span> 
    
    <span data-ttu-id="2ab87-223">在**SetLocalVar**框中，输入**FilterRecords**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-223">In the **SetLocalVar** box, enter **FilterRecords**.</span></span> 
    
    <span data-ttu-id="2ab87-224">**RunDataMacro**操作调用我们之前创建**TasksDueSoon**数据宏，并将其结果存储在名为**FilterRecords**的变量。</span><span class="sxs-lookup"><span data-stu-id="2ab87-224">The **RunDataMacro** action calls the **TasksDueSoon** data macro we created earlier and stores its result in a variable named **FilterRecords**.</span></span> 
    
4. <span data-ttu-id="2ab87-225">从**添加新操作**列表框中，选择**如果**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-225">From the **Add New Action** list box, choose **If**.</span></span> 
    
5. <span data-ttu-id="2ab87-226">在**如果**框中，输入 **[FilterRecords] ="Yes"**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-226">In the **If** box, enter **[FilterRecords]="Yes"**.</span></span> 
    
6. <span data-ttu-id="2ab87-227">从**添加新操作**列表框中，选择**RequeryRecords**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-227">From the **Add New Action** list box, choose **RequeryRecords**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="2ab87-228">您将看到两个**添加新操作**列表框，一个**If**块中，和其他外部**If**块中。</span><span class="sxs-lookup"><span data-stu-id="2ab87-228">You'll see two **Add New Action** list boxes, one within the **If** block, and another outside the **If** block.</span></span> <span data-ttu-id="2ab87-229">应选择**If**块中，在**添加新操作**列表框，如图 6 所示。</span><span class="sxs-lookup"><span data-stu-id="2ab87-229">You should choose the **Add New Action** list box within the **If** block, as shown in Figure 6.</span></span> 
  
   <span data-ttu-id="2ab87-230">**图 6。添加新操作列表框**</span><span class="sxs-lookup"><span data-stu-id="2ab87-230">**Figure 6. Add New Action list box**</span></span>

   <span data-ttu-id="2ab87-231">![添加新操作下拉列表](media/odc_Access2013_FilterFormByUsingMacro_Figure06.jpg "添加新操作下拉列表")</span><span class="sxs-lookup"><span data-stu-id="2ab87-231">![Add New Action dropdown](media/odc_Access2013_FilterFormByUsingMacro_Figure06.jpg "Add New Action dropdown")</span></span>
  
7. <span data-ttu-id="2ab87-232">在**位置**框中，输入 **[任务]。 [截止日期]\<DateAdd(Day,7,Today()) 和 [任务]。[状态]\< \>"完成"**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-232">In the **Where** box, enter **[Tasks].[Due Date]\<DateAdd(Day,7,Today()) AND [Tasks].[Status]\<\>"Completed"**.</span></span> 
    
8. <span data-ttu-id="2ab87-233">在**Order By**框中，输入 **[截止日期]**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-233">In the **Order By** box, enter **[Due Date]**.</span></span> 
    
9. <span data-ttu-id="2ab87-234">选择**添加 Else**链接，如图 7 中所示显示**添加新操作**框的右侧。</span><span class="sxs-lookup"><span data-stu-id="2ab87-234">Choose the **Add Else** link that appears to the right side of the **Add New Action** box as shown in Figure 7.</span></span> 
    
   <span data-ttu-id="2ab87-235">**图 7。添加 Else 链接**</span><span class="sxs-lookup"><span data-stu-id="2ab87-235">**Figure 7. Add Else link**</span></span>

   <span data-ttu-id="2ab87-236">![添加 Else 链接](media/odc_Access2013_FilterFormByUsingMacro_Figure07.jpg "添加 Else 链接")</span><span class="sxs-lookup"><span data-stu-id="2ab87-236">![Add Else link](media/odc_Access2013_FilterFormByUsingMacro_Figure07.jpg "Add Else link")</span></span>
  
    <span data-ttu-id="2ab87-237">Else 子句添加到 If 块。</span><span class="sxs-lookup"><span data-stu-id="2ab87-237">An Else clause is added to the If block.</span></span>
    
10. <span data-ttu-id="2ab87-238">从**添加新操作**列表框中，选择**MessageBox**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-238">From the **Add New Action** list box, choose **MessageBox**.</span></span> 
    
11. <span data-ttu-id="2ab87-239">在**消息**框中，输入**没有任务的过期或内到期且随后 7 天 ！**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-239">In the **Message** box, enter **No tasks are overdue or due in the next 7 days!**.</span></span> 
    
12. <span data-ttu-id="2ab87-240">选择“保存”****。</span><span class="sxs-lookup"><span data-stu-id="2ab87-240">Choose **Save**.</span></span>
    
    <span data-ttu-id="2ab87-241">宏应类似于图 8 中所示的宏。</span><span class="sxs-lookup"><span data-stu-id="2ab87-241">The macro should resemble the macro shown in Figure 8.</span></span>
    
    <span data-ttu-id="2ab87-242">**图 8。用于筛选视图的 UI 宏**</span><span class="sxs-lookup"><span data-stu-id="2ab87-242">**Figure 8. UI macro to filter the view**</span></span>

    <span data-ttu-id="2ab87-243">![用于筛选视图的 UI 宏](media/odc_Access2013_FilterFormByUsingMacro_Figure08.jpg "用于筛选视图的 UI 宏")</span><span class="sxs-lookup"><span data-stu-id="2ab87-243">![UI macro to filter the view](media/odc_Access2013_FilterFormByUsingMacro_Figure08.jpg "UI macro to filter the view")</span></span>
  
13. <span data-ttu-id="2ab87-244">关闭宏设计视图。</span><span class="sxs-lookup"><span data-stu-id="2ab87-244">Close macro Design View.</span></span>
    
<span data-ttu-id="2ab87-245">此时，我们已创建要显示的紧急任务的任务列表视图的筛选器的 UI 宏。</span><span class="sxs-lookup"><span data-stu-id="2ab87-245">At this point, we've created the UI macro that filters the Tasks List view to display the urgent tasks.</span></span> <span data-ttu-id="2ab87-246">它不会有礼貌将视图保留在筛选状态，而不需要提供方法要删除筛选器。</span><span class="sxs-lookup"><span data-stu-id="2ab87-246">It wouldn't be polite to leave the view in a filtered state without providing a method to remove the filter.</span></span> <span data-ttu-id="2ab87-247">若要执行此操作，添加另一个操作栏按钮和 UI 宏。</span><span class="sxs-lookup"><span data-stu-id="2ab87-247">To do this, add another Action Bar button and UI Macro.</span></span>
  
### <a name="to-add-an-action-bar-button-to-remove-the-filter"></a><span data-ttu-id="2ab87-248">若要删除筛选器操作栏按钮添加</span><span class="sxs-lookup"><span data-stu-id="2ab87-248">To add an Action Bar Button to remove the filter</span></span>

1. <span data-ttu-id="2ab87-249">选择**添加自定义操作**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-249">Choose **Add custom action**.</span></span>
    
    <span data-ttu-id="2ab87-250">新操作显示为具有星形图标的按钮</span><span class="sxs-lookup"><span data-stu-id="2ab87-250">The new action is displayed as a button with a star icon</span></span>
    
2. <span data-ttu-id="2ab87-251">选择自定义操作栏按钮，然后选择**数据**图标。</span><span class="sxs-lookup"><span data-stu-id="2ab87-251">Choose the custom Action Bar button, and then choose the **Data** icon.</span></span> 
    
    <span data-ttu-id="2ab87-252">出现**数据**对话框。</span><span class="sxs-lookup"><span data-stu-id="2ab87-252">The **Data** dialog box appears.</span></span> 
    
3. <span data-ttu-id="2ab87-253">在**控件名称**框中，输入**RemoveFilter**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-253">In the **Control Name** box, enter **RemoveFilter**.</span></span> 
    
4. <span data-ttu-id="2ab87-254">在**工具提示**框中，输入**删除所有筛选器应用于视图**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-254">In the **Tooltip** box, enter **Remove all filter applied to the view**.</span></span> 
    
<span data-ttu-id="2ab87-255">现在，我们已准备好创建将删除窗体筛选视图的 UI 宏。</span><span class="sxs-lookup"><span data-stu-id="2ab87-255">Now, we're ready to create the UI macro that will remove the filter form the view.</span></span>
  
### <a name="to-create-the-ui-macro-to-remove-the-filter-from-the-view"></a><span data-ttu-id="2ab87-256">若要创建要从视图中删除筛选器的 UI 宏</span><span class="sxs-lookup"><span data-stu-id="2ab87-256">To create the UI macro to remove the filter from the view</span></span>

1. <span data-ttu-id="2ab87-257">在**数据**对话框中，选择**上单击**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-257">In the **Data** dialog box, choose **On Click**.</span></span>
    
    <span data-ttu-id="2ab87-258">在宏设计视图中打开一个空的 UI 宏。</span><span class="sxs-lookup"><span data-stu-id="2ab87-258">A blank UI macro is opened in macro Design View.</span></span>
    
2. <span data-ttu-id="2ab87-259">从**添加新操作**列表框中，选择**RequeryRecords**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-259">From the **Add New Action** list box, choose **RequeryRecords**.</span></span> 
    
    <span data-ttu-id="2ab87-260">此时，我们将保留**其中**和**Order By**框为空。</span><span class="sxs-lookup"><span data-stu-id="2ab87-260">This time, we'll leave the **Where** and **Order By** boxes empty.</span></span> <span data-ttu-id="2ab87-261">**RequeryRecords**操作调用不带任何参数，然后从视图中删除所有筛选器。</span><span class="sxs-lookup"><span data-stu-id="2ab87-261">Then the **RequeryRecords** action is called without any parameters, all filters are removed from the view.</span></span> 
    
3. <span data-ttu-id="2ab87-262">选择“保存”****。</span><span class="sxs-lookup"><span data-stu-id="2ab87-262">Choose **Save**.</span></span>
    
4. <span data-ttu-id="2ab87-263">关闭宏设计视图。</span><span class="sxs-lookup"><span data-stu-id="2ab87-263">Close macro Design View.</span></span>
    
5. <span data-ttu-id="2ab87-264">关闭任务列表视图。</span><span class="sxs-lookup"><span data-stu-id="2ab87-264">Close the Tasks List view.</span></span> <span data-ttu-id="2ab87-265">当提示您保存所做的更改时，请选择**是**。</span><span class="sxs-lookup"><span data-stu-id="2ab87-265">Choose **Yes** when you are prompted to save your changes.</span></span> 
    
<span data-ttu-id="2ab87-266">现在，我们已准备好自定义项的文本。</span><span class="sxs-lookup"><span data-stu-id="2ab87-266">Now, we're ready to text the customization.</span></span> <span data-ttu-id="2ab87-267">选择**启动应用程序**以在 web 浏览器中打开应用程序，然后选择自定义 FilterTasks 操作栏按钮。</span><span class="sxs-lookup"><span data-stu-id="2ab87-267">Choose **Launch App** to open the app in your web browser and then choose the custom FilterTasks Action Bar button.</span></span> <span data-ttu-id="2ab87-268">显示随后 7 天内到期且或以前的任何任务。</span><span class="sxs-lookup"><span data-stu-id="2ab87-268">Any tasks past due or due in the next 7 days are displayed.</span></span> <span data-ttu-id="2ab87-269">如果应用程序包含没有紧急任务，则显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="2ab87-269">A message is displayed if the app contains no urgent tasks.</span></span> 
  
## <a name="conclusion"></a><span data-ttu-id="2ab87-270">结论</span><span class="sxs-lookup"><span data-stu-id="2ab87-270">Conclusion</span></span>

<span data-ttu-id="2ab87-271">您可以使用中的 UI 宏**RequeryRecords**宏操作筛选根据您选择的标准视图。</span><span class="sxs-lookup"><span data-stu-id="2ab87-271">You can use the **RequeryRecords** macro action in a UI macro to filter the view based on the criteria that you choose.</span></span> <span data-ttu-id="2ab87-272">根据所需的行为，您可能要创建验证记录满足的条件，才能使用**RequeryRecords**宏操作的数据宏。</span><span class="sxs-lookup"><span data-stu-id="2ab87-272">Depending on the behavior that you want, you may want to create a data macro to verify that a record meets the criteria before you use the **RequeryRecords** macro action.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2ab87-273">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ab87-273">See also</span></span>

- [<span data-ttu-id="2ab87-274">Access 中面向开发人员的新增功能</span><span class="sxs-lookup"><span data-stu-id="2ab87-274">What's new for Access 2013 developers</span></span>](http://msdn.microsoft.com/library/df778f51-d65e-4c30-b618-65003ceb39b3%28Office.15%29.aspx)
    

