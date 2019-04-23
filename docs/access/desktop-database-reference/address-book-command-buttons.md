---
title: 通讯簿命令按钮
TOCTitle: Address Book command buttons
ms:assetid: bcea6f53-3e36-b067-03c2-b157ed02d41d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249908(v=office.15)
ms:contentKeyID: 48547422
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 09f2513a3c541c76352e773f7f2a8f0c24f78850
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282476"
---
# <a name="address-book-command-buttons"></a><span data-ttu-id="a94b4-102">通讯簿命令按钮</span><span class="sxs-lookup"><span data-stu-id="a94b4-102">Address Book command buttons</span></span>


<span data-ttu-id="a94b4-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="a94b4-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="a94b4-104">通讯簿应用程序包括以下命令按钮：</span><span class="sxs-lookup"><span data-stu-id="a94b4-104">The Address Book application includes the following command buttons:</span></span>

- <span data-ttu-id="a94b4-105">**“查找”** 按钮，用于向数据库提交查询。</span><span class="sxs-lookup"><span data-stu-id="a94b4-105">A **Find** button to submit a query to the database.</span></span>

- <span data-ttu-id="a94b4-106">“清除”\*\*\*\* 按钮，用于在开始新的搜索之前清除文本框中的内容。</span><span class="sxs-lookup"><span data-stu-id="a94b4-106">A **Clear** button to clear the text boxes before starting a new search.</span></span>

- <span data-ttu-id="a94b4-107">**“更新配置文件”** 按钮，用于保存对雇员记录所做的更改。</span><span class="sxs-lookup"><span data-stu-id="a94b4-107">An **Update Profile** button to save changes to an employee record.</span></span>

- <span data-ttu-id="a94b4-108">**“取消更改”** 按钮，用于放弃更改。</span><span class="sxs-lookup"><span data-stu-id="a94b4-108">A **Cancel Changes** button to discard changes.</span></span>

## <a name="find-button"></a><span data-ttu-id="a94b4-109">“查找”按钮</span><span class="sxs-lookup"><span data-stu-id="a94b4-109">Find Button</span></span>

<span data-ttu-id="a94b4-110">单击 "**查找**" 按钮将激活 VBScript\_Find OnClick Sub 过程, 该过程将生成并发送 SQL 查询。</span><span class="sxs-lookup"><span data-stu-id="a94b4-110">Clicking the **Find** button activates the VBScript Find\_OnClick Sub procedure, which builds and sends the SQL query.</span></span> <span data-ttu-id="a94b4-111">单击此按钮可填充数据网格。</span><span class="sxs-lookup"><span data-stu-id="a94b4-111">Clicking this button populates the data grid.</span></span>

## <a name="building-the-sql-query"></a><span data-ttu-id="a94b4-112">生成 SQL 查询</span><span class="sxs-lookup"><span data-stu-id="a94b4-112">Building the SQL Query</span></span>

<span data-ttu-id="a94b4-113">Find\_OnClick Sub 过程的第一部分通过将文本字符串追加到全局 SQL SELECT 语句来生成 SQL 查询 (一次一个短语)。</span><span class="sxs-lookup"><span data-stu-id="a94b4-113">The first part of the Find\_OnClick Sub procedure builds the SQL query, one phrase at a time, by appending text strings to a global SQL SELECT statement.</span></span> <span data-ttu-id="a94b4-114">首先, 它将变量设置为 SQL SELECT 语句, 该语句请求数据源表中的所有数据行。</span><span class="sxs-lookup"><span data-stu-id="a94b4-114">It begins by setting the variable to a SQL SELECT statement that requests all rows of data from the data source table.</span></span> <span data-ttu-id="a94b4-115">然后，子过程对页面上的四个输入框逐一进行扫描。</span><span class="sxs-lookup"><span data-stu-id="a94b4-115">Next, the Sub procedure scans each of the four input boxes on the page.</span></span>

<span data-ttu-id="a94b4-116">由于程序在生成 SQL 语句时使用单词, 因此查询是子字符串搜索, 而不是完全匹配。</span><span class="sxs-lookup"><span data-stu-id="a94b4-116">Because the program uses the word in building the SQL statements, the queries are substring searches rather than exact matches.</span></span>

<span data-ttu-id="a94b4-117">例如, 如果 "**姓氏**" 框中包含条目 "高", 并且 "**标题**" 框中包含 "程序管理员" 条目, 则 SQL 语句 (值) 将会被读取:</span><span class="sxs-lookup"><span data-stu-id="a94b4-117">For example, if the **Last Name** box contained the entry "Berge" and the **Title** box contained the entry "Program Manager", the SQL statement (value of ) would read:</span></span>

```vb 
 
Select FirstName, LastName, Title, Email, Building, Room, Phone from Employee where lastname like 'Berge%' and title like 'Program Manager%' 
```

<span data-ttu-id="a94b4-118">如果查询成功，则姓氏中包含文本“高”（如“高”和“高阳”），且职务中包含“程序管理员”（如“高级技术程序管理员”）的所有人都将显示在 HTML 数据网格中。</span><span class="sxs-lookup"><span data-stu-id="a94b4-118">If the query was successful, all persons with a last name containing the text "Berge" (such as Berge and Berger) and with a title containing the words "Program Manager" (for example, Program Manager, Advanced Technologies) are displayed in the HTML data grid.</span></span>

