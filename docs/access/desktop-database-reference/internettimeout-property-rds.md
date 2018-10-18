---
title: InternetTimeout 属性 (RDS)
TOCTitle: InternetTimeout Property (RDS)
ms:assetid: 66fc6e87-3d23-ce2c-18f5-0fc83ac43801
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249401(v=office.15)
ms:contentKeyID: 48545353
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: fd0fdc8f64207e1233ac56812ef009da865ce01a
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25603460"
---
# <a name="internettimeout-property-rds"></a>InternetTimeout 属性 (RDS)


**适用于**： Access 2013 |Office 2013

指示请求超时前等待的毫秒数。

<<<<<<< 标头
## <a name="settings-and-return-values"></a>设置和返回值
=======
## <a name="settings-and-return-values"></a>设置和返回值
>>>>>>> master

设置或返回一个 **Long** 值，该值表示请求超时前等待的毫秒数。

## <a name="remarks"></a>备注

此属性仅适用于通过 HTTP 或 HTTPS 协议发送的请求。

执行三层环境中的请求可能需要几分钟的时间。使用此属性可为长时间运行的请求指定附加时间。

