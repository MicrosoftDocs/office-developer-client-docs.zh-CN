---
title: DataFactory 对象 (RDSServer)
TOCTitle: DataFactory object (RDSServer)
ms:assetid: 1de76cdd-34dc-8547-29aa-48ad6067bdea
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248971(v=office.15)
ms:contentKeyID: 48543605
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4090b517dfdbe6d6870c04bf4118addad861ad95
ms.sourcegitcommit: 48bfe5ab15b11105f4f52937b886c92bdc26525a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25910633"
---
# <a name="datafactory-object-rdsserver"></a>DataFactory 对象 (RDSServer)


**适用于**： Access 2013、 Office 2013

该默认服务器端业务对象实现的某些方法，为客户端应用程序提供对指定数据源的读/写数据访问权限。

## <a name="remarks"></a>说明

**RDSServer.DataFactory** 对象是作为接收客户端请求的服务器端 Automation 对象设计的。 在 Internet 实现中，它驻留在 web 服务器上并实例化 ADISAPI 组件。 **RDSServer.DataFactory** 对象提供对指定数据源的读写访问权限，但不包含任何验证或业务规则逻辑。

如果使用在 **RDSServer.DataFactory** 和 [RDS.DataControl](datacontrol-object-rds.md) 对象中都可用的方法，则远程数据服务默认情况下会使用的 **RDS.DataControl** 版本。默认情况下假定为基本编程方案，在该方案中， **RDSServer.DataFactory** 作为泛型服务器端业务对象。

如果您希望您的 web 应用程序，以处理特定于任务的服务器端处理，您可以将替换自定义业务对象**RDSServer.DataFactory** 。

可以创建调用 **RDSServer.DataFactory** 方法的服务器端业务对象，例如， [Query](query-method-rds.md) 和 [CreateRecordset](createrecordset-method-rds.md)。如果希望向业务对象添加功能，但要利用现有远程数据服务技术，这种方式非常有用。

**RDSServer.DataFactory** 对象的类 ID 为 9381D8F5-0288-11D0-9501-00AA00B911A5。

