---
title: ConnectComplete 和 Disconnect 事件 (ADO)
TOCTitle: ConnectComplete and Disconnect Events (ADO)
ms:assetid: 8ecb080b-7fc9-7565-25bd-bd57b983750d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249629(v=office.15)
ms:contentKeyID: 48546293
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f9233ba547ecf746d3b4db7b4e008976a813afff
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "25891181"
---
# <a name="connectcomplete-and-disconnect-events-ado"></a>ConnectComplete 和 Disconnect 事件 (ADO)


**适用于**： Access 2013、 Office 2013

**ConnectComplete** 事件在连接*启动*之后调用。**Disconnect** 事件在连接*终止*之后调用。

## <a name="syntax"></a>语法

ConnectComplete*pError*， *adStatus* *pConnection*

断开*adStatus*， *pConnection*

## <a name="parameters"></a>参数

  - *pError*

  - [Error](error-object-ado.md) 对象。如果 *adStatus* 的值为 **adStatusErrorsOccurred** ，则此参数描述所发生的错误，否则不设置此参数。

  - *adStatus*

  - [EventStatusEnum](eventstatusenum.md)
    
    调用 **ConnectComplete** 时，如果 **WillConnect** 事件已请求取消挂起的连接，则该参数设置为 **adStatusCancel** 。
    
    在任何一个事件返回之前，将该参数设置为 **adStatusUnwantedEvent** 可以阻止随后进行通知。但是，关闭然后重新打开 [Connection](connection-object-ado.md) 会导致这些事件再次发生。

  - *pConnection*

  - 为其应用该事件的 **Connection** 对象。

