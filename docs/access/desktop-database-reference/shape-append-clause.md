---
title: Shape Append 子句
TOCTitle: Shape Append Clause
ms:assetid: 8f29afc3-fb93-4439-b67b-cad0eed0bda9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249633(v=office.15)
ms:contentKeyID: 48546301
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: cb8e60c52ded359350adff737807c3e0f92cb7c4
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25862121"
---
# <a name="shape-append-clause"></a><span data-ttu-id="a2cd4-102">Shape Append 子句</span><span class="sxs-lookup"><span data-stu-id="a2cd4-102">Shape Append Clause</span></span>


<span data-ttu-id="a2cd4-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="a2cd4-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="a2cd4-p101">shape 命令 APPEND 子句用于将一个或多个列追加到 **Recordset** 中。通常，这些列是章节列，而章节列是对子 **Recordset** 的引用。</span><span class="sxs-lookup"><span data-stu-id="a2cd4-p101">The shape command APPEND clause appends a column or columns to a **Recordset**. Often these columns are chapter columns, which refer to a child **Recordset**.</span></span>

## <a name="syntax"></a><span data-ttu-id="a2cd4-106">语法</span><span class="sxs-lookup"><span data-stu-id="a2cd4-106">Syntax</span></span>

```vb 
 
SHAPE [parent-command [[AS] parent-alias]] APPEND column-list
```

## <a name="description"></a><span data-ttu-id="a2cd4-107">说明</span><span class="sxs-lookup"><span data-stu-id="a2cd4-107">Description</span></span>

<span data-ttu-id="a2cd4-108">此子句的各部分如下所示：</span><span class="sxs-lookup"><span data-stu-id="a2cd4-108">The parts of this clause are as follows:</span></span>

- <span data-ttu-id="a2cd4-109">*parent-command*</span><span class="sxs-lookup"><span data-stu-id="a2cd4-109">*parent-command*</span></span>

- <span data-ttu-id="a2cd4-110">零个或者 （可以完全省略*父命令*） 以下一项：</span><span class="sxs-lookup"><span data-stu-id="a2cd4-110">Zero or one of the following (you may omit the *parent-command* entirely):</span></span>
    
  - <span data-ttu-id="a2cd4-p102">返回 {} 对象的提供程序命令，放在大括号（"\*\*\*\*"）中。该命令向基础数据提供程序发出，其语法取决于该提供程序的要求。这通常是 SQL 语言，但 ADO 不需要任何特定的查询语言。</span><span class="sxs-lookup"><span data-stu-id="a2cd4-p102">A provider command within curly braces ("{}") that returns a **Recordset** object. The command is issued to the underlying data provider, and its syntax depends on the requirements of that provider. This will typically be the SQL language, although ADO does not require any particular query language.</span></span>
    
  - <span data-ttu-id="a2cd4-114">嵌入在括号中的另一个 Shape 命令。</span><span class="sxs-lookup"><span data-stu-id="a2cd4-114">Another shape command embedded in parentheses.</span></span>
    
  - <span data-ttu-id="a2cd4-115">TABLE 关键字，后跟数据提供程序中的表的名称。</span><span class="sxs-lookup"><span data-stu-id="a2cd4-115">The TABLE keyword, followed by the name of a table in the data provider.</span></span>

- <span data-ttu-id="a2cd4-116">*parent-alias*</span><span class="sxs-lookup"><span data-stu-id="a2cd4-116">*parent-alias*</span></span>

  - <span data-ttu-id="a2cd4-117">用于引用父 **Recordset** 的可选别名。</span><span class="sxs-lookup"><span data-stu-id="a2cd4-117">An optional alias that refers to the parent **Recordset**.</span></span>

- <span data-ttu-id="a2cd4-118">*column-list*</span><span class="sxs-lookup"><span data-stu-id="a2cd4-118">*column-list*</span></span>

  - <span data-ttu-id="a2cd4-119">一个或多个以下项：</span><span class="sxs-lookup"><span data-stu-id="a2cd4-119">One or more of the following:</span></span>
    
    - <span data-ttu-id="a2cd4-120">聚合列。</span><span class="sxs-lookup"><span data-stu-id="a2cd4-120">An aggregate column.</span></span>
    
    - <span data-ttu-id="a2cd4-121">计算列。</span><span class="sxs-lookup"><span data-stu-id="a2cd4-121">A calculated column.</span></span>
    
    - <span data-ttu-id="a2cd4-122">用 NEW 子句创建的新列。</span><span class="sxs-lookup"><span data-stu-id="a2cd4-122">A new column created with the NEW clause.</span></span>
    
    - <span data-ttu-id="a2cd4-p103">章节列。章节列的定义放在括号（"()"）中。请参阅以下语法：</span><span class="sxs-lookup"><span data-stu-id="a2cd4-p103">A chapter column. A chapter column definition is enclosed in parentheses ("()"). See syntax below:</span></span>


        ```vb 
        
        SHAPE [parent-command [[AS] parent-alias]] 
        APPEND (child-recordset [ [[AS] child-alias] 
        RELATE parent-column TO child-column | PARAMETER param-number, ... ]) 
        [[AS] chapter-alias] 
        [, ... ] 
        ```

