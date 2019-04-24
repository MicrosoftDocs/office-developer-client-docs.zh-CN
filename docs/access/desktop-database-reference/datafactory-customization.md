---
title: DataFactory 自定义
TOCTitle: DataFactory customization
ms:assetid: 43cd7416-1f05-87ee-22f0-6cf0d2d1b39f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249205(v=office.15)
ms:contentKeyID: 48544511
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a5fc1c284ee7aae77c4fb067ad57d50200119594
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294502"
---
# <a name="datafactory-customization"></a><span data-ttu-id="cb810-102">DataFactory 自定义</span><span class="sxs-lookup"><span data-stu-id="cb810-102">DataFactory customization</span></span>


<span data-ttu-id="cb810-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="cb810-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="cb810-p101">远程数据服务 (RDS) 使您能够在三层客户端/服务器系统中很容易地执行数据访问。客户端数据控件可以指定连接和命令字符串参数，以便对远程数据源执行查询，或者指定连接字符串和 [Recordset](recordset-object-ado.md) 对象参数，以执行更新。</span><span class="sxs-lookup"><span data-stu-id="cb810-p101">Remote Data Service (RDS) provides a way to easily perform data access in a three-tier client/server system. A client data control specifies connection and command string parameters to perform a query on a remote data source, or connection string and [Recordset](recordset-object-ado.md) object parameters to perform an update.</span></span>

<span data-ttu-id="cb810-p102">参数将传递给服务器程序，后者将对远程数据源执行数据访问操作。RDS 提供了称为 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 对象的默认服务器程序。 **RDSServer.DataFactory** 对象将返回对客户端的查询所产生的任何 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="cb810-p102">The parameters are passed to a server program, which performs the data-access operation on the remote data source. RDS provides a default server program called the [RDSServer.DataFactory](datafactory-object-rdsserver.md) object. The **RDSServer.DataFactory** object returns any **Recordset** object produced by a query to the client.</span></span>

<span data-ttu-id="cb810-p103">但是， **RDSServer.DataFactory** 只能执行查询和更新。它无法对连接或命令字符串执行任何验证或处理。</span><span class="sxs-lookup"><span data-stu-id="cb810-p103">However, the **RDSServer.DataFactory** is limited to performing queries and updates. It cannot perform any validation or processing on the connection or command strings.</span></span>

<span data-ttu-id="cb810-p104">使用 ADO，可以指定让 **DataFactory** 与另一种类型的服务器程序（称为*处理程序*）配合工作。在用客户端连接和命令字符串访问数据源之前，处理程序可以对它们进行修改。此外，处理程序可以强制实施访问权，访问权控制客户端在数据源中读取和写入数据的能力。</span><span class="sxs-lookup"><span data-stu-id="cb810-p104">With ADO, you can specify that the **DataFactory** work in conjunction with another type of server program called a *handler*. The handler can modify client connection and command strings before they are used to access the data source. In addition, the handler can enforce access rights, which govern the ability of the client to read and write data to the data source.</span></span>

<span data-ttu-id="cb810-114">处理程序用来修改客户端参数和访问权的参数是在自定义文件的节中指定的。</span><span class="sxs-lookup"><span data-stu-id="cb810-114">The parameters the handler uses to modify client parameters and access rights are specified in sections of a customization file.</span></span>

<span data-ttu-id="cb810-115">有关自定义 **DataFactory** 对象的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="cb810-115">See the following topics for more information about customizing the **DataFactory** object:</span></span>

- [<span data-ttu-id="cb810-116">了解自定义文件</span><span class="sxs-lookup"><span data-stu-id="cb810-116">Understanding the Customization File</span></span>](understanding-the-customization-file.md)
- [<span data-ttu-id="cb810-117">自定义文件 Connect 部分</span><span class="sxs-lookup"><span data-stu-id="cb810-117">Customization File Connect section</span></span>](customization-file-connect-section.md)
- [<span data-ttu-id="cb810-118">自定义文件 SQL 部分</span><span class="sxs-lookup"><span data-stu-id="cb810-118">Customization File SQL section</span></span>](customization-file-sql-section.md)
- [<span data-ttu-id="cb810-119">自定义文件 UserList 部分</span><span class="sxs-lookup"><span data-stu-id="cb810-119">Customization File UserList section</span></span>](customization-file-userlist-section.md)
- [<span data-ttu-id="cb810-120">自定义文件 Logs 部分</span><span class="sxs-lookup"><span data-stu-id="cb810-120">Customization File Logs section</span></span>](customization-file-logs-section.md)
- [<span data-ttu-id="cb810-121">必需的客户端设置</span><span class="sxs-lookup"><span data-stu-id="cb810-121">Required client settings</span></span>](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/required-client-settings)
- [<span data-ttu-id="cb810-122">编写自己的自定义处理程序</span><span class="sxs-lookup"><span data-stu-id="cb810-122">Writing your own customized handler</span></span>](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/writing-your-own-customized-handler)
