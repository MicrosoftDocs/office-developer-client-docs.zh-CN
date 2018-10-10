---
title: 参数化命令的操作
TOCTitle: Operation of Parameterized Commands
ms:assetid: 71edbd16-21db-7afa-356b-d8e7afb92b3a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249456(v=office.15)
ms:contentKeyID: 48545596
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 42f0e8ffc7472dbf8a8c03fa320d3ae2b4a2e21b
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468817"
---
# <a name="operation-of-parameterized-commands"></a><span data-ttu-id="9abaa-102">参数化命令的操作</span><span class="sxs-lookup"><span data-stu-id="9abaa-102">Operation of Parameterized Commands</span></span>


<span data-ttu-id="9abaa-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="9abaa-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="9abaa-104">如果要使用大型子 **Recordset** （尤其是与父 **Recordset** 的大小相比较），但只需要访问少量子章节，则可能发现使用参数化命令会更有效。</span><span class="sxs-lookup"><span data-stu-id="9abaa-104">If you are working with a large child **Recordset**, especially compared to the size of the parent **Recordset**, but need to access only a few child chapters, you might find it more efficient to use a parameterized command.</span></span>

<span data-ttu-id="9abaa-105">*非参数化命令*检索整个父和子**Recordset**和追加章节列到父级，然后分配对每个父行的相关的子章节的引用。</span><span class="sxs-lookup"><span data-stu-id="9abaa-105">A *non-parameterized command* retrieves both the entire parent and child **Recordsets**, appends a chapter column to the parent, and then assigns a reference to the related child chapter for each parent row.</span></span>

<span data-ttu-id="9abaa-106">*参数化的命令*检索整个父**记录集**，但访问的章节列时检索仅章**Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="9abaa-106">A *parameterized command* retrieves the entire parent **Recordset**, but retrieves only the chapter **Recordset** when the chapter column is accessed.</span></span> <span data-ttu-id="9abaa-107">此检索策略差异可以产生极大的性能收益。</span><span class="sxs-lookup"><span data-stu-id="9abaa-107">This difference in retrieval strategy can yield significant performance benefits.</span></span>

<span data-ttu-id="9abaa-108">例如，可以指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="9abaa-108">For example, you can specify the following:</span></span>

```vb 
 
SHAPE {SELECT * FROM customer} 
 APPEND ({SELECT * FROM orders WHERE cust_id = ?} 
 RELATE cust_id TO PARAMETER 0) 
```

