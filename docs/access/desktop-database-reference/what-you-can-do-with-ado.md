---
title: 使用 ADO 可以执行的操作
TOCTitle: What You Can Do With ADO
ms:assetid: 98246cb0-aec6-6a77-c953-85895ad83a5d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249681(v=office.15)
ms:contentKeyID: 48546483
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 5b7d0bab179cd7ec658bc04cee05f486947f38c9
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28702115"
---
# <a name="what-you-can-do-with-ado"></a><span data-ttu-id="73179-102">ADO 有何用途</span><span class="sxs-lookup"><span data-stu-id="73179-102">What you can do with ADO</span></span>


<span data-ttu-id="73179-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="73179-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="73179-p101">ADO 旨在向开发人员提供一个功能强大的逻辑对象模型，使用该模型，可以通过 OLE DB 系统接口以编程方式访问、编辑和更新广泛的数据源。ADO 最常见的用法是：在关系数据库中查询表，在应用程序中检索记录并显示结果，有可能允许用户更改数据并保存所做的更改。使用 ADO，还能够以编程方式执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="73179-p101">ADO is designed to provide developers with a powerful, logical object model for programmatically accessing, editing, and updating a wide variety of data sources through OLE DB system interfaces. The most common usage of ADO is to query a table or tables in a relational database, retrieve and display the results in an application, and perhaps allow users to make and save changes to the data. Other things that can be done programmatically with ADO include:</span></span>

- <span data-ttu-id="73179-107">使用 SQL 查询数据库并显示结果。</span><span class="sxs-lookup"><span data-stu-id="73179-107">Querying a database using SQL and displaying the results.</span></span>

- <span data-ttu-id="73179-108">通过 Internet 访问文件存储区中的信息。</span><span class="sxs-lookup"><span data-stu-id="73179-108">Accessing information in a file store over the Internet.</span></span>

- <span data-ttu-id="73179-109">操作电子邮件系统中的邮件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="73179-109">Manipulating messages and folders in an email system.</span></span>

- <span data-ttu-id="73179-110">将数据库中的数据保存到 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="73179-110">Saving data from a database into an XML file.</span></span>

- <span data-ttu-id="73179-111">允许用户检索数据库表中的数据并对这些数据进行更改。</span><span class="sxs-lookup"><span data-stu-id="73179-111">Allowing a user to review and make changes to data in database tables.</span></span>

- <span data-ttu-id="73179-112">创建和重新使用参数化数据库命令。</span><span class="sxs-lookup"><span data-stu-id="73179-112">Creating and reusing parameterized database commands.</span></span>

- <span data-ttu-id="73179-113">执行存储过程。</span><span class="sxs-lookup"><span data-stu-id="73179-113">Executing stored procedures.</span></span>

- <span data-ttu-id="73179-114">以动态方式创建一个名为 **Recordset** 的灵活结构，用来存放、导航和操作数据。</span><span class="sxs-lookup"><span data-stu-id="73179-114">Dynamically creating a flexible structure, called a **Recordset**, to hold, navigate, and manipulate data.</span></span>

- <span data-ttu-id="73179-115">执行事务数据库操作。</span><span class="sxs-lookup"><span data-stu-id="73179-115">Performing transactional database operations.</span></span>

- <span data-ttu-id="73179-116">基于运行时条件对数据库信息的本地副本进行筛选和排序。</span><span class="sxs-lookup"><span data-stu-id="73179-116">Filtering and sorting local copies of database information based on run-time criteria.</span></span>

- <span data-ttu-id="73179-117">创建和操作数据库中的分层结果。</span><span class="sxs-lookup"><span data-stu-id="73179-117">Creating and manipulating hierarchical results from databases.</span></span>

- <span data-ttu-id="73179-118">将数据库中的字段绑定到能够识别数据的组件。</span><span class="sxs-lookup"><span data-stu-id="73179-118">Binding database fields to data-aware components.</span></span>

- <span data-ttu-id="73179-119">创建已断开连接的远程 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="73179-119">Creating remote, disconnected **Recordsets**.</span></span>

<span data-ttu-id="73179-p102">ADO 必须公开广泛的选项和设置，才能提供这样的灵活性。因此，一定要采取系统的方法来了解如何在应用程序中使用 ADO，并将每个目标都分成可管理的部分。</span><span class="sxs-lookup"><span data-stu-id="73179-p102">ADO must expose a wide variety of options and settings in order to provide such flexibility. Therefore it's important to take a methodical approach to learning how to use ADO in an application, breaking down each of your goals into manageable pieces.</span></span>

<span data-ttu-id="73179-p103">大多数 ADO 程序都涉及四个主要操作：获取数据、检查数据、编辑数据和更新数据。接下来的四章将更详细地介绍各个操作。</span><span class="sxs-lookup"><span data-stu-id="73179-p103">Four primary operations are involved in most ADO programs: getting data, examining data, editing data, and updating data. The next four chapters examine each of these operations in more detail.</span></span>

<span data-ttu-id="73179-p104">在继续之前，请先熟悉 ADO 对象模型中的对象。然后查看 [HelloData：简单 ADO 应用程序](hellodata-a-simple-ado-application.md)，这个应用程序是用 Visual Basic 编写的，可用来执行这四个主要的 ADO 操作。</span><span class="sxs-lookup"><span data-stu-id="73179-p104">Before proceeding, familiarize yourself with the objects in the ADO Object Model. Then review [HelloData: A Simple ADO Application](hellodata-a-simple-ado-application.md). This application is written in Visual Basic and performs each of the four primary ADO operations.</span></span>

