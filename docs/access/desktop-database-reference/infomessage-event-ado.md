---
title: InfoMessage 事件 (ADO)
TOCTitle: InfoMessage event (ADO)
ms:assetid: 5d4f487f-96c8-4cf6-60ab-583510d3096f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249328(v=office.15)
ms:contentKeyID: 48545109
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 879d8e7b3733937687671a164f86dbb273cf7533
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28699896"
---
# <a name="infomessage-event-ado"></a>InfoMessage 事件 (ADO)

**适用于**： Access 2013、 Office 2013

只要在 **ConnectionEvent** 操作期间发生警告，便会调用 **InfoMessage** 事件。

## <a name="syntax"></a>语法

InfoMessage*pError*， *adStatus* *pConnection*

## <a name="parameters"></a>Parameters

|参数|说明|
|:--------|:----------|
|*pError* |[Error](error-object-ado.md) 对象。此参数包含返回的任何错误。如果返回了多个错误，则枚举 **Errors** 集合以找到这些错误。|
|*adStatus* |[EventStatusEnum](eventstatusenum.md)。 在此事件返回之前，将该参数设置为 **adStatusUnwantedEvent** 可以阻止随后进行通知。|
|*pConnection* |[Connection](connection-object-ado.md) 对象。发生警告的连接。例如，当打开 **Connection** 对象或对 [Connection](command-object-ado.md) 执行 **Command** 时，会发生警告。|

