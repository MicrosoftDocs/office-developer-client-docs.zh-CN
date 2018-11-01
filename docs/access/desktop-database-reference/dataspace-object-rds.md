---
title: DataSpace 对象 (RDS)
TOCTitle: DataSpace Object (RDS)
ms:assetid: 7db181d5-422b-49fe-b6af-a20f5da520ff
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249527(v=office.15)
ms:contentKeyID: 48545862
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1715a1d1207955d47897fee8ba191117bcfaa244
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25882915"
---
# <a name="dataspace-object-rds"></a>DataSpace 对象 (RDS)

**适用于**： Access 2013、 Office 2013

创建位于中间层的自定义业务对象的客户端代理。

## <a name="remarks"></a>说明

远程数据服务需要业务对象代理，以便客户端组件可以与位于中间层的业务对象通信。通过代理，可以方便地利用跨进程或计算机边界的应用程序的 [Recordset](recordset-object-ado.md) 数据的打包、解包和传输（封送处理）功能。

远程数据服务使用 **RDS.DataSpace** 对象的 [CreateObject](createobject-method-rds.md) 方法创建业务对象代理。每当创建业务对象的中间层业务对象对应方的实例时，就会动态创建业务对象代理。远程数据服务支持下列协议：HTTP、HTTPS（HTTP 安全套接字）、DCOM 以及进程中（客户端组件和驻留在同一计算机上的业务对象）。

> [!NOTE]
> [!注释] 当 **RDS.DataSpace** 对象使用 HTTP 或 HTTPS 协议时，RDS 的行为模式为"无状态"。即，服务器返回响应后，就会丢弃有关客户端请求的所有内部信息。

尽管好像在业务对象代理的整个生命周期中都存在业务对象，而实际上仅在将响应发送给请求之前才存在业务对象。发送请求后（即，调用了业务对象的方法），代理会打开一个与服务器的新连接，服务器会创建该业务对象的新实例。业务对象响应请求后，服务器会破坏业务对象并关闭连接。

这种行为意味着您不能使用业务对象属性或变量将数据从一个请求传递到另一个请求。必须使用某些其他机制（如文件或方法参数）来保留状态数据。

**RDS.DataSpace** 对象的类 ID 为 BD96C556-65A3-11D0-983A-00C04FC29E36。

