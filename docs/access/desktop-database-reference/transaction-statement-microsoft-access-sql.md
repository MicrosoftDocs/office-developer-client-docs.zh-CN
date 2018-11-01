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
ms.openlocfilehash: f48b1ab98f6f0f729fdb32b4ff20be09c5d942bf
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25886387"
---
# <a name="transaction-statement-microsoft-access-sql"></a>TRANSACTION 语句 (Microsoft Access SQL)

**适用于**： Access 2013、 Office 2013

用于初始化和结束显式事务处理。

## <a name="syntax"></a>语法

**启动新的事务**：

BEGIN TRANSACTION

**通过提交事务的所有工作的结束提问执行事务过程**：

提交\[事务 |工作\]

**结束提问通过回滚事务交易期间执行的所有工作**：

回滚\[事务 |工作\]

## <a name="remarks"></a>说明

事务处理不会自动启动。若要启动一个事务处理，必须通过 BEGIN TRANSACTION 进行显式调用。

事务处理嵌套的最大深度为五级。若要启动一个嵌套事务处理，请在现有的事务处理上下文中使用 BEGIN TRANSACTION。

链接表不支持事务处理。

