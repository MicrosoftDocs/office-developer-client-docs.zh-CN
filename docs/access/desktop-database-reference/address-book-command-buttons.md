---
title: 通讯簿命令按钮
TOCTitle: Address Book Command Buttons
ms:assetid: bcea6f53-3e36-b067-03c2-b157ed02d41d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249908(v=office.15)
ms:contentKeyID: 48547422
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 15a79db455032ddf2eb9fa0d9555d8f7a4959313
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468724"
---
# <a name="address-book-command-buttons"></a><span data-ttu-id="2c360-102">通讯簿命令按钮</span><span class="sxs-lookup"><span data-stu-id="2c360-102">Address Book Command Buttons</span></span>


<span data-ttu-id="2c360-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="2c360-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="2c360-104">通讯簿应用程序包括以下命令按钮：</span><span class="sxs-lookup"><span data-stu-id="2c360-104">The Address Book application includes the following command buttons:</span></span>

  - <span data-ttu-id="2c360-105">“查找”按钮，用于向数据库提交查询。</span><span class="sxs-lookup"><span data-stu-id="2c360-105">A Find button to submit a query to the database.</span></span>

  - <span data-ttu-id="2c360-106">**清除**的按钮，用于在开始新的搜索之前清除文本框。</span><span class="sxs-lookup"><span data-stu-id="2c360-106">A **Clear** button to clear the text boxes before starting a new search.</span></span>

  - <span data-ttu-id="2c360-107">“更新配置文件”按钮，用于保存对雇员记录所做的更改。</span><span class="sxs-lookup"><span data-stu-id="2c360-107">An Update Profile button to save changes to an employee record.</span></span>

  - <span data-ttu-id="2c360-108">“取消更改”按钮，用于放弃更改。</span><span class="sxs-lookup"><span data-stu-id="2c360-108">A Cancel Changes button to discard changes.</span></span>

## <a name="find-button"></a><span data-ttu-id="2c360-109">"查找"按钮</span><span class="sxs-lookup"><span data-stu-id="2c360-109">Find Button</span></span>

<span data-ttu-id="2c360-110">单击**查找**按钮可激活 VBScript 查找\_OnClick Sub 过程，用于生成和发送 SQL 查询。</span><span class="sxs-lookup"><span data-stu-id="2c360-110">Clicking the **Find** button activates the VBScript Find\_OnClick Sub procedure, which builds and sends the SQL query.</span></span> <span data-ttu-id="2c360-111">单击此按钮填充数据网格。</span><span class="sxs-lookup"><span data-stu-id="2c360-111">Clicking this button populates the data grid.</span></span>

## <a name="building-the-sql-query"></a><span data-ttu-id="2c360-112">生成 SQL 查询</span><span class="sxs-lookup"><span data-stu-id="2c360-112">Building the SQL Query</span></span>

<span data-ttu-id="2c360-113">查找的第一部分\_OnClick Sub 过程生成 SQL 查询，一次的某个短语，通过将文本字符串追加到全局 SQL SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="2c360-113">The first part of the Find\_OnClick Sub procedure builds the SQL query, one phrase at a time, by appending text strings to a global SQL SELECT statement.</span></span> <span data-ttu-id="2c360-114">通过将变量设置为 SQL SELECT 语句中的数据源表从请求的数据的所有行开始。</span><span class="sxs-lookup"><span data-stu-id="2c360-114">It begins by setting the variable to a SQL SELECT statement that requests all rows of data from the data source table.</span></span> <span data-ttu-id="2c360-115">然后，子过程对页面上的四个输入框逐一进行扫描。</span><span class="sxs-lookup"><span data-stu-id="2c360-115">Next, the Sub procedure scans each of the four input boxes on the page.</span></span>

<span data-ttu-id="2c360-116">由于程序使用构建 SQL 语句中的单词，查询将为子字符串搜索，而不是完全匹配。</span><span class="sxs-lookup"><span data-stu-id="2c360-116">Because the program uses the word in building the SQL statements, the queries are substring searches rather than exact matches.</span></span>

<span data-ttu-id="2c360-117">例如，如果**姓氏**框中包含条目"姓氏"和**标题**框中包含条目"程序管理员"，将读取 SQL 语句 （的值）：</span><span class="sxs-lookup"><span data-stu-id="2c360-117">For example, if the **Last Name** box contained the entry "Berge" and the **Title** box contained the entry "Program Manager", the SQL statement (value of ) would read:</span></span>

```vb 
 
Select FirstName, LastName, Title, Email, Building, Room, Phone from Employee where lastname like 'Berge%' and title like 'Program Manager%' 
```

<span data-ttu-id="2c360-118">如果查询成功，则姓氏中包含文本"高"（如"高"和"高阳"），且职务中包含"程序管理员"（如"高级技术程序管理员"）的所有人都将显示在 HTML 数据网格中。</span><span class="sxs-lookup"><span data-stu-id="2c360-118">If the query was successful, all persons with a last name containing the text "Berge" (such as Berge and Berger) and with a title containing the words "Program Manager" (for example, Program Manager, Advanced Technologies) are displayed in the HTML data grid.</span></span>

