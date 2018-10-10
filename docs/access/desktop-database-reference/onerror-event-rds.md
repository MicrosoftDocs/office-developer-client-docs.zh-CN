---
title: onError 事件 (RDS)
TOCTitle: onError Event (RDS)
ms:assetid: e26a3f7f-0f00-919a-65ad-bf39ffb83e92
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250153(v=office.15)
ms:contentKeyID: 48548292
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3fe6f6b78297008e25e15dc17e243ae982a5ccf3
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468646"
---
# <a name="onerror-event-rds"></a>onError 事件 (RDS)


**适用于**： Access 2013 |Office 2013

只要在操作期间发生错误，便会调用 **onError** 事件。

## <a name="syntax"></a>语法

onError*SCode*，*说明*，*源*， *CancelDisplay*

## <a name="parameters"></a>参数

  - *SCode*

  - 指示错误的状态代码的整数。

  - *Description*

  - **字符串型** ，指示错误的说明。

  - *Source*

  - **字符串型** ，指示导致错误的查询或命令。

  - *CancelDisplay*

  - **Boolean** 值，如果设置为 **True** ，则禁止在对话框中显示错误。