## <a name="preparing-and-sending-the-query"></a><span data-ttu-id="a94b4-119">准备和发送查询</span><span class="sxs-lookup"><span data-stu-id="a94b4-119">Preparing and Sending the Query</span></span>

<span data-ttu-id="a94b4-120">Find\_OnClick Sub 过程的最后一部分由两个语句组成。</span><span class="sxs-lookup"><span data-stu-id="a94b4-120">The last part of the Find\_OnClick Sub procedure consists of two statements.</span></span> <span data-ttu-id="a94b4-121">第一个语句为 RDS.DataControl 对象的 SQL 属性赋值以动态生成 SQL 查询。</span><span class="sxs-lookup"><span data-stu-id="a94b4-121">The first statement assigns the SQL property of the RDS.DataControl object equal to the dynamically built SQL query.</span></span> <span data-ttu-id="a94b4-122">第二个语句导致**RDS。rds.datacontrol**对象 () 查询数据库, 然后在网格中显示查询的新结果。</span><span class="sxs-lookup"><span data-stu-id="a94b4-122">The second statement causes the **RDS.DataControl** object () to query the database, and then display the new results of the query in the grid.</span></span>

```vb 
 
Sub Find_OnClick 
 '... 
 DC1.SQL = myQuery 
 DC1.Refresh 
End Sub 
```

## <a name="update-profile-button"></a><span data-ttu-id="a94b4-123">“更新配置文件”按钮</span><span class="sxs-lookup"><span data-stu-id="a94b4-123">Update Profile Button</span></span>

<span data-ttu-id="a94b4-124">单击 "**更新配置文件**" 按钮将激活\_VBScript Update OnClick Sub 过程, 该过程将执行 RDS。rds.datacontrol 对象的 () SubmitChanges 和 Refresh 方法。</span><span class="sxs-lookup"><span data-stu-id="a94b4-124">Clicking the **Update Profile** button activates the VBScript Update\_OnClick Sub procedure, which executes the RDS.DataControl object's () SubmitChanges and Refresh methods.</span></span>

```vb 
 
Sub Update_OnClick 
 DC1.SubmitChanges 
 DC1.Refresh 
End Sub 
```

<span data-ttu-id="a94b4-125">当 DC1 时。SubmitChanges 执行时, 远程数据服务会将所有更新信息打包, 并通过 HTTP 将其发送到服务器。</span><span class="sxs-lookup"><span data-stu-id="a94b4-125">When DC1.SubmitChanges executes, the Remote Data Service packages all the update information and sends it to the server via HTTP.</span></span> <span data-ttu-id="a94b4-126">The update is all-or-nothing; if a part of the update is unsuccessful, none of the changes is made, and a status message is returned.</span><span class="sxs-lookup"><span data-stu-id="a94b4-126">The update is all-or-nothing; if a part of the update is unsuccessful, none of the changes is made, and a status message is returned.</span></span> <span data-ttu-id="a94b4-127">executes, the Remote Data Service packages all the update information and sends it to the server via HTTP.</span><span class="sxs-lookup"><span data-stu-id="a94b4-127">executes, the Remote Data Service packages all the update information and sends it to the server via HTTP.</span></span> <span data-ttu-id="a94b4-128">The update is all-or-nothing; if a part of the update is unsuccessful, none of the changes is made, and a status message is returned.</span><span class="sxs-lookup"><span data-stu-id="a94b4-128">The update is all-or-nothing; if a part of the update is unsuccessful, none of the changes is made, and a status message is returned.</span></span> <span data-ttu-id="a94b4-129">DC1.在使用远程数据服务**SubmitChanges**之后, 不需要进行刷新, 但可确保使用最新的数据。</span><span class="sxs-lookup"><span data-stu-id="a94b4-129">DC1.Refresh isn't necessary after **SubmitChanges** with Remote Data Service, but it ensures fresh data.</span></span>

## <a name="cancel-changes-button"></a><span data-ttu-id="a94b4-130">“取消更改”按钮</span><span class="sxs-lookup"><span data-stu-id="a94b4-130">Cancel Changes Button</span></span>

<span data-ttu-id="a94b4-131">单击 "**取消更改**" 将激活\_VBScript Cancel OnClick Sub 过程, 该过程将执行 RDS。rds.datacontrol 对象的 (CancelUpdate 方法。</span><span class="sxs-lookup"><span data-stu-id="a94b4-131">Clicking **Cancel Changes** activates the VBScript Cancel\_OnClick Sub procedure, which executes the RDS.DataControl object's ( CancelUpdate method.</span></span>

```vb 
 
Sub Cancel_OnClick 
 DC1.CancelUpdate 
End Sub 
```

<span data-ttu-id="a94b4-132">在执行此操作时, 它会丢弃用户自上一次查询或更新以来对数据网格上的员工记录所做的任何编辑。</span><span class="sxs-lookup"><span data-stu-id="a94b4-132">When executes, it discards any edits that a user has made to an employee record on the data grid since the last query or update.</span></span> <span data-ttu-id="a94b4-133">它将还原原始值。</span><span class="sxs-lookup"><span data-stu-id="a94b4-133">It restores the original values.</span></span>

