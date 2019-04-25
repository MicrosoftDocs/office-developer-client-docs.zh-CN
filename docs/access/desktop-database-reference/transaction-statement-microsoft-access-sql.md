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
# <a name="transaction-statement-microsoft-access-sql"></a>TRANSACTION 语句 (Microsoft Access SQL)

**适用于**：Access 2013、Office 2013

用于启动和结束显式事务。

## <a name="syntax"></a>语法

**启动新事务**：

BEGIN TRANSACTION

**通过提交在完成事务期间执行的所有工作来结束事务**：

COMMIT \[TRANSACTION | WORK\]

**通过回滚在完成事务期间执行的所有工作来结束事务**：

ROLLBACK \[TRANSACTION | WORK\]

## <a name="remarks"></a>说明

事务不会自动启动。若要启动事务，必须使用 BEGIN TRANSACTION 显式启动。

事务最多可嵌套五层。要启动嵌套事务，请在现有事务的上下文中使用 BEGIN TRANSACTION。

链接表不支持事务。

