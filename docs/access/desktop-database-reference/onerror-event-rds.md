---
title: onError 事件 (RDS)
TOCTitle: onError event (RDS)
ms:assetid: e26a3f7f-0f00-919a-65ad-bf39ffb83e92
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250153(v=office.15)
ms:contentKeyID: 48548292
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9fc51522d143306d9625cdc07251edfe1dddf22d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288474"
---
# <a name="onerror-event-rds"></a>onError 事件 (RDS)

**适用于**：Access 2013、Office 2013

只要在操作期间发生错误，便会调用 **onError** 事件。

## <a name="syntax"></a>语法

onError*SCode*、 *Description*、 *Source*、 *CancelDisplay*

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*SCode* |指示错误的状态代码的整数。|
|*Description* |**字符串型** ，指示错误的说明。|
|*Source* |**字符串型** ，指示导致错误的查询或命令。|
|*CancelDisplay* |**Boolean** 值，如果设置为 **True** ，则禁止在对话框中显示错误。|

