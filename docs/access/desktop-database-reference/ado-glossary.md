---
title: ActiveX 数据对象 (ADO) 术语表
TOCTitle: ADO Glossary
ms:assetid: 40f00876-7525-4117-8f57-f3d87c54be99
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249184(v=office.15)
ms:contentKeyID: 48544438
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 7ecb6208a8c970f037cb0ac699c947544eb8f547
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32284832"
---
# <a name="ado-glossary"></a><span data-ttu-id="de624-102">ADO 术语表</span><span class="sxs-lookup"><span data-stu-id="de624-102">ADO glossary</span></span>

<span data-ttu-id="de624-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="de624-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="a"></a><span data-ttu-id="de624-104">A</span><span class="sxs-lookup"><span data-stu-id="de624-104">A</span></span>

<span data-ttu-id="de624-105">**绝对 URL**</span><span class="sxs-lookup"><span data-stu-id="de624-105">**absolute URL**</span></span>

<span data-ttu-id="de624-106">一个完全限定的 URL, 用于指定驻留在 Internet 或 intranet 上的资源的位置。</span><span class="sxs-lookup"><span data-stu-id="de624-106">A fully qualified URL that specifies the location of a resource that resides on the Internet or an intranet.</span></span> <span data-ttu-id="de624-107">另请参阅**url**和**相对 url**。</span><span class="sxs-lookup"><span data-stu-id="de624-107">See also **URL** and **relative URL**.</span></span>

<span data-ttu-id="de624-108">**ActiveX 控件**</span><span class="sxs-lookup"><span data-stu-id="de624-108">**ActiveX control**</span></span>

<span data-ttu-id="de624-109">在设计时或运行时通常具有 visual 元素的自注册进程内 COM 组件。</span><span class="sxs-lookup"><span data-stu-id="de624-109">Self-registering, in-process COM component that often has a visual element either at design time or run time.</span></span> <span data-ttu-id="de624-110">ActiveX 控件还能够与活动文档容器 (如 Microsoft Internet Explorer) 进行通信。</span><span class="sxs-lookup"><span data-stu-id="de624-110">ActiveX controls also have the ability to communicate with an Active Document container, such as Microsoft Internet Explorer.</span></span>

<span data-ttu-id="de624-111">**ADISAPI (高级数据 Internet 服务器应用程序编程接口)**</span><span class="sxs-lookup"><span data-stu-id="de624-111">**ADISAPI (Advanced Data Internet Server Application Programming Interface)**</span></span>

<span data-ttu-id="de624-112">提供分析、自动化控制、 **Recordset**封送和 MIME 打包的 ISAPI DLL。</span><span class="sxs-lookup"><span data-stu-id="de624-112">An ISAPI DLL that provides parsing, Automation control, **Recordset** marshaling, and MIME packaging.</span></span> <span data-ttu-id="de624-113">ADISAPI 组件通过 Internet 信息服务 (IIS) 提供的 API 进行工作。</span><span class="sxs-lookup"><span data-stu-id="de624-113">The ADISAPI component works through the API provided by Internet Information Services (IIS).</span></span> <span data-ttu-id="de624-114">另请参阅**ISAPI**。</span><span class="sxs-lookup"><span data-stu-id="de624-114">See also **ISAPI**.</span></span>

<span data-ttu-id="de624-115">**聚合函数**</span><span class="sxs-lookup"><span data-stu-id="de624-115">**aggregate function**</span></span>

<span data-ttu-id="de624-116">在查询中, 使用表的某一列中的所有行计算值的函数 (如 COUNT、AVG 或 STDEV)。</span><span class="sxs-lookup"><span data-stu-id="de624-116">In a query, a function such as COUNT, AVG, or STDEV that calculates a value using all the rows in a column of a table.</span></span> <span data-ttu-id="de624-117">在编写表达式和编程中, 可以使用 SQL 聚合函数 (包括上面列出的三个) 和域聚合函数来确定各种统计信息。</span><span class="sxs-lookup"><span data-stu-id="de624-117">In writing expressions and in programming, you can use SQL aggregate functions (including the three listed above) and domain aggregate functions to determine various statistics.</span></span>

<span data-ttu-id="de624-118">**alias**</span><span class="sxs-lookup"><span data-stu-id="de624-118">**alias**</span></span>

<span data-ttu-id="de624-119">您为 SQL SELECT 语句中的列或表达式赋予的替代名称, 通常较短或更有意义。</span><span class="sxs-lookup"><span data-stu-id="de624-119">An alternate name you give to a column or expression in an SQL SELECT statement, often shorter or more meaningful.</span></span> <span data-ttu-id="de624-120">例如, BobSales 是以下 SELECT 语句中的别名: "SELECT wr-Sales as BobSales from SalesDB"。</span><span class="sxs-lookup"><span data-stu-id="de624-120">For example, BobSales is the alias in the following SELECT statement: "Select wr-Sales as BobSales from SalesDB".</span></span> <span data-ttu-id="de624-121">可以使用别名在**rds.datacontrol**对象上将列动态分配给控件绑定。</span><span class="sxs-lookup"><span data-stu-id="de624-121">An alias can be used to dynamically assign columns to control bindings on the **DataControl** object.</span></span>

<span data-ttu-id="de624-122">**单元线程**</span><span class="sxs-lookup"><span data-stu-id="de624-122">**apartment threading**</span></span>

<span data-ttu-id="de624-123">一个 COM 线程模型, 其中对象的所有调用都发生在一个线程上。</span><span class="sxs-lookup"><span data-stu-id="de624-123">A COM threading model where all calls to an object occur on one thread.</span></span> <span data-ttu-id="de624-124">在单元线程中, COM 将同步和封送调用。</span><span class="sxs-lookup"><span data-stu-id="de624-124">In apartment threading, COM synchronizes and marshals calls.</span></span> <span data-ttu-id="de624-125">另请参阅**COM**。</span><span class="sxs-lookup"><span data-stu-id="de624-125">See also **COM**.</span></span>

<span data-ttu-id="de624-126">**异步操作**</span><span class="sxs-lookup"><span data-stu-id="de624-126">**asynchronous operation**</span></span>

<span data-ttu-id="de624-127">在不等待操作完成的情况下, 将控制返回给调用程序的操作。</span><span class="sxs-lookup"><span data-stu-id="de624-127">An operation that returns control to the calling program without waiting for the operation to complete.</span></span> <span data-ttu-id="de624-128">在操作完成之前, 将继续执行代码。</span><span class="sxs-lookup"><span data-stu-id="de624-128">Before the operation is complete, code execution continues.</span></span> <span data-ttu-id="de624-129">另请参阅**同步操作**。</span><span class="sxs-lookup"><span data-stu-id="de624-129">See also **synchronous operation**.</span></span>

<span data-ttu-id="de624-130">返回顶部</span><span class="sxs-lookup"><span data-stu-id="de624-130">Return to top</span></span>

## <a name="b"></a><span data-ttu-id="de624-131">B</span><span class="sxs-lookup"><span data-stu-id="de624-131">B</span></span>

<span data-ttu-id="de624-132">**绑定条目**</span><span class="sxs-lookup"><span data-stu-id="de624-132">**binding entry**</span></span>

<span data-ttu-id="de624-133">表中的字段和变量之间的映射。</span><span class="sxs-lookup"><span data-stu-id="de624-133">A mapping between a field in a table and a variable.</span></span> <span data-ttu-id="de624-134">在 ADO Visual c + + 扩展中, **Recordset**字段映射到 c/c + + 变量。</span><span class="sxs-lookup"><span data-stu-id="de624-134">In the ADO Visual C++ extensions, **Recordset** fields are mapped to C/C++ variables.</span></span>

<span data-ttu-id="de624-135">**位掩码**</span><span class="sxs-lookup"><span data-stu-id="de624-135">**bitmask**</span></span>

<span data-ttu-id="de624-136">一个用于按位值与其他数值进行比较的数值, 通常用于标记参数或返回值中的选项。</span><span class="sxs-lookup"><span data-stu-id="de624-136">A numeric value intended for a bit-by-bit value comparison with other numeric values, typically to flag options in parameter or return values.</span></span> <span data-ttu-id="de624-137">通常, 此比较是通过按位逻辑运算符 (如**and**和**Or**在 Visual Basic **&** 和**|** c + + 中完成的) 实现的。</span><span class="sxs-lookup"><span data-stu-id="de624-137">Usually this comparison is done with bitwise logical operators, such as **And** and **Or** in Visual Basic, **&** and **|** in C++.</span></span>

<span data-ttu-id="de624-138">例如, 可以将 ADO **FieldAttributeEnum**值用作位掩码, 以确定字段的属性。</span><span class="sxs-lookup"><span data-stu-id="de624-138">For example, the ADO **FieldAttributeEnum** values can be used as bitmasks to determine the attributes of a field.</span></span> <span data-ttu-id="de624-139">假设您想要确定字段是否可更新。</span><span class="sxs-lookup"><span data-stu-id="de624-139">Suppose you wanted to determine if a field was updateable.</span></span> <span data-ttu-id="de624-140">您可以使用 Visual Basic 中的以下表达式对此进行测试:</span><span class="sxs-lookup"><span data-stu-id="de624-140">You could test for this with the following expression in Visual Basic:</span></span>  
  

<span data-ttu-id="de624-141">如果结果为 TRUE, 则字段是可更新的。</span><span class="sxs-lookup"><span data-stu-id="de624-141">If the result is TRUE, then the field is updateable.</span></span>

<span data-ttu-id="de624-142">**bookmark**</span><span class="sxs-lookup"><span data-stu-id="de624-142">**bookmark**</span></span>

<span data-ttu-id="de624-143">唯一标识一组行中的行的标记, 以便用户可以快速导航到该数据行。</span><span class="sxs-lookup"><span data-stu-id="de624-143">A marker that uniquely identifies a row within a set of rows so that a user can quickly navigate to it.</span></span>