<span data-ttu-id="9abaa-109">父和子表中常见，客户具有列名称\_*。* id</span><span class="sxs-lookup"><span data-stu-id="9abaa-109">The parent and child tables have a column name in common, cust\_id *.*</span></span> <span data-ttu-id="9abaa-110">*子命令*具有对建立关系子句所指的"?"占位符 (即"...参数 0"）。</span><span class="sxs-lookup"><span data-stu-id="9abaa-110">The *child-command* has a "?" placeholder, to which the RELATE clause refers (that is, "...PARAMETER 0").</span></span>


> [!NOTE]
> <P><span data-ttu-id="9abaa-p103">[!注释] PARAMETER 子句仅仅属于 Shape 命令语法。它不与 ADO <A href="parameter-object-ado.md">Parameter</A> 对象或 <A href="parameters-collection-ado.md">Parameters</A> 集合关联。</span><span class="sxs-lookup"><span data-stu-id="9abaa-p103">The PARAMETER clause pertains solely to the shape command syntax. It is not associated with either the ADO <A href="parameter-object-ado.md">Parameter</A> object or the <A href="parameters-collection-ado.md">Parameters</A> collection.</span></span></P>



<span data-ttu-id="9abaa-113">执行参数化 Shape 命令时，将发生以下操作：</span><span class="sxs-lookup"><span data-stu-id="9abaa-113">When the parameterized shape command is executed, the following occurs:</span></span>

1.  <span data-ttu-id="9abaa-114">*父命令*将执行，并从客户表返回父**Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="9abaa-114">The *parent-command* is executed and returns a parent **Recordset** from the Customers table.</span></span>

2.  <span data-ttu-id="9abaa-115">向父 **Recordset** 追加章节列。</span><span class="sxs-lookup"><span data-stu-id="9abaa-115">A chapter column is appended to the parent **Recordset**.</span></span>

3.  <span data-ttu-id="9abaa-116">当访问父行的章节列时，使用 customer.cust 的值执行*子命令*\_id 作为参数的值。</span><span class="sxs-lookup"><span data-stu-id="9abaa-116">When the chapter column of a parent row is accessed, the *child-command* is executed using the value of the customer.cust\_id as the value of the parameter.</span></span>

4.  <span data-ttu-id="9abaa-117">使用在步骤 3 中创建的数据提供程序行集的所有行来填充子 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="9abaa-117">All rows in the data provider rowset created in step 3 are used to populate the child **Recordset**.</span></span> <span data-ttu-id="9abaa-118">在此示例中，该元素是在其中订单表中的所有行客户\_id 等于的 customer.cust 值\_id。</span><span class="sxs-lookup"><span data-stu-id="9abaa-118">In this example, that is all the rows in the Orders table in which the cust\_id equals the value of customer.cust\_id.</span></span> <span data-ttu-id="9abaa-119">默认情况下的子**Recordset**s 将进行缓存在客户端上直到释放所有引用父**Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="9abaa-119">By default, the child **Recordset**s will be cached on the client until all references to the parent **Recordset** are released.</span></span> <span data-ttu-id="9abaa-120">若要更改此行为，请将**Recordset** [动态属性](ado-dynamic-property-index.md)**缓存子行**设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="9abaa-120">To change this behavior, set the **Recordset** [dynamic property](ado-dynamic-property-index.md)**Cache Child Rows** to **False**.</span></span>

5.  <span data-ttu-id="9abaa-121">对所检索的子行的引用（即子 **Recordset** 的章节）将放在父 **Recordset** 的当前行的章节列中。</span><span class="sxs-lookup"><span data-stu-id="9abaa-121">A reference to the retrieved child rows (that is, the chapter of the child **Recordset**) is placed in the chapter column of the current row of the parent **Recordset**.</span></span>

6.  <span data-ttu-id="9abaa-122">在访问另一个行的章节列时，将重复步骤 3–5。</span><span class="sxs-lookup"><span data-stu-id="9abaa-122">Steps 3–5 are repeated when the chapter column of another row is accessed.</span></span>

<span data-ttu-id="9abaa-p105">默认情况下， **Cache Child Rows** 动态属性设置为 **True** 。缓存行为因查询的参数值而异。在使用单个参数的查询中，在请求具有该值的子项的间隔期中，系统将缓存给定参数值的子 **Recordset** 。以下代码演示了这种情况：</span><span class="sxs-lookup"><span data-stu-id="9abaa-p105">The **Cache Child Rows** dynamic property is set to **True** by default. The caching behavior varies depending upon the parameter values of the query. In a query with a single parameter, the child **Recordset** for a given parameter value will be cached between requests for a child with that value. The following code demonstrates this:</span></span>

```vb 
 
... 
SCmd = "SHAPE {select * from customer} " & _ 
 "APPEND({select * from orders where cust_id = ?} " & _ 
 "RELATE cust_id TO PARAMETER 0) AS chpCustOrder" 
Rst1.Open sCmd, Cnn1 
Set RstChild = Rst1("chpCustOrder").Value 
Rst1.MoveNext ' Next cust_id passed to Param 0, & new rs fetched 
 ' into RstChild. 
Rst1.MovePrevious ' RstChild now holds cached rs, saving round trip. 
... 
```

<span data-ttu-id="9abaa-127">在具有两个或更多个参数的查询中，只有当所有参数值都与缓存值匹配时，才会使用缓存的子项。</span><span class="sxs-lookup"><span data-stu-id="9abaa-127">In a query with two or more parameters, a cached child is used only if all the parameter values match the cached values.</span></span>

## <a name="parameterized-commands-and-complex-parent-child-relations"></a><span data-ttu-id="9abaa-128">参数化命令和复杂的父子关系</span><span class="sxs-lookup"><span data-stu-id="9abaa-128">Parameterized Commands and Complex Parent Child Relations</span></span>

<span data-ttu-id="9abaa-129">除了使用参数化命令来改进 equi-join 类型层次结构的性能以外，还可以用参数化命令来支持更复杂的父子关系。</span><span class="sxs-lookup"><span data-stu-id="9abaa-129">In addition to using parameterized commands to improve performance of an equi-join type hierarchy, parameterized commands can be used to support more complex parent-child relationships.</span></span> <span data-ttu-id="9abaa-130">例如，考虑两个表少联盟的数据库： 一个包含团队 (团队\_id、 团队\_名称) 和其他的游戏 (日期，主\_团队，访问\_团队)。</span><span class="sxs-lookup"><span data-stu-id="9abaa-130">For example, consider a Little League database with two tables: one consisting of the teams (team\_id, team\_name) and the other of games (date, home\_team, visiting\_team).</span></span>

<span data-ttu-id="9abaa-131">如果使用非参数化层次结构，则无法通过让团队表和比赛表相关来使每个团队的子 **Recordset** 都包含它已完成的赛程。</span><span class="sxs-lookup"><span data-stu-id="9abaa-131">Using a non-parameterized hierarchy, there is no way to relate the teams and games tables in such a way that the child **Recordset** for each team contains its complete schedule.</span></span> <span data-ttu-id="9abaa-132">可以创建包含主场赛程或客场赛程（但不同时包含这二者）的章节。</span><span class="sxs-lookup"><span data-stu-id="9abaa-132">You can create chapters that contain the home schedule or the road schedule, but not both.</span></span> <span data-ttu-id="9abaa-133">这是因为 RELATE 子句使您只能建立形式为 (pc1=cc1) AND (pc2=pc2) 的父子关系。</span><span class="sxs-lookup"><span data-stu-id="9abaa-133">This is because the RELATE clause limits you to parent-child relationships of the form (pc1=cc1) AND (pc2=pc2).</span></span> <span data-ttu-id="9abaa-134">因此，如果您的命令包括"建立关系团队\_id 收件人主页\_团队、 团队\_id 与访问\_团队"，您将获取仅游戏团队已播放本身。</span><span class="sxs-lookup"><span data-stu-id="9abaa-134">So, if your command included "RELATE team\_id TO home\_team, team\_id TO visiting\_team", you would get only games where a team was playing itself.</span></span> <span data-ttu-id="9abaa-135">您需要的是"(团队\_id = 主页\_团队) 或者 (团队\_id = 访问\_团队)"，但形状提供程序不支持 OR 子句。</span><span class="sxs-lookup"><span data-stu-id="9abaa-135">What you want is "(team\_id=home\_team) OR (team\_id=visiting\_team)", but the Shape provider does not support the OR clause.</span></span>

<span data-ttu-id="9abaa-p108">若要获得希望的结果，可以使用参数化命令。例如：</span><span class="sxs-lookup"><span data-stu-id="9abaa-p108">To obtain the desired result, you can use a parameterized command. For example:</span></span>

```vb 
 
SHAPE {SELECT * FROM teams} 
APPEND ({SELECT * FROM games WHERE home_team = ? OR visiting_team = ?} 
 RELATE team_id TO PARAMETER 0, 
 team_id TO PARAMETER 1) 
```

<span data-ttu-id="9abaa-138">此示例利用 SQL WHERE 子句具有的更大灵活性来获得需要的结果。</span><span class="sxs-lookup"><span data-stu-id="9abaa-138">This example exploits the greater flexibility of the SQL WHERE clause to get the result you need.</span></span>

