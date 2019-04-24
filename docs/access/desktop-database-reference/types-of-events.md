---
title: 事件类型 (Access desktop database reference)
TOCTitle: Types of Events
ms:assetid: 94660fc1-65c3-1d21-c451-f3898014e0b6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249660(v=office.15)
ms:contentKeyID: 48546414
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 3bcf631ffc6c9b4b847af3f973114d6b271d26f5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314152"
---
# <a name="types-of-events"></a>事件类型


**适用于**：Access 2013、Office 2013



事件有两种基本类型。一种是“Will 事件”，在操作开始之前调用，通常名称中包括“Will”，如 **WillChangeRecordset** 或 **WillConnect**。而在事件完成之后调用的事件，其名称中往往包括“Complete”，如 **RecordChangeComplete** 或 **ConnectComplete**。也有例外情况，如 **InfoMessage**，不过它发生在关联的操作完成之后。

## <a name="will-events"></a>Will 事件

在操作开始之前调用的事件处理程序，为您提供了检查或修改操作参数、随后或取消操作或允许操作完成的机会。 这些事件处理程序例程的名称通常都是 * **** 的形式。

## <a name="complete-events"></a>Complete 事件

在操作完成之后调用的事件处理程序可以通知应用程序操作已结束。 如果 Will 事件处理程序取消了挂起的操作，则也会通知此事件处理程序。 这些事件处理程序例程的 "form ***event ***" 的名称通常为 "完成"。

Will 和 Complete 事件通常成对使用。

## <a name="other-events"></a>其他事件

其他事件处理程序, 即那些名称不是窗体的事件将在操作完成之后调用的事件 ***事件*** 或 ***事件 * 完成**。 这些事件包括 **Disconnect**、**EndOfRecordset** 和 **InfoMessage**。

