---
title: Server 属性 (RDS)
TOCTitle: Server property (RDS)
ms:assetid: 17519dbe-a43a-1d0d-22c1-dc0def2f63ab
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248926(v=office.15)
ms:contentKeyID: 48543448
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4f35910591d86e0e5a2b92d680be3c5f64504088
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28710347"
---
# <a name="server-property-rds"></a>Server 属性 (RDS)

**适用于**： Access 2013、 Office 2013

指示 Internet 信息服务 (IIS) 名称和通信协议。

可以在设计时在 **RDS.DataControl** 对象的 OBJECT 标记中设置 [Server](datacontrol-object-rds.md) 属性，也可以在运行时在脚本代码中进行设置。

## <a name="syntax"></a>语法

|协议|设计时语法|
|:-------|:-----------------|
|HTTP|`<PARAM NAME="Server" VALUE="https://awebsrvr:port">`|
|HTTPS|`<PARAM NAME="Server" VALUE="https://awebsrvr:port">`|
|DCOM|`<PARAM NAME="Server" VALUE="computername">`|
|In-process|`<PARAM NAME="Server" VALUE="">`|


|协议|运行时语法|
|:-------|:--------------|
|HTTP|`DataControl.Server="https://awebsrvr:port"`|
|HTTPS|`DataControl.Server="https://awebsrvr:port"`|
|DCOM|`DataControl.Server="computername"`|
|In-process|`DataControl.Server=""`|


## <a name="parameters"></a>参数

|参数|说明|
|:--------|:----------|
|*awebsrvr*或*computername* |一个包含 Internet 或 Intranet 路径的 **String** 值，如果服务器位于远程计算机上，则为计算机名；如果服务器位于本地计算机上，则为空字符串。|
|*端口* |可选。 用于连接到的 IIS 服务器的端口。 在 Internet Explorer 中设置的端口号 （在**工具**菜单中，单击**Internet 选项**，然后选择**连接**选项卡） 或在 IIS 中。|
|*DataControl* |一个代表 **RDS.DataControl** 对象的对象变量。|

## <a name="remarks"></a>说明

服务器是处理 **RDS.DataControl** 请求（即查询或更新）的位置。 默认情况下，所有请求均由 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 对象、 [MSDFMAP.Handler](datafactory-customization.md) 组件以及指定的服务器上的 [MSDFMAP.INI](understanding-the-customization-file.md) 文件进行处理。 

在更换服务器时应记住这一点，以便调整新旧 **MSDFMAP.INI** 文件中的设置。 不兼容会导致在一台服务器上成功处理的请求在另一台服务器上失败。 如果 Server 属性设置为 ""，则将在本地计算机上使用这些对象。

