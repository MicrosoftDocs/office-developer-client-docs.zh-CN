---
title: ActiveX 数据对象 (ADO) 术语表
TOCTitle: ADO Glossary
ms:assetid: 40f00876-7525-4117-8f57-f3d87c54be99
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249184(v=office.15)
ms:contentKeyID: 48544438
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d991da62a8820db3506059e81d136208cca73db3
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25607058"
---
# <a name="ado-glossary"></a><span data-ttu-id="0880c-102">ADO 术语表</span><span class="sxs-lookup"><span data-stu-id="0880c-102">ADO Glossary</span></span>

<span data-ttu-id="0880c-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="0880c-103">**Applies to**: Access 2013 | Office 2013</span></span>

## <a name="a"></a><span data-ttu-id="0880c-104">A</span><span class="sxs-lookup"><span data-stu-id="0880c-104">A</span></span>

<span data-ttu-id="0880c-105">**绝对 URL**</span><span class="sxs-lookup"><span data-stu-id="0880c-105">**absolute URL**</span></span>

<span data-ttu-id="0880c-106">Internet 或 intranet 指定的资源的所在位置的完全限定的 URL。</span><span class="sxs-lookup"><span data-stu-id="0880c-106">A fully qualified URL that specifies the location of a resource that resides on the Internet or an intranet.</span></span> <span data-ttu-id="0880c-107">请参阅**URL**和**相对 URL**。</span><span class="sxs-lookup"><span data-stu-id="0880c-107">See also **URL** and **relative URL**.</span></span>

<span data-ttu-id="0880c-108">**ActiveX 控件**</span><span class="sxs-lookup"><span data-stu-id="0880c-108">**ActiveX control**</span></span>

<span data-ttu-id="0880c-109">自注册，进程内通常具有 visual 元素在设计时或运行的时的 COM 组件。</span><span class="sxs-lookup"><span data-stu-id="0880c-109">Self-registering, in-process COM component that often has a visual element either at design time or run time.</span></span> <span data-ttu-id="0880c-110">ActiveX 控件还能够与活动文档容器，如 Microsoft Internet Explorer 进行通信。</span><span class="sxs-lookup"><span data-stu-id="0880c-110">ActiveX controls also have the ability to communicate with an Active Document container, such as Microsoft Internet Explorer.</span></span>

<span data-ttu-id="0880c-111">**ADISAPI （高级数据 Internet 服务器应用程序编程接口）**</span><span class="sxs-lookup"><span data-stu-id="0880c-111">**ADISAPI (Advanced Data Internet Server Application Programming Interface)**</span></span>

<span data-ttu-id="0880c-112">ISAPI DLL 提供分析、 自动化控件、 **Recordset**封送，和 MIME 打包。</span><span class="sxs-lookup"><span data-stu-id="0880c-112">An ISAPI DLL that provides parsing, Automation control, **Recordset** marshaling, and MIME packaging.</span></span> <span data-ttu-id="0880c-113">ADISAPI 组件适用于通过提供 Internet 信息服务 (IIS) API。</span><span class="sxs-lookup"><span data-stu-id="0880c-113">The ADISAPI component works through the API provided by Internet Information Services (IIS).</span></span> <span data-ttu-id="0880c-114">请参阅**ISAPI**。</span><span class="sxs-lookup"><span data-stu-id="0880c-114">See also **ISAPI**.</span></span>

<span data-ttu-id="0880c-115">**聚合函数**</span><span class="sxs-lookup"><span data-stu-id="0880c-115">**aggregate function**</span></span>

<span data-ttu-id="0880c-116">在查询中，如 COUNT、 AVG 或 STDEV 的计算值表的列中使用的所有行的函数。</span><span class="sxs-lookup"><span data-stu-id="0880c-116">In a query, a function such as COUNT, AVG, or STDEV that calculates a value using all the rows in a column of a table.</span></span> <span data-ttu-id="0880c-117">在编写表达式和编程中，您可以使用 SQL 聚合函数 （包括上面列出的三个） 和域聚合函数来确定各种统计信息。</span><span class="sxs-lookup"><span data-stu-id="0880c-117">In writing expressions and in programming, you can use SQL aggregate functions (including the three listed above) and domain aggregate functions to determine various statistics.</span></span>

<span data-ttu-id="0880c-118">**alias**</span><span class="sxs-lookup"><span data-stu-id="0880c-118">**alias**</span></span>

<span data-ttu-id="0880c-119">授予对列或表达式中的 SQL SELECT 语句，通常较短或更有意义的替代名称。</span><span class="sxs-lookup"><span data-stu-id="0880c-119">An alternate name you give to a column or expression in an SQL SELECT statement, often shorter or more meaningful.</span></span> <span data-ttu-id="0880c-120">例如，BobSales 是以下的 SELECT 语句中的别名:"以从 SalesDB BobSales 选择 wr 销售"。</span><span class="sxs-lookup"><span data-stu-id="0880c-120">For example, BobSales is the alias in the following SELECT statement: "Select wr-Sales as BobSales from SalesDB".</span></span> <span data-ttu-id="0880c-121">别名可用于动态分配要控制在**DataControl**对象的绑定列。</span><span class="sxs-lookup"><span data-stu-id="0880c-121">An alias can be used to dynamically assign columns to control bindings on the **DataControl** object.</span></span>

<span data-ttu-id="0880c-122">**单元线程**</span><span class="sxs-lookup"><span data-stu-id="0880c-122">**apartment threading**</span></span>

<span data-ttu-id="0880c-123">线程的模型其中对对象的所有呼叫都发生在一个线程 COM。</span><span class="sxs-lookup"><span data-stu-id="0880c-123">A COM threading model where all calls to an object occur on one thread.</span></span> <span data-ttu-id="0880c-124">在单元线程，COM 同步，并将封送呼叫。</span><span class="sxs-lookup"><span data-stu-id="0880c-124">In apartment threading, COM synchronizes and marshals calls.</span></span> <span data-ttu-id="0880c-125">另请参阅**COM**。</span><span class="sxs-lookup"><span data-stu-id="0880c-125">See also **COM**.</span></span>

<span data-ttu-id="0880c-126">**异步操作**</span><span class="sxs-lookup"><span data-stu-id="0880c-126">**asynchronous operation**</span></span>

<span data-ttu-id="0880c-127">返回到调用程序控件，而无需等待操作完成操作。</span><span class="sxs-lookup"><span data-stu-id="0880c-127">An operation that returns control to the calling program without waiting for the operation to complete.</span></span> <span data-ttu-id="0880c-128">操作已完成之前，请继续执行代码。</span><span class="sxs-lookup"><span data-stu-id="0880c-128">Before the operation is complete, code execution continues.</span></span> <span data-ttu-id="0880c-129">请参阅**同步操作**。</span><span class="sxs-lookup"><span data-stu-id="0880c-129">See also **synchronous operation**.</span></span>

<span data-ttu-id="0880c-130">返回顶部</span><span class="sxs-lookup"><span data-stu-id="0880c-130">Return to top</span></span>

## <a name="b"></a><span data-ttu-id="0880c-131">B</span><span class="sxs-lookup"><span data-stu-id="0880c-131">B</span></span>

<span data-ttu-id="0880c-132">**绑定项**</span><span class="sxs-lookup"><span data-stu-id="0880c-132">**binding entry**</span></span>

<span data-ttu-id="0880c-133">表中的字段和变量之间的映射。</span><span class="sxs-lookup"><span data-stu-id="0880c-133">A mapping between a field in a table and a variable.</span></span> <span data-ttu-id="0880c-134">在 Visual c + + 的 ADO 扩展， **Recordset**字段映射到 C/c + + 变量。</span><span class="sxs-lookup"><span data-stu-id="0880c-134">In the ADO Visual C++ extensions, **Recordset** fields are mapped to C/C++ variables.</span></span>

<span data-ttu-id="0880c-135">**位掩码**</span><span class="sxs-lookup"><span data-stu-id="0880c-135">**bitmask**</span></span>

<span data-ttu-id="0880c-136">一个数值，它适用于与其他数值，由位值比较通常要标记参数或返回值中的选项。</span><span class="sxs-lookup"><span data-stu-id="0880c-136">A numeric value intended for a bit-by-bit value comparison with other numeric values, typically to flag options in parameter or return values.</span></span> <span data-ttu-id="0880c-137">通常使用按位的逻辑运算符，如**And**和**或**在 Visual Basic 中，执行此比较**&** 和**|** c + + 中。</span><span class="sxs-lookup"><span data-stu-id="0880c-137">Usually this comparison is done with bitwise logical operators, such as **And** and **Or** in Visual Basic, **&** and **|** in C++.</span></span>

<span data-ttu-id="0880c-138">例如，ADO **FieldAttributeEnum**值可为位掩码来确定字段的属性。</span><span class="sxs-lookup"><span data-stu-id="0880c-138">For example, the ADO **FieldAttributeEnum** values can be used as bitmasks to determine the attributes of a field.</span></span> <span data-ttu-id="0880c-139">假设您要确定是否可更新字段。</span><span class="sxs-lookup"><span data-stu-id="0880c-139">Suppose you wanted to determine if a field was updateable.</span></span> <span data-ttu-id="0880c-140">使用以下表达式在 Visual Basic 中，您无法为此测试：</span><span class="sxs-lookup"><span data-stu-id="0880c-140">You could test for this with the following expression in Visual Basic:</span></span>  
  

<span data-ttu-id="0880c-141">如果结果为 TRUE，则可更新字段。</span><span class="sxs-lookup"><span data-stu-id="0880c-141">If the result is TRUE, then the field is updateable.</span></span>

<span data-ttu-id="0880c-142">**bookmark**</span><span class="sxs-lookup"><span data-stu-id="0880c-142">**bookmark**</span></span>

<span data-ttu-id="0880c-143">唯一标识中的一组行的行，以便用户可以迅速导航至其标记。</span><span class="sxs-lookup"><span data-stu-id="0880c-143">A marker that uniquely identifies a row within a set of rows so that a user can quickly navigate to it.</span></span>

<span data-ttu-id="0880c-144">**业务对象**</span><span class="sxs-lookup"><span data-stu-id="0880c-144">**business object**</span></span>

<span data-ttu-id="0880c-145">执行一组定义的操作，如数据验证或业务规则逻辑的对象。</span><span class="sxs-lookup"><span data-stu-id="0880c-145">An object that performs a defined set of operations, such as data validation or business rule logic.</span></span> <span data-ttu-id="0880c-146">业务对象通常位于中间层。</span><span class="sxs-lookup"><span data-stu-id="0880c-146">Business objects usually reside on the middle tier.</span></span>

