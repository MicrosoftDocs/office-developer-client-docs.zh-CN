---
title: 基本 RDS 编程模型
TOCTitle: Basic RDS programming model
ms:assetid: a8dd22b0-ac9b-b5c3-4e31-d2990d36230a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249781(v=office.15)
ms:contentKeyID: 48546911
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 947a6355d07ba2e9fb9b2a9b76c4c1941d83e668
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296883"
---
# <a name="basic-rds-programming-model"></a>基本 RDS 编程模型

**适用于**：Access 2013、Office 2013

RDS 针对的是存在于以下环境中的应用程序：客户端应用程序指定了一个将在服务器上执行的程序，以及返回所需信息所必需的参数。服务器上调用的程序对指定数据源进行访问，检索信息，还可以处理数据，然后将得到的信息以便于使用的形式返回给客户端应用程序。RDS 为您执行以下操作序列提供了途径：

- 指定要在服务器上调用的程序，获得从客户端引用它的方式。（该引用有时称为*代理*。它代表远程服务器程序。客户端应用程序将“调用”该代理，就好像它是本地程序，但实际上它调用的是远程服务器程序。）

- 调用服务器程序。将用于标识数据源和要发出的命令的参数传递给服务器程序。（服务器程序实际上使用 ADO 来访问该数据源。ADO 用一个给定参数建立连接，然后发出在另一个参数中指定的命令。）

- 服务器程序从数据源获得 [Recordset](recordset-object-ado.md) 对象。还可以在服务器上处理 **Recordset** 对象。

- 服务器程序将最终的 **Recordset** 对象返回给客户端应用程序。

- 在客户端上， **Recordset** 对象将转换为可视控件很容易使用的形式。

- 对 **Recordset** 对象的任何修改都将发送到服务器程序，后者将使用它们来更新数据源。

此编程模型包含某些方便功能。如果不需要复杂的服务器程序来访问数据源，并且您提供了必需的连接和命令参数，则 RDS 将用简单的默认服务器程序自动检索指定的数据。

如果需要进行更复杂的处理，则可以指定自己的自定义服务器程序。例如，由于自定义服务器程序有受其支配的完整的 ADO 功能，因此它可以连接到几个不同的数据源，然后将它们的数据以某种复杂的方式组合在一起，之后再将经过处理的简单结果返回给客户端应用程序。

最后，如果您的需要介于这二者之间，ADO 现在支持默认服务器程序的行为进行自定义。

