---
title: RDS 编程模型详述
TOCTitle: RDS programming model in detail
ms:assetid: 133fc059-9b51-52e2-2e61-339716d8d965
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248906(v=office.15)
ms:contentKeyID: 48543364
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4a2312be682ee63368397109377690b6dde3e627
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300866"
---
# <a name="rds-programming-model-in-detail"></a>RDS 编程模型详述

**适用于**：Access 2013、Office 2013

以下列出了 RDS 编程模型的主要组成部分：

- RDS.DataSpace
- rdsserver.datafactory。 DataFactory
- RDS.rds.datacontrol
- 事件

## <a name="rdsdataspace"></a>RDS.DataSpace

客户端应用程序必须指定要调用的服务器和服务器程序。反过来，应用程序收到一个针对服务器程序的引用，该引用可以被视作服务器程序本身。

RDS 对象模型通过 [RDS.DataSpace](dataspace-object-rds.md) 对象来实现此功能。

服务器程序用程序标识符或 *ProgID* 来指定。服务器使用 *ProgID* 以及服务器计算机的注册表来查找有关要初始化的实际程序的信息。

根据服务器程序是位于 Internet 或 Intranet 上的远程服务器上，还是位于局域网中的服务器上，还是根本不在服务器上而是位于本地动态链接库 (DLL) 上，RDS 将在内部区别对待。该区别决定了客户端与服务器之间的信息交换方式，并造成返回客户端应用程序的引用类型的切实不同。不过，从您的角度而言，这种区别并没有什么特殊意义，对于您而言，最重要的是收到一个可用的程序引用。

## <a name="rdsserverdatafactory"></a>rdsserver.datafactory。 DataFactory

RDS 提供了一个默认的服务器程序，该程序可以针对数据源执行 SQL 查询并返回 [Recordset](recordset-object-ado.md) 对象，还可以采用 **Recordset** 对象并更新数据源。

RDS 对象模型通过 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 对象来实现此功能。

此外, 此对象还提供了一种方法, 用于创建可通过编程方式填充的空**Recordset**对象 ([CreateRecordset](createrecordset-method-rds.md)), 另一种方法是将**Recordset**对象转换为文本字符串以生成网页 ([ConvertToString](converttostring-method-rds.md))。

通过 ADO，可以用 **DataFactory** 处理程序和包含连接、命令和安全参数的自定义文件替代 **RDSServer.DataFactory** 的某些标准连接和命令行为。

服务器程序有时也称为*业务对象*。您可以编写自定义的业务对象，用于执行复杂的数据访问、有效性检查等。即使是在编写自定义业务对象时，您也可以创建 **RDSServer.DataFactory** 对象的实例并使用该对象的某些方法来完成您自己的任务。

## <a name="rdsdatacontrol"></a>RDS.rds.datacontrol

可以通过 RDS 提供的方法，将 **RDS.DataSpace** 和 **RDSServer.DataFactory** 的功能结合在一起，并启用可视控件，以轻松地使用查询从数据源返回的 **Recordset** 对象。最常见的情况是，RDS 会尽可能地自动获取有关服务器的信息的访问权，并将信息显示在可视控件中。

RDS 对象模型通过 [RDS.DataControl](datacontrol-object-rds.md) 对象来实现此功能。

**RDS.DataControl** 具有两个方面。其中一个方面关系到数据源。如果使用 **RDS.DataControl** 的 **Connect** 和 **SQL** 属性设置命令和连接信息，则它将自动使用 **RDS.DataSpace** 创建针对默认 **RDSServer.DataFactory** 对象的引用。随后，**RDSServer.DataFactory** 将使用 **Connect** 属性值连接到数据源，使用 **SQL** 属性值从数据源获取 **Recordset**，并将 **Recordset** 对象返回给 **RDS.DataControl**。

另一个方面关系到可视控件中返回的 **Recordset** 信息的显示。 您可以将可视控件与 RDS 控件相关联 **。rds.datacontrol** (在进程中称为 "绑定"), 并获取相关**Recordset**对象中的信息的访问权限, 在 Microsoft Internet Explorer 中的网页上显示查询结果。 每个 **RDS.DataControl** 对象将一个表示单个查询结果的 **Recordset** 对象绑定到一个或多个可视控件（如文本框、组合框、网格控件等）。 每个页面上可能有多个 **RDS.DataControl** 对象。 每个 **RDS.DataControl** 对象可以连接到不同的数据源，并包含不同查询的结果。

对于关联的 **Recordset** 对象的行，**RDS.DataControl** 对象还有自己的导航、排序和筛选方法。这些方法与 ADO **Recordset** 对象的方法很类似，但不尽相同。

## <a name="events"></a>事件

RDS 支持自己的两个事件，这些事件独立于 ADO 事件模型。 每当 RDS 发生时, 将调用[onReadyStateChange](onreadystatechange-event-rds.md)事件 **。rds.datacontrol** [ReadyState](readystate-property-rds.md)属性的更改, 从而在异步操作成功完成、终止或遇到错误时通知您。 只要发生错误，便调用 [onError](onerror-event-rds.md) 事件，即使该错误发生于异步操作过程中也不例外。

> [!NOTE]
> Microsoft Internet Explorer 为 RDS 提供了其他两个事件：**onDataSetChanged**（**Recordset** 可用但仍在检索行）和 **onDataSetComplete**（**Recordset** 已完成行的检索）。