<span data-ttu-id="de624-144">**业务对象**</span><span class="sxs-lookup"><span data-stu-id="de624-144">**business object**</span></span>

<span data-ttu-id="de624-145">执行定义的一组操作 (如数据验证或业务规则逻辑) 的对象。</span><span class="sxs-lookup"><span data-stu-id="de624-145">An object that performs a defined set of operations, such as data validation or business rule logic.</span></span> <span data-ttu-id="de624-146">业务对象通常驻留在中间层上。</span><span class="sxs-lookup"><span data-stu-id="de624-146">Business objects usually reside on the middle tier.</span></span>

<span data-ttu-id="de624-147">**业务规则**</span><span class="sxs-lookup"><span data-stu-id="de624-147">**business rule**</span></span>

<span data-ttu-id="de624-148">验证编辑、登录验证、数据库查找、策略和算法转换的组合构成了企业开展业务的方式。</span><span class="sxs-lookup"><span data-stu-id="de624-148">The combination of validation edits, logon verifications, database lookups, policies, and algorithmic transformations that constitute an enterprise's way of doing business.</span></span> <span data-ttu-id="de624-149">也称为*业务逻辑*。</span><span class="sxs-lookup"><span data-stu-id="de624-149">Also known as *business logic*.</span></span>

<span data-ttu-id="de624-150">返回顶部</span><span class="sxs-lookup"><span data-stu-id="de624-150">Return to top</span></span>

## <a name="c"></a><span data-ttu-id="de624-151">C</span><span class="sxs-lookup"><span data-stu-id="de624-151">C</span></span>

<span data-ttu-id="de624-152">**计算表达式**</span><span class="sxs-lookup"><span data-stu-id="de624-152">**calculated expression**</span></span>

<span data-ttu-id="de624-153">一个不是常量, 但其值取决于其他值的表达式。</span><span class="sxs-lookup"><span data-stu-id="de624-153">An expression that is not constant, but whose value depends upon other values.</span></span> <span data-ttu-id="de624-154">计算的表达式必须从其他源 (通常在其他字段或行中) 获取和计算值, 才能对其进行计算。</span><span class="sxs-lookup"><span data-stu-id="de624-154">To be evaluated, a calculated expression must obtain and compute values from other sources, typically in other fields or rows.</span></span>

<span data-ttu-id="de624-155">**第二章**</span><span class="sxs-lookup"><span data-stu-id="de624-155">**chapter**</span></span>

<span data-ttu-id="de624-156">对数据源中的行区域的引用。</span><span class="sxs-lookup"><span data-stu-id="de624-156">A reference to a range of rows from a data source.</span></span> <span data-ttu-id="de624-157">在 ADO 中, 一章通常是对另一个**Recordset**的引用。</span><span class="sxs-lookup"><span data-stu-id="de624-157">In ADO, a chapter is typically a reference to another **Recordset**.</span></span>

<span data-ttu-id="de624-158">章节列使您可以定义*父子*关系，其中*父*是包含章节列的 **Recordset**，而*子*是章节所表示的 **Recordset**。</span><span class="sxs-lookup"><span data-stu-id="de624-158">Chapter columns make it possible to define a *parent-child* relationship where the *parent* is the **Recordset** containing the chapter column and the *child* is the **Recordset** represented by the chapter.</span></span>

<span data-ttu-id="de624-159">**chapter-alias**</span><span class="sxs-lookup"><span data-stu-id="de624-159">**chapter-alias**</span></span>

<span data-ttu-id="de624-160">引用追加到父项的列的别名。</span><span class="sxs-lookup"><span data-stu-id="de624-160">An alias that refers to the column appended to the parent.</span></span>

<span data-ttu-id="de624-161">**字符集**</span><span class="sxs-lookup"><span data-stu-id="de624-161">**character set**</span></span>

<span data-ttu-id="de624-162">一组字符到它们的数值的映射。</span><span class="sxs-lookup"><span data-stu-id="de624-162">A mapping of a set of characters to their numeric values.</span></span> <span data-ttu-id="de624-163">例如, Unicode 是一种16位字符集, 能够对所有已知字符进行编码, 并将其用作全球字符编码标准。</span><span class="sxs-lookup"><span data-stu-id="de624-163">For example, Unicode is a 16-bit character set capable of encoding all known characters and used as a worldwide character-encoding standard.</span></span>

<span data-ttu-id="de624-164">**该子**</span><span class="sxs-lookup"><span data-stu-id="de624-164">**child**</span></span>

<span data-ttu-id="de624-165">层次结构关系的从属端。</span><span class="sxs-lookup"><span data-stu-id="de624-165">The dependent side of a hierarchical relationship.</span></span> <span data-ttu-id="de624-166">子节点是层次结构中具有另一个节点 (更接近于根) 的节点。</span><span class="sxs-lookup"><span data-stu-id="de624-166">A child is a node in a hierarchical structure that has another node above it (closer to the root).</span></span> <span data-ttu-id="de624-167">另请参阅**子别名**、**父-子关系**和**父项**。</span><span class="sxs-lookup"><span data-stu-id="de624-167">See also **child-alias**, **parent-child relationship**, **parent**.</span></span>

<span data-ttu-id="de624-168">**child-alias**</span><span class="sxs-lookup"><span data-stu-id="de624-168">**child-alias**</span></span>

<span data-ttu-id="de624-169">引用子级的别名。</span><span class="sxs-lookup"><span data-stu-id="de624-169">An alias that refers to the child.</span></span> <span data-ttu-id="de624-170">另请参阅**alias**、**子级**。</span><span class="sxs-lookup"><span data-stu-id="de624-170">See also **alias**, **child**.</span></span>

<span data-ttu-id="de624-171">**CLSID (类标识符)**</span><span class="sxs-lookup"><span data-stu-id="de624-171">**CLSID (class identifier)**</span></span>

<span data-ttu-id="de624-172">标识 COM 组件的通用唯一标识符 (UUID)。</span><span class="sxs-lookup"><span data-stu-id="de624-172">A universally unique identifier (UUID) that identifies a COM component.</span></span> <span data-ttu-id="de624-173">每个 COM 组件在 Windows 注册表中都有其 CLSID, 以便其他应用程序可以加载它。</span><span class="sxs-lookup"><span data-stu-id="de624-173">Each COM component has its CLSID in the Windows Registry so that it can be loaded by other applications.</span></span> <span data-ttu-id="de624-174">另请参阅**ProgID**和**COM**。</span><span class="sxs-lookup"><span data-stu-id="de624-174">See also **ProgID**, **COM**.</span></span>

<span data-ttu-id="de624-175">**客户端层**</span><span class="sxs-lookup"><span data-stu-id="de624-175">**client tier**</span></span>

<span data-ttu-id="de624-176">通常向用户提供数据并处理来自用户的输入的分布式系统的逻辑层, 有时称为*前端*。</span><span class="sxs-lookup"><span data-stu-id="de624-176">A logical layer of a distributed system that typically presents data to and processes input from the user, sometimes referred to as the *front end*.</span></span> <span data-ttu-id="de624-177">通常情况下, 客户端层根据输入从服务器请求数据, 然后设置并显示结果。</span><span class="sxs-lookup"><span data-stu-id="de624-177">Usually, the client tier requests data from a server based on input, and then formats and displays the result.</span></span> <span data-ttu-id="de624-178">另请参阅**中间层**、**数据源层**和**分布式应用程序**。</span><span class="sxs-lookup"><span data-stu-id="de624-178">See also **middle tier**, **data source tier**, **distributed application**.</span></span>

<span data-ttu-id="de624-179">**COM (组件对象模型)**</span><span class="sxs-lookup"><span data-stu-id="de624-179">**COM (Component Object Model)**</span></span>

<span data-ttu-id="de624-180">一种二进制标准, 使对象能够在网络环境中进行互操作, 而不管它们是在什么语言中开发的, 或者它们驻留在哪些计算机上。</span><span class="sxs-lookup"><span data-stu-id="de624-180">A binary standard that enables objects to interoperate in a networked environment regardless of the language in which they were developed or on which computers they reside.</span></span> <span data-ttu-id="de624-181">基于 COM 的技术包括 ActiveX 控件、自动化和对象链接和嵌入 (OLE)。</span><span class="sxs-lookup"><span data-stu-id="de624-181">COM-based technologies include ActiveX Controls, Automation, and object linking and embedding (OLE).</span></span> <span data-ttu-id="de624-182">COM 允许对象向其他组件和主机应用程序公开其功能。</span><span class="sxs-lookup"><span data-stu-id="de624-182">COM allows an object to expose its functionality to other components and to host applications.</span></span> <span data-ttu-id="de624-183">它定义对象如何公开自己以及此公开在各个进程之间以及跨网络的工作方式。</span><span class="sxs-lookup"><span data-stu-id="de624-183">It defines both how the object exposes itself and how this exposure works across processes and across networks.</span></span> <span data-ttu-id="de624-184">COM 还定义对象的生命周期。</span><span class="sxs-lookup"><span data-stu-id="de624-184">COM also defines the object's life cycle.</span></span>

<span data-ttu-id="de624-185">**COM 组件**</span><span class="sxs-lookup"><span data-stu-id="de624-185">**COM component**</span></span>

<span data-ttu-id="de624-186">二进制文件 (如 .dll、.ocx 和一些 .exe 文件), 它们支持用于提供对象的 COM 标准。</span><span class="sxs-lookup"><span data-stu-id="de624-186">Binary file — such as .dll, .ocx, and some .exe files — that supports the COM standard for providing objects.</span></span> <span data-ttu-id="de624-187">此类文件包含用于一个或多个类工厂、COM 类、注册表项机制、加载代码等的代码。</span><span class="sxs-lookup"><span data-stu-id="de624-187">Such a file contains code for one or more class factories, COM classes, registry-entry mechanisms, loading code, and so on.</span></span>