<span data-ttu-id="0880c-147">**业务规则**</span><span class="sxs-lookup"><span data-stu-id="0880c-147">**business rule**</span></span>

<span data-ttu-id="0880c-148">验证编辑、 登录校验、 数据库查找、 策略和构成开展业务的企业的方式的算法变换的组合。</span><span class="sxs-lookup"><span data-stu-id="0880c-148">The combination of validation edits, logon verifications, database lookups, policies, and algorithmic transformations that constitute an enterprise's way of doing business.</span></span> <span data-ttu-id="0880c-149">也称为为*业务逻辑*。</span><span class="sxs-lookup"><span data-stu-id="0880c-149">Also known as *business logic*.</span></span>

<span data-ttu-id="0880c-150">返回顶部</span><span class="sxs-lookup"><span data-stu-id="0880c-150">Return to top</span></span>

## <a name="c"></a><span data-ttu-id="0880c-151">C</span><span class="sxs-lookup"><span data-stu-id="0880c-151">C</span></span>

<span data-ttu-id="0880c-152">**计算的表达式**</span><span class="sxs-lookup"><span data-stu-id="0880c-152">**calculated expression**</span></span>

<span data-ttu-id="0880c-153">一个表达式不是常量，但其值取决于其他值。</span><span class="sxs-lookup"><span data-stu-id="0880c-153">An expression that is not constant, but whose value depends upon other values.</span></span> <span data-ttu-id="0880c-154">要进行求值计算的表达式必须获取并计算从其他源，通常在其他字段或行中的值。</span><span class="sxs-lookup"><span data-stu-id="0880c-154">To be evaluated, a calculated expression must obtain and compute values from other sources, typically in other fields or rows.</span></span>

<span data-ttu-id="0880c-155">**章**</span><span class="sxs-lookup"><span data-stu-id="0880c-155">**chapter**</span></span>

<span data-ttu-id="0880c-156">对行的范围从数据源的引用。</span><span class="sxs-lookup"><span data-stu-id="0880c-156">A reference to a range of rows from a data source.</span></span> <span data-ttu-id="0880c-157">在 ADO 中，一章通常是另一个**记录集**的引用。</span><span class="sxs-lookup"><span data-stu-id="0880c-157">In ADO, a chapter is typically a reference to another **Recordset**.</span></span>

<span data-ttu-id="0880c-158">章节列使定义*的父子*关系其中*父*是**Recordset** ，其中包含的章节列和\*子\***记录集**由中的一章。</span><span class="sxs-lookup"><span data-stu-id="0880c-158">Chapter columns make it possible to define a *parent-child* relationship where the *parent* is the **Recordset** containing the chapter column and the *child* is the **Recordset** represented by the chapter.</span></span>

<span data-ttu-id="0880c-159">**chapter-alias**</span><span class="sxs-lookup"><span data-stu-id="0880c-159">**chapter-alias**</span></span>

<span data-ttu-id="0880c-160">引用追加到父对象的列别名。</span><span class="sxs-lookup"><span data-stu-id="0880c-160">An alias that refers to the column appended to the parent.</span></span>

<span data-ttu-id="0880c-161">**字符集**</span><span class="sxs-lookup"><span data-stu-id="0880c-161">**character set**</span></span>

<span data-ttu-id="0880c-162">映射到其数值字符的一组。</span><span class="sxs-lookup"><span data-stu-id="0880c-162">A mapping of a set of characters to their numeric values.</span></span> <span data-ttu-id="0880c-163">例如，Unicode 是一个 16 位字符集能够对所有已知的字符进行编码和用作全球的字符编码标准。</span><span class="sxs-lookup"><span data-stu-id="0880c-163">For example, Unicode is a 16-bit character set capable of encoding all known characters and used as a worldwide character-encoding standard.</span></span>

<span data-ttu-id="0880c-164">**子**</span><span class="sxs-lookup"><span data-stu-id="0880c-164">**child**</span></span>

<span data-ttu-id="0880c-165">相关的一侧的分层关系。</span><span class="sxs-lookup"><span data-stu-id="0880c-165">The dependent side of a hierarchical relationship.</span></span> <span data-ttu-id="0880c-166">子元素是具有之上的另一个节点的层次结构中的节点 （接近根目录）。</span><span class="sxs-lookup"><span data-stu-id="0880c-166">A child is a node in a hierarchical structure that has another node above it (closer to the root).</span></span> <span data-ttu-id="0880c-167">请参阅**子别名**、**父子关系**和**父**。</span><span class="sxs-lookup"><span data-stu-id="0880c-167">See also **child-alias**, **parent-child relationship**, **parent**.</span></span>

<span data-ttu-id="0880c-168">**child-alias**</span><span class="sxs-lookup"><span data-stu-id="0880c-168">**child-alias**</span></span>

<span data-ttu-id="0880c-169">引用子别名。</span><span class="sxs-lookup"><span data-stu-id="0880c-169">An alias that refers to the child.</span></span> <span data-ttu-id="0880c-170">请参阅**别名**，**子**。</span><span class="sxs-lookup"><span data-stu-id="0880c-170">See also **alias**, **child**.</span></span>

<span data-ttu-id="0880c-171">**CLSID （类标识符）**</span><span class="sxs-lookup"><span data-stu-id="0880c-171">**CLSID (class identifier)**</span></span>

<span data-ttu-id="0880c-172">全局唯一标识符 (UUID) 标识的 COM 组件。</span><span class="sxs-lookup"><span data-stu-id="0880c-172">A universally unique identifier (UUID) that identifies a COM component.</span></span> <span data-ttu-id="0880c-173">每个 COM 组件具有其 CLSID Windows 注册表中，以便可以由其他应用程序加载它。</span><span class="sxs-lookup"><span data-stu-id="0880c-173">Each COM component has its CLSID in the Windows Registry so that it can be loaded by other applications.</span></span> <span data-ttu-id="0880c-174">请参阅**ProgID**， **COM**。</span><span class="sxs-lookup"><span data-stu-id="0880c-174">See also **ProgID**, **COM**.</span></span>

<span data-ttu-id="0880c-175">**客户端层**</span><span class="sxs-lookup"><span data-stu-id="0880c-175">**client tier**</span></span>

<span data-ttu-id="0880c-176">分布式系统通常将数据提交给和处理来自用户，有时也称为*前端*输入的逻辑图层。</span><span class="sxs-lookup"><span data-stu-id="0880c-176">A logical layer of a distributed system that typically presents data to and processes input from the user, sometimes referred to as the *front end*.</span></span> <span data-ttu-id="0880c-177">通常情况下，客户端层请求从基于输入服务器的数据，然后设置格式，并显示结果。</span><span class="sxs-lookup"><span data-stu-id="0880c-177">Usually, the client tier requests data from a server based on input, and then formats and displays the result.</span></span> <span data-ttu-id="0880c-178">请参阅**中间层**、**层的数据源**和**分布式应用程序**。</span><span class="sxs-lookup"><span data-stu-id="0880c-178">See also **middle tier**, **data source tier**, **distributed application**.</span></span>

<span data-ttu-id="0880c-179">**COM （组件对象模型）**</span><span class="sxs-lookup"><span data-stu-id="0880c-179">**COM (Component Object Model)**</span></span>

<span data-ttu-id="0880c-180">使对象来实现互操作，而不考虑其开发语言或其所在的计算机上的网络环境中的一种二进制标准。</span><span class="sxs-lookup"><span data-stu-id="0880c-180">A binary standard that enables objects to interoperate in a networked environment regardless of the language in which they were developed or on which computers they reside.</span></span> <span data-ttu-id="0880c-181">基于 COM 的技术包括 ActiveX 控件、 自动化和对象链接和嵌入 (OLE)。</span><span class="sxs-lookup"><span data-stu-id="0880c-181">COM-based technologies include ActiveX Controls, Automation, and object linking and embedding (OLE).</span></span> <span data-ttu-id="0880c-182">COM 允许对象公开其功能的其他组件和主机应用程序。</span><span class="sxs-lookup"><span data-stu-id="0880c-182">COM allows an object to expose its functionality to other components and to host applications.</span></span> <span data-ttu-id="0880c-183">它定义同时对象如何公开本身和各个进程和各个网络这种公开的工作原理。</span><span class="sxs-lookup"><span data-stu-id="0880c-183">It defines both how the object exposes itself and how this exposure works across processes and across networks.</span></span> <span data-ttu-id="0880c-184">COM 还定义对象的生命周期。</span><span class="sxs-lookup"><span data-stu-id="0880c-184">COM also defines the object's life cycle.</span></span>

<span data-ttu-id="0880c-185">**COM 组件**</span><span class="sxs-lookup"><span data-stu-id="0880c-185">**COM component**</span></span>

<span data-ttu-id="0880c-186">二进制文件 — 例如.dll、.ocx 和某些.exe 文件 — 提供对象支持 COM 标准的。</span><span class="sxs-lookup"><span data-stu-id="0880c-186">Binary file — such as .dll, .ocx, and some .exe files — that supports the COM standard for providing objects.</span></span> <span data-ttu-id="0880c-187">此类文件包含代码的一个或多个类工厂、 COM 类、 注册表项的机制，加载代码，等等。</span><span class="sxs-lookup"><span data-stu-id="0880c-187">Such a file contains code for one or more class factories, COM classes, registry-entry mechanisms, loading code, and so on.</span></span>

<span data-ttu-id="0880c-188">**比较运算符**</span><span class="sxs-lookup"><span data-stu-id="0880c-188">**comparison operator**</span></span>

<span data-ttu-id="0880c-189">运算符，比较两个表达式，返回一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="0880c-189">An operator that compares two expressions and returns a Boolean value.</span></span>

<span data-ttu-id="0880c-190">条件参数的可能表示为"\>"（大于），"\<"（小于），"="（等于），"\>="（大于或等于），"\<="（小于或等于），"\<\>"（不等于），或"like"（模式匹配）。</span><span class="sxs-lookup"><span data-stu-id="0880c-190">A criteria parameter that may be expressed as "\>" (greater than), "\<" (less than), "=" (equal), "\>=" (greater than or equal), "\<=" (less than or equal), "\<\>" (not equal), or "like" (pattern matching).</span></span>

<span data-ttu-id="0880c-191">**component**</span><span class="sxs-lookup"><span data-stu-id="0880c-191">**component**</span></span>

