---
title: 控制事务
TOCTitle: Controlling Transactions
ms:assetid: 21a9f055-6907-3818-e232-21e579cc67b7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248994(v=office.15)
ms:contentKeyID: 48543685
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ced1ae7b32d25fbae53c670959a4a6c77bcea0be
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28716619"
---
# <a name="controlling-transactions"></a><span data-ttu-id="4cad0-102">控制事务</span><span class="sxs-lookup"><span data-stu-id="4cad0-102">Controlling Transactions</span></span>


<span data-ttu-id="4cad0-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="4cad0-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="4cad0-104">*事务*确定的开头和结尾的一系列连接上发生的数据访问操作。</span><span class="sxs-lookup"><span data-stu-id="4cad0-104">A *transaction* delimits the beginning and end of a series of data access operations that transpire across a connection.</span></span> <span data-ttu-id="4cad0-105">根据数据源的事务处理功能，利用 **Connection** 对象还可以创建和管理事务。</span><span class="sxs-lookup"><span data-stu-id="4cad0-105">Subject to the transactional capabilities of your data source, the **Connection** object also allows you to create and manage transactions.</span></span> <span data-ttu-id="4cad0-106">例如，使用 Microsoft OLE DB Provider for SQL Server 访问 Microsoft SQL Server 2000 上的数据库，您可以为所执行的命令创建多个嵌套事务。</span><span class="sxs-lookup"><span data-stu-id="4cad0-106">For example, using the Microsoft OLE DB Provider for SQL Server to access a database on Microsoft SQL Server 2000, you can create multiple nested transactions for the commands you execute.</span></span>

<span data-ttu-id="4cad0-107">ADO 确保由于事务中的操作而引起的数据源更改一起成功发生或者根本不发生。</span><span class="sxs-lookup"><span data-stu-id="4cad0-107">ADO ensures that changes to a data source resulting from operations in a transaction occur successfully together or not at all.</span></span>

<span data-ttu-id="4cad0-p102">如果取消该事务，或其中一个操作失败，最终结果就像事务中没有发生任何操作一样。数据源将仍然保持事务开始前的状态。</span><span class="sxs-lookup"><span data-stu-id="4cad0-p102">If you cancel the transaction, or if one of its operations fails, the ultimate result will be as if none of the operations in the transaction occurred. The data source will remain as it was before the transaction began.</span></span>

<span data-ttu-id="4cad0-110">ADO 对象模型不显式包括事务，但会用一组 **Connection** 对象方法（**BeginTrans**、**CommitTrans** 和 **RollbackTrans**）来代表它们。</span><span class="sxs-lookup"><span data-stu-id="4cad0-110">The ADO object model does not explicitly include transactions, but represents them with a set of **Connection** object methods (**BeginTrans**, **CommitTrans**, and **RollbackTrans**).</span></span>

<span data-ttu-id="4cad0-111">有关事务的详细信息，请参阅[第 5 章：更新和持久化数据](chapter-5-updating-and-persisting-data.md)。</span><span class="sxs-lookup"><span data-stu-id="4cad0-111">For more information about transactions, see [Chapter 5: Updating and Persisting Data](chapter-5-updating-and-persisting-data.md).</span></span>

