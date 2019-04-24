---
title: DataFactory 对象 (rdsserver.datafactory)
TOCTitle: DataFactory object (RDSServer)
ms:assetid: 1de76cdd-34dc-8547-29aa-48ad6067bdea
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248971(v=office.15)
ms:contentKeyID: 48543605
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 77cd06992ef0062859d0a1372d115f8e65246a5d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294475"
---
# <a name="datafactory-object-rdsserver"></a><span data-ttu-id="eb89c-102">DataFactory 对象 (rdsserver.datafactory)</span><span class="sxs-lookup"><span data-stu-id="eb89c-102">DataFactory object (RDSServer)</span></span>


<span data-ttu-id="eb89c-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="eb89c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="eb89c-104">该默认服务器端业务对象实现的某些方法，为客户端应用程序提供对指定数据源的读/写数据访问权限。</span><span class="sxs-lookup"><span data-stu-id="eb89c-104">This default server-side business object implements methods that provide read/write data access to specified data sources for client-side applications.</span></span>

## <a name="remarks"></a><span data-ttu-id="eb89c-105">注解</span><span class="sxs-lookup"><span data-stu-id="eb89c-105">Remarks</span></span>

<span data-ttu-id="eb89c-106">**RDSServer.DataFactory** 对象是作为接收客户端请求的服务器端 Automation 对象设计的。</span><span class="sxs-lookup"><span data-stu-id="eb89c-106">The **RDSServer.DataFactory** object is designed as a server-side Automation object that receives client requests.</span></span> <span data-ttu-id="eb89c-107">在 Internet 实现中, 它驻留在 web 服务器上, 并由 ADISAPI 组件进行实例化。</span><span class="sxs-lookup"><span data-stu-id="eb89c-107">In an Internet implementation, it resides on a web server and is instantiated by the ADISAPI component.</span></span> <span data-ttu-id="eb89c-108">**RDSServer.DataFactory** 对象提供对指定数据源的读写访问权限，但不包含任何验证或业务规则逻辑。</span><span class="sxs-lookup"><span data-stu-id="eb89c-108">The **RDSServer.DataFactory** object provides read and write access to specified data sources, but doesn't contain any validation or business rules logic.</span></span>

<span data-ttu-id="eb89c-p102">如果使用在 **RDSServer.DataFactory** 和 [RDS.DataControl](datacontrol-object-rds.md) 对象中都可用的方法，则远程数据服务默认情况下会使用的 **RDS.DataControl** 版本。默认情况下假定为基本编程方案，在该方案中， **RDSServer.DataFactory** 作为泛型服务器端业务对象。</span><span class="sxs-lookup"><span data-stu-id="eb89c-p102">If you use a method that is available in both the **RDSServer.DataFactory** and [RDS.DataControl](datacontrol-object-rds.md) objects, Remote Data Service uses the **RDS.DataControl** version by default. The default assumes a basic programming scenario, where the **RDSServer.DataFactory** serves as a generic server-side business object.</span></span>

<span data-ttu-id="eb89c-111">如果希望 web 应用程序处理特定于任务的服务器端处理, 可以将 DataFactory 替换为自定义业务对象的**rdsserver.datafactory** 。</span><span class="sxs-lookup"><span data-stu-id="eb89c-111">If you want your web application to handle task-specific server-side processing, you can replace the **RDSServer.DataFactory** with a custom business object.</span></span>

<span data-ttu-id="eb89c-p103">可以创建调用 **RDSServer.DataFactory** 方法的服务器端业务对象，例如， [Query](query-method-rds.md) 和 [CreateRecordset](createrecordset-method-rds.md)。如果希望向业务对象添加功能，但要利用现有远程数据服务技术，这种方式非常有用。</span><span class="sxs-lookup"><span data-stu-id="eb89c-p103">You can create server-side business objects that call the **RDSServer.DataFactory** methods, such as [Query](query-method-rds.md) and [CreateRecordset](createrecordset-method-rds.md). This is helpful if you want to add functionality to your business objects, but take advantage of existing Remote Data Service technologies.</span></span>

<span data-ttu-id="eb89c-114">**RDSServer.DataFactory** 对象的类 ID 为 9381D8F5-0288-11D0-9501-00AA00B911A5。</span><span class="sxs-lookup"><span data-stu-id="eb89c-114">The class ID for the **RDSServer.DataFactory** object is 9381D8F5-0288-11D0-9501-00AA00B911A5.</span></span>