## <a name="preparing-and-sending-the-query"></a><span data-ttu-id="2c360-119">准备和发送查询</span><span class="sxs-lookup"><span data-stu-id="2c360-119">Preparing and Sending the Query</span></span>

<span data-ttu-id="2c360-120">查找的最后一部分\_OnClick Sub 过程包括两个语句。</span><span class="sxs-lookup"><span data-stu-id="2c360-120">The last part of the Find\_OnClick Sub procedure consists of two statements.</span></span> <span data-ttu-id="2c360-121">第一个语句为 RDS.DataControl 对象的 SQL 属性赋值以动态生成 SQL 查询。</span><span class="sxs-lookup"><span data-stu-id="2c360-121">The first statement assigns the SQL property of the RDS.DataControl object equal to the dynamically built SQL query.</span></span> <span data-ttu-id="2c360-122">第二个语句会导致**rds.DataControl**对象 （） 查询数据库，然后显示网格中的新查询的结果。</span><span class="sxs-lookup"><span data-stu-id="2c360-122">The second statement causes the **RDS.DataControl** object () to query the database, and then display the new results of the query in the grid.</span></span>

```vb 
 
Sub Find_OnClick 
 '... 
 DC1.SQL = myQuery 
 DC1.Refresh 
End Sub 
```

## <a name="update-profile-button"></a><span data-ttu-id="2c360-123">"更新配置文件"按钮</span><span class="sxs-lookup"><span data-stu-id="2c360-123">Update Profile Button</span></span>

<span data-ttu-id="2c360-124">单击**更新配置文件**按钮可激活 VBScript 更新\_OnClick Sub 过程，这将执行 rds.DataControl 对象 （） 的 SubmitChanges 和 Refresh 方法。</span><span class="sxs-lookup"><span data-stu-id="2c360-124">Clicking the **Update Profile** button activates the VBScript Update\_OnClick Sub procedure, which executes the RDS.DataControl object's () SubmitChanges and Refresh methods.</span></span>

```vb 
 
Sub Update_OnClick 
 DC1.SubmitChanges 
 DC1.Refresh 
End Sub 
```

<span data-ttu-id="2c360-125">当 DC1。SubmitChanges 执行，远程数据服务包更新的所有信息并将其发送到服务器通过 HTTP。</span><span class="sxs-lookup"><span data-stu-id="2c360-125">When DC1.SubmitChanges executes, the Remote Data Service packages all the update information and sends it to the server via HTTP.</span></span> <span data-ttu-id="2c360-126">更新是这;如果未成功更新的一部分，进行任何更改，并返回状态邮件。</span><span class="sxs-lookup"><span data-stu-id="2c360-126">The update is all-or-nothing; if a part of the update is unsuccessful, none of the changes is made, and a status message is returned.</span></span> <span data-ttu-id="2c360-127">执行时，远程数据服务包更新的所有信息并将其发送到服务器通过 HTTP。</span><span class="sxs-lookup"><span data-stu-id="2c360-127">executes, the Remote Data Service packages all the update information and sends it to the server via HTTP.</span></span> <span data-ttu-id="2c360-128">更新是这;如果未成功更新的一部分，进行任何更改，并返回状态邮件。</span><span class="sxs-lookup"><span data-stu-id="2c360-128">The update is all-or-nothing; if a part of the update is unsuccessful, none of the changes is made, and a status message is returned.</span></span> <span data-ttu-id="2c360-129">DC1。与远程数据服务，**则 SubmitChanges**后，刷新不是必需，但它可以确保刷新数据。</span><span class="sxs-lookup"><span data-stu-id="2c360-129">DC1.Refresh isn't necessary after **SubmitChanges** with Remote Data Service, but it ensures fresh data.</span></span>

## <a name="cancel-changes-button"></a><span data-ttu-id="2c360-130">"取消更改"按钮</span><span class="sxs-lookup"><span data-stu-id="2c360-130">Cancel Changes Button</span></span>

<span data-ttu-id="2c360-131">单击**取消更改**可激活 VBScript 取消\_OnClick Sub 过程，这将执行 rds.DataControl 对象的 （CancelUpdate 方法。</span><span class="sxs-lookup"><span data-stu-id="2c360-131">Clicking **Cancel Changes** activates the VBScript Cancel\_OnClick Sub procedure, which executes the RDS.DataControl object's ( CancelUpdate method.</span></span>

```vb 
 
Sub Cancel_OnClick 
 DC1.CancelUpdate 
End Sub 
```

<span data-ttu-id="2c360-132">当执行时，它将丢弃以来的最后一个查询或更新用户对数据网格上雇员记录所做的任何编辑。</span><span class="sxs-lookup"><span data-stu-id="2c360-132">When executes, it discards any edits that a user has made to an employee record on the data grid since the last query or update.</span></span> <span data-ttu-id="2c360-133">它将还原的原始值。</span><span class="sxs-lookup"><span data-stu-id="2c360-133">It restores the original values.</span></span>