<span data-ttu-id="de624-188">**比较运算符**</span><span class="sxs-lookup"><span data-stu-id="de624-188">**comparison operator**</span></span>

<span data-ttu-id="de624-189">一个运算符, 用于比较两个表达式并返回一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="de624-189">An operator that compares two expressions and returns a Boolean value.</span></span>

<span data-ttu-id="de624-190">一个 criteria 参数\>, 可表示为 "" (大于)、"\<(小于)、" = "(等)、"\>= "(大于或等于)、"\<= "(小于或等于)、" = "(小于或等于\<\>)、" "(不等于) 或" like "(模式匹配)。</span><span class="sxs-lookup"><span data-stu-id="de624-190">A criteria parameter that may be expressed as "\>" (greater than), "\<" (less than), "=" (equal), "\>=" (greater than or equal), "\<=" (less than or equal), "\<\>" (not equal), or "like" (pattern matching).</span></span>

<span data-ttu-id="de624-191">**component**</span><span class="sxs-lookup"><span data-stu-id="de624-191">**component**</span></span>

<span data-ttu-id="de624-192">一个对象, 它封装数据和代码, 并提供一组特定的公开提供的服务。</span><span class="sxs-lookup"><span data-stu-id="de624-192">An object that encapsulates both data and code, and provides a well-specified set of publicly available services.</span></span>

<span data-ttu-id="de624-193">**复合文件**</span><span class="sxs-lookup"><span data-stu-id="de624-193">**compound file**</span></span>

<span data-ttu-id="de624-194">文件的 COM 结构化存储的实现。</span><span class="sxs-lookup"><span data-stu-id="de624-194">An implementation of COM structured storage for files.</span></span> <span data-ttu-id="de624-195">复合文件将单独的对象存储在单个结构化文件中, 其中包含两个主要元素: storage 对象和 stream 对象。</span><span class="sxs-lookup"><span data-stu-id="de624-195">A compound file stores separate objects in a single, structured file consisting of two main elements: storage objects and stream objects.</span></span> <span data-ttu-id="de624-196">它们一起工作, 就像文件中的文件系统。</span><span class="sxs-lookup"><span data-stu-id="de624-196">Together, they function like a file system within a file.</span></span> <span data-ttu-id="de624-197">有关详细信息, 请参阅 Microsoft Platform SDK 中的复合文件。</span><span class="sxs-lookup"><span data-stu-id="de624-197">For more information, see Compound Files in the Microsoft Platform SDK.</span></span>

<span data-ttu-id="de624-198">在一个物理文件中绑定在一起的多个单个文件。</span><span class="sxs-lookup"><span data-stu-id="de624-198">A number of individual files bound together in one physical file.</span></span> <span data-ttu-id="de624-199">复合文件中的每个单独文件都可以像访问单个物理文件一样被访问。</span><span class="sxs-lookup"><span data-stu-id="de624-199">Each individual file in a compound file can be accessed as if it were a single physical file.</span></span>

<span data-ttu-id="de624-200">**常量**</span><span class="sxs-lookup"><span data-stu-id="de624-200">**constant**</span></span>

<span data-ttu-id="de624-201">不更改的数值或字符串值。</span><span class="sxs-lookup"><span data-stu-id="de624-201">A numeric or string value that does not change.</span></span> <span data-ttu-id="de624-202">命名的 ADO 枚举 (枚举常量) 可在代码中使用, 而不是实际值, 例如, **adUseClient**是一个值为3的常量。</span><span class="sxs-lookup"><span data-stu-id="de624-202">Named ADO enumerations (enumerated constants) can be used in your code instead of actual values, for example, **adUseClient** is a constant whose value is 3.</span></span> <span data-ttu-id="de624-203">(Const adUseClient = 3)。</span><span class="sxs-lookup"><span data-stu-id="de624-203">(Const adUseClient = 3).</span></span> <span data-ttu-id="de624-204">另请参阅**枚举**。</span><span class="sxs-lookup"><span data-stu-id="de624-204">See also **enumeration**.</span></span>

<span data-ttu-id="de624-205">**游标**</span><span class="sxs-lookup"><span data-stu-id="de624-205">**cursor**</span></span>

<span data-ttu-id="de624-206">一个数据库元素, 用于控制记录导航、数据更新以及其他用户对数据库所做更改的可见性。</span><span class="sxs-lookup"><span data-stu-id="de624-206">A database element that controls record navigation, updateability of data, and the visibility of changes made to the database by other users.</span></span>

<span data-ttu-id="de624-207">返回顶部</span><span class="sxs-lookup"><span data-stu-id="de624-207">Return to top</span></span>

## <a name="d"></a><span data-ttu-id="de624-208">D</span><span class="sxs-lookup"><span data-stu-id="de624-208">D</span></span>

<span data-ttu-id="de624-209">**数据绑定**</span><span class="sxs-lookup"><span data-stu-id="de624-209">**data binding**</span></span>

<span data-ttu-id="de624-210">将应用程序的对象或控件与数据源关联的过程。</span><span class="sxs-lookup"><span data-stu-id="de624-210">The process of associating the objects or controls of an application to a data source.</span></span> <span data-ttu-id="de624-211">与数据源关联的控件称为*数据绑定控件*。</span><span class="sxs-lookup"><span data-stu-id="de624-211">A control associated with a data source is called a *data-bound control*.</span></span>

<span data-ttu-id="de624-212">数据绑定控件的内容与数据库中的值相关联。</span><span class="sxs-lookup"><span data-stu-id="de624-212">The contents of a data-bound control are associated with values from a database.</span></span> <span data-ttu-id="de624-213">例如, 在更新**recordset**中的行时, 可以更新绑定到**recordset**对象的网格控件。</span><span class="sxs-lookup"><span data-stu-id="de624-213">For example, a grid control that is bound to a **Recordset** object can be updated when the rows in the **Recordset** are updated.</span></span> <span data-ttu-id="de624-214">当**Recordset**检索新值时, 新值将显示在网格中。</span><span class="sxs-lookup"><span data-stu-id="de624-214">When new values are retrieved by the **Recordset**, new values are displayed in the grid.</span></span>

<span data-ttu-id="de624-215">**数据提供程序**</span><span class="sxs-lookup"><span data-stu-id="de624-215">**data provider**</span></span>

<span data-ttu-id="de624-216">直接或通过服务提供程序向 ADO 应用程序公开数据的软件。</span><span class="sxs-lookup"><span data-stu-id="de624-216">Software that exposes data to an ADO application either directly or via a service provider.</span></span> <span data-ttu-id="de624-217">另请参阅**服务提供程序**。</span><span class="sxs-lookup"><span data-stu-id="de624-217">See also **service provider**.</span></span>

<span data-ttu-id="de624-218">**数据定形**</span><span class="sxs-lookup"><span data-stu-id="de624-218">**data shaping**</span></span>

<span data-ttu-id="de624-219">一种使用形式化语法 (称为 " **Shape language**") 定义专用**recordset**对象 (称为 "**整形" recordset**) 的技术, 它不仅包含数据, 还包含对其他**Recordset**对象的引用和/or 基于这些其他**Recordset**对象的计算值。</span><span class="sxs-lookup"><span data-stu-id="de624-219">A technique which makes use of a formalized syntax (called **Shape language**) to define a specialized **Recordset** object (called a **shaped Recordset**) that contains not just data, but also references to other **Recordset** objects and/or computed values based on those other **Recordset** objects.</span></span>

<span data-ttu-id="de624-220">**数据源层**</span><span class="sxs-lookup"><span data-stu-id="de624-220">**data source tier**</span></span>

<span data-ttu-id="de624-221">表示运行 DBMS 的计算机 (如 SQL Server 数据库) 的分布式系统的逻辑层。</span><span class="sxs-lookup"><span data-stu-id="de624-221">A logical layer of a distributed system that represents a computer running a DBMS, such as an SQL Server database.</span></span> <span data-ttu-id="de624-222">另请参阅**客户端层**、**中间层**、**分布式应用程序**。</span><span class="sxs-lookup"><span data-stu-id="de624-222">See also **client tier**, **middle tier**, **distributed application**.</span></span>

<span data-ttu-id="de624-223">**封锁**</span><span class="sxs-lookup"><span data-stu-id="de624-223">**DCOM**</span></span>

<span data-ttu-id="de624-224">使 COM 组件能够在网络中彼此直接通信的电线协议。</span><span class="sxs-lookup"><span data-stu-id="de624-224">A wire protocol that enables COM components to communicate directly with each other across a network.</span></span> <span data-ttu-id="de624-225">另请参阅**COM**、**组件**。</span><span class="sxs-lookup"><span data-stu-id="de624-225">See also **COM**, **component**.</span></span>

<span data-ttu-id="de624-226">**DDL (数据定义语言)**</span><span class="sxs-lookup"><span data-stu-id="de624-226">**DDL (Data Definition Language)**</span></span>

<span data-ttu-id="de624-227">SQL 中的那些定义 (而不是操作数据) 的语句。</span><span class="sxs-lookup"><span data-stu-id="de624-227">Those statements in SQL that define, as opposed to manipulate, data.</span></span> <span data-ttu-id="de624-228">使用 DDL 创建或修改数据库的架构。</span><span class="sxs-lookup"><span data-stu-id="de624-228">The schema of a database is created or modified with DDL.</span></span> <span data-ttu-id="de624-229">例如, **create TABLE**、 **create INDEX**、 **GRANT**和**REVOKE**是 SQL DDL 语句。</span><span class="sxs-lookup"><span data-stu-id="de624-229">For example, **CREATE TABLE**, **CREATE INDEX**, **GRANT**, and **REVOKE** are SQL DDL statements.</span></span>

<span data-ttu-id="de624-230">**默认流**</span><span class="sxs-lookup"><span data-stu-id="de624-230">**default stream**</span></span>

