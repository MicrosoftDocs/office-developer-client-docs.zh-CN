---
title: DBEngine.BeginTrans Method (DAO)
TOCTitle: BeginTrans Method
ms:assetid: fdde662f-2472-3af6-67d6-c8ca7fb1dca7
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837255(v=office.15)
ms:contentKeyID: 48548925
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 114f5c1cfd08098b8dc0a2731709965e2c3f2ea4
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466942"
---
# <a name="dbenginebegintrans-method-dao"></a><span data-ttu-id="5a0c4-102">DBEngine.BeginTrans Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="5a0c4-102">DBEngine.BeginTrans Method (DAO)</span></span>


<span data-ttu-id="5a0c4-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="5a0c4-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="5a0c4-p101">开始新的事务。可读写 **Database**。</span><span class="sxs-lookup"><span data-stu-id="5a0c4-p101">Begins a new transaction. Read/write **Database**.</span></span>

## <a name="syntax"></a><span data-ttu-id="5a0c4-106">语法</span><span class="sxs-lookup"><span data-stu-id="5a0c4-106">Syntax</span></span>

<span data-ttu-id="5a0c4-107">*表达式*。BeginTrans</span><span class="sxs-lookup"><span data-stu-id="5a0c4-107">*expression* .BeginTrans</span></span>

<span data-ttu-id="5a0c4-108">*表达式*一个代表**DBEngine**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="5a0c4-108">*expression* A variable that represents a **DBEngine** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="5a0c4-109">注解</span><span class="sxs-lookup"><span data-stu-id="5a0c4-109">Remarks</span></span>

<span data-ttu-id="5a0c4-p102">事务方法 **BeginTrans**、 **CommitTrans** 和 **Rollback** 可在 **Workspace** 对象定义的会话期间管理事务处理。如果要将会话中的数据库发生的一系列更改视为一个单元，请对 **Workspace** 对象使用这些方法。</span><span class="sxs-lookup"><span data-stu-id="5a0c4-p102">The transaction methods **BeginTrans**, **CommitTrans**, and **Rollback** manage transaction processing during a session defined by a **Workspace** object. You use these methods with a **Workspace** object when you want to treat a series of changes made to the databases in a session as one unit.</span></span>

<span data-ttu-id="5a0c4-p103">通常，如果既要更新两个或更多个表中的记录，又要确保完成（提交）所有表中的更改，或者确保不完成（提交）任何表中的更改（回滚），可使用事务维护数据的完整性。例如，如果将现金从一个帐户转到另一个帐户，可以从一个帐户中减去一个金额，然后将此金额添加到另一个帐户。如果其中任意一个更新失败，那么这两个帐户之间将不再平衡。在更新第一条记录之前，使用 **BeginTrans** 方法，然后，如果任何后续更新失败，可以使用 **Rollback** 方法撤消所有更改。成功更新最后一条记录后，使用 **CommitTrans** 方法。</span><span class="sxs-lookup"><span data-stu-id="5a0c4-p103">Typically, you use transactions to maintain the integrity of your data when you must both update records in two or more tables and ensure changes are completed (committed) in all tables or none at all (rolled back). For example, if you transfer money from one account to another, you might subtract an amount from one and add the amount to another. If either update fails, the accounts no longer balance. Use the **BeginTrans** method before updating the first record, and then, if any subsequent update fails, you can use the **Rollback** method to undo all of the updates. Use the **CommitTrans** method after you successfully update the last record.</span></span>


> [!NOTE]
> <P><span data-ttu-id="5a0c4-p104">[!注释] 在一个 <STRONG>Workspace</STRONG> 对象中，事务对 <STRONG>Workspace</STRONG> 始终是全局的，不会只限于一个 <STRONG>Connection</STRONG> 或 <STRONG>Database</STRONG> 对象。如果在 <STRONG>Workspace</STRONG> 事务中对多个连接或数据库执行操作，解析事务（即使用 <STRONG>CommitTrans</STRONG> 或 <STRONG>Rollback</STRONG> 方法）将影响对该工作区中所有连接和数据库执行的所有操作。</span><span class="sxs-lookup"><span data-stu-id="5a0c4-p104">Within one <STRONG>Workspace</STRONG> object, transactions are always global to the <STRONG>Workspace</STRONG> and aren't limited to only one <STRONG>Connection</STRONG> or <STRONG>Database</STRONG> object. If you perform operations on more than one connection or database within a <STRONG>Workspace</STRONG> transaction, resolving the transaction (that is, using the <STRONG>CommitTrans</STRONG> or <STRONG>Rollback</STRONG> method) affects all operations on all connections and databases within that workspace.</span></span></P>



<span data-ttu-id="5a0c4-p105">使用 **CommitTrans** 后，除非事务嵌套在另一个自己回滚的事务中，否则您无法撤消该事务期间所做的更改。如果要嵌套事务，必须先解析当前事务，然后才可以解析更高嵌套级别的事务。</span><span class="sxs-lookup"><span data-stu-id="5a0c4-p105">After you use **CommitTrans**, you can't undo changes made during that transaction unless the transaction is nested within another transaction that is itself rolled back. If you nest transactions, you must resolve the current transaction before you can resolve a transaction at a higher level of nesting.</span></span>

<span data-ttu-id="5a0c4-121">如果要实现具有重叠、非嵌套范围的同步事务，可创建额外的 **Workspace** 对象以包含并发事务。</span><span class="sxs-lookup"><span data-stu-id="5a0c4-121">If you want to have simultaneous transactions with overlapping, non-nested scopes, you can create additional **Workspace** objects to contain the concurrent transactions.</span></span>

