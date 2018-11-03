---
title: 基本 RDS 编程模型
TOCTitle: Basic RDS programming model
ms:assetid: a8dd22b0-ac9b-b5c3-4e31-d2990d36230a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249781(v=office.15)
ms:contentKeyID: 48546911
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ad7a6d31fa973ffd8d04b4478d73a88312d52073
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25944808"
---
# <a name="basic-rds-programming-model"></a><span data-ttu-id="d3e5a-102">基本 RDS 编程模型</span><span class="sxs-lookup"><span data-stu-id="d3e5a-102">Basic RDS programming model</span></span>

<span data-ttu-id="d3e5a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="d3e5a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="d3e5a-p101">RDS 针对的是存在于以下环境中的应用程序：客户端应用程序指定了一个将在服务器上执行的程序，以及返回所需信息所必需的参数。服务器上调用的程序对指定数据源进行访问，检索信息，还可以处理数据，然后将得到的信息以便于使用的形式返回给客户端应用程序。RDS 为您执行以下操作序列提供了途径：</span><span class="sxs-lookup"><span data-stu-id="d3e5a-p101">RDS addresses applications that exist in the following environment: A client application specifies a program that will execute on a server and the parameters required to return the desired information. The program invoked on the server gains access to the specified data source, retrieves the information, optionally processes the data, and then returns the resulting information to your client application in a form that it can easily use. RDS provides the means for you to perform the following sequence of actions:</span></span>

- <span data-ttu-id="d3e5a-p102">指定要在服务器上调用的程序，获得从客户端引用它的方式。（该引用有时称为*代理*。它代表远程服务器程序。客户端应用程序将“调用”该代理，就好像它是本地程序，但实际上它调用的是远程服务器程序。）</span><span class="sxs-lookup"><span data-stu-id="d3e5a-p102">Specify the program to be invoked on the server, and obtain a way to refer to it from the client. (This reference is sometimes called a *proxy*. It represents the remote server program. The client application will "call" the proxy as if it were a local program, but it actually invokes the remote server program.)</span></span>

- <span data-ttu-id="d3e5a-p103">调用服务器程序。将用于标识数据源和要发出的命令的参数传递给服务器程序。（服务器程序实际上使用 ADO 来访问该数据源。ADO 用一个给定参数建立连接，然后发出在另一个参数中指定的命令。）</span><span class="sxs-lookup"><span data-stu-id="d3e5a-p103">Invoke the server program. Pass parameters to the server program that identify the data source and the command to issue. (The server program actually uses ADO to gain access to the data source. ADO makes a connection with one of the given parameters, and then issues the command specified in the other parameter.)</span></span>

- <span data-ttu-id="d3e5a-p104">服务器程序从数据源获得 [Recordset](recordset-object-ado.md) 对象。还可以在服务器上处理 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="d3e5a-p104">The server program obtains a [Recordset](recordset-object-ado.md) object from the data source. Optionally, the **Recordset** object is processed on the server.</span></span>

- <span data-ttu-id="d3e5a-117">服务器程序将最终的 **Recordset** 对象返回给客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="d3e5a-117">The server program returns the final **Recordset** object to the client application.</span></span>

- <span data-ttu-id="d3e5a-118">在客户端上， **Recordset** 对象将转换为可视控件很容易使用的形式。</span><span class="sxs-lookup"><span data-stu-id="d3e5a-118">On the client, the **Recordset** object is put into a form that can be easily used by visual controls.</span></span>

- <span data-ttu-id="d3e5a-119">对 **Recordset** 对象的任何修改都将发送到服务器程序，后者将使用它们来更新数据源。</span><span class="sxs-lookup"><span data-stu-id="d3e5a-119">Any modifications to the **Recordset** object are sent back to the server program, which uses them to update the data source.</span></span>

<span data-ttu-id="d3e5a-p105">此编程模型包含某些方便功能。如果不需要复杂的服务器程序来访问数据源，并且您提供了必需的连接和命令参数，则 RDS 将用简单的默认服务器程序自动检索指定的数据。</span><span class="sxs-lookup"><span data-stu-id="d3e5a-p105">This programming model contains certain convenience features. If you do not need a complex server program to access the data source, and if you provide the required connection and command parameters, RDS will automatically retrieve the specified data with a simple, default server program.</span></span>

<span data-ttu-id="d3e5a-p106">如果需要进行更复杂的处理，则可以指定自己的自定义服务器程序。例如，由于自定义服务器程序有受其支配的完整的 ADO 功能，因此它可以连接到几个不同的数据源，然后将它们的数据以某种复杂的方式组合在一起，之后再将经过处理的简单结果返回给客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="d3e5a-p106">If you need more complex processing, you can specify your own custom server program. For example, because a custom server program has the full power of ADO at its disposal, it could connect to several different data sources, combine their data in some complex way, and then return a simple, processed result to the client application.</span></span>

<span data-ttu-id="d3e5a-124">最后，如果您的需要介于这二者之间，ADO 现在支持默认服务器程序的行为进行自定义。</span><span class="sxs-lookup"><span data-stu-id="d3e5a-124">Finally, if your needs are somewhere in between, ADO now supports customizing the behavior of the default server program.</span></span>

