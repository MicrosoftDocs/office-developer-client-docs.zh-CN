---
title: Shape Append 子句
TOCTitle: Shape Append clause
ms:assetid: 8f29afc3-fb93-4439-b67b-cad0eed0bda9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249633(v=office.15)
ms:contentKeyID: 48546301
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 40c35e8b2c3fb3f0b92bf261b62c252a61a367b4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306445"
---
# <a name="shape-append-clause"></a><span data-ttu-id="6a546-102">Shape Append 子句</span><span class="sxs-lookup"><span data-stu-id="6a546-102">Shape Append clause</span></span>


<span data-ttu-id="6a546-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="6a546-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="6a546-p101">shape 命令 APPEND 子句用于将一个或多个列追加到 **Recordset** 中。通常，这些列是章节列，而章节列是对子 **Recordset** 的引用。</span><span class="sxs-lookup"><span data-stu-id="6a546-p101">The shape command APPEND clause appends a column or columns to a **Recordset**. Often these columns are chapter columns, which refer to a child **Recordset**.</span></span>

## <a name="syntax"></a><span data-ttu-id="6a546-106">语法</span><span class="sxs-lookup"><span data-stu-id="6a546-106">Syntax</span></span>

```vb 
 
SHAPE [parent-command [[AS] parent-alias]] APPEND column-list
```

## <a name="description"></a><span data-ttu-id="6a546-107">说明</span><span class="sxs-lookup"><span data-stu-id="6a546-107">Description</span></span>

<span data-ttu-id="6a546-108">此子句的各部分如下所示：</span><span class="sxs-lookup"><span data-stu-id="6a546-108">The parts of this clause are as follows:</span></span>

- <span data-ttu-id="6a546-109">*parent-command*</span><span class="sxs-lookup"><span data-stu-id="6a546-109">*parent-command*</span></span>

- <span data-ttu-id="6a546-110">零个或下列项之一（可以完全省略 *parent-command*）：</span><span class="sxs-lookup"><span data-stu-id="6a546-110">Zero or one of the following (you may omit the *parent-command* entirely):</span></span>
    
  - <span data-ttu-id="6a546-111">在大括号 ("{}") 中返回**Recordset**对象的提供程序命令。</span><span class="sxs-lookup"><span data-stu-id="6a546-111">A provider command within curly braces ("{}") that returns a **Recordset** object.</span></span> <span data-ttu-id="6a546-112">该命令向基础数据提供程序发出，其语法取决于该提供程序的要求。</span><span class="sxs-lookup"><span data-stu-id="6a546-112">The command is issued to the underlying data provider, and its syntax depends on the requirements of that provider.</span></span> <span data-ttu-id="6a546-113">这通常是 SQL 语言，但 ADO 不需要任何特定的查询语言。</span><span class="sxs-lookup"><span data-stu-id="6a546-113">This will typically be the SQL language, although ADO does not require any particular query language.</span></span>
    
  - <span data-ttu-id="6a546-114">嵌入在括号中的另一个 Shape 命令。</span><span class="sxs-lookup"><span data-stu-id="6a546-114">Another shape command embedded in parentheses.</span></span>
    
  - <span data-ttu-id="6a546-115">TABLE 关键字，后跟数据提供程序中的表的名称。</span><span class="sxs-lookup"><span data-stu-id="6a546-115">The TABLE keyword, followed by the name of a table in the data provider.</span></span>

- <span data-ttu-id="6a546-116">*parent-alias*</span><span class="sxs-lookup"><span data-stu-id="6a546-116">*parent-alias*</span></span>

  - <span data-ttu-id="6a546-117">用于引用父 **Recordset** 的可选别名。</span><span class="sxs-lookup"><span data-stu-id="6a546-117">An optional alias that refers to the parent **Recordset**.</span></span>