<span data-ttu-id="0880c-192">一个对象，封装数据和代码，并提供了一套合理指定可公开访问服务。</span><span class="sxs-lookup"><span data-stu-id="0880c-192">An object that encapsulates both data and code, and provides a well-specified set of publicly available services.</span></span>

<span data-ttu-id="0880c-193">**复合文件**</span><span class="sxs-lookup"><span data-stu-id="0880c-193">**compound file**</span></span>

<span data-ttu-id="0880c-194">COM 实现结构化存储文件。</span><span class="sxs-lookup"><span data-stu-id="0880c-194">An implementation of COM structured storage for files.</span></span> <span data-ttu-id="0880c-195">复合文件将单独对象存储在单一的结构化组成的文件，两个主要元素： 存储对象和 stream 对象。</span><span class="sxs-lookup"><span data-stu-id="0880c-195">A compound file stores separate objects in a single, structured file consisting of two main elements: storage objects and stream objects.</span></span> <span data-ttu-id="0880c-196">在一起，它们的功能类似文件中的文件系统。</span><span class="sxs-lookup"><span data-stu-id="0880c-196">Together, they function like a file system within a file.</span></span> <span data-ttu-id="0880c-197">有关详细信息，请参阅复合的 Microsoft Platform SDK 中的文件。</span><span class="sxs-lookup"><span data-stu-id="0880c-197">For more information, see Compound Files in the Microsoft Platform SDK.</span></span>

<span data-ttu-id="0880c-198">一个物理文件中绑定在一起的单个文件数。</span><span class="sxs-lookup"><span data-stu-id="0880c-198">A number of individual files bound together in one physical file.</span></span> <span data-ttu-id="0880c-199">好像它是一个物理文件，可以访问复合文件中的每个单独的文件。</span><span class="sxs-lookup"><span data-stu-id="0880c-199">Each individual file in a compound file can be accessed as if it were a single physical file.</span></span>

<span data-ttu-id="0880c-200">**常量**</span><span class="sxs-lookup"><span data-stu-id="0880c-200">**constant**</span></span>

<span data-ttu-id="0880c-201">一个数字或字符串的值，不会更改。</span><span class="sxs-lookup"><span data-stu-id="0880c-201">A numeric or string value that does not change.</span></span> <span data-ttu-id="0880c-202">可以而不是实际值在代码中使用命名的 ADO 枚举 （枚举常量），例如， **adUseClient**是其值为 3 的常量。</span><span class="sxs-lookup"><span data-stu-id="0880c-202">Named ADO enumerations (enumerated constants) can be used in your code instead of actual values, for example, **adUseClient** is a constant whose value is 3.</span></span> <span data-ttu-id="0880c-203">(Const adUseClient = 3)。</span><span class="sxs-lookup"><span data-stu-id="0880c-203">(Const adUseClient = 3).</span></span> <span data-ttu-id="0880c-204">请参阅**枚举**。</span><span class="sxs-lookup"><span data-stu-id="0880c-204">See also **enumeration**.</span></span>

<span data-ttu-id="0880c-205">**游标**</span><span class="sxs-lookup"><span data-stu-id="0880c-205">**cursor**</span></span>

<span data-ttu-id="0880c-206">一个数据库元素，控制记录导航、 数据，可更新性和其他用户对数据库所做的更改的可见性。</span><span class="sxs-lookup"><span data-stu-id="0880c-206">A database element that controls record navigation, updateability of data, and the visibility of changes made to the database by other users.</span></span>

<span data-ttu-id="0880c-207">返回顶部</span><span class="sxs-lookup"><span data-stu-id="0880c-207">Return to top</span></span>

## <a name="d"></a><span data-ttu-id="0880c-208">D</span><span class="sxs-lookup"><span data-stu-id="0880c-208">D</span></span>

<span data-ttu-id="0880c-209">**数据绑定**</span><span class="sxs-lookup"><span data-stu-id="0880c-209">**data binding**</span></span>

<span data-ttu-id="0880c-210">相关联的对象或控件的数据源的应用程序的过程。</span><span class="sxs-lookup"><span data-stu-id="0880c-210">The process of associating the objects or controls of an application to a data source.</span></span> <span data-ttu-id="0880c-211">与数据源关联的控件称为*数据绑定控件*。</span><span class="sxs-lookup"><span data-stu-id="0880c-211">A control associated with a data source is called a *data-bound control*.</span></span>

<span data-ttu-id="0880c-212">数据绑定控件的内容相关联的数据库中的值。</span><span class="sxs-lookup"><span data-stu-id="0880c-212">The contents of a data-bound control are associated with values from a database.</span></span> <span data-ttu-id="0880c-213">例如，更新**Recordset**中的行时，可以更新绑定到**Recordset**对象的网格控件。</span><span class="sxs-lookup"><span data-stu-id="0880c-213">For example, a grid control that is bound to a **Recordset** object can be updated when the rows in the **Recordset** are updated.</span></span> <span data-ttu-id="0880c-214">当**Recordset**中检索新值时，新值显示在网格中。</span><span class="sxs-lookup"><span data-stu-id="0880c-214">When new values are retrieved by the **Recordset**, new values are displayed in the grid.</span></span>

<span data-ttu-id="0880c-215">**数据提供程序**</span><span class="sxs-lookup"><span data-stu-id="0880c-215">**data provider**</span></span>

<span data-ttu-id="0880c-216">公开到 ADO 应用程序的数据的软件直接或通过服务提供商。</span><span class="sxs-lookup"><span data-stu-id="0880c-216">Software that exposes data to an ADO application either directly or via a service provider.</span></span> <span data-ttu-id="0880c-217">请参阅**服务提供程序**。</span><span class="sxs-lookup"><span data-stu-id="0880c-217">See also **service provider**.</span></span>

<span data-ttu-id="0880c-218">**数据定形**</span><span class="sxs-lookup"><span data-stu-id="0880c-218">**data shaping**</span></span>

<span data-ttu-id="0880c-219">哪些利用 （称为**形状语言**） 的正式语法来定义一个专用的**Recordset**对象 （称为**已构形 Recordset**） 的包含而不仅仅是数据，但是还引用的其他**Recordset**对象的技术和/ 或计算基于这些**Recordset**对象的值。</span><span class="sxs-lookup"><span data-stu-id="0880c-219">A technique which makes use of a formalized syntax (called **Shape language**) to define a specialized **Recordset** object (called a **shaped Recordset**) that contains not just data, but also references to other **Recordset** objects and/or computed values based on those other **Recordset** objects.</span></span>

<span data-ttu-id="0880c-220">**数据源层**</span><span class="sxs-lookup"><span data-stu-id="0880c-220">**data source tier**</span></span>

<span data-ttu-id="0880c-221">代表运行 DBMS，例如 SQL Server 数据库的计算机的分布式系统逻辑层。</span><span class="sxs-lookup"><span data-stu-id="0880c-221">A logical layer of a distributed system that represents a computer running a DBMS, such as an SQL Server database.</span></span> <span data-ttu-id="0880c-222">**客户端层**，**中间层**，**分布式应用程序**，请参阅。</span><span class="sxs-lookup"><span data-stu-id="0880c-222">See also **client tier**, **middle tier**, **distributed application**.</span></span>

<span data-ttu-id="0880c-223">**DCOM**</span><span class="sxs-lookup"><span data-stu-id="0880c-223">**DCOM**</span></span>

<span data-ttu-id="0880c-224">允许 COM 组件相互直接通过网络线路协议。</span><span class="sxs-lookup"><span data-stu-id="0880c-224">A wire protocol that enables COM components to communicate directly with each other across a network.</span></span> <span data-ttu-id="0880c-225">请参阅**COM**，**组件**。</span><span class="sxs-lookup"><span data-stu-id="0880c-225">See also **COM**, **component**.</span></span>

<span data-ttu-id="0880c-226">**DDL （数据定义语言）**</span><span class="sxs-lookup"><span data-stu-id="0880c-226">**DDL (Data Definition Language)**</span></span>

<span data-ttu-id="0880c-227">这些的定义，而不是操作，数据在 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="0880c-227">Those statements in SQL that define, as opposed to manipulate, data.</span></span> <span data-ttu-id="0880c-228">创建或修改与 DDL 数据库的架构。</span><span class="sxs-lookup"><span data-stu-id="0880c-228">The schema of a database is created or modified with DDL.</span></span> <span data-ttu-id="0880c-229">例如， **CREATE TABLE**、 **CREATE INDEX**、**授予**、 和**取消**是 SQL DDL 语句。</span><span class="sxs-lookup"><span data-stu-id="0880c-229">For example, **CREATE TABLE**, **CREATE INDEX**, **GRANT**, and **REVOKE** are SQL DDL statements.</span></span>

<span data-ttu-id="0880c-230">**默认流**</span><span class="sxs-lookup"><span data-stu-id="0880c-230">**default stream**</span></span>

<span data-ttu-id="0880c-231">文本或二进制流 （由**Stream**对象），其中使用某些 OLE DB 提供程序，如 Microsoft OLE DB Provider for Internet Publishing 时与**Record**或**Recordset**对象相关联。</span><span class="sxs-lookup"><span data-stu-id="0880c-231">A text or binary stream (represented by a **Stream** object) that is associated with **Record** or **Recordset** objects when using certain OLE DB providers, such as the Microsoft OLE DB Provider for Internet Publishing.</span></span> <span data-ttu-id="0880c-232">默认流通常包含网站的根目录的文件 （如 HTML 代码） 的内容。</span><span class="sxs-lookup"><span data-stu-id="0880c-232">The default stream typically contains the contents of a file such as the HTML code for the root of a website.</span></span>

<span data-ttu-id="0880c-233">**分布式应用程序**</span><span class="sxs-lookup"><span data-stu-id="0880c-233">**distributed application**</span></span>

<span data-ttu-id="0880c-234">编写，以便通过网络可以跨多台计算机划分处理程序。</span><span class="sxs-lookup"><span data-stu-id="0880c-234">A program written so that the processing can be divided across multiple computers over a network.</span></span> <span data-ttu-id="0880c-235">通常，分布式应用程序划分为演示文稿、 业务逻辑和数据存储区层或*层*。</span><span class="sxs-lookup"><span data-stu-id="0880c-235">Typically, a distributed application is divided into presentation, business logic, and data store layers, or *tiers*.</span></span> <span data-ttu-id="0880c-236">请参阅**客户端层**、**中间层**和**数据源层**。</span><span class="sxs-lookup"><span data-stu-id="0880c-236">See also **client tier**, **middle tier**, **data source tier**.</span></span>

