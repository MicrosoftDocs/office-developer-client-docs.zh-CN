---
title: RDS 编程模型与对象
TOCTitle: RDS Programming Model with Objects
ms:assetid: 207150ec-8eb5-bec5-3059-db37a0e28c19
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248987(v=office.15)
ms:contentKeyID: 48543663
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 833d3676c8fa3fac1e5cb8e16477073cde611199
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466489"
---
# <a name="rds-programming-model-with-objects"></a><span data-ttu-id="905f1-102">RDS 编程模型与对象</span><span class="sxs-lookup"><span data-stu-id="905f1-102">RDS Programming Model with Objects</span></span>


<span data-ttu-id="905f1-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="905f1-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="905f1-p101">RDS 的目标是通过 IIS 等中介访问并更新数据源。编程模型指定完成此目标所需的活动序列。对象模型则指定其方法和属性会影响编程模型的对象。</span><span class="sxs-lookup"><span data-stu-id="905f1-p101">The goal of RDS is to gain access to and update data sources through an intermediary such as IIS. The programming model specifies the sequence of activities necessary to accomplish this goal. The object model specifies the objects whose methods and properties affect the programming model.</span></span>

<span data-ttu-id="905f1-107">RDS 提供了执行以下操作序列的方法：</span><span class="sxs-lookup"><span data-stu-id="905f1-107">RDS provides the means to perform the following sequence of actions:</span></span>

  - <span data-ttu-id="905f1-108">指定要在服务器上调用的程序，并获得从客户端 ([RDS.DataSpace](dataspace-object-rds.md)) 引用该程序的方式（代理）。</span><span class="sxs-lookup"><span data-stu-id="905f1-108">Specify the program to be invoked on the server, and obtain a way (proxy) to refer to it from the client ([RDS.DataSpace](dataspace-object-rds.md)).</span></span>

  - <span data-ttu-id="905f1-p102">调用服务器程序。向服务器程序传递参数，该参数可标识数据源和要发出的命令（代理或 [RDS.DataControl](datacontrol-object-rds.md)）。</span><span class="sxs-lookup"><span data-stu-id="905f1-p102">Invoke the server program. Pass parameters to the server program that identifies the data source and the command to issue (proxy or [RDS.DataControl](datacontrol-object-rds.md)).</span></span>

  - <span data-ttu-id="905f1-p103">服务器程序从数据源获得 [Recordset](recordset-object-ado.md) 对象（通常使用 ADO）。还可以在服务器 ([RDSServer.DataFactory](datafactory-object-rdsserver.md)) 上处理 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="905f1-p103">The server program obtains a [Recordset](recordset-object-ado.md) object from the data source, typically by using ADO. Optionally, the **Recordset** object is processed on the server ([RDSServer.DataFactory](datafactory-object-rdsserver.md)).</span></span>

  - <span data-ttu-id="905f1-113">服务器程序将最终的 **Recordset** 对象返回给客户端应用程序（代理）。</span><span class="sxs-lookup"><span data-stu-id="905f1-113">The server program returns the final **Recordset** object to the client application (proxy).</span></span>

  - <span data-ttu-id="905f1-114">在客户端上，将 **Recordset** 对象转换成可视控件（可视控件和 **RDS.DataControl**）很容易使用的形式。</span><span class="sxs-lookup"><span data-stu-id="905f1-114">On the client, the **Recordset** object is put into a form that can be easily used by visual controls (visual control and **RDS.DataControl**).</span></span>

  - <span data-ttu-id="905f1-115">对 **Recordset** 对象的更改将发送回服务器，并用来更新数据源 (**RDS.DataControl** 或 **RDSServer.DataFactory**)。</span><span class="sxs-lookup"><span data-stu-id="905f1-115">Changes to the **Recordset** object are sent back to the server and used to update the data source (**RDS.DataControl** or **RDSServer.DataFactory**).</span></span>