<span data-ttu-id="5a0c4-122">如果关闭了一个 **Workspace** 对象且没有解析任何待定事务，事务将自动回滚。</span><span class="sxs-lookup"><span data-stu-id="5a0c4-122">If you close a **Workspace** object without resolving any pending transactions, the transactions are automatically rolled back.</span></span>

<span data-ttu-id="5a0c4-123">如果在没有首先使用 **BeginTrans** 方法的情况下使用了 **CommitTrans** 或 **Rollback** 方法，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="5a0c4-123">If you use the **CommitTrans** or **Rollback** method without first using the **BeginTrans** method, an error occurs.</span></span>

<span data-ttu-id="5a0c4-p106">Microsoft Access 工作区中使用的某些 ISAM 数据库可能不支持事务，在这种情况下， **Database** 对象或 **Recordset** 对象的 **Transactions** 属性为 **False**。若要确保数据库支持事务，请在使用 **BeginTrans** 方法之前，检查 **Database** 对象的 **Transactions** 属性的值。如果使用的是基于多个数据库的 **Recordset** 对象，请检查 **Recordset** 对象的 **Transactions** 属性。如果 **Recordset** 完全基于 Microsoft Access 数据库引擎表，则始终都可以使用事务。但是，基于由其他数据库产品创建的表的 **Recordset** 对象可能不支持事务。例如，不能在基于 Paradox 表的 **Recordset** 中使用事务。在这种情况下， **Transactions** 属性为 **False**。如果 **Database** 或 **Recordset** 不支持事务，将忽略这些方法，并且不发生错误。</span><span class="sxs-lookup"><span data-stu-id="5a0c4-p106">Some ISAM databases used in a Microsoft Access workspace may not support transactions, in which case the **Transactions** property of the **Database** object or **Recordset** object is **False**. To make sure the database supports transactions, check the value of the **Transactions** property of the **Database** object before using the **BeginTrans** method. If you are using a **Recordset** object based on more than one database, check the **Transactions** property of the **Recordset** object. If a **Recordset** is based entirely on Microsoft Access database engine tables, you can always use transactions. **Recordset** objects based on tables created by other database products, however, may not support transactions. For example, you can't use transactions in a **Recordset** based on a Paradox table. In this case, the **Transactions** property is **False**. If the **Database** or **Recordset** doesn't support transactions, the methods are ignored and no error occurs.</span></span>

<span data-ttu-id="5a0c4-132">如果通过 Microsoft Access 数据库引擎访问 ODBC 数据源，则无法嵌套事务。</span><span class="sxs-lookup"><span data-stu-id="5a0c4-132">You can't nest transactions if you are accessing ODBC data sources through the Microsoft Access database engine.</span></span>

<span data-ttu-id="5a0c4-p107">在 ODBC 工作区中，如果使用 **CommitTrans**，游标可能不再有效。使用 **Requery** 方法查看 **Recordset** 中的更改，或关闭再重新打开 **Recordset**。</span><span class="sxs-lookup"><span data-stu-id="5a0c4-p107">In ODBC workspaces, when you use **CommitTrans** your cursor may no longer be valid. Use the **Requery** method to view the changes in the **Recordset**, or close and re-open the **Recordset**.</span></span>


> [!NOTE]
> <UL>
> <LI>
> <P><span data-ttu-id="5a0c4-p108">可以经常通过中断需要对磁盘中的事务块进行访问的操作，来改善应用程序的性能。这将会缓冲您的操作，并可显著地减少访问磁盘的次数。</span><span class="sxs-lookup"><span data-stu-id="5a0c4-p108">You can often improve the performance of your application by breaking operations that require disk access into transaction blocks. This buffers your operations and may significantly reduce the number of times a disk is accessed.</span></span></P>
> <LI>
> <P><span data-ttu-id="5a0c4-p109">在 Microsoft Access 工作区中，事务将记录在一个文件内，该文件保存在由工作站上的 TEMP 环境变量指定的目录中。如果事务日志文件耗尽了 TEMP 驱动器上的可用存储，数据库引擎将触发一个运行时错误。此时，如果使用 <STRONG>CommitTrans</STRONG>，将提交不确定的操作次数，但是余下的未完成操作将会丢失，并且必须要重新启动操作。使用 <STRONG>Rollback</STRONG> 方法将释放事务日志，同时回滚事务中的所有操作。</span><span class="sxs-lookup"><span data-stu-id="5a0c4-p109">In a Microsoft Access workspace, transactions are logged in a file kept in the directory specified by the TEMP environment variable on the workstation. If the transaction log file exhausts the available storage on your TEMP drive, the database engine triggers a run-time error. At this point, if you use <STRONG>CommitTrans</STRONG>, an indeterminate number of operations are committed, but the remaining uncompleted operations are lost, and the operation has to be restarted. Using a <STRONG>Rollback</STRONG> method releases the transaction log and rolls back all operations in the transaction.</span></span></P>
> <LI>
> <P><span data-ttu-id="5a0c4-141">在待定事务中关闭克隆 <STRONG>Recordset</STRONG> 将导致隐式 <STRONG>Rollback</STRONG> 操作。</span><span class="sxs-lookup"><span data-stu-id="5a0c4-141">Closing a clone <STRONG>Recordset</STRONG> within a pending transaction will cause an implicit <STRONG>Rollback</STRONG> operation.</span></span></P></LI></UL>