- <span data-ttu-id="6a546-118">*column-list*</span><span class="sxs-lookup"><span data-stu-id="6a546-118">*column-list*</span></span>

  - <span data-ttu-id="6a546-119">一个或多个以下项：</span><span class="sxs-lookup"><span data-stu-id="6a546-119">One or more of the following:</span></span>
    
    - <span data-ttu-id="6a546-120">聚合列。</span><span class="sxs-lookup"><span data-stu-id="6a546-120">An aggregate column.</span></span>
    
    - <span data-ttu-id="6a546-121">计算列。</span><span class="sxs-lookup"><span data-stu-id="6a546-121">A calculated column.</span></span>
    
    - <span data-ttu-id="6a546-122">用 NEW 子句创建的新列。</span><span class="sxs-lookup"><span data-stu-id="6a546-122">A new column created with the NEW clause.</span></span>
    
    - <span data-ttu-id="6a546-p103">章节列。章节列的定义放在括号（"()"）中。请参阅以下语法：</span><span class="sxs-lookup"><span data-stu-id="6a546-p103">A chapter column. A chapter column definition is enclosed in parentheses ("()"). See syntax below:</span></span>


        ```vb 
        
        SHAPE [parent-command [[AS] parent-alias]] 
        APPEND (child-recordset [ [[AS] child-alias] 
        RELATE parent-column TO child-column | PARAMETER param-number, ... ]) 
        [[AS] chapter-alias] 
        [, ... ] 
        ```

- <span data-ttu-id="6a546-126">*child-recordset*</span><span class="sxs-lookup"><span data-stu-id="6a546-126">*child-recordset*</span></span>

  - <span data-ttu-id="6a546-127">在大括号 ("{}") 中返回**Recordset**对象的提供程序命令。</span><span class="sxs-lookup"><span data-stu-id="6a546-127">A provider command within curly braces ("{}") that returns a **Recordset** object.</span></span> <span data-ttu-id="6a546-128">该命令向基础数据提供程序发出，其语法取决于该提供程序的要求。</span><span class="sxs-lookup"><span data-stu-id="6a546-128">The command is issued to the underlying data provider, and its syntax depends on the requirements of that provider.</span></span> <span data-ttu-id="6a546-129">这通常是 SQL 语言，但 ADO 不需要任何特定的查询语言。</span><span class="sxs-lookup"><span data-stu-id="6a546-129">This will typically be the SQL language, although ADO does not require any particular query language.</span></span>
    
  - <span data-ttu-id="6a546-130">嵌入在括号中的另一个 Shape 命令。</span><span class="sxs-lookup"><span data-stu-id="6a546-130">Another shape command embedded in parentheses.</span></span>
    
  - <span data-ttu-id="6a546-131">现有已构形 **Recordset** 的名称。</span><span class="sxs-lookup"><span data-stu-id="6a546-131">The name of an existing shaped **Recordset**.</span></span>
    
  - <span data-ttu-id="6a546-132">TABLE 关键字，后跟数据提供程序中的表的名称。</span><span class="sxs-lookup"><span data-stu-id="6a546-132">The TABLE keyword, followed by the name of a table in the data provider.</span></span>

- <span data-ttu-id="6a546-133">*child-alias*</span><span class="sxs-lookup"><span data-stu-id="6a546-133">*child-alias*</span></span>

  - <span data-ttu-id="6a546-134">引用子 **Recordset** 的别名。</span><span class="sxs-lookup"><span data-stu-id="6a546-134">An alias that refers to the child **Recordset**.</span></span>

- <span data-ttu-id="6a546-135">*parent-column*</span><span class="sxs-lookup"><span data-stu-id="6a546-135">*parent-column*</span></span>

  - <span data-ttu-id="6a546-136">由 *parent-command* 返回的 **Recordset** 中的列。</span><span class="sxs-lookup"><span data-stu-id="6a546-136">A column in the **Recordset** returned by the *parent-command.*</span></span>

- <span data-ttu-id="6a546-137">*child-column*</span><span class="sxs-lookup"><span data-stu-id="6a546-137">*child-column*</span></span>

  - <span data-ttu-id="6a546-138">由 *child-command* 返回的 **Recordset** 中的列。</span><span class="sxs-lookup"><span data-stu-id="6a546-138">A column in the **Recordset** returned by the *child-command*.</span></span>

- <span data-ttu-id="6a546-139">*param-number*</span><span class="sxs-lookup"><span data-stu-id="6a546-139">*param-number*</span></span>

  - <span data-ttu-id="6a546-140">请参阅[参数化命令的操作](operation-of-parameterized-commands.md)。</span><span class="sxs-lookup"><span data-stu-id="6a546-140">See [Operation of Parameterized Commands](operation-of-parameterized-commands.md).</span></span>

- <span data-ttu-id="6a546-141">*chapter-alias*</span><span class="sxs-lookup"><span data-stu-id="6a546-141">*chapter-alias*</span></span>

  - <span data-ttu-id="6a546-142">引用追加到父记录集的章节列的别名。</span><span class="sxs-lookup"><span data-stu-id="6a546-142">An alias that refers to the chapter column appended to the parent.</span></span>