<span data-ttu-id="de624-231">在使用某些 OLE db 提供程序 (如用于 Internet 发布的 Microsoft OLE db 提供程序) 时, 与**Record**或**Recordset**对象相关联的文本或二进制流 (由**stream**对象表示)。</span><span class="sxs-lookup"><span data-stu-id="de624-231">A text or binary stream (represented by a **Stream** object) that is associated with **Record** or **Recordset** objects when using certain OLE DB providers, such as the Microsoft OLE DB Provider for Internet Publishing.</span></span> <span data-ttu-id="de624-232">默认流通常包含文件的内容, 如网站的根的 HTML 代码。</span><span class="sxs-lookup"><span data-stu-id="de624-232">The default stream typically contains the contents of a file such as the HTML code for the root of a website.</span></span>

<span data-ttu-id="de624-233">**分布式应用程序**</span><span class="sxs-lookup"><span data-stu-id="de624-233">**distributed application**</span></span>

<span data-ttu-id="de624-234">一种写入的程序, 可在网络中跨多台计算机划分处理。</span><span class="sxs-lookup"><span data-stu-id="de624-234">A program written so that the processing can be divided across multiple computers over a network.</span></span> <span data-ttu-id="de624-235">通常情况下, 分布式应用程序分为演示、业务逻辑和数据存储层或*层*。</span><span class="sxs-lookup"><span data-stu-id="de624-235">Typically, a distributed application is divided into presentation, business logic, and data store layers, or *tiers*.</span></span> <span data-ttu-id="de624-236">另请参阅**客户端层**、**中间层**和**数据源层**。</span><span class="sxs-lookup"><span data-stu-id="de624-236">See also **client tier**, **middle tier**, **data source tier**.</span></span>

<span data-ttu-id="de624-237">**断开连接的 Recordset**</span><span class="sxs-lookup"><span data-stu-id="de624-237">**disconnected Recordset**</span></span>

<span data-ttu-id="de624-238">客户端缓存中的**Recordset**对象, 该对象不再具有到服务器的活动连接。</span><span class="sxs-lookup"><span data-stu-id="de624-238">A **Recordset** object in a client cache that no longer has a live connection to the server.</span></span> <span data-ttu-id="de624-239">如果由于某种原因 (如更新数据) 而需要再次访问原始数据源, 则必须重新建立连接。</span><span class="sxs-lookup"><span data-stu-id="de624-239">If the original data source needs to be accessed again for some reason, such as updating data, the connection must be re-established.</span></span> <span data-ttu-id="de624-240">但是, 仍然可以访问已断开连接的**Recordset**的集合、属性和方法。</span><span class="sxs-lookup"><span data-stu-id="de624-240">However, the collections, properties, and methods of a disconnected **Recordset** can still be accessed.</span></span>

<span data-ttu-id="de624-241">**DLL (动态链接库)**</span><span class="sxs-lookup"><span data-stu-id="de624-241">**DLL (dynamic-link library)**</span></span>

<span data-ttu-id="de624-242">一个文件, 其中包含一个或多个编译、链接和存储与使用它们的进程分开的函数。</span><span class="sxs-lookup"><span data-stu-id="de624-242">A file that contains one or more functions that are compiled, linked, and stored separately from the processes that use them.</span></span> <span data-ttu-id="de624-243">在进程启动时或正在运行时, 操作系统将 dll 映射到调用进程的地址空间。</span><span class="sxs-lookup"><span data-stu-id="de624-243">The operating system maps the DLLs into the address space of the calling process when the process is starting, or while it is running.</span></span>

<span data-ttu-id="de624-244">**DML (数据操作语言)**</span><span class="sxs-lookup"><span data-stu-id="de624-244">**DML (Data Manipulation Language)**</span></span>

<span data-ttu-id="de624-245">SQL 中的那些操作 (与定义数据相对) 的语句。</span><span class="sxs-lookup"><span data-stu-id="de624-245">Those statements in SQL that manipulate, as opposed to define, data.</span></span> <span data-ttu-id="de624-246">将选择数据库中的值, 并使用 DML 修改这些值。</span><span class="sxs-lookup"><span data-stu-id="de624-246">The values in a database are selected and modified with DML.</span></span> <span data-ttu-id="de624-247">例如, **INSERT**、 **UPDATE**、 **DELETE**和**SELECT**是 SQL DML 语句。</span><span class="sxs-lookup"><span data-stu-id="de624-247">For example, **INSERT**, **UPDATE**, **DELETE**, and **SELECT** are SQL DML statements.</span></span>

<span data-ttu-id="de624-248">**文档源提供程序**</span><span class="sxs-lookup"><span data-stu-id="de624-248">**document source provider**</span></span>

<span data-ttu-id="de624-249">管理文件夹和文档的特殊类型的提供程序。</span><span class="sxs-lookup"><span data-stu-id="de624-249">A special class of providers that manage folders and documents.</span></span> <span data-ttu-id="de624-250">当文档由**Record**对象表示, 或文档的文件夹由**Recordset**对象表示时, 文档源提供程序将使用描述文档特征的一组唯一字段填充这些对象。而不是实际的文档本身。</span><span class="sxs-lookup"><span data-stu-id="de624-250">When a document is represented by a **Record** object, or a folder of documents is represented by a **Recordset** object, the document source provider populates those objects with a unique set of fields that describe characteristics of the document, instead of the actual document itself.</span></span> <span data-ttu-id="de624-251">另请参阅**资源记录**。</span><span class="sxs-lookup"><span data-stu-id="de624-251">See also **resource record**.</span></span>

<span data-ttu-id="de624-252">**DSN (数据源名称)**</span><span class="sxs-lookup"><span data-stu-id="de624-252">**DSN (data source name)**</span></span>

<span data-ttu-id="de624-253">用于将应用程序连接到特定 ODBC 数据库的信息的集合。</span><span class="sxs-lookup"><span data-stu-id="de624-253">The collection of information used to connect your application to a particular ODBC database.</span></span> <span data-ttu-id="de624-254">ODBC 驱动程序管理器使用此信息创建与数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="de624-254">The ODBC Driver Manager uses this information to create a connection to the database.</span></span> <span data-ttu-id="de624-255">DSN 可以存储在文件 (文件 DSN) 或 Windows 注册表 (计算机 DSN) 中。</span><span class="sxs-lookup"><span data-stu-id="de624-255">A DSN can be stored in a file (a file DSN) or in the Windows Registry (a machine DSN).</span></span>

<span data-ttu-id="de624-256">**动态属性**</span><span class="sxs-lookup"><span data-stu-id="de624-256">**dynamic property**</span></span>

<span data-ttu-id="de624-257">特定于数据提供程序或游标服务的属性。</span><span class="sxs-lookup"><span data-stu-id="de624-257">A property specific to a data provider or the cursor service.</span></span> <span data-ttu-id="de624-258">对象的**Properties**集合将自动填充 ("动态")。</span><span class="sxs-lookup"><span data-stu-id="de624-258">The **Properties** collection of an object is populated with these automatically ("dynamically").</span></span> <span data-ttu-id="de624-259">在通过特定数据提供程序连接到数据源之前, 对象没有动态属性。</span><span class="sxs-lookup"><span data-stu-id="de624-259">An object has no dynamic properties until it is connected to a data source through a particular data provider.</span></span> <span data-ttu-id="de624-260">另请参阅**数据提供程序**和**游标**。</span><span class="sxs-lookup"><span data-stu-id="de624-260">See also **data provider**, **cursor**.</span></span>

<span data-ttu-id="de624-261">返回顶部</span><span class="sxs-lookup"><span data-stu-id="de624-261">Return to top</span></span>

## <a name="e-i"></a><span data-ttu-id="de624-262">E-I</span><span class="sxs-lookup"><span data-stu-id="de624-262">E-I</span></span>

<span data-ttu-id="de624-263">**枚举**</span><span class="sxs-lookup"><span data-stu-id="de624-263">**enumeration**</span></span>

<span data-ttu-id="de624-264">已命名常量的列表。</span><span class="sxs-lookup"><span data-stu-id="de624-264">A list of named constants.</span></span> <span data-ttu-id="de624-265">枚举值不必是唯一的。</span><span class="sxs-lookup"><span data-stu-id="de624-265">Enumerated values need not be unique.</span></span> <span data-ttu-id="de624-266">但是, 每个值的名称在定义枚举的范围内必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="de624-266">However the name of each value must be unique within the scope where the enumeration is defined.</span></span> <span data-ttu-id="de624-267">在 ADO 中, 枚举用于数值参数和返回值, 用于向 ADO 代码添加含义, 并可从数值中防护开发人员 (可能会因版本而变化)。</span><span class="sxs-lookup"><span data-stu-id="de624-267">In ADO, enumerations are used for numeric parameter and return values, to add meaning to ADO code and to shield the developer from the numeric values (which may change from version to version).</span></span> <span data-ttu-id="de624-268">例如, 若要打开静态**Recordset**, 请使用**adOpenStatic**枚举值:</span><span class="sxs-lookup"><span data-stu-id="de624-268">For example, to open a static **Recordset**, use the **adOpenStatic** enumerated value:</span></span>  
  

<span data-ttu-id="de624-269">也称为 "*枚举常量*"。</span><span class="sxs-lookup"><span data-stu-id="de624-269">Also referred to as *enumerated constant*.</span></span> <span data-ttu-id="de624-270">另请参阅**常量**。</span><span class="sxs-lookup"><span data-stu-id="de624-270">See also **constant**.</span></span>

<span data-ttu-id="de624-271">**event**</span><span class="sxs-lookup"><span data-stu-id="de624-271">**event**</span></span>

<span data-ttu-id="de624-272">由对象识别的操作, 可为其编写代码以进行响应。</span><span class="sxs-lookup"><span data-stu-id="de624-272">An action recognized by an object, for which you can write code to respond.</span></span> <span data-ttu-id="de624-273">事件可以通过命令执行、事务完成、记录集导航和数据更新等其他操作生成。</span><span class="sxs-lookup"><span data-stu-id="de624-273">Events can be generated by command execution, transaction completion, recordset navigation, and data updates, among other actions.</span></span> <span data-ttu-id="de624-274">另请参阅**事件处理程序**。</span><span class="sxs-lookup"><span data-stu-id="de624-274">See also **event handler**.</span></span>