- <span data-ttu-id="a2cd4-126">*child-recordset*</span><span class="sxs-lookup"><span data-stu-id="a2cd4-126">*child-recordset*</span></span>

  - <span data-ttu-id="a2cd4-p104">返回 {} 对象的提供程序命令，放在大括号（"\*\*\*\*"）中。该命令向基础数据提供程序发出，其语法取决于该提供程序的要求。这通常是 SQL 语言，但 ADO 不需要任何特定的查询语言。</span><span class="sxs-lookup"><span data-stu-id="a2cd4-p104">A provider command within curly braces ("{}") that returns a **Recordset** object. The command is issued to the underlying data provider, and its syntax depends on the requirements of that provider. This will typically be the SQL language, although ADO does not require any particular query language.</span></span>
    
  - <span data-ttu-id="a2cd4-130">嵌入在括号中的另一个 Shape 命令。</span><span class="sxs-lookup"><span data-stu-id="a2cd4-130">Another shape command embedded in parentheses.</span></span>
    
  - <span data-ttu-id="a2cd4-131">现有已构形 **Recordset** 的名称。</span><span class="sxs-lookup"><span data-stu-id="a2cd4-131">The name of an existing shaped **Recordset**.</span></span>
    
  - <span data-ttu-id="a2cd4-132">TABLE 关键字，后跟数据提供程序中的表的名称。</span><span class="sxs-lookup"><span data-stu-id="a2cd4-132">The TABLE keyword, followed by the name of a table in the data provider.</span></span>

- <span data-ttu-id="a2cd4-133">*child-alias*</span><span class="sxs-lookup"><span data-stu-id="a2cd4-133">*child-alias*</span></span>

  - <span data-ttu-id="a2cd4-134">引用子 **Recordset** 的别名。</span><span class="sxs-lookup"><span data-stu-id="a2cd4-134">An alias that refers to the child **Recordset**.</span></span>

- <span data-ttu-id="a2cd4-135">*parent-column*</span><span class="sxs-lookup"><span data-stu-id="a2cd4-135">*parent-column*</span></span>

  - <span data-ttu-id="a2cd4-136">返回**Recordset**中的列*父命令。*</span><span class="sxs-lookup"><span data-stu-id="a2cd4-136">A column in the **Recordset** returned by the *parent-command.*</span></span>

- <span data-ttu-id="a2cd4-137">*child-column*</span><span class="sxs-lookup"><span data-stu-id="a2cd4-137">*child-column*</span></span>

  - <span data-ttu-id="a2cd4-138">由 *child-command* 返回的 **Recordset** 中的列。</span><span class="sxs-lookup"><span data-stu-id="a2cd4-138">A column in the **Recordset** returned by the *child-command*.</span></span>

- <span data-ttu-id="a2cd4-139">*param-number*</span><span class="sxs-lookup"><span data-stu-id="a2cd4-139">*param-number*</span></span>

  - <span data-ttu-id="a2cd4-140">请参阅[参数化命令的操作](operation-of-parameterized-commands.md)。</span><span class="sxs-lookup"><span data-stu-id="a2cd4-140">See [Operation of Parameterized Commands](operation-of-parameterized-commands.md).</span></span>

- <span data-ttu-id="a2cd4-141">*chapter-alias*</span><span class="sxs-lookup"><span data-stu-id="a2cd4-141">*chapter-alias*</span></span>

  - <span data-ttu-id="a2cd4-142">引用追加到父记录集的章节列的别名。</span><span class="sxs-lookup"><span data-stu-id="a2cd4-142">An alias that refers to the chapter column appended to the parent.</span></span>


