---
title: RDS 返回"Stream Not Read"错误
TOCTitle: RDS returns "Stream Not Read" error
ms:assetid: 325f7b9d-8e71-bc2c-94e3-b4b4a1a2dc58
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249097(v=office.15)
ms:contentKeyID: 48544075
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 56bd90daef7b7571d8f0c6adca239ef24955f65a
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25944625"
---
# <a name="rds-returns-stream-not-read-error"></a>RDS 返回\"Stream Not Read\"错误


**适用于**： Access 2013、 Office 2013

“The Stream object could not be read because it is empty, or the current position is at the end of the Stream. For non-empty Streams, set the current position with the Position property. To determine if a Stream is empty, check the Size property.”

如果您获得上面的错误，则可能是由于您尝试通过 http 使用参数化分层查询。RDS 不允许您远程使用参数化层次结构。

