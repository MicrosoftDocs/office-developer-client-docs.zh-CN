---
title: DataControl 对象 (RDS)
TOCTitle: DataControl object (RDS)
ms:assetid: ac430669-7628-696c-c036-b5d35405d788
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249801(v=office.15)
ms:contentKeyID: 48547001
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 8cb71c5e51e56447636b25639dae0733a729bdb1
ms.sourcegitcommit: 48bfe5ab15b11105f4f52937b886c92bdc26525a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25910864"
---
# <a name="datacontrol-object-rds"></a>DataControl 对象 (RDS)

**适用于**： Access 2013、 Office 2013

将数据查询[Recordset](recordset-object-ado.md)绑定到一个或多个控件 （如文本框、 网格控件或组合框） 以便在网页上显示**Recordset**数据。

## <a name="syntax"></a>语法

```vb
    <OBJECT CLASSID="clsid:BD96C556-65A3-11D0-983A-00C04FC29E33" ID="DataControl"
       <PARAM NAME="Connect" VALUE="DSN=DSNName;UID=usr;PWD=pw;">
       <PARAM NAME="Server" VALUE="https://awebsrvr">
       <PARAM NAME="SQL" VALUE="QueryText">
    </OBJECT>
```

## <a name="remarks"></a>说明

**RDS.DataControl** 对象的类 ID 为 BD96C556-65A3-11D0-983A-00C04FC29E33。

> [!NOTE]
> [!注释] 如果出现一个错误，指示 [RDS.DataSpace](dataspace-object-rds.md) 或 **RDS.DataControl** 对象没有加载，请确保使用的类 ID 正确。这些对象的类 ID 已从版本 1.0 更改为版本 1.1。

对于基本方案，只需设置 **RDS.DataControl** 对象的 **SQL** 、 **Connect** 和 **Server** 属性, 该对象会自动调用默认业务对象 [RDSServer.DataFactory](datafactory-object-rdsserver.md)。

**RDS.DataControl** 中的所有属性都是可选的，因为自定义业务对象可以替代他们的功能。

> [!NOTE]
> [!注释] 如果查询多个结果，则仅返回第一个 [Recordset](recordset-object-ado.md)。 如果需要多个结果集，可将每个结果集分配给它自己的 **DataControl** 。 
> 
> 针对多个结果的查询的示例可以是以下： `"Select * from Authors, Select * from Topics"`。

如果在使用 **RDS.DataControl** 对象时将"DFMode=20;"添加到连接字符串中，则可以提高服务器更新数据时的性能。通过使用此设置，服务器上的 **RDSServer.DataFactory** 对象可使用资源占用量较少的模式。但是，以下功能在此配置中不可用：

  - 使用参数化的查询。

  - 调用 **Execute** 方法之前获取参数信息或列信息。

  - 将 **Transact Updates** 设置为 **True** 。

  - 获取行状态。

  - 调用 [Resync](resync-method-ado.md) 方法。

  - 通过 [Update Resync](update-resync-property-dynamic-ado.md) 属性刷新（显式或自动）。

  - 设置 **Command** 或 [Recordset](recordset-sourcerecordset-properties-rds.md) 属性。

  - 使用 **adCmdTableDirect** 。

默认情况下， **RDS.DataControl** 对象在异步模式下运行。如果需要同步执行应用程序，可将 [ExecuteOptions](executeoptions-property-rds.md) 参数设置为等于 **adcExecSync** ，将 [FetchOptions](fetchoptions-property-rds.md) 参数设置为等于 **adcFetchUpFront** ，如以下示例所示。

```vb
    <OBJECT CLASSID="clsid:BD96C556-65A3-11D0-983A-00C04FC29E33" 
        ID="DataControl"
       <PARAM NAME="Connect" VALUE="DSN=DSNName;UID=usr;PWD=pw;">
       <PARAM NAME="Server" VALUE="https://awebsrvr">
       <PARAM NAME="SQL" VALUE="QueryText">
       <PARAM NAME="ExecuteOptions" VALUE="1">
       <PARAM NAME="FetchOptions" VALUE="1">
    </OBJECT>
```

使用一个 **RDS.DataControl** 对象将一个查询的结果链接到一个或多个可视控件。例如，假设您要编写一个请求客户数据（姓名、住址、出生地、年龄和客户状态优先级）的查询。您可以使用一个 **RDS.DataControl** 对象在三个单独的文本框中显示客户姓名、年龄和地区；在一个复选框中显示客户状态优先级；并在一个网格控件中显示所有数据。

使用不同的 **RDS.DataControl** 对象将多个查询的结果链接到不同的可视控件。例如，假设您使用一个查询获取有关客户的信息，使用第二个查询获取有关客户已购商品的信息。您希望在三个文本框和一个复选框中显示第一个查询的结果，在网格控件中显示第二个查询的结果。如果使用默认业务对象（**RDSServer.DataFactory**），您需要执行以下操作：

  - 添加两个**rds.DataControl**对象与您的网页。

  - 编写两个查询，分别用于两个 **RDS.DataControl** 对象的每个 **SQL** 属性。一个 **RDS.DataControl** 对象将包含请求客户信息的 SQL 查询；另一个对象将包含请求客户已购商品列表的查询。

  - 在绑定控件各个 OBJECT 标记中，指定 DATAFLD 值以设置要在每个可视控件中显示的数据的值。

Rds.**的数量没有计数限制DataControl**可以通过 OBJECT 标记单个网页上嵌入的对象。

当您定义**rds.DataControl**网页上对象，请使用如 1 的非零**Height**和**Width**值 （以避免包含额外空间）。

远程数据服务客户端组件已作为 Internet Explorer 4.0 的一部分提供，因此不需要在 **RDS.DataControl** 对象标记中包括 CODEBASE 参数。

使用 Internet Explorer 4.0 或更高版本，仅当数据标记为单元模型控件时，才能使用 HTML 控件和 ActiveX® 控件绑定数据。

**Microsoft Visual Basic 用户****Rds.DataControl**仅在基于 web 的应用程序中使用。 Visual Basic 客户端应用程序不需要它。

