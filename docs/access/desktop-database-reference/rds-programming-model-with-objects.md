---
title: 包含对象的 RDS 编程模型
TOCTitle: RDS programming model with objects
ms:assetid: 207150ec-8eb5-bec5-3059-db37a0e28c19
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248987(v=office.15)
ms:contentKeyID: 48543663
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9743fb1e7329457abb60ed8ed41bc39067f3551d
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28710963"
---
# <a name="rds-programming-model-with-objects"></a>包含对象的 RDS 编程模型

**适用于**： Access 2013、 Office 2013

RDS 的目标是通过 IIS 等中介访问并更新数据源。编程模型指定完成此目标所需的活动序列。对象模型则指定其方法和属性会影响编程模型的对象。

RDS 提供了执行以下操作序列的方法：

- 指定要在服务器上调用的程序，并获得从客户端 ([RDS.DataSpace](dataspace-object-rds.md)) 引用该程序的方式（代理）。

- 调用服务器程序。向服务器程序传递参数，该参数可标识数据源和要发出的命令（代理或 [RDS.DataControl](datacontrol-object-rds.md)）。

- 服务器程序从数据源获得 [Recordset](recordset-object-ado.md) 对象（通常使用 ADO）。还可以在服务器 ([RDSServer.DataFactory](datafactory-object-rdsserver.md)) 上处理 **Recordset** 对象。

- 服务器程序将最终的 **Recordset** 对象返回给客户端应用程序（代理）。

- 在客户端上，将 **Recordset** 对象转换成可视控件（可视控件和 **RDS.DataControl**）很容易使用的形式。

- 对 **Recordset** 对象的更改将发送回服务器，并用来更新数据源 (**RDS.DataControl** 或 **RDSServer.DataFactory**)。