> [!NOTE]
> - <span data-ttu-id="a2cd4-143">_"父列收件人子-列"_ 子句实际上是一个列表，其中每个关系定义并用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="a2cd4-143">The _"parent-column TO child-column"_ clause is actually a list, where each relation defined is separated by a comma.</span></span>
> - <span data-ttu-id="a2cd4-144">[!注释] APPEND 关键字后面的子句实际上是列表，其中每个子句均以逗号分隔，并且定义了要追加到父记录集的其他列。</span><span class="sxs-lookup"><span data-stu-id="a2cd4-144">The clause after the APPEND keyword is actually a list, where each clause is separated by a comma and defines another column to be appended to the parent.</span></span>



## <a name="remarks"></a><span data-ttu-id="a2cd4-145">说明</span><span class="sxs-lookup"><span data-stu-id="a2cd4-145">Remarks</span></span>

<span data-ttu-id="a2cd4-p105">利用用户输入来构造提供程序命令以便将其作为 SHAPE 命令的一部分时，SHAPE 会将用户提供的提供程序命令当作不透明的字符串，并如实地传递给提供程序。例如，在以下 SHAPE 命令中，</span><span class="sxs-lookup"><span data-stu-id="a2cd4-p105">When you construct provider commands from user input as part of a SHAPE command, SHAPE will treat the user-supplied a provider command as an opaque string and pass them faithfully to the provider. For example, in the following SHAPE command,</span></span>

```vb 
 
SHAPE {select * from t1} APPEND ({select * from t2} RELATE k1 TO k2) 
```

<span data-ttu-id="a2cd4-148">形状将执行两个命令： 选择\*从 t1 和 (选择\*从 t2 建立关系版 k1 收件人 k2)。</span><span class="sxs-lookup"><span data-stu-id="a2cd4-148">SHAPE will execute two commands: select \* from t1 and (select \* from t2 RELATE k1 TO k2).</span></span> <span data-ttu-id="a2cd4-149">如果用户提供了由多个提供程序命令组成并以分号分隔的复合命令，SHAPE 将无法辨别差异。</span><span class="sxs-lookup"><span data-stu-id="a2cd4-149">If the user supplies a compound command consisting of multiple provider commands separated by semicolons, SHAPE is not able to discern the difference.</span></span> <span data-ttu-id="a2cd4-150">因此，在以下 SHAPE 命令中，</span><span class="sxs-lookup"><span data-stu-id="a2cd4-150">So in the following SHAPE command,</span></span>

```vb 
 
SHAPE {select * from t1; drop table t1} APPEND ({select * from t2} RELATE k1 TO k2) 
```

<span data-ttu-id="a2cd4-151">形状执行选择\*从 t1;drop 表 t1 和 (选择\*从 t2 建立关系版 k1 收件人 k2)，未意识到的投递表 t1 单独和在此案例、 危险，提供程序命令。</span><span class="sxs-lookup"><span data-stu-id="a2cd4-151">SHAPE executes select \* from t1; drop table t1 and (select \* from t2 RELATE k1 TO k2), not realizing that drop table t1 is a separate and in this case, dangerous, provider command.</span></span> <span data-ttu-id="a2cd4-152">应用程序必须始终验证用户输入，以防止发生类似潜在黑客攻击。</span><span class="sxs-lookup"><span data-stu-id="a2cd4-152">Applications must always validate the user input to prevent such potential hacker attacks from happening.</span></span>

<span data-ttu-id="a2cd4-153">本节包括下列主题：</span><span class="sxs-lookup"><span data-stu-id="a2cd4-153">This section includes the following topics:</span></span>

- [<span data-ttu-id="a2cd4-154">非参数化命令的操作</span><span class="sxs-lookup"><span data-stu-id="a2cd4-154">Operation of Non-Parameterized Commands</span></span>](operation-of-non-parameterized-commands.md)

- [<span data-ttu-id="a2cd4-155">非参数化命令的操作</span><span class="sxs-lookup"><span data-stu-id="a2cd4-155">Operation of Parameterized Commands</span></span>](operation-of-parameterized-commands.md)

- [<span data-ttu-id="a2cd4-156">混合命令</span><span class="sxs-lookup"><span data-stu-id="a2cd4-156">Hybrid Commands</span></span>](hybrid-commands.md)

- [<span data-ttu-id="a2cd4-157">中间 Shape COMPUTE 子句</span><span class="sxs-lookup"><span data-stu-id="a2cd4-157">Intervening Shape COMPUTE Clauses</span></span>](intervening-shape-compute-clauses.md)