<span data-ttu-id="de624-275">**事件处理程序**</span><span class="sxs-lookup"><span data-stu-id="de624-275">**event handler**</span></span>

<span data-ttu-id="de624-276">事件处理程序是在发生事件时执行的代码。</span><span class="sxs-lookup"><span data-stu-id="de624-276">An event handler is the code that is executed when an event occurs.</span></span> <span data-ttu-id="de624-277">另请参阅**事件**。</span><span class="sxs-lookup"><span data-stu-id="de624-277">See also **event**.</span></span>

<span data-ttu-id="de624-278">**handler**</span><span class="sxs-lookup"><span data-stu-id="de624-278">**handler**</span></span>

<span data-ttu-id="de624-279">管理常见且相对简单的条件或操作 (如错误恢复或数据管理) 的例程。</span><span class="sxs-lookup"><span data-stu-id="de624-279">A routine that manages a common and relatively simple condition or operation, such as error recovery or data management.</span></span>

<span data-ttu-id="de624-280">**分层记录集**</span><span class="sxs-lookup"><span data-stu-id="de624-280">**hierarchical Recordset**</span></span>

<span data-ttu-id="de624-281">包含另一个**recordset**的**recordset** 。</span><span class="sxs-lookup"><span data-stu-id="de624-281">A **Recordset** that contains another **Recordset**.</span></span> <span data-ttu-id="de624-282">另请参阅**数据定形**和**章节**。</span><span class="sxs-lookup"><span data-stu-id="de624-282">See also **data shaping**, **chapter**.</span></span>

<span data-ttu-id="de624-283">有关详细信息, 请参阅[访问分层记录集中的行](accessing-rows-in-a-hierarchical-recordset.md)</span><span class="sxs-lookup"><span data-stu-id="de624-283">For more information, see [Accessing Rows in a Hierarchical Recordset](accessing-rows-in-a-hierarchical-recordset.md)</span></span>

<span data-ttu-id="de624-284">**等级**</span><span class="sxs-lookup"><span data-stu-id="de624-284">**hierarchy**</span></span>

<span data-ttu-id="de624-285">通常情况下, 层次结构是具有顶级级别和从属级别的排名结构。</span><span class="sxs-lookup"><span data-stu-id="de624-285">In general, a hierarchy is a ranked structure with a top level and subordinate levels.</span></span> <span data-ttu-id="de624-286">在 ADO 中, 分层**记录集**用于表示记录和章节之间的父子关系。</span><span class="sxs-lookup"><span data-stu-id="de624-286">In ADO, hierarchical **Recordsets** are used to represent the parent-child relationship between a record and a chapter.</span></span> <span data-ttu-id="de624-287">此外, 在 ADO 中, **Record**和**Stream**对象也可用于访问层次结构树结构, 如文件夹和文档。</span><span class="sxs-lookup"><span data-stu-id="de624-287">Also in ADO, **Record** and **Stream** objects can be used to access hierarchical tree structures such as a folder and documents.</span></span> <span data-ttu-id="de624-288">ADO MD 还包括**层次结构**对象, 以表示 OLAP 多维数据集中的维度级别之间的关系。</span><span class="sxs-lookup"><span data-stu-id="de624-288">ADO MD also includes **Hierarchy** objects to represent a relationship between the levels of a dimension in an OLAP cube.</span></span> <span data-ttu-id="de624-289">另请参阅**分层记录集**、**父-子关系**、**章节**、**树**。</span><span class="sxs-lookup"><span data-stu-id="de624-289">See also **hierarchical Recordsets**, **parent-child relationship**, **chapter**, **tree**.</span></span>

<span data-ttu-id="de624-290">**ISAPI (Internet 服务器应用程序编程接口)**</span><span class="sxs-lookup"><span data-stu-id="de624-290">**ISAPI (Internet Server Application Programming Interface)**</span></span>

<span data-ttu-id="de624-291">一组用于 Internet 服务器的函数, 例如运行 Microsoft Internet information Services (IIS) 的 windows NT server/windows 2000 Server。</span><span class="sxs-lookup"><span data-stu-id="de624-291">A set of functions for Internet servers, such as a Windows NT Server/Windows 2000 Server running Microsoft Internet Information Services (IIS).</span></span>

<span data-ttu-id="de624-292">返回顶部</span><span class="sxs-lookup"><span data-stu-id="de624-292">Return to top</span></span>

## <a name="k-m"></a><span data-ttu-id="de624-293">K-M</span><span class="sxs-lookup"><span data-stu-id="de624-293">K-M</span></span>

<span data-ttu-id="de624-294">**key**</span><span class="sxs-lookup"><span data-stu-id="de624-294">**key**</span></span>

<span data-ttu-id="de624-295">唯一标识行的表中的一个或多个列。通常用于对表编制索引。</span><span class="sxs-lookup"><span data-stu-id="de624-295">A column or columns in a table that uniquely identify a row; often used to index a table.</span></span>

<span data-ttu-id="de624-296">**处理**</span><span class="sxs-lookup"><span data-stu-id="de624-296">**marshaling**</span></span>

<span data-ttu-id="de624-297">跨线程或进程边界对接口方法参数进行打包、发送和 unpackaging 的过程。</span><span class="sxs-lookup"><span data-stu-id="de624-297">The process of packaging, sending, and unpackaging interface method parameters across thread or process boundaries.</span></span>

<span data-ttu-id="de624-298">**中间层**</span><span class="sxs-lookup"><span data-stu-id="de624-298">**middle tier**</span></span>

<span data-ttu-id="de624-299">在用户界面或 web 客户端与数据库之间的分布式系统中的逻辑层。</span><span class="sxs-lookup"><span data-stu-id="de624-299">The logical layer in a distributed system between a user interface or web client and the database.</span></span> <span data-ttu-id="de624-300">这通常是实例化业务对象的地方。</span><span class="sxs-lookup"><span data-stu-id="de624-300">This is typically where business objects are instantiated.</span></span> <span data-ttu-id="de624-301">中间层是在接收信息时生成和运行的业务规则和函数的集合。</span><span class="sxs-lookup"><span data-stu-id="de624-301">The middle tier is a collection of business rules and functions that generate and operate upon receiving information.</span></span> <span data-ttu-id="de624-302">它们通过业务规则 (可能会频繁更改) 实现此目的, 从而封装到物理上与应用程序逻辑本身分开的组件中。</span><span class="sxs-lookup"><span data-stu-id="de624-302">They accomplish this through business rules, which can change frequently, and are thus encapsulated into components that are physically separate from the application logic itself.</span></span> <span data-ttu-id="de624-303">也称为 "*应用程序服务器层*"。</span><span class="sxs-lookup"><span data-stu-id="de624-303">Also known as *application server tier*.</span></span> <span data-ttu-id="de624-304">另请参阅**分布式应用程序**、**客户端层**和**数据源层**。</span><span class="sxs-lookup"><span data-stu-id="de624-304">See also **distributed application**, **client tier**, **data source tier**.</span></span>

<span data-ttu-id="de624-305">**MIME (多用途 Internet 邮件扩展)**</span><span class="sxs-lookup"><span data-stu-id="de624-305">**MIME (Multi-purpose Internet Mail Extension)**</span></span>

<span data-ttu-id="de624-306">最初开发的 Internet 协议, 允许跨异类网络、计算机和电子邮件环境交换具有丰富内容的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="de624-306">An Internet protocol originally developed to allow exchange of electronic mail messages with rich content across heterogeneous network, machine, and email environments.</span></span> <span data-ttu-id="de624-307">实际上, 非邮件应用程序也采用和扩展了 MIME。</span><span class="sxs-lookup"><span data-stu-id="de624-307">In practice, MIME has also been adopted and extended by non-mail applications.</span></span>

<span data-ttu-id="de624-308">MIME 是一项允许在 Internet 上发布和读取二进制数据的标准。</span><span class="sxs-lookup"><span data-stu-id="de624-308">MIME is a standard that allows binary data to be published and read on the Internet.</span></span> <span data-ttu-id="de624-309">包含二进制数据的文件的标头包含数据的 MIME 类型;这会通知客户端程序 (例如, web 浏览器和邮件包) 需要以不同的方式处理数据, 而不是处理直线文本。</span><span class="sxs-lookup"><span data-stu-id="de624-309">The header of a file with binary data contains the MIME type of the data; this informs client programs (web browsers and mail packages, for instance) that they will need to handle the data in a different way than they handle straight text.</span></span> <span data-ttu-id="de624-310">例如, 包含 jpeg 图形的 web 文档的标题包含特定于 jpeg 文件格式的 MIME 类型。</span><span class="sxs-lookup"><span data-stu-id="de624-310">For example, the header of a web document containing a JPEG graphic contains the MIME type specific to the JPEG file format.</span></span> <span data-ttu-id="de624-311">这将允许浏览器显示文件及其 JPEG 查看器 (如果存在)。</span><span class="sxs-lookup"><span data-stu-id="de624-311">This allows a browser to display the file with its JPEG viewer, if one is present.</span></span>

<span data-ttu-id="de624-312">返回顶部</span><span class="sxs-lookup"><span data-stu-id="de624-312">Return to top</span></span>

## <a name="n-o"></a><span data-ttu-id="de624-313">N-O</span><span class="sxs-lookup"><span data-stu-id="de624-313">N-O</span></span>

<span data-ttu-id="de624-314">**节点**</span><span class="sxs-lookup"><span data-stu-id="de624-314">**node**</span></span>