> [!NOTE]
> - <span data-ttu-id="6a546-143">“_parent-column TO child-column_”子句实际上是列表，其中所定义的每个关系均以逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="6a546-143">The _"parent-column TO child-column"_ clause is actually a list, where each relation defined is separated by a comma.</span></span>
> - <span data-ttu-id="6a546-144">APPEND 关键字后面的子句实际上是列表，其中每个子句均以逗号分隔，并且定义了要追加到父记录集的其他列。</span><span class="sxs-lookup"><span data-stu-id="6a546-144">The clause after the APPEND keyword is actually a list, where each clause is separated by a comma and defines another column to be appended to the parent.</span></span>



## <a name="remarks"></a><span data-ttu-id="6a546-145">注解</span><span class="sxs-lookup"><span data-stu-id="6a546-145">Remarks</span></span>

<span data-ttu-id="6a546-p105">利用用户输入来构造提供程序命令以便将其作为 SHAPE 命令的一部分时，SHAPE 会将用户提供的提供程序命令当作不透明的字符串，并如实地传递给提供程序。例如，在以下 SHAPE 命令中，</span><span class="sxs-lookup"><span data-stu-id="6a546-p105">When you construct provider commands from user input as part of a SHAPE command, SHAPE will treat the user-supplied a provider command as an opaque string and pass them faithfully to the provider. For example, in the following SHAPE command,</span></span>

```vb 
 
SHAPE {select * from t1} APPEND ({select * from t2} RELATE k1 TO k2) 
```

<span data-ttu-id="6a546-148">SHAPE 将执行两个命令: \*选择 "从 t1" \*和 (选择 "从 t2 关联 k1 到 k2")。</span><span class="sxs-lookup"><span data-stu-id="6a546-148">SHAPE will execute two commands: select \* from t1 and (select \* from t2 RELATE k1 TO k2).</span></span> <span data-ttu-id="6a546-149">如果用户提供了由多个提供程序命令组成并以分号分隔的复合命令，SHAPE 将无法辨别差异。</span><span class="sxs-lookup"><span data-stu-id="6a546-149">If the user supplies a compound command consisting of multiple provider commands separated by semicolons, SHAPE is not able to discern the difference.</span></span> <span data-ttu-id="6a546-150">因此，在以下 SHAPE 命令中，</span><span class="sxs-lookup"><span data-stu-id="6a546-150">So in the following SHAPE command,</span></span>

```vb 
 
SHAPE {select * from t1; drop table t1} APPEND ({select * from t2} RELATE k1 TO k2) 
```

<span data-ttu-id="6a546-151">形状从 t1 \*执行选择;删除表 t1 和 (从\* t2 中选择 "k1" 与 k2 关联), 未实现 drop table t1 是单独的, 在此示例中, 是危险的提供程序命令。</span><span class="sxs-lookup"><span data-stu-id="6a546-151">SHAPE executes select \* from t1; drop table t1 and (select \* from t2 RELATE k1 TO k2), not realizing that drop table t1 is a separate and in this case, dangerous, provider command.</span></span> <span data-ttu-id="6a546-152">应用程序必须始终验证用户输入，以防止发生类似潜在黑客攻击。</span><span class="sxs-lookup"><span data-stu-id="6a546-152">Applications must always validate the user input to prevent such potential hacker attacks from happening.</span></span>

<span data-ttu-id="6a546-153">本节包括下列主题：</span><span class="sxs-lookup"><span data-stu-id="6a546-153">This section includes the following topics:</span></span>

- [<span data-ttu-id="6a546-154">非参数化命令的操作</span><span class="sxs-lookup"><span data-stu-id="6a546-154">Operation of Non-Parameterized Commands</span></span>](operation-of-non-parameterized-commands.md)

- [<span data-ttu-id="6a546-155">参数化命令的操作</span><span class="sxs-lookup"><span data-stu-id="6a546-155">Operation of Parameterized Commands</span></span>](operation-of-parameterized-commands.md)

- [<span data-ttu-id="6a546-156">混合命令</span><span class="sxs-lookup"><span data-stu-id="6a546-156">Hybrid Commands</span></span>](hybrid-commands.md)

- [<span data-ttu-id="6a546-157">插入形状计算子句</span><span class="sxs-lookup"><span data-stu-id="6a546-157">Intervening Shape COMPUTE Clauses</span></span>](intervening-shape-compute-clauses.md)