<span data-ttu-id="0880c-237">**断开连接的记录集**</span><span class="sxs-lookup"><span data-stu-id="0880c-237">**disconnected Recordset**</span></span>

<span data-ttu-id="0880c-238">**Recordset**对象不再具有连接到服务器的 live 客户端缓存中。</span><span class="sxs-lookup"><span data-stu-id="0880c-238">A **Recordset** object in a client cache that no longer has a live connection to the server.</span></span> <span data-ttu-id="0880c-239">如果原始数据源需要访问再次由于某种原因，如更新数据，必须重新建立连接。</span><span class="sxs-lookup"><span data-stu-id="0880c-239">If the original data source needs to be accessed again for some reason, such as updating data, the connection must be re-established.</span></span> <span data-ttu-id="0880c-240">但是，集合、 属性和已断开连接的**Recordset**的方法仍可。</span><span class="sxs-lookup"><span data-stu-id="0880c-240">However, the collections, properties, and methods of a disconnected **Recordset** can still be accessed.</span></span>

<span data-ttu-id="0880c-241">**DLL （动态链接库）**</span><span class="sxs-lookup"><span data-stu-id="0880c-241">**DLL (dynamic-link library)**</span></span>

<span data-ttu-id="0880c-242">包含一个或多个函数的已经编译的文件的链接，并分开存放使用它们的过程。</span><span class="sxs-lookup"><span data-stu-id="0880c-242">A file that contains one or more functions that are compiled, linked, and stored separately from the processes that use them.</span></span> <span data-ttu-id="0880c-243">操作系统将 Dll 映射到调用进程的地址空间时正在启动过程，或运行时。</span><span class="sxs-lookup"><span data-stu-id="0880c-243">The operating system maps the DLLs into the address space of the calling process when the process is starting, or while it is running.</span></span>

<span data-ttu-id="0880c-244">**DML （数据操作语言）**</span><span class="sxs-lookup"><span data-stu-id="0880c-244">**DML (Data Manipulation Language)**</span></span>

<span data-ttu-id="0880c-245">这些操作，而不是定义，数据的在 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="0880c-245">Those statements in SQL that manipulate, as opposed to define, data.</span></span> <span data-ttu-id="0880c-246">数据库中的值是选择，使用 DML 修改。</span><span class="sxs-lookup"><span data-stu-id="0880c-246">The values in a database are selected and modified with DML.</span></span> <span data-ttu-id="0880c-247">例如，**插入**、**更新**、**删除**和**选择**是 SQL DML 语句。</span><span class="sxs-lookup"><span data-stu-id="0880c-247">For example, **INSERT**, **UPDATE**, **DELETE**, and **SELECT** are SQL DML statements.</span></span>

<span data-ttu-id="0880c-248">**文档源提供程序**</span><span class="sxs-lookup"><span data-stu-id="0880c-248">**document source provider**</span></span>

<span data-ttu-id="0880c-249">提供用于管理文件夹和文档的特殊类。</span><span class="sxs-lookup"><span data-stu-id="0880c-249">A special class of providers that manage folders and documents.</span></span> <span data-ttu-id="0880c-250">在由**Record**对象表示文档或文档的文件夹由**Recordset**对象时，文档源提供程序使用填充唯一的一组字段来描述特征的文档，这些对象而不是实际文档本身。</span><span class="sxs-lookup"><span data-stu-id="0880c-250">When a document is represented by a **Record** object, or a folder of documents is represented by a **Recordset** object, the document source provider populates those objects with a unique set of fields that describe characteristics of the document, instead of the actual document itself.</span></span> <span data-ttu-id="0880c-251">请参阅**资源记录**。</span><span class="sxs-lookup"><span data-stu-id="0880c-251">See also **resource record**.</span></span>

<span data-ttu-id="0880c-252">**DSN （数据源名称）**</span><span class="sxs-lookup"><span data-stu-id="0880c-252">**DSN (data source name)**</span></span>

<span data-ttu-id="0880c-253">用于连接到特定的 ODBC 数据库应用程序的信息的集合。</span><span class="sxs-lookup"><span data-stu-id="0880c-253">The collection of information used to connect your application to a particular ODBC database.</span></span> <span data-ttu-id="0880c-254">ODBC 驱动程序经理使用此信息来创建与数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="0880c-254">The ODBC Driver Manager uses this information to create a connection to the database.</span></span> <span data-ttu-id="0880c-255">DSN 可以存储在文件 （文件 DSN） 或 Windows 注册表 （计算机 DSN） 中。</span><span class="sxs-lookup"><span data-stu-id="0880c-255">A DSN can be stored in a file (a file DSN) or in the Windows Registry (a machine DSN).</span></span>

<span data-ttu-id="0880c-256">**动态属性**</span><span class="sxs-lookup"><span data-stu-id="0880c-256">**dynamic property**</span></span>

<span data-ttu-id="0880c-257">特定于数据提供程序或游标服务的属性。</span><span class="sxs-lookup"><span data-stu-id="0880c-257">A property specific to a data provider or the cursor service.</span></span> <span data-ttu-id="0880c-258">对象的**Properties**集合自动填充这些 （"动态"）。</span><span class="sxs-lookup"><span data-stu-id="0880c-258">The **Properties** collection of an object is populated with these automatically ("dynamically").</span></span> <span data-ttu-id="0880c-259">对象具有任何动态属性，直到连接到通过特定数据提供程序的数据源。</span><span class="sxs-lookup"><span data-stu-id="0880c-259">An object has no dynamic properties until it is connected to a data source through a particular data provider.</span></span> <span data-ttu-id="0880c-260">请参阅还**数据提供程序**，**光标**。</span><span class="sxs-lookup"><span data-stu-id="0880c-260">See also **data provider**, **cursor**.</span></span>

<span data-ttu-id="0880c-261">返回顶部</span><span class="sxs-lookup"><span data-stu-id="0880c-261">Return to top</span></span>

## <a name="e-i"></a><span data-ttu-id="0880c-262">E-I</span><span class="sxs-lookup"><span data-stu-id="0880c-262">E-I</span></span>

<span data-ttu-id="0880c-263">**枚举**</span><span class="sxs-lookup"><span data-stu-id="0880c-263">**enumeration**</span></span>

<span data-ttu-id="0880c-264">命名常量的列表。</span><span class="sxs-lookup"><span data-stu-id="0880c-264">A list of named constants.</span></span> <span data-ttu-id="0880c-265">不需要唯一枚举的值。</span><span class="sxs-lookup"><span data-stu-id="0880c-265">Enumerated values need not be unique.</span></span> <span data-ttu-id="0880c-266">但是每个值的名称必须是唯一定义枚举的位置范围内。</span><span class="sxs-lookup"><span data-stu-id="0880c-266">However the name of each value must be unique within the scope where the enumeration is defined.</span></span> <span data-ttu-id="0880c-267">在 ADO 中枚举用于数值参数和返回值，将添加到 ADO 代码含义和屏蔽 （这可能会更改版本到版本） 的数值从开发人员。</span><span class="sxs-lookup"><span data-stu-id="0880c-267">In ADO, enumerations are used for numeric parameter and return values, to add meaning to ADO code and to shield the developer from the numeric values (which may change from version to version).</span></span> <span data-ttu-id="0880c-268">例如，若要打开静态**记录集**，请使用**为 adOpenStatic**枚举值：</span><span class="sxs-lookup"><span data-stu-id="0880c-268">For example, to open a static **Recordset**, use the **adOpenStatic** enumerated value:</span></span>  
  

<span data-ttu-id="0880c-269">也称为*枚举常量*。</span><span class="sxs-lookup"><span data-stu-id="0880c-269">Also referred to as *enumerated constant*.</span></span> <span data-ttu-id="0880c-270">请参阅**常量**。</span><span class="sxs-lookup"><span data-stu-id="0880c-270">See also **constant**.</span></span>

<span data-ttu-id="0880c-271">**事件**</span><span class="sxs-lookup"><span data-stu-id="0880c-271">**event**</span></span>

<span data-ttu-id="0880c-272">一个对象，可以为其编写代码以响应由识别的操作。</span><span class="sxs-lookup"><span data-stu-id="0880c-272">An action recognized by an object, for which you can write code to respond.</span></span> <span data-ttu-id="0880c-273">可以通过执行命令、 事务完成、 recordset 导航和数据更新等其他操作生成事件。</span><span class="sxs-lookup"><span data-stu-id="0880c-273">Events can be generated by command execution, transaction completion, recordset navigation, and data updates, among other actions.</span></span> <span data-ttu-id="0880c-274">请参阅**事件处理程序**。</span><span class="sxs-lookup"><span data-stu-id="0880c-274">See also **event handler**.</span></span>

<span data-ttu-id="0880c-275">**事件处理程序**</span><span class="sxs-lookup"><span data-stu-id="0880c-275">**event handler**</span></span>

<span data-ttu-id="0880c-276">事件处理程序是在事件发生时执行的代码。</span><span class="sxs-lookup"><span data-stu-id="0880c-276">An event handler is the code that is executed when an event occurs.</span></span> <span data-ttu-id="0880c-277">请参阅**事件**。</span><span class="sxs-lookup"><span data-stu-id="0880c-277">See also **event**.</span></span>

<span data-ttu-id="0880c-278">**handler**</span><span class="sxs-lookup"><span data-stu-id="0880c-278">**handler**</span></span>

<span data-ttu-id="0880c-279">管理常规且相对简单条件或操作，如错误恢复或数据管理例程。</span><span class="sxs-lookup"><span data-stu-id="0880c-279">A routine that manages a common and relatively simple condition or operation, such as error recovery or data management.</span></span>

<span data-ttu-id="0880c-280">**分层记录集**</span><span class="sxs-lookup"><span data-stu-id="0880c-280">**hierarchical Recordset**</span></span>

<span data-ttu-id="0880c-281">包含另一个**记录集\*\*\*\*记录集**。</span><span class="sxs-lookup"><span data-stu-id="0880c-281">A **Recordset** that contains another **Recordset**.</span></span> <span data-ttu-id="0880c-282">另请参阅**数据定形**，**章节**。</span><span class="sxs-lookup"><span data-stu-id="0880c-282">See also **data shaping**, **chapter**.</span></span>

<span data-ttu-id="0880c-283">有关详细信息，请参阅[访问分层记录集中的行](accessing-rows-in-a-hierarchical-recordset.md)</span><span class="sxs-lookup"><span data-stu-id="0880c-283">For more information, see [Accessing Rows in a Hierarchical Recordset](accessing-rows-in-a-hierarchical-recordset.md)</span></span>

