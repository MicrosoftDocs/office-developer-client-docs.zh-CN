---
title: 启用 DLL 以在 DCOM 上运行
TOCTitle: Enabling a DLL to run on DCOM
ms:assetid: b405f767-91f0-c869-d34e-7a953de49106
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249859(v=office.15)
ms:contentKeyID: 48547211
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f9feb189221a1d447e6c2e0242240ca13784b7fe
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25946459"
---
# <a name="enabling-a-dll-to-run-on-dcom"></a><span data-ttu-id="fb1c8-102">启用 DLL 以在 DCOM 上运行</span><span class="sxs-lookup"><span data-stu-id="fb1c8-102">Enabling a DLL to run on DCOM</span></span>


<span data-ttu-id="fb1c8-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="fb1c8-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="fb1c8-104">以下步骤概述了如何启用业务对象动态链接库，使用 DCOM 和 Microsoft Internet 信息服务 (HTTP) 通过组件服务。</span><span class="sxs-lookup"><span data-stu-id="fb1c8-104">The following steps outline how to enable a business object dynamic-link libraries to use both DCOM and Microsoft Internet Information Services (HTTP) via Component Services.</span></span>

1.  <span data-ttu-id="fb1c8-p101">在组件服务 MMC 管理单元中创建一个新的空包。 您将使用组件服务 MMC 管理单元来创建包，并将 DLL 添加到此包中。执行此操作之后，可通过 DCOM 访问 .dll，但无法通过 IIS 进行访问。（如果在注册表中查看 .dll，则 **Inproc** 项现在为空。设置激活属性，在 **Inproc** 项中添加值，本主题后面将对此进行解释。）</span><span class="sxs-lookup"><span data-stu-id="fb1c8-p101">Create a new empty package in the Component Services MMC snap-in. You will use the Component Services MMC snap-in to create a package and add the DLL into this package. This makes the .dll accessible through DCOM, but it removes the accessibility through IIS. (If you check in the registry for the .dll, the **Inproc** key is now empty; setting the Activation attribute, explained later in this topic, adds a value in the **Inproc** key.)</span></span>

2.  <span data-ttu-id="fb1c8-p102">将业务对象安装在包中。 -或者- 将 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 对象导入包中。</span><span class="sxs-lookup"><span data-stu-id="fb1c8-p102">Install a business object into the package. -or- Import the [RDSServer.DataFactory](datafactory-object-rdsserver.md) object into the package.</span></span>

3.  <span data-ttu-id="fb1c8-p103">将包的激活属性设置为 **In the creator's process** （库应用程序）。 若要在同一台计算机上通过 DCOM 和 IIS 访问 .dll，必须在组件服务 MMC 管理单元中设置组件的激活属性。将属性设置为 **In the creator's process** 之后，您会注意到注册表中添加了 **Inproc** 服务器项，该项指向组件服务代理 .dll。</span><span class="sxs-lookup"><span data-stu-id="fb1c8-p103">Set the Activation attribute for the package to **In the creator's process** (Library application). To make the .dll accessible through DCOM and IIS on the same computer, you must set the component's Activation attribute in the Component Services MMC snap-in. After you set the attribute to **In the creator's process**, you will notice that an **Inproc** server key in the registry has been added that points to a Component Services surrogate .dll.</span></span>

