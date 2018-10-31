---
title: TRANSACTION 语句 (Microsoft Access SQL)
TOCTitle: TRANSACTION statement (Microsoft Access SQL)
ms:assetid: 481e807d-94e4-f201-adac-d25ee89d9220
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193241(v=office.15)
ms:contentKeyID: 48544614
ms.date: 10/18/2018
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277472
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 6d93fc90beded30d96b4db54c35ab3046da06899
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25862658"
---
# <a name="transaction-statement-microsoft-access-sql"></a><span data-ttu-id="361c4-102">TRANSACTION 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="361c4-102">TRANSACTION statement (Microsoft Access SQL)</span></span>

<span data-ttu-id="361c4-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="361c4-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="361c4-104">用于初始化和结束显式事务处理。</span><span class="sxs-lookup"><span data-stu-id="361c4-104">Used to initiate and conclude explicit transactions.</span></span>

## <a name="syntax"></a><span data-ttu-id="361c4-105">语法</span><span class="sxs-lookup"><span data-stu-id="361c4-105">Syntax</span></span>

<span data-ttu-id="361c4-106">**启动新的事务**：</span><span class="sxs-lookup"><span data-stu-id="361c4-106">**Initiate a new transaction**:</span></span>

<span data-ttu-id="361c4-107">BEGIN TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="361c4-107">BEGIN TRANSACTION</span></span>

<span data-ttu-id="361c4-108">**通过提交事务的所有工作的结束提问执行事务过程**：</span><span class="sxs-lookup"><span data-stu-id="361c4-108">**Conclude a transaction by committing all work performed during the transaction**:</span></span>

<span data-ttu-id="361c4-109">提交\[事务 |工作\]</span><span class="sxs-lookup"><span data-stu-id="361c4-109">COMMIT \[TRANSACTION | WORK\]</span></span>

<span data-ttu-id="361c4-110">**结束提问通过回滚事务交易期间执行的所有工作**：</span><span class="sxs-lookup"><span data-stu-id="361c4-110">**Conclude a transaction by rolling back all work performed during the transaction**:</span></span>

<span data-ttu-id="361c4-111">回滚\[事务 |工作\]</span><span class="sxs-lookup"><span data-stu-id="361c4-111">ROLLBACK \[TRANSACTION | WORK\]</span></span>

## <a name="remarks"></a><span data-ttu-id="361c4-112">说明</span><span class="sxs-lookup"><span data-stu-id="361c4-112">Remarks</span></span>

<span data-ttu-id="361c4-p101">事务处理不会自动启动。若要启动一个事务处理，必须通过 BEGIN TRANSACTION 进行显式调用。</span><span class="sxs-lookup"><span data-stu-id="361c4-p101">Transactions are not started automatically. To start a transaction, you must do so explicitly using BEGIN TRANSACTION.</span></span>

<span data-ttu-id="361c4-p102">事务处理嵌套的最大深度为五级。若要启动一个嵌套事务处理，请在现有的事务处理上下文中使用 BEGIN TRANSACTION。</span><span class="sxs-lookup"><span data-stu-id="361c4-p102">Transactions can be nested up to five levels deep. To start a nested transaction, use BEGIN TRANSACTION within the context of an existing transaction.</span></span>

<span data-ttu-id="361c4-117">链接表不支持事务处理。</span><span class="sxs-lookup"><span data-stu-id="361c4-117">Transactions are not supported for linked tables.</span></span>

