---
title: 在组件服务中运行业务对象
TOCTitle: Running Business Objects in Component Services
ms:assetid: 12103458-b1dd-10fc-37e8-883fd6c6b9d1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248893(v=office.15)
ms:contentKeyID: 48543328
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c398dc0733b58c72fb021c104eaf1a546fd9c66a
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25881676"
---
# <a name="running-business-objects-in-component-services"></a><span data-ttu-id="13eb1-102">在组件服务中运行业务对象</span><span class="sxs-lookup"><span data-stu-id="13eb1-102">Running Business Objects in Component Services</span></span>


<span data-ttu-id="13eb1-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="13eb1-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="13eb1-p101">业务对象可以是可执行文件 (.exe) 或动态链接库 (.dll)。采用何种配置来运行业务对象取决于该对象是 .dll 还是 .exe 文件：</span><span class="sxs-lookup"><span data-stu-id="13eb1-p101">Business objects can be executable files (.exe) or dynamic-link libraries (.dll). The configuration you use to run the business object depends on whether the object is a .dll or .exe file:</span></span>

  - <span data-ttu-id="13eb1-p102">可以通过 DCOM 调用作为 .exe 文件创建的业务对象。如果通过 Internet 信息服务 (IIS) 使用此类业务对象，则还必须进行数据封送，这将降低客户端性能。</span><span class="sxs-lookup"><span data-stu-id="13eb1-p102">Business objects created as .exe files can be called through DCOM. If these business objects are used through Internet Information Services (IIS), they are subject to additional marshalingof data, which will slow client performance.</span></span>

  - <span data-ttu-id="13eb1-p103">可以通过 IIS（以及 HTTP）使用作为 .dll 文件创建的业务对象。此类业务对象还可以在 DCOM 上使用，但只能通过组件服务或 Microsoft Transaction Server（如果使用 Windows NT）。业务对象 DLL 需要在 IIS 服务器计算机上进行注册，这样才能通过 IIS 进行访问。（有关如何配置 DLL 以在 DCOM 上运行的步骤，请参阅"[启用 DLL 以在 DCOM 上运行](enabling-a-dll-to-run-on-dcom.md)"部分。）</span><span class="sxs-lookup"><span data-stu-id="13eb1-p103">Business objects created as .dll files can be used via IIS (and therefore HTTP). They can also be used over DCOM only via Component Services (or Microsoft Transaction Server, if you are using Windows NT). Business object DLLs will need to be registered on the IIS server computer to give you accessibility via IIS. (For steps on how to configure a DLL to run on DCOM, see the section, "[Enabling a DLL to Run on DCOM](enabling-a-dll-to-run-on-dcom.md).")</span></span>


> [!NOTE]
> <span data-ttu-id="13eb1-112">中间层上的业务对象是作为组件服务组件 （使用**GetObjectContext**、 **SetComplete**和**异常**） 实施的它们可以使用组件服务 （或 MTS，如果您使用的 Windows NT） 上下文对象添加到跨多个客户端呼叫维护其状态。</span><span class="sxs-lookup"><span data-stu-id="13eb1-112">When business objects on the middle tier are implemented as Component Services components (using **GetObjectContext**, **SetComplete**, and **SetAbort**), they can use Component Services (or MTS, if you are using Windows NT) context objects to maintain their state across multiple client calls.</span></span> <span data-ttu-id="13eb1-113">此方案可以通过 DCOM 来实施，DCOM 通常在可信客户端与服务器 (Intranet) 之间实现。</span><span class="sxs-lookup"><span data-stu-id="13eb1-113">This scenario is possible with DCOM, which is typically implemented between trusted clients and servers (an intranet).</span></span> 
>
> <span data-ttu-id="13eb1-114">此时，客户端上的 [RDS.DataSpace](dataspace-object-rds.md) 对象和 [CreateObject](createobject-method-rds.md) 方法被事务上下文对象和 **CreateInstance** 方法（由 **ITransactionContext** 接口提供）所取代，并由组件服务实现。</span><span class="sxs-lookup"><span data-stu-id="13eb1-114">In this case, the [RDS.DataSpace](dataspace-object-rds.md) object and [CreateObject](createobject-method-rds.md) method on the client side are replaced by the transaction context object and **CreateInstance** method (provided by the **ITransactionContext** interface), implemented by Component Services.</span></span>


## <a name="see-also"></a><span data-ttu-id="13eb1-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13eb1-115">See also</span></span>

- [<span data-ttu-id="13eb1-116">组件服务 (SQL Server) 中运行业务对象</span><span class="sxs-lookup"><span data-stu-id="13eb1-116">Running Business Objects in Component Services (SQL Server)</span></span>](https://docs.microsoft.com/sql/ado/guide/remote-data-service/running-business-objects-in-component-services?view=sql-server-2017)