---
title: RDS 返回“Stream Not Read”错误
TOCTitle: RDS Returns "Stream Not Read" Error
ms:assetid: 325f7b9d-8e71-bc2c-94e3-b4b4a1a2dc58
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249097(v=office.15)
ms:contentKeyID: 48544075
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a9b3372db2ff86ea2af401720ba091100d4cfce1
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468818"
---
# <a name="rds-returns-stream-not-read-error"></a>RDS 返回\"Stream Not Read\"错误


**适用于**： Access 2013 |Office 2013

“The Stream object could not be read because it is empty, or the current position is at the end of the Stream. For non-empty Streams, set the current position with the Position property. To determine if a Stream is empty, check the Size property.”

如果您获得上面的错误，则可能是由于您尝试通过 http 使用参数化分层查询。RDS 不允许您远程使用参数化层次结构。