<span data-ttu-id="de624-315">层次结构树结构中的元素。</span><span class="sxs-lookup"><span data-stu-id="de624-315">An element in a hierarchical tree structure.</span></span> <span data-ttu-id="de624-316">一个节点可以是根, 也可以是另一个节点的子级。</span><span class="sxs-lookup"><span data-stu-id="de624-316">A node may be the root, or the child of another node.</span></span> <span data-ttu-id="de624-317">节点也可以是多个子元素的父级。</span><span class="sxs-lookup"><span data-stu-id="de624-317">A node can also be the parent of multiple children.</span></span> <span data-ttu-id="de624-318">另请参阅**层次结构**、**树**、**根**、**子**和**父**。</span><span class="sxs-lookup"><span data-stu-id="de624-318">See also **hierarchy**, **tree**, **root**, **child**, **parent**.</span></span>

<span data-ttu-id="de624-319">**对象变量**</span><span class="sxs-lookup"><span data-stu-id="de624-319">**object variable**</span></span>

<span data-ttu-id="de624-320">包含对象引用的变量。</span><span class="sxs-lookup"><span data-stu-id="de624-320">A variable that contains a reference to an object.</span></span> <span data-ttu-id="de624-321">例如, objCustomObject 是一个指向 CustomObject 类型的对象的变量:</span><span class="sxs-lookup"><span data-stu-id="de624-321">For example, objCustomObject is a variable that points to an object of type CustomObject:</span></span>  
  
<span data-ttu-id="de624-322">是一个指向 CustomObject 类型对象的变量:</span><span class="sxs-lookup"><span data-stu-id="de624-322">is a variable that points to an object of type CustomObject:</span></span>  
  