<span data-ttu-id="0880c-284">**层次结构**</span><span class="sxs-lookup"><span data-stu-id="0880c-284">**hierarchy**</span></span>

<span data-ttu-id="0880c-285">一般情况下，层次结构是具有一个顶点的排名的结构级别和附属级别。</span><span class="sxs-lookup"><span data-stu-id="0880c-285">In general, a hierarchy is a ranked structure with a top level and subordinate levels.</span></span> <span data-ttu-id="0880c-286">在 ADO 中，分层**记录集**用于表示记录和一章之间的父子关系。</span><span class="sxs-lookup"><span data-stu-id="0880c-286">In ADO, hierarchical **Recordsets** are used to represent the parent-child relationship between a record and a chapter.</span></span> <span data-ttu-id="0880c-287">此外在 ADO 中， **Record**和**Stream**对象可用于访问分层树结构，如文件夹和文档。</span><span class="sxs-lookup"><span data-stu-id="0880c-287">Also in ADO, **Record** and **Stream** objects can be used to access hierarchical tree structures such as a folder and documents.</span></span> <span data-ttu-id="0880c-288">ADO MD 还包括**Hierarchy**对象表示的 OLAP 多维数据集中的维度的级别之间的关系。</span><span class="sxs-lookup"><span data-stu-id="0880c-288">ADO MD also includes **Hierarchy** objects to represent a relationship between the levels of a dimension in an OLAP cube.</span></span> <span data-ttu-id="0880c-289">请参阅**分层记录集**，**父子关系**、**章节**和**树**。</span><span class="sxs-lookup"><span data-stu-id="0880c-289">See also **hierarchical Recordsets**, **parent-child relationship**, **chapter**, **tree**.</span></span>

<span data-ttu-id="0880c-290">**ISAPI （Internet 服务器应用程序编程接口）**</span><span class="sxs-lookup"><span data-stu-id="0880c-290">**ISAPI (Internet Server Application Programming Interface)**</span></span>

<span data-ttu-id="0880c-291">对于 Internet 服务器，如 Windows NT Server/Windows 2000 服务器运行 Microsoft Internet 信息服务 (IIS) 的功能集。</span><span class="sxs-lookup"><span data-stu-id="0880c-291">A set of functions for Internet servers, such as a Windows NT Server/Windows 2000 Server running Microsoft Internet Information Services (IIS).</span></span>

<span data-ttu-id="0880c-292">返回顶部</span><span class="sxs-lookup"><span data-stu-id="0880c-292">Return to top</span></span>

## <a name="k-m"></a><span data-ttu-id="0880c-293">K-M</span><span class="sxs-lookup"><span data-stu-id="0880c-293">K-M</span></span>

<span data-ttu-id="0880c-294">**key**</span><span class="sxs-lookup"><span data-stu-id="0880c-294">**key**</span></span>

<span data-ttu-id="0880c-295">一列或表格中的列唯一标识行;通常用于索引表。</span><span class="sxs-lookup"><span data-stu-id="0880c-295">A column or columns in a table that uniquely identify a row; often used to index a table.</span></span>

<span data-ttu-id="0880c-296">**封送处理**</span><span class="sxs-lookup"><span data-stu-id="0880c-296">**marshaling**</span></span>

<span data-ttu-id="0880c-297">打包、 发送，和解接口方法参数跨线程或进程边界的过程。</span><span class="sxs-lookup"><span data-stu-id="0880c-297">The process of packaging, sending, and unpackaging interface method parameters across thread or process boundaries.</span></span>

<span data-ttu-id="0880c-298">**中间层**</span><span class="sxs-lookup"><span data-stu-id="0880c-298">**middle tier**</span></span>

<span data-ttu-id="0880c-299"><<<<<<< 头中的用户界面或 Web 客户端和数据库之间的分布式系统的逻辑层。</span><span class="sxs-lookup"><span data-stu-id="0880c-299"><<<<<<< HEAD The logical layer in a distributed system between a user interface or Web client and the database.</span></span> <span data-ttu-id="0880c-300">这通常是其中业务对象进行实例化。</span><span class="sxs-lookup"><span data-stu-id="0880c-300">This is typically where business objects are instantiated.</span></span> <span data-ttu-id="0880c-301">中间层是业务规则和函数的生成和运行时信息的集合。</span><span class="sxs-lookup"><span data-stu-id="0880c-301">The middle tier is a collection of business rules and functions that generate and operate upon receiving information.</span></span> <span data-ttu-id="0880c-302">它们通过它可以经常发生更改，并因此封装到物理独立于应用程序逻辑本身的组件的业务规则实现这一点。</span><span class="sxs-lookup"><span data-stu-id="0880c-302">They accomplish this through business rules, which can change frequently, and are thus encapsulated into components that are physically separate from the application logic itself.</span></span> <span data-ttu-id="0880c-303">也称为为*应用程序服务器层*。</span><span class="sxs-lookup"><span data-stu-id="0880c-303">Also known as *application server tier*.</span></span> <span data-ttu-id="0880c-304">请参阅**分布式应用程序**、**客户端层**和**数据源层**。</span><span class="sxs-lookup"><span data-stu-id="0880c-304">See also **distributed application**, **client tier**, **data source tier**.</span></span>
<span data-ttu-id="0880c-305">=== 在分布式系统用户界面或 web 客户端和数据库之间逻辑层。</span><span class="sxs-lookup"><span data-stu-id="0880c-305">======= The logical layer in a distributed system between a user interface or web client and the database.</span></span> <span data-ttu-id="0880c-306">这通常是其中业务对象进行实例化。</span><span class="sxs-lookup"><span data-stu-id="0880c-306">This is typically where business objects are instantiated.</span></span> <span data-ttu-id="0880c-307">中间层是业务规则和函数的生成和运行时信息的集合。</span><span class="sxs-lookup"><span data-stu-id="0880c-307">The middle tier is a collection of business rules and functions that generate and operate upon receiving information.</span></span> <span data-ttu-id="0880c-308">它们通过它可以经常发生更改，并因此封装到物理独立于应用程序逻辑本身的组件的业务规则实现这一点。</span><span class="sxs-lookup"><span data-stu-id="0880c-308">They accomplish this through business rules, which can change frequently, and are thus encapsulated into components that are physically separate from the application logic itself.</span></span> <span data-ttu-id="0880c-309">也称为为*应用程序服务器层*。</span><span class="sxs-lookup"><span data-stu-id="0880c-309">Also known as *application server tier*.</span></span> <span data-ttu-id="0880c-310">请参阅**分布式应用程序**、**客户端层**和**数据源层**。</span><span class="sxs-lookup"><span data-stu-id="0880c-310">See also **distributed application**, **client tier**, **data source tier**.</span></span>
>>>>>>> <span data-ttu-id="0880c-311">master</span><span class="sxs-lookup"><span data-stu-id="0880c-311">master</span></span>

<span data-ttu-id="0880c-312">**MIME （多用途 Internet 邮件扩展）**</span><span class="sxs-lookup"><span data-stu-id="0880c-312">**MIME (Multi-purpose Internet Mail Extension)**</span></span>

<span data-ttu-id="0880c-313">Internet 协议最初开发的丰富内容的电子邮件的 exchange 允许跨异构网络、 计算机和电子邮件环境。</span><span class="sxs-lookup"><span data-stu-id="0880c-313">An Internet protocol originally developed to allow exchange of electronic mail messages with rich content across heterogeneous network, machine, and e-mail environments.</span></span> <span data-ttu-id="0880c-314">实际上，MIME 也已采用并扩展非邮件应用程序。</span><span class="sxs-lookup"><span data-stu-id="0880c-314">In practice, MIME has also been adopted and extended by non-mail applications.</span></span>

<span data-ttu-id="0880c-315"><<<<<<< MIME 标头是允许二进制数据的发布和阅读 Internet 上的标准。</span><span class="sxs-lookup"><span data-stu-id="0880c-315"><<<<<<< HEAD MIME is a standard that allows binary data to be published and read on the Internet.</span></span> <span data-ttu-id="0880c-316">包含二进制数据的文件的标头包含数据; 的 MIME 类型这将通知客户端程序 (Web 浏览器和邮件包，例如)，他们将需要多于它们处理直线文本以不同方式处理数据。</span><span class="sxs-lookup"><span data-stu-id="0880c-316">The header of a file with binary data contains the MIME type of the data; this informs client programs (Web browsers and mail packages, for instance) that they will need to handle the data in a different way than they handle straight text.</span></span> <span data-ttu-id="0880c-317">例如，包含 JPEG 图形 Web 文档的标头中包含特定于 JPEG 文件格式的 MIME 类型。</span><span class="sxs-lookup"><span data-stu-id="0880c-317">For example, the header of a Web document containing a JPEG graphic contains the MIME type specific to the JPEG file format.</span></span> <span data-ttu-id="0880c-318">如果有的话，这样，浏览器以显示其 JPEG 查看器中，使用的文件。</span><span class="sxs-lookup"><span data-stu-id="0880c-318">This allows a browser to display the file with its JPEG viewer, if one is present.</span></span>
<span data-ttu-id="0880c-319">=== MIME 是允许二进制数据的发布和阅读 Internet 上的标准。</span><span class="sxs-lookup"><span data-stu-id="0880c-319">======= MIME is a standard that allows binary data to be published and read on the Internet.</span></span> <span data-ttu-id="0880c-320">包含二进制数据的文件的标头包含数据; 的 MIME 类型这将通知客户端程序 (web 浏览器和邮件包，例如)，他们将需要多于它们处理直线文本以不同方式处理数据。</span><span class="sxs-lookup"><span data-stu-id="0880c-320">The header of a file with binary data contains the MIME type of the data; this informs client programs (web browsers and mail packages, for instance) that they will need to handle the data in a different way than they handle straight text.</span></span> <span data-ttu-id="0880c-321">例如，包含 JPEG 图形 web 文档的标头中包含特定于 JPEG 文件格式的 MIME 类型。</span><span class="sxs-lookup"><span data-stu-id="0880c-321">For example, the header of a web document containing a JPEG graphic contains the MIME type specific to the JPEG file format.</span></span> <span data-ttu-id="0880c-322">如果有的话，这样，浏览器以显示其 JPEG 查看器中，使用的文件。</span><span class="sxs-lookup"><span data-stu-id="0880c-322">This allows a browser to display the file with its JPEG viewer, if one is present.</span></span>
>>>>>>> <span data-ttu-id="0880c-323">master</span><span class="sxs-lookup"><span data-stu-id="0880c-323">master</span></span>

