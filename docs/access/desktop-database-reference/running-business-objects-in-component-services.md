---
title: 在组件服务中运行业务对象
TOCTitle: Running business objects in component services
ms:assetid: 12103458-b1dd-10fc-37e8-883fd6c6b9d1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248893(v=office.15)
ms:contentKeyID: 48543328
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 23cb90161e5e0728aa652ae5d496216676f781a5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309203"
---
# <a name="running-business-objects-in-component-services"></a>在组件服务中运行业务对象

**适用于**：Access 2013、Office 2013

业务对象可以是可执行文件 (.exe) 或动态链接库 (.dll)。采用何种配置来运行业务对象取决于该对象是 .dll 还是 .exe 文件：

- 可以通过 DCOM 调用作为 .exe 文件创建的业务对象。如果通过 Internet 信息服务 (IIS) 使用此类业务对象，则还必须进行数据封送，这将降低客户端性能。

- 可以通过 IIS（以及 HTTP）使用作为 .dll 文件创建的业务对象。此类业务对象还可以在 DCOM 上使用，但只能通过组件服务或 Microsoft Transaction Server（如果使用 Windows NT）。业务对象 DLL 需要在 IIS 服务器计算机上进行注册，这样才能通过 IIS 进行访问。（有关如何配置 DLL 以在 DCOM 上运行的步骤，请参阅"[启用 DLL 以在 DCOM 上运行](enabling-a-dll-to-run-on-dcom.md)"部分。）


> [!NOTE]
> 当中间层上的业务对象作为组件服务组件实现时 (使用**GetObjectContext**、 **SetComplete**和**SetAbort**), 它们可以使用组件服务 (如果使用的是 Windows NT) context 对象, 则可以使用 "组件服务" (如果使用的是 MTS)跨多个客户端调用维护其状态。 此方案可以通过 DCOM 来实施，DCOM 通常在可信客户端与服务器 (Intranet) 之间实现。 
>
> 此时，客户端上的 [RDS.DataSpace](dataspace-object-rds.md) 对象和 [CreateObject](createobject-method-rds.md) 方法被事务上下文对象和 **CreateInstance** 方法（由 **ITransactionContext** 接口提供）所取代，并由组件服务实现。


## <a name="see-also"></a>另请参阅

- [在组件服务中运行业务对象 (SQL Server)](https://docs.microsoft.com/sql/ado/guide/remote-data-service/running-business-objects-in-component-services?view=sql-server-2017)