<span data-ttu-id="de624-323">设置 objCustomObject = CreateObject (adodb。集</span><span class="sxs-lookup"><span data-stu-id="de624-323">Set objCustomObject = CreateObject(adodb.Recordset)</span></span>

<span data-ttu-id="de624-324">**ODBC（开放式数据库连接）**</span><span class="sxs-lookup"><span data-stu-id="de624-324">**ODBC (Open Database Connectivity)**</span></span>

<span data-ttu-id="de624-325">用于连接到各种数据源的标准编程语言接口。</span><span class="sxs-lookup"><span data-stu-id="de624-325">A standard programming language interface used to connect to a variety of data sources.</span></span> <span data-ttu-id="de624-326">这通常通过 "控制面板" 访问, 其中可分配数据源名称 (dsn) 以使用特定的 ODBC 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="de624-326">This is usually accessed through Control Panel, where data source names (DSNs) can be assigned to use specific ODBC drivers.</span></span>

<span data-ttu-id="de624-327">**OLE DB**</span><span class="sxs-lookup"><span data-stu-id="de624-327">**OLE DB**</span></span>

<span data-ttu-id="de624-328">使用 COM 公开各种源中的数据的一组接口。</span><span class="sxs-lookup"><span data-stu-id="de624-328">A set of interfaces that expose data from a variety of sources using COM.</span></span> <span data-ttu-id="de624-329">OLE DB 接口为应用程序提供了对各种信息源中存储的数据的统一访问。</span><span class="sxs-lookup"><span data-stu-id="de624-329">OLE DB interfaces provide applications with uniform access to data stored in diverse information sources.</span></span> <span data-ttu-id="de624-330">这些接口支持与数据源适合的 DBMS 功能的数量, 使其可以共享其数据。</span><span class="sxs-lookup"><span data-stu-id="de624-330">These interfaces support the amount of DBMS functionality appropriate to the data source, enabling it to share its data.</span></span> <span data-ttu-id="de624-331">另请参阅**COM**。</span><span class="sxs-lookup"><span data-stu-id="de624-331">See also **COM**.</span></span>

<span data-ttu-id="de624-332">**乐观锁定**</span><span class="sxs-lookup"><span data-stu-id="de624-332">**optimistic locking**</span></span>

<span data-ttu-id="de624-333">一种锁定类型, 其中包含一个或多个记录 (包括正在编辑的记录) 的数据页面, 只有在使用**update**方法更新记录时, 其他用户才能使用该锁定, 但在调用**更新**之前和之后都可以使用它们。.</span><span class="sxs-lookup"><span data-stu-id="de624-333">A type of locking in which the data page containing one or more records, including the record being edited, is unavailable to other users only while the record is being updated by the **Update** method, but is available before and after the call to **Update**.</span></span>

<span data-ttu-id="de624-334">当使用**LockType**参数或属性设置为**adLockOptimistic**或**adLockBatchOptimistic**, 打开**Recordset**对象时, 将使用开放式锁定。</span><span class="sxs-lookup"><span data-stu-id="de624-334">Optimistic locking is used when the **Recordset** object is opened with the **LockType** parameter or property set to **adLockOptimistic** or **adLockBatchOptimistic**.</span></span> <span data-ttu-id="de624-335">另请参阅**保守锁定**。</span><span class="sxs-lookup"><span data-stu-id="de624-335">See also **pessimistic locking**.</span></span>

<span data-ttu-id="de624-336">**序号值**</span><span class="sxs-lookup"><span data-stu-id="de624-336">**ordinal value**</span></span>

<span data-ttu-id="de624-337">项目在订单中的数值位置。</span><span class="sxs-lookup"><span data-stu-id="de624-337">The numeric location of an item within an order.</span></span> <span data-ttu-id="de624-338">在 ADO 集合中, 第一项的序号值为零 (0)。</span><span class="sxs-lookup"><span data-stu-id="de624-338">In an ADO collection, the ordinal value of the first item is zero (0).</span></span> <span data-ttu-id="de624-339">下一项为一 (1), 依此类推。</span><span class="sxs-lookup"><span data-stu-id="de624-339">The next item is one (1), and so on.</span></span>

<span data-ttu-id="de624-340">返回顶部</span><span class="sxs-lookup"><span data-stu-id="de624-340">Return to top</span></span>

## <a name="p"></a><span data-ttu-id="de624-341">P</span><span class="sxs-lookup"><span data-stu-id="de624-341">P</span></span>

<span data-ttu-id="de624-342">**参数化命令**</span><span class="sxs-lookup"><span data-stu-id="de624-342">**parameterized command**</span></span>

<span data-ttu-id="de624-343">允许您在执行命令前设置参数值的查询或命令。</span><span class="sxs-lookup"><span data-stu-id="de624-343">A query or command that allows you to set parameter values before the command is executed.</span></span> <span data-ttu-id="de624-344">例如, 可以通过在 sql 字符串中嵌入参数标记 (由 '？ ' 字符指定) 来参数化 sql 字符串。</span><span class="sxs-lookup"><span data-stu-id="de624-344">For example, a SQL string can be parameterized by embedding parameter markers in the SQL string (designated by the '?' character).</span></span> <span data-ttu-id="de624-345">然后, 应用程序为每个参数指定值并执行命令。</span><span class="sxs-lookup"><span data-stu-id="de624-345">The application then specifies values for each parameter and executes the command.</span></span>

<span data-ttu-id="de624-346">**母语**</span><span class="sxs-lookup"><span data-stu-id="de624-346">**parent**</span></span>

<span data-ttu-id="de624-347">层次结构关系的控制侧。</span><span class="sxs-lookup"><span data-stu-id="de624-347">The controlling side of a hierarchical relationship.</span></span> <span data-ttu-id="de624-348">在层次结构中, 父节点在层次结构中直接在其下方包含一个或多个子节点。</span><span class="sxs-lookup"><span data-stu-id="de624-348">In a hierarchical structure, a parent has one or more child nodes directly beneath it in the hierarchy.</span></span> <span data-ttu-id="de624-349">另请参阅**父别名**、**父-子关系**和**子级**。</span><span class="sxs-lookup"><span data-stu-id="de624-349">See also **parent-alias**, **parent-child relationship**, **child**.</span></span>

<span data-ttu-id="de624-350">**parent-alias**</span><span class="sxs-lookup"><span data-stu-id="de624-350">**parent-alias**</span></span>

<span data-ttu-id="de624-351">引用父项的别名。</span><span class="sxs-lookup"><span data-stu-id="de624-351">An alias that refers to the parent.</span></span> <span data-ttu-id="de624-352">另请参阅**别名**和**父**。</span><span class="sxs-lookup"><span data-stu-id="de624-352">See also **alias**, **parent**.</span></span>

<span data-ttu-id="de624-353">**父子关系**</span><span class="sxs-lookup"><span data-stu-id="de624-353">**parent-child relationship**</span></span>

<span data-ttu-id="de624-354">层次结构中的一个关系, 其中的父级的级别较高, 与一个或多个子项直接关联。</span><span class="sxs-lookup"><span data-stu-id="de624-354">A relationship in a hierarchical structure in which the parent is one level higher and directly associated with one or more children.</span></span> <span data-ttu-id="de624-355">子级的级别低于一个级别, 并且必须具有一个父项。</span><span class="sxs-lookup"><span data-stu-id="de624-355">A child is one level lower and must have one parent.</span></span> <span data-ttu-id="de624-356">另请参阅**parent**、 **child**。</span><span class="sxs-lookup"><span data-stu-id="de624-356">See also **parent**, **child**.</span></span>

<span data-ttu-id="de624-357">**下来**</span><span class="sxs-lookup"><span data-stu-id="de624-357">**persist**</span></span>

<span data-ttu-id="de624-358">将数据保存为永久性状态, 如将**Recordset**保存到文件中。</span><span class="sxs-lookup"><span data-stu-id="de624-358">To save data in a permanent state, such as saving a **Recordset** to a file.</span></span>

<span data-ttu-id="de624-359">**保守式锁定**</span><span class="sxs-lookup"><span data-stu-id="de624-359">**pessimistic locking**</span></span>

<span data-ttu-id="de624-360">一种锁定类型, 其中包含一个或多个记录 (包括正在编辑的记录) 的页面对其他用户不可用, 以确保将进行更新。</span><span class="sxs-lookup"><span data-stu-id="de624-360">A type of locking in which the page containing one or more records, including the record being edited, is unavailable to other users to ensure that an update will be made.</span></span> <span data-ttu-id="de624-361">保守式锁定行为由 OLE DB 提供程序定义。</span><span class="sxs-lookup"><span data-stu-id="de624-361">Pessimistic locking behavior is defined by the OLE DB provider.</span></span> <span data-ttu-id="de624-362">通常情况下, 记录在编辑时处于锁定状态, 并且在**更新**方法完成前仍不可用。</span><span class="sxs-lookup"><span data-stu-id="de624-362">Typically, records are locked upon editing and remain unavailable until the **Update** method has completed.</span></span>

<span data-ttu-id="de624-363">当使用**LockType**参数或属性设置为**adLockPessimistic**时, 打开**Recordset**对象时, 将启用保守式锁定。</span><span class="sxs-lookup"><span data-stu-id="de624-363">Pessimistic locking is enabled when the **Recordset** object is opened with the **LockType** parameter or property set to **adLockPessimistic**.</span></span> <span data-ttu-id="de624-364">另请参阅**开放式锁定**。</span><span class="sxs-lookup"><span data-stu-id="de624-364">See also **optimistic locking**.</span></span>

<span data-ttu-id="de624-365">**处理**</span><span class="sxs-lookup"><span data-stu-id="de624-365">**pooling**</span></span>

<span data-ttu-id="de624-366">基于预分配资源的集合 (如对象或数据库连接) 的性能优化。</span><span class="sxs-lookup"><span data-stu-id="de624-366">A performance optimization based on using collections of pre-allocated resources, such as objects or database connections.</span></span> <span data-ttu-id="de624-367">从池 (而不是创建新资源) 中绘制现有资源效率更高。</span><span class="sxs-lookup"><span data-stu-id="de624-367">It is more efficient to draw an existing resource from the pool than to create a new resource.</span></span>

<span data-ttu-id="de624-368">**ProgID (编程标识符)**</span><span class="sxs-lookup"><span data-stu-id="de624-368">**ProgID (programmatic identifier)**</span></span>

<span data-ttu-id="de624-369">一个由 COM 应用程序映射到 Windows 注册表的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="de624-369">A unique name mapped to the Windows registry by a COM application.</span></span> <span data-ttu-id="de624-370">ADO 连接的 ProgID 是 "ADODB"。Connection "。</span><span class="sxs-lookup"><span data-stu-id="de624-370">The ProgID for an ADO Connection is "ADODB.Connection".</span></span> <span data-ttu-id="de624-371">另请参阅**CLSID**、 **COM**。</span><span class="sxs-lookup"><span data-stu-id="de624-371">See also **CLSID**, **COM**.</span></span>

<span data-ttu-id="de624-372">**代理**</span><span class="sxs-lookup"><span data-stu-id="de624-372">**proxy**</span></span>

<span data-ttu-id="de624-373">特定于接口的对象, 提供客户端调用在不同的执行环境中运行的应用程序对象 (如在不同的线程上或在另一个进程中) 时所需的参数封送和通信。</span><span class="sxs-lookup"><span data-stu-id="de624-373">An interface-specific object that provides the parameter marshaling and communication required for a client to call an application object that is running in a different execution environment, such as on a different thread or in another process.</span></span> <span data-ttu-id="de624-374">代理与客户端进行通信, 并与与被调用的 application 对象位于一起的相应存根进行通信。</span><span class="sxs-lookup"><span data-stu-id="de624-374">The proxy is located with the client and communicates with a corresponding stub that is located with the application object that is being called.</span></span> <span data-ttu-id="de624-375">另请参阅**存根**。</span><span class="sxs-lookup"><span data-stu-id="de624-375">See also **stub**.</span></span>

<span data-ttu-id="de624-376">返回顶部</span><span class="sxs-lookup"><span data-stu-id="de624-376">Return to top</span></span>

## <a name="r"></a><span data-ttu-id="de624-377">R</span><span class="sxs-lookup"><span data-stu-id="de624-377">R</span></span>

<span data-ttu-id="de624-378">**相对 URL**</span><span class="sxs-lookup"><span data-stu-id="de624-378">**relative URL**</span></span>

<span data-ttu-id="de624-379">指定 Internet 或 intranet 上的资源的部分限定的 URL, 其位置相对于绝对 URL 或等效 ADO Connection 对象指定的起始点。</span><span class="sxs-lookup"><span data-stu-id="de624-379">A partially qualified URL that specifies a resource on the Internet or an intranet whose location is relative to a starting point specified by an absolute URL or equivalent ADO Connection object.</span></span> <span data-ttu-id="de624-380">实际上, 串联的绝对 url 和相对 url consitute 完整的 url。</span><span class="sxs-lookup"><span data-stu-id="de624-380">In effect, the concatenated absolute and relative URLs consitute a complete URL.</span></span> <span data-ttu-id="de624-381">另请参阅**url**和**绝对 URL**。</span><span class="sxs-lookup"><span data-stu-id="de624-381">See also **URL** and **absolute URL**.</span></span>

<span data-ttu-id="de624-382">**远程数据源**</span><span class="sxs-lookup"><span data-stu-id="de624-382">**remote data source**</span></span>

<span data-ttu-id="de624-383">在另一台计算机上, 而不是在本地系统 (客户端应用程序运行的位置) 上存在的数据源。</span><span class="sxs-lookup"><span data-stu-id="de624-383">A data source that exists on a another computer, rather than on the local system (where the client application runs).</span></span>

<span data-ttu-id="de624-384">**资源记录**</span><span class="sxs-lookup"><span data-stu-id="de624-384">**resource record**</span></span>

<span data-ttu-id="de624-385">文档源提供程序中的一条记录, 其中包含文件夹或文档的定义和说明的字段。</span><span class="sxs-lookup"><span data-stu-id="de624-385">A record from a document source provider that contains fields for the definition and description of a folder or document.</span></span> <span data-ttu-id="de624-386">文档本身并不包含在资源记录中, 但通常可以通过默认流或包含 URL 的资源记录中的字段进行访问。</span><span class="sxs-lookup"><span data-stu-id="de624-386">The document itself is not contained in the resource record but typically can be accessed by the default stream or a field in the resource record containing a URL.</span></span> <span data-ttu-id="de624-387">另请参阅**文档源提供程序**、**默认流**和**URL**。</span><span class="sxs-lookup"><span data-stu-id="de624-387">See also **document source provider**, **default stream**, **URL**.</span></span>

<span data-ttu-id="de624-388">**root**</span><span class="sxs-lookup"><span data-stu-id="de624-388">**root**</span></span>

<span data-ttu-id="de624-389">层次结构树结构中的顶层。</span><span class="sxs-lookup"><span data-stu-id="de624-389">The top level in a hierarchical tree structure.</span></span> <span data-ttu-id="de624-390">根节点没有父节点, 但可能有子项。</span><span class="sxs-lookup"><span data-stu-id="de624-390">The root node has no parents, but may have children.</span></span> <span data-ttu-id="de624-391">另请参阅**层次结构**、**树**、**父级**和**子级**。</span><span class="sxs-lookup"><span data-stu-id="de624-391">See also **hierarchy**, **tree**, **parent**, **child**.</span></span>

<span data-ttu-id="de624-392">**rowset**</span><span class="sxs-lookup"><span data-stu-id="de624-392">**rowset**</span></span>

<span data-ttu-id="de624-393">数据源中的一组行, 所有这些行都具有相同的字段架构。</span><span class="sxs-lookup"><span data-stu-id="de624-393">A set of rows from a data source, all having the same field schema.</span></span> <span data-ttu-id="de624-394">一个行集可以表示表中的所有字段或部分字段。</span><span class="sxs-lookup"><span data-stu-id="de624-394">A rowset can represent all or some fields from a table.</span></span> <span data-ttu-id="de624-395">行集还可以表示由查询或两个或更多表的联接创建的虚拟表。</span><span class="sxs-lookup"><span data-stu-id="de624-395">A rowset can also represent a virtual table, created by a query or a join of two or more tables.</span></span> <span data-ttu-id="de624-396">在 ADO 中, 行集由**Recordset**对象表示。</span><span class="sxs-lookup"><span data-stu-id="de624-396">In ADO, rowsets are represented by **Recordset** objects.</span></span>

<span data-ttu-id="de624-397">返回顶部</span><span class="sxs-lookup"><span data-stu-id="de624-397">Return to top</span></span>

## <a name="s"></a><span data-ttu-id="de624-398">S</span><span class="sxs-lookup"><span data-stu-id="de624-398">S</span></span>

<span data-ttu-id="de624-399">**架构**</span><span class="sxs-lookup"><span data-stu-id="de624-399">**schema**</span></span>

<span data-ttu-id="de624-400">数据库管理系统 (DBMS) 的数据库说明, 通常使用 DBMS 提供的数据定义语言生成。</span><span class="sxs-lookup"><span data-stu-id="de624-400">A description of a database to the database management system (DBMS), typically generated using the data definition language provided by the DBMS.</span></span> <span data-ttu-id="de624-401">架构定义数据库的属性, 如表、列和属性。</span><span class="sxs-lookup"><span data-stu-id="de624-401">A schema defines attributes of the database, such as tables, columns, and properties.</span></span>

<span data-ttu-id="de624-402">**scope**</span><span class="sxs-lookup"><span data-stu-id="de624-402">**scope**</span></span>

<span data-ttu-id="de624-403">对象或变量的引用范围或视图或表中的记录范围。</span><span class="sxs-lookup"><span data-stu-id="de624-403">The range of reference for an object or variable or a range of records in a view or table.</span></span> <span data-ttu-id="de624-404">例如, 只能在定义局部变量的过程中引用这些变量。</span><span class="sxs-lookup"><span data-stu-id="de624-404">For example, local variables can be referenced only within the procedure in which they were defined.</span></span> <span data-ttu-id="de624-405">公共变量可从应用程序中的任何位置访问。</span><span class="sxs-lookup"><span data-stu-id="de624-405">Public variables are accessible from anywhere in the application.</span></span> <span data-ttu-id="de624-406">如果对象位于定义的搜索路径中, 则这些对象 (如当前数据库) 在范围内。</span><span class="sxs-lookup"><span data-stu-id="de624-406">Objects, such as the current database, are in scope if they are in the defined search path.</span></span> <span data-ttu-id="de624-407">在许多命令中, 可以使用 Scope 子句指定记录范围。</span><span class="sxs-lookup"><span data-stu-id="de624-407">Record ranges can be specified with a Scope clause in many commands.</span></span>

<span data-ttu-id="de624-408">**服务提供程序**</span><span class="sxs-lookup"><span data-stu-id="de624-408">**service provider**</span></span>

<span data-ttu-id="de624-409">通过生成和使用数据以及在 ADO 应用程序中补充功能来封装服务的软件。</span><span class="sxs-lookup"><span data-stu-id="de624-409">Software that encapsulates a service by producing and consuming data, augmenting features in your ADO applications.</span></span> <span data-ttu-id="de624-410">它是一个不直接公开数据的提供程序, 而是提供一种服务, 例如查询处理。</span><span class="sxs-lookup"><span data-stu-id="de624-410">It is a provider that does not directly expose data, rather it provides a service, such as query processing.</span></span> <span data-ttu-id="de624-411">服务提供程序可能会处理由数据提供程序提供的数据。</span><span class="sxs-lookup"><span data-stu-id="de624-411">The service provider may process data provided by a data provider.</span></span> <span data-ttu-id="de624-412">另请参阅**data provider**。</span><span class="sxs-lookup"><span data-stu-id="de624-412">See also **data provider**.</span></span>

<span data-ttu-id="de624-413">**整形 Recordset**</span><span class="sxs-lookup"><span data-stu-id="de624-413">**shaped Recordset**</span></span>

<span data-ttu-id="de624-414">一种**Recordset** , 其列已明确定义为仅包含数据, 还包含对其他**recordset**对象和/或基于其他**recordset**对象的计算值的引用 (称为 "章节")。</span><span class="sxs-lookup"><span data-stu-id="de624-414">A **Recordset** whose columns have been specifically defined to contain not just data, but also references (called chapters) to other **Recordset** objects and/or computed values based on other **Recordset** objects.</span></span>

<span data-ttu-id="de624-415">**同辈**</span><span class="sxs-lookup"><span data-stu-id="de624-415">**sibling**</span></span>

<span data-ttu-id="de624-416">层次结构中相同级别上的任意两个或更多个节点。</span><span class="sxs-lookup"><span data-stu-id="de624-416">Any two or more nodes in a hierarchical structure that are on the same level in the hierarchy.</span></span> <span data-ttu-id="de624-417">层次结构中的根节点没有同级。</span><span class="sxs-lookup"><span data-stu-id="de624-417">The root node in a hierarchy has no siblings.</span></span>

<span data-ttu-id="de624-418">**存储过程**</span><span class="sxs-lookup"><span data-stu-id="de624-418">**stored procedure**</span></span>

<span data-ttu-id="de624-419">代码的预编译集合, 如 SQL 语句和可选的控制流语句, 它们存储在一个名称下并作为一个单元处理。</span><span class="sxs-lookup"><span data-stu-id="de624-419">A precompiled collection of code such as SQL statements and optional control-of-flow statements stored under a name and processed as a unit.</span></span> <span data-ttu-id="de624-420">存储过程存储在数据库中;可以使用来自应用程序的一个调用来执行这些操作, 并允许用户声明的变量、条件执行和其他功能强大的编程功能。</span><span class="sxs-lookup"><span data-stu-id="de624-420">Stored procedures are stored within a database; they can be executed with one call from an application and allow user-declared variables, conditional execution, and other powerful programming features.</span></span>

<span data-ttu-id="de624-421">**根**</span><span class="sxs-lookup"><span data-stu-id="de624-421">**stub**</span></span>

<span data-ttu-id="de624-422">特定于接口的对象, 提供应用程序对象从运行在不同的执行环境中的客户端 (例如, 在不同的线程上或在另一个进程中) 中接收调用所需的参数封送和通信。</span><span class="sxs-lookup"><span data-stu-id="de624-422">An interface-specific object that provides the parameter marshaling and communication required for an application object to receive calls from a client that is running in a different execution environment, such as on a different thread or in another process.</span></span> <span data-ttu-id="de624-423">存根与 application 对象放置在一起, 并与调用它的客户端上的相应代理进行通信。</span><span class="sxs-lookup"><span data-stu-id="de624-423">The stub is located with the application object and communicates with a corresponding proxy that is located with the client that calls it.</span></span> <span data-ttu-id="de624-424">另请参阅**proxy**。</span><span class="sxs-lookup"><span data-stu-id="de624-424">See also **proxy**.</span></span>

<span data-ttu-id="de624-425">**子节点**</span><span class="sxs-lookup"><span data-stu-id="de624-425">**sub-node**</span></span>

<span data-ttu-id="de624-426">请参阅**子级**。</span><span class="sxs-lookup"><span data-stu-id="de624-426">See **child**.</span></span>

<span data-ttu-id="de624-427">**同步操作**</span><span class="sxs-lookup"><span data-stu-id="de624-427">**synchronous operation**</span></span>

<span data-ttu-id="de624-428">由代码启动的操作, 在下一操作可能开始之前完成。</span><span class="sxs-lookup"><span data-stu-id="de624-428">An operation initiated by code that completes before the next operation may start.</span></span> <span data-ttu-id="de624-429">另请参阅**异步操作**。</span><span class="sxs-lookup"><span data-stu-id="de624-429">See also **asynchronous operation**.</span></span>

<span data-ttu-id="de624-430">返回顶部</span><span class="sxs-lookup"><span data-stu-id="de624-430">Return to top</span></span>

## <a name="t-w"></a><span data-ttu-id="de624-431">T W</span><span class="sxs-lookup"><span data-stu-id="de624-431">T-W</span></span>

<span data-ttu-id="de624-432">**树**</span><span class="sxs-lookup"><span data-stu-id="de624-432">**tree**</span></span>

<span data-ttu-id="de624-433">一个表示元素 (节点) 之间的层次结构关系的结构。</span><span class="sxs-lookup"><span data-stu-id="de624-433">A structure representing a hierarchical relationship between elements (nodes).</span></span> <span data-ttu-id="de624-434">树的顶层有一个节点 (根)。</span><span class="sxs-lookup"><span data-stu-id="de624-434">There is one node at the top level of a tree (the root).</span></span> <span data-ttu-id="de624-435">在根下, 可以有多个子级。</span><span class="sxs-lookup"><span data-stu-id="de624-435">Underneath the root, there can be multiple children.</span></span> <span data-ttu-id="de624-436">每个子项又可能是其他子级的父项, 因此像树这样的分支。</span><span class="sxs-lookup"><span data-stu-id="de624-436">Each child may in turn be the parent of other children, thus branching like a tree.</span></span> <span data-ttu-id="de624-437">包含文档和其他文件夹的文件夹是树状结构的典型示例。</span><span class="sxs-lookup"><span data-stu-id="de624-437">A folder containing documents and other folders is a typical example of a tree structure.</span></span> <span data-ttu-id="de624-438">另请参阅**层次结构**、**节点**、**根**、**子**和**父**。</span><span class="sxs-lookup"><span data-stu-id="de624-438">See also **hierarchy**, **node**, **root**, **child**, **parent**.</span></span>

<span data-ttu-id="de624-439">**URL (统一资源定位器)**</span><span class="sxs-lookup"><span data-stu-id="de624-439">**URL (Uniform Resource Locator)**</span></span>

<span data-ttu-id="de624-440">指定驻留在 Internet 或 intranet 上的资源的位置。</span><span class="sxs-lookup"><span data-stu-id="de624-440">Specifies the location of a resource residing on the Internet or an intranet.</span></span> <span data-ttu-id="de624-441">完整的 URL 包含一个方案 (如 FTP、HTTP、mailto、文件等), 后跟冒号、服务器名称和资源的完整路径 (如文档、图形或其他文件)。</span><span class="sxs-lookup"><span data-stu-id="de624-441">A complete URL consists of a scheme (such as FTP, HTTP, mailto, file, and so on), followed by a colon, a server name, and the full path of a resource (such as a document, graphic, or other file).</span></span> <span data-ttu-id="de624-442">url 的一些示例如下:</span><span class="sxs-lookup"><span data-stu-id="de624-442">Some examples of URLs are:</span></span>  
  
- https://www.domain.com/default.html  
- <span data-ttu-id="de624-443">ftp://ftp.server.somewhere/ftp.file</span><span class="sxs-lookup"><span data-stu-id="de624-443">ftp://ftp.server.somewhere/ftp.file</span></span>  
  
- <span data-ttu-id="de624-444">ftp://ftp.server.somewhere/ftp.file</span><span class="sxs-lookup"><span data-stu-id="de624-444">ftp://ftp.server.somewhere/ftp.file</span></span>  
- <span data-ttu-id="de624-445">file://Server/Share/File.doc</span><span class="sxs-lookup"><span data-stu-id="de624-445">file://Server/Share/File.doc</span></span>

<span data-ttu-id="de624-446">另请参阅**绝对 url**和**相对 url**。</span><span class="sxs-lookup"><span data-stu-id="de624-446">See also **absolute URL** and **relative URL**.</span></span>

<span data-ttu-id="de624-447">**web 服务器**</span><span class="sxs-lookup"><span data-stu-id="de624-447">**web server**</span></span>

<span data-ttu-id="de624-448">向 intranet 和 Internet 用户提供 web 服务和页面的计算机。</span><span class="sxs-lookup"><span data-stu-id="de624-448">A computer that provides web services and pages to intranet and Internet users.</span></span>