<span data-ttu-id="0880c-324">返回顶部</span><span class="sxs-lookup"><span data-stu-id="0880c-324">Return to top</span></span>

## <a name="n-o"></a><span data-ttu-id="0880c-325">N-O</span><span class="sxs-lookup"><span data-stu-id="0880c-325">N-O</span></span>

<span data-ttu-id="0880c-326">**节点**</span><span class="sxs-lookup"><span data-stu-id="0880c-326">**node**</span></span>

<span data-ttu-id="0880c-327">一个分层树结构中的元素。</span><span class="sxs-lookup"><span data-stu-id="0880c-327">An element in a hierarchical tree structure.</span></span> <span data-ttu-id="0880c-328">节点可能根目录中或另一个节点的子级。</span><span class="sxs-lookup"><span data-stu-id="0880c-328">A node may be the root, or the child of another node.</span></span> <span data-ttu-id="0880c-329">节点也可以是多个子元素的父对象。</span><span class="sxs-lookup"><span data-stu-id="0880c-329">A node can also be the parent of multiple children.</span></span> <span data-ttu-id="0880c-330">请参阅**层次结构**、**树**、**根**、**子**和**父**。</span><span class="sxs-lookup"><span data-stu-id="0880c-330">See also **hierarchy**, **tree**, **root**, **child**, **parent**.</span></span>

<span data-ttu-id="0880c-331">**对象变量**</span><span class="sxs-lookup"><span data-stu-id="0880c-331">**object variable**</span></span>

<span data-ttu-id="0880c-332">包含对对象的引用的变量。</span><span class="sxs-lookup"><span data-stu-id="0880c-332">A variable that contains a reference to an object.</span></span> <span data-ttu-id="0880c-333">例如，objCustomObject 是指向 CustomObject 类型的对象的变量：</span><span class="sxs-lookup"><span data-stu-id="0880c-333">For example, objCustomObject is a variable that points to an object of type CustomObject:</span></span>  
  
<span data-ttu-id="0880c-334">是指向 CustomObject 类型的对象的变量：</span><span class="sxs-lookup"><span data-stu-id="0880c-334">is a variable that points to an object of type CustomObject:</span></span>  
  
<span data-ttu-id="0880c-335">设置 objCustomObject = CreateObject (adodb。Recordset)</span><span class="sxs-lookup"><span data-stu-id="0880c-335">Set objCustomObject = CreateObject(adodb.Recordset)</span></span>

<span data-ttu-id="0880c-336">**ODBC （开放式数据库连接）**</span><span class="sxs-lookup"><span data-stu-id="0880c-336">**ODBC (Open Database Connectivity)**</span></span>

<span data-ttu-id="0880c-337">用于连接到各种数据源标准的编程语言接口。</span><span class="sxs-lookup"><span data-stu-id="0880c-337">A standard programming language interface used to connect to a variety of data sources.</span></span> <span data-ttu-id="0880c-338">这通常通过控制面板中，可以分配数据源名称 (Dsn) 使用特定的 ODBC 驱动程序访问。</span><span class="sxs-lookup"><span data-stu-id="0880c-338">This is usually accessed through Control Panel, where data source names (DSNs) can be assigned to use specific ODBC drivers.</span></span>

<span data-ttu-id="0880c-339">**OLE DB**</span><span class="sxs-lookup"><span data-stu-id="0880c-339">**OLE DB**</span></span>

<span data-ttu-id="0880c-340">一组公开来自各种源使用数据的接口</span><span class="sxs-lookup"><span data-stu-id="0880c-340">A set of interfaces that expose data from a variety of sources using COM.</span></span> <span data-ttu-id="0880c-341">OLE DB 接口提供了使用统一访问存储在不同信息源的数据的应用程序。</span><span class="sxs-lookup"><span data-stu-id="0880c-341">OLE DB interfaces provide applications with uniform access to data stored in diverse information sources.</span></span> <span data-ttu-id="0880c-342">这些接口支持 DBMS 功能适用于数据源，使其能够共享它的数据量。</span><span class="sxs-lookup"><span data-stu-id="0880c-342">These interfaces support the amount of DBMS functionality appropriate to the data source, enabling it to share its data.</span></span> <span data-ttu-id="0880c-343">另请参阅**COM**。</span><span class="sxs-lookup"><span data-stu-id="0880c-343">See also **COM**.</span></span>

<span data-ttu-id="0880c-344">**开放式锁定**</span><span class="sxs-lookup"><span data-stu-id="0880c-344">**optimistic locking**</span></span>

<span data-ttu-id="0880c-345">一种类型的其中均包含一个或多个记录，其中包括正在编辑的记录的数据页锁定向其他用户不可用仅时更新记录后使用**Update**方法，但位于之前和之后在调用**Update**.</span><span class="sxs-lookup"><span data-stu-id="0880c-345">A type of locking in which the data page containing one or more records, including the record being edited, is unavailable to other users only while the record is being updated by the **Update** method, but is available before and after the call to **Update**.</span></span>

<span data-ttu-id="0880c-346">**LockType**参数或属性设置为**adLockOptimistic**或**adLockBatchOptimistic**打开**Recordset**对象时，使用开放式锁定。</span><span class="sxs-lookup"><span data-stu-id="0880c-346">Optimistic locking is used when the **Recordset** object is opened with the **LockType** parameter or property set to **adLockOptimistic** or **adLockBatchOptimistic**.</span></span> <span data-ttu-id="0880c-347">请参阅**保守的锁定**。</span><span class="sxs-lookup"><span data-stu-id="0880c-347">See also **pessimistic locking**.</span></span>

<span data-ttu-id="0880c-348">**序号值**</span><span class="sxs-lookup"><span data-stu-id="0880c-348">**ordinal value**</span></span>

<span data-ttu-id="0880c-349">数字顺序中的项的位置。</span><span class="sxs-lookup"><span data-stu-id="0880c-349">The numeric location of an item within an order.</span></span> <span data-ttu-id="0880c-350">一个 ADO 集合，集合中的第一个项目的序号值为零 (0)。</span><span class="sxs-lookup"><span data-stu-id="0880c-350">In an ADO collection, the ordinal value of the first item is zero (0).</span></span> <span data-ttu-id="0880c-351">下一项是一个 （1），依次类推。</span><span class="sxs-lookup"><span data-stu-id="0880c-351">The next item is one (1), and so on.</span></span>

<span data-ttu-id="0880c-352">返回顶部</span><span class="sxs-lookup"><span data-stu-id="0880c-352">Return to top</span></span>

## <a name="p"></a><span data-ttu-id="0880c-353">P</span><span class="sxs-lookup"><span data-stu-id="0880c-353">P</span></span>

<span data-ttu-id="0880c-354">**参数化的命令**</span><span class="sxs-lookup"><span data-stu-id="0880c-354">**parameterized command**</span></span>

<span data-ttu-id="0880c-355">查询或命令，它使您能够执行命令前设置参数值。</span><span class="sxs-lookup"><span data-stu-id="0880c-355">A query or command that allows you to set parameter values before the command is executed.</span></span> <span data-ttu-id="0880c-356">例如，SQL 字符串也可以通过嵌入参数标记中的 SQL 字符串参数化 (指定？ 字符)。</span><span class="sxs-lookup"><span data-stu-id="0880c-356">For example, a SQL string can be parameterized by embedding parameter markers in the SQL string (designated by the '?' character).</span></span> <span data-ttu-id="0880c-357">然后，应用程序指定的每个参数的值，并执行命令。</span><span class="sxs-lookup"><span data-stu-id="0880c-357">The application then specifies values for each parameter and executes the command.</span></span>

<span data-ttu-id="0880c-358">**父**</span><span class="sxs-lookup"><span data-stu-id="0880c-358">**parent**</span></span>

<span data-ttu-id="0880c-359">分层关系的控制一端。</span><span class="sxs-lookup"><span data-stu-id="0880c-359">The controlling side of a hierarchical relationship.</span></span> <span data-ttu-id="0880c-360">层次结构中，在父层次结构中有一个或多个直接位于其下方的子节点。</span><span class="sxs-lookup"><span data-stu-id="0880c-360">In a hierarchical structure, a parent has one or more child nodes directly beneath it in the hierarchy.</span></span> <span data-ttu-id="0880c-361">请参阅**父别名**、**父子关系**和**子**。</span><span class="sxs-lookup"><span data-stu-id="0880c-361">See also **parent-alias**, **parent-child relationship**, **child**.</span></span>

<span data-ttu-id="0880c-362">**parent-alias**</span><span class="sxs-lookup"><span data-stu-id="0880c-362">**parent-alias**</span></span>

<span data-ttu-id="0880c-363">用于引用父别名。</span><span class="sxs-lookup"><span data-stu-id="0880c-363">An alias that refers to the parent.</span></span> <span data-ttu-id="0880c-364">请参阅**别名**，**父**。</span><span class="sxs-lookup"><span data-stu-id="0880c-364">See also **alias**, **parent**.</span></span>

<span data-ttu-id="0880c-365">**父子关系**</span><span class="sxs-lookup"><span data-stu-id="0880c-365">**parent-child relationship**</span></span>

<span data-ttu-id="0880c-366">中的父对象是更高版本和直接与一个或多个子相关联的一级层次结构中的关系。</span><span class="sxs-lookup"><span data-stu-id="0880c-366">A relationship in a hierarchical structure in which the parent is one level higher and directly associated with one or more children.</span></span> <span data-ttu-id="0880c-367">子元素是一个级别较低，并且必须具有一个父。</span><span class="sxs-lookup"><span data-stu-id="0880c-367">A child is one level lower and must have one parent.</span></span> <span data-ttu-id="0880c-368">请参阅**父**，**子**。</span><span class="sxs-lookup"><span data-stu-id="0880c-368">See also **parent**, **child**.</span></span>

<span data-ttu-id="0880c-369">**保留**</span><span class="sxs-lookup"><span data-stu-id="0880c-369">**persist**</span></span>

<span data-ttu-id="0880c-370">若要将数据保存在永久的状态，例如将**Recordset**保存到文件中。</span><span class="sxs-lookup"><span data-stu-id="0880c-370">To save data in a permanent state, such as saving a **Recordset** to a file.</span></span>

<span data-ttu-id="0880c-371">**保守式锁定**</span><span class="sxs-lookup"><span data-stu-id="0880c-371">**pessimistic locking**</span></span>

