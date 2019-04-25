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
localization_priority: Priority
ms.openlocfilehash: 828bccfad83320d27f9473d532ab86f73b2fde98
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314145"
---
# <a name="transaction-statement-microsoft-access-sql"></a><span data-ttu-id="11adb-102">TRANSACTION 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="11adb-102">TRANSACTION Statement (Microsoft Access SQL)</span></span>

<span data-ttu-id="11adb-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="11adb-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="11adb-104">用于启动和结束显式事务。</span><span class="sxs-lookup"><span data-stu-id="11adb-104">Used to initiate and conclude explicit transactions.</span></span>

## <a name="syntax"></a><span data-ttu-id="11adb-105">语法</span><span class="sxs-lookup"><span data-stu-id="11adb-105">Syntax</span></span>

<span data-ttu-id="11adb-106">**启动新事务**：</span><span class="sxs-lookup"><span data-stu-id="11adb-106">Initiate a new transaction.</span></span>

<span data-ttu-id="11adb-107">BEGIN TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="11adb-107">BEGIN TRANSACTION</span></span>

<span data-ttu-id="11adb-108">**通过提交在完成事务期间执行的所有工作来结束事务**：</span><span class="sxs-lookup"><span data-stu-id="11adb-108">Conclude a transaction by committing all work performed during the transaction.</span></span>

<span data-ttu-id="11adb-109">COMMIT \[TRANSACTION | WORK\]</span><span class="sxs-lookup"><span data-stu-id="11adb-109">COMMIT [TRANSACTION | WORK]</span></span>

<span data-ttu-id="11adb-110">**通过回滚在完成事务期间执行的所有工作来结束事务**：</span><span class="sxs-lookup"><span data-stu-id="11adb-110">Conclude a transaction by rolling back all work performed during the transaction.</span></span>

<span data-ttu-id="11adb-111">ROLLBACK \[TRANSACTION | WORK\]</span><span class="sxs-lookup"><span data-stu-id="11adb-111">ROLLBACK [TRANSACTION | WORK]</span></span>

## <a name="remarks"></a><span data-ttu-id="11adb-112">说明</span><span class="sxs-lookup"><span data-stu-id="11adb-112">Remarks</span></span>

<span data-ttu-id="11adb-p101">事务不会自动启动。若要启动事务，必须使用 BEGIN TRANSACTION 显式启动。</span><span class="sxs-lookup"><span data-stu-id="11adb-p101">Transactions are not started automatically. To start a transaction, you must do so explicitly using BEGIN TRANSACTION.</span></span>

<span data-ttu-id="11adb-p102">事务最多可嵌套五层。要启动嵌套事务，请在现有事务的上下文中使用 BEGIN TRANSACTION。</span><span class="sxs-lookup"><span data-stu-id="11adb-p102">Transactions can be nested up to five levels deep. To start a nested transaction, use BEGIN TRANSACTION within the context of an existing transaction.</span></span>

<span data-ttu-id="11adb-117">链接表不支持事务。</span><span class="sxs-lookup"><span data-stu-id="11adb-117">Transactions are not supported for linked tables.</span></span>