<span data-ttu-id="0880c-372">一种锁定类型中包含一个或多个记录，其中包括正在编辑的记录的页是对其他用户，以确保更新将进行不可用。</span><span class="sxs-lookup"><span data-stu-id="0880c-372">A type of locking in which the page containing one or more records, including the record being edited, is unavailable to other users to ensure that an update will be made.</span></span> <span data-ttu-id="0880c-373">保守锁定行为由 OLE DB 提供程序定义。</span><span class="sxs-lookup"><span data-stu-id="0880c-373">Pessimistic locking behavior is defined by the OLE DB provider.</span></span> <span data-ttu-id="0880c-374">通常情况下，记录锁定后编辑和**Update**方法完成之前保持为不可用。</span><span class="sxs-lookup"><span data-stu-id="0880c-374">Typically, records are locked upon editing and remain unavailable until the **Update** method has completed.</span></span>

<span data-ttu-id="0880c-375">**LockType**参数或属性设置为**adLockPessimistic**打开**Recordset**对象时，会启用保守式锁定。</span><span class="sxs-lookup"><span data-stu-id="0880c-375">Pessimistic locking is enabled when the **Recordset** object is opened with the **LockType** parameter or property set to **adLockPessimistic**.</span></span> <span data-ttu-id="0880c-376">另请参阅**开放式锁定**。</span><span class="sxs-lookup"><span data-stu-id="0880c-376">See also **optimistic locking**.</span></span>

<span data-ttu-id="0880c-377">**池**</span><span class="sxs-lookup"><span data-stu-id="0880c-377">**pooling**</span></span>

<span data-ttu-id="0880c-378">优化性能基于使用预先分配的资源，如对象或数据库连接的集合。</span><span class="sxs-lookup"><span data-stu-id="0880c-378">A performance optimization based on using collections of pre-allocated resources, such as objects or database connections.</span></span> <span data-ttu-id="0880c-379">它是从比创建新资源池绘制现有资源更有效。</span><span class="sxs-lookup"><span data-stu-id="0880c-379">It is more efficient to draw an existing resource from the pool than to create a new resource.</span></span>

<span data-ttu-id="0880c-380">**ProgID （编程标识符）**</span><span class="sxs-lookup"><span data-stu-id="0880c-380">**ProgID (programmatic identifier)**</span></span>

<span data-ttu-id="0880c-381">COM 应用程序映射到 Windows 注册表的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="0880c-381">A unique name mapped to the Windows registry by a COM application.</span></span> <span data-ttu-id="0880c-382">ADO 连接的 ProgID 是"ADODB。连接"。</span><span class="sxs-lookup"><span data-stu-id="0880c-382">The ProgID for an ADO Connection is "ADODB.Connection".</span></span> <span data-ttu-id="0880c-383">请参阅**CLSID**， **COM**。</span><span class="sxs-lookup"><span data-stu-id="0880c-383">See also **CLSID**, **COM**.</span></span>

<span data-ttu-id="0880c-384">**代理**</span><span class="sxs-lookup"><span data-stu-id="0880c-384">**proxy**</span></span>

<span data-ttu-id="0880c-385">特定于接口的对象，提供参数封送处理和所需的客户端调用运行在不同的执行环境中，如在不同线程上或另一个进程中一个 application 对象的通信。</span><span class="sxs-lookup"><span data-stu-id="0880c-385">An interface-specific object that provides the parameter marshaling and communication required for a client to call an application object that is running in a different execution environment, such as on a different thread or in another process.</span></span> <span data-ttu-id="0880c-386">代理位于与客户端和通信与相应的存根位于所调用 application 对象。</span><span class="sxs-lookup"><span data-stu-id="0880c-386">The proxy is located with the client and communicates with a corresponding stub that is located with the application object that is being called.</span></span> <span data-ttu-id="0880c-387">请参阅**存根**。</span><span class="sxs-lookup"><span data-stu-id="0880c-387">See also **stub**.</span></span>

<span data-ttu-id="0880c-388">返回顶部</span><span class="sxs-lookup"><span data-stu-id="0880c-388">Return to top</span></span>

## <a name="r"></a><span data-ttu-id="0880c-389">R</span><span class="sxs-lookup"><span data-stu-id="0880c-389">R</span></span>

<span data-ttu-id="0880c-390">**相对 URL**</span><span class="sxs-lookup"><span data-stu-id="0880c-390">**relative URL**</span></span>

<span data-ttu-id="0880c-391">在 Internet 或 intranet 其位置是相对于指定的绝对 URL 或等效的 ADO Connection 对象的起始点指定的资源部分限定的 URL。</span><span class="sxs-lookup"><span data-stu-id="0880c-391">A partially qualified URL that specifies a resource on the Internet or an intranet whose location is relative to a starting point specified by an absolute URL or equivalent ADO Connection object.</span></span> <span data-ttu-id="0880c-392">实际上，串联绝对和相对 Url consitute 完整 URL。</span><span class="sxs-lookup"><span data-stu-id="0880c-392">In effect, the concatenated absolute and relative URLs consitute a complete URL.</span></span> <span data-ttu-id="0880c-393">请参阅**URL**和**绝对 URL**。</span><span class="sxs-lookup"><span data-stu-id="0880c-393">See also **URL** and **absolute URL**.</span></span>

<span data-ttu-id="0880c-394">**远程数据源**</span><span class="sxs-lookup"><span data-stu-id="0880c-394">**remote data source**</span></span>

<span data-ttu-id="0880c-395">数据源已存在另一台计算机，而不是本地系统上 （客户端应用程序运行位置）。</span><span class="sxs-lookup"><span data-stu-id="0880c-395">A data source that exists on a another computer, rather than on the local system (where the client application runs).</span></span>

<span data-ttu-id="0880c-396">**资源记录**</span><span class="sxs-lookup"><span data-stu-id="0880c-396">**resource record**</span></span>

<span data-ttu-id="0880c-397">包含字段的定义和文件夹或文档的描述文档源提供程序中的记录。</span><span class="sxs-lookup"><span data-stu-id="0880c-397">A record from a document source provider that contains fields for the definition and description of a folder or document.</span></span> <span data-ttu-id="0880c-398">文档本身不包含在资源记录，但通常可以访问的默认流或包含 URL 的资源记录中的字段。</span><span class="sxs-lookup"><span data-stu-id="0880c-398">The document itself is not contained in the resource record but typically can be accessed by the default stream or a field in the resource record containing a URL.</span></span> <span data-ttu-id="0880c-399">请参阅还**文档源提供程序**，**默认流**， **URL**。</span><span class="sxs-lookup"><span data-stu-id="0880c-399">See also **document source provider**, **default stream**, **URL**.</span></span>

<span data-ttu-id="0880c-400">**根**</span><span class="sxs-lookup"><span data-stu-id="0880c-400">**root**</span></span>

<span data-ttu-id="0880c-401">中的顶层一个分层树结构。</span><span class="sxs-lookup"><span data-stu-id="0880c-401">The top level in a hierarchical tree structure.</span></span> <span data-ttu-id="0880c-402">根节点没有父，但可能有子级。</span><span class="sxs-lookup"><span data-stu-id="0880c-402">The root node has no parents, but may have children.</span></span> <span data-ttu-id="0880c-403">请参阅**层次结构**、**树**、**父**和**子**。</span><span class="sxs-lookup"><span data-stu-id="0880c-403">See also **hierarchy**, **tree**, **parent**, **child**.</span></span>

<span data-ttu-id="0880c-404">**行集**</span><span class="sxs-lookup"><span data-stu-id="0880c-404">**rowset**</span></span>

<span data-ttu-id="0880c-405">一组数据源，所有具有相同的字段架构中的行。</span><span class="sxs-lookup"><span data-stu-id="0880c-405">A set of rows from a data source, all having the same field schema.</span></span> <span data-ttu-id="0880c-406">行集可以表示表中的所有或某些字段。</span><span class="sxs-lookup"><span data-stu-id="0880c-406">A rowset can represent all or some fields from a table.</span></span> <span data-ttu-id="0880c-407">行集还可以表示由查询或两个或多个表的联接创建的虚拟表。</span><span class="sxs-lookup"><span data-stu-id="0880c-407">A rowset can also represent a virtual table, created by a query or a join of two or more tables.</span></span> <span data-ttu-id="0880c-408">在 ADO 中，由**Recordset**对象表示行集。</span><span class="sxs-lookup"><span data-stu-id="0880c-408">In ADO, rowsets are represented by **Recordset** objects.</span></span>

<span data-ttu-id="0880c-409">返回顶部</span><span class="sxs-lookup"><span data-stu-id="0880c-409">Return to top</span></span>

## <a name="s"></a><span data-ttu-id="0880c-410">S</span><span class="sxs-lookup"><span data-stu-id="0880c-410">S</span></span>

<span data-ttu-id="0880c-411">**架构**</span><span class="sxs-lookup"><span data-stu-id="0880c-411">**schema**</span></span>

<span data-ttu-id="0880c-412">数据库的数据库管理系统 (DBMS)，通常使用由 DBMS 提供的数据定义语言生成的说明。</span><span class="sxs-lookup"><span data-stu-id="0880c-412">A description of a database to the database management system (DBMS), typically generated using the data definition language provided by the DBMS.</span></span> <span data-ttu-id="0880c-413">架构定义的数据库，如表、 列和属性的属性。</span><span class="sxs-lookup"><span data-stu-id="0880c-413">A schema defines attributes of the database, such as tables, columns, and properties.</span></span>

<span data-ttu-id="0880c-414">**scope**</span><span class="sxs-lookup"><span data-stu-id="0880c-414">**scope**</span></span>

<span data-ttu-id="0880c-415">参考 （英文） 的对象或变量或视图或表中的记录区域的区域。</span><span class="sxs-lookup"><span data-stu-id="0880c-415">The range of reference for an object or variable or a range of records in a view or table.</span></span> <span data-ttu-id="0880c-416">例如，可以仅在其中定义的过程中引用本地变量。</span><span class="sxs-lookup"><span data-stu-id="0880c-416">For example, local variables can be referenced only within the procedure in which they were defined.</span></span> <span data-ttu-id="0880c-417">Public 变量是可从任意位置的应用程序中访问。</span><span class="sxs-lookup"><span data-stu-id="0880c-417">Public variables are accessible from anywhere in the application.</span></span> <span data-ttu-id="0880c-418">对象，如当前数据库，位于范围，它们是否中定义的搜索路径。</span><span class="sxs-lookup"><span data-stu-id="0880c-418">Objects, such as the current database, are in scope if they are in the defined search path.</span></span> <span data-ttu-id="0880c-419">可以使用多个命令中的范围子句中指定记录的范围。</span><span class="sxs-lookup"><span data-stu-id="0880c-419">Record ranges can be specified with a Scope clause in many commands.</span></span>

<span data-ttu-id="0880c-420">**服务提供商**</span><span class="sxs-lookup"><span data-stu-id="0880c-420">**service provider**</span></span>

<span data-ttu-id="0880c-421">通过生成和使用数据，并增加 ADO 应用程序中的功能来封装服务的软件。</span><span class="sxs-lookup"><span data-stu-id="0880c-421">Software that encapsulates a service by producing and consuming data, augmenting features in your ADO applications.</span></span> <span data-ttu-id="0880c-422">不直接公开数据提供程序，而不显示，它提供了一种服务，如查询处理。</span><span class="sxs-lookup"><span data-stu-id="0880c-422">It is a provider that does not directly expose data, rather it provides a service, such as query processing.</span></span> <span data-ttu-id="0880c-423">服务提供程序可以处理数据提供程序提供的数据。</span><span class="sxs-lookup"><span data-stu-id="0880c-423">The service provider may process data provided by a data provider.</span></span> <span data-ttu-id="0880c-424">请参阅**数据提供程序**。</span><span class="sxs-lookup"><span data-stu-id="0880c-424">See also **data provider**.</span></span>

<span data-ttu-id="0880c-425">**定形的 Recordset**</span><span class="sxs-lookup"><span data-stu-id="0880c-425">**shaped Recordset**</span></span>

<span data-ttu-id="0880c-426">**记录集**已专门定义其列到其他**Recordset**对象和/或其他**Recordset**对象所基于的计算的值包含而不仅仅是数据，但还 （称为章节） 的引用。</span><span class="sxs-lookup"><span data-stu-id="0880c-426">A **Recordset** whose columns have been specifically defined to contain not just data, but also references (called chapters) to other **Recordset** objects and/or computed values based on other **Recordset** objects.</span></span>

<span data-ttu-id="0880c-427">**同级**</span><span class="sxs-lookup"><span data-stu-id="0880c-427">**sibling**</span></span>

<span data-ttu-id="0880c-428">任何两个或多个层次结构中节点上层次结构中相同的级别。</span><span class="sxs-lookup"><span data-stu-id="0880c-428">Any two or more nodes in a hierarchical structure that are on the same level in the hierarchy.</span></span> <span data-ttu-id="0880c-429">层次结构中的根节点具有没有同级。</span><span class="sxs-lookup"><span data-stu-id="0880c-429">The root node in a hierarchy has no siblings.</span></span>

<span data-ttu-id="0880c-430">**存储的过程**</span><span class="sxs-lookup"><span data-stu-id="0880c-430">**stored procedure**</span></span>

<span data-ttu-id="0880c-431">如 SQL 语句和可选的控制流语句的代码的预编译的集合存储在名称下，并作为一个整体。</span><span class="sxs-lookup"><span data-stu-id="0880c-431">A precompiled collection of code such as SQL statements and optional control-of-flow statements stored under a name and processed as a unit.</span></span> <span data-ttu-id="0880c-432">存储的过程存储在数据库;他们可以通过从应用程序的一个呼叫执行，并允许用户声明的变量、 条件执行和其他功能强大的编程功能。</span><span class="sxs-lookup"><span data-stu-id="0880c-432">Stored procedures are stored within a database; they can be executed with one call from an application and allow user-declared variables, conditional execution, and other powerful programming features.</span></span>

<span data-ttu-id="0880c-433">**存根**</span><span class="sxs-lookup"><span data-stu-id="0880c-433">**stub**</span></span>

<span data-ttu-id="0880c-434">特定于接口的对象，提供参数封送处理和通信所需的应用程序对象从运行在不同的执行环境中，如在不同线程上或另一个进程中的客户端接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="0880c-434">An interface-specific object that provides the parameter marshaling and communication required for an application object to receive calls from a client that is running in a different execution environment, such as on a different thread or in another process.</span></span> <span data-ttu-id="0880c-435">存根位于 application 对象，并具有与客户端调用它所在的相应代理进行通信。</span><span class="sxs-lookup"><span data-stu-id="0880c-435">The stub is located with the application object and communicates with a corresponding proxy that is located with the client that calls it.</span></span> <span data-ttu-id="0880c-436">另请参阅**代理**。</span><span class="sxs-lookup"><span data-stu-id="0880c-436">See also **proxy**.</span></span>

<span data-ttu-id="0880c-437">**子节点**</span><span class="sxs-lookup"><span data-stu-id="0880c-437">**sub-node**</span></span>

<span data-ttu-id="0880c-438">请参阅**子级**。</span><span class="sxs-lookup"><span data-stu-id="0880c-438">See **child**.</span></span>

<span data-ttu-id="0880c-439">**同步操作**</span><span class="sxs-lookup"><span data-stu-id="0880c-439">**synchronous operation**</span></span>

<span data-ttu-id="0880c-440">下一步操作可能会启动之前完成的代码由启动的操作。</span><span class="sxs-lookup"><span data-stu-id="0880c-440">An operation initiated by code that completes before the next operation may start.</span></span> <span data-ttu-id="0880c-441">请参阅**异步操作**。</span><span class="sxs-lookup"><span data-stu-id="0880c-441">See also **asynchronous operation**.</span></span>

<span data-ttu-id="0880c-442">返回顶部</span><span class="sxs-lookup"><span data-stu-id="0880c-442">Return to top</span></span>

## <a name="t-w"></a><span data-ttu-id="0880c-443">T-W</span><span class="sxs-lookup"><span data-stu-id="0880c-443">T-W</span></span>

<span data-ttu-id="0880c-444">**树**</span><span class="sxs-lookup"><span data-stu-id="0880c-444">**tree**</span></span>

<span data-ttu-id="0880c-445">表示元素 （节点） 之间的分层关系的结构。</span><span class="sxs-lookup"><span data-stu-id="0880c-445">A structure representing a hierarchical relationship between elements (nodes).</span></span> <span data-ttu-id="0880c-446">在顶级 （根） 树的没有一个节点。</span><span class="sxs-lookup"><span data-stu-id="0880c-446">There is one node at the top level of a tree (the root).</span></span> <span data-ttu-id="0880c-447">下方根目录中，可以有多个子级。</span><span class="sxs-lookup"><span data-stu-id="0880c-447">Underneath the root, there can be multiple children.</span></span> <span data-ttu-id="0880c-448">每个子反过来可能其他子级，因此分支像树的父对象。</span><span class="sxs-lookup"><span data-stu-id="0880c-448">Each child may in turn be the parent of other children, thus branching like a tree.</span></span> <span data-ttu-id="0880c-449">包含文档和其他文件夹的文件夹是树状结构中的典型示例。</span><span class="sxs-lookup"><span data-stu-id="0880c-449">A folder containing documents and other folders is a typical example of a tree structure.</span></span> <span data-ttu-id="0880c-450">请参阅**层次结构**、**节点**、**根**、**子**和**父**。</span><span class="sxs-lookup"><span data-stu-id="0880c-450">See also **hierarchy**, **node**, **root**, **child**, **parent**.</span></span>

<span data-ttu-id="0880c-451">**URL （统一资源定位器）**</span><span class="sxs-lookup"><span data-stu-id="0880c-451">**URL (Uniform Resource Locator)**</span></span>

<span data-ttu-id="0880c-452">指定驻留在 Internet 或 intranet 上的资源的位置。</span><span class="sxs-lookup"><span data-stu-id="0880c-452">Specifies the location of a resource residing on the Internet or an intranet.</span></span> <span data-ttu-id="0880c-453">完整的 URL 包含配色方案 （如 FTP、 HTTP、 mailto、 文件，等等） 后, 跟一个冒号和一个服务器名称，资源 （如文档、 图片或其他文件） 的完整路径。</span><span class="sxs-lookup"><span data-stu-id="0880c-453">A complete URL consists of a scheme (such as FTP, HTTP, mailto, file, and so on), followed by a colon, a server name, and the full path of a resource (such as a document, graphic, or other file).</span></span> <span data-ttu-id="0880c-454">Url 的一些示例包括：</span><span class="sxs-lookup"><span data-stu-id="0880c-454">Some examples of URLs are:</span></span>  
  
https://www.domain.com/default.html  
<span data-ttu-id="0880c-455">ftp://ftp.server.somewhere/ftp.file</span><span class="sxs-lookup"><span data-stu-id="0880c-455">ftp://ftp.server.somewhere/ftp.file</span></span>  
  
<span data-ttu-id="0880c-456">ftp://ftp.server.somewhere/ftp.file</span><span class="sxs-lookup"><span data-stu-id="0880c-456">ftp://ftp.server.somewhere/ftp.file</span></span>  
<span data-ttu-id="0880c-457">file://Server/Share/File.doc</span><span class="sxs-lookup"><span data-stu-id="0880c-457">file://Server/Share/File.doc</span></span>

<span data-ttu-id="0880c-458">另请参阅**绝对 URL**和**相对 URL**。</span><span class="sxs-lookup"><span data-stu-id="0880c-458">See also **absolute URL** and **relative URL**.</span></span>

<span data-ttu-id="0880c-459"><<<<<<< 标头**Web 服务器**</span><span class="sxs-lookup"><span data-stu-id="0880c-459"><<<<<<< HEAD **Web server**</span></span>

<a name="a-computer-that-provides-web-services-and-pages-to-intranet-and-internet-users"></a><span data-ttu-id="0880c-460">提供 Web 服务和页 intranet 和 Internet 用户的计算机。</span><span class="sxs-lookup"><span data-stu-id="0880c-460">A computer that provides Web services and pages to intranet and Internet users.</span></span>
=======
<span data-ttu-id="0880c-461">**web 服务器**</span><span class="sxs-lookup"><span data-stu-id="0880c-461">**web server**</span></span>

<span data-ttu-id="0880c-462">提供 web 服务和页 intranet 和 Internet 用户的计算机。</span><span class="sxs-lookup"><span data-stu-id="0880c-462">A computer that provides web services and pages to intranet and Internet users.</span></span>
>>>>>>> <span data-ttu-id="0880c-463">master</span><span class="sxs-lookup"><span data-stu-id="0880c-463">master</span></span>

<span data-ttu-id="0880c-464">返回顶部</span><span class="sxs-lookup"><span data-stu-id="0880c-464">Return to top</span></span>

