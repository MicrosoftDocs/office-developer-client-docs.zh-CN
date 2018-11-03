---
title: SubmitChanges 方法 (RDS)
TOCTitle: SubmitChanges method (RDS)
ms:assetid: ecaea12d-7e1a-095d-17e7-d631ef230b90
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250201(v=office.15)
ms:contentKeyID: 48548521
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ba6b6ff2d373a8b05d0839d4cc113f48b47d8cad
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949584"
---
# <a name="submitchanges-method-rds"></a>SubmitChanges 方法 (RDS)

**适用于**： Access 2013、 Office 2013

可向在 [Connect](recordset-object-ado.md) 属性或 [URL](connect-property-rds.md) 属性中指定的数据源提交在本地缓存且可更新的 [Recordset](url-property-rds.md) 的挂起更改。

## <a name="syntax"></a>语法

*DataControl*。SubmitChanges

*DataFactory*。SubmitChanges*连接* *Recordset*

## <a name="parameters"></a>参数

|参数|说明|
|:--------|:----------|
|*DataControl* |一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。|
|*DataFactory* |一个代表 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 对象的对象变量。|
|*Connection* |**字符串型** 值，表示用 **RDS.DataControl** 对象的 **Connect** 属性创建的连接。|
|*Recordset* |一个代表 **Recordset** 对象的对象变量。|

## <a name="remarks"></a>备注

必须先设置 [Connect](connect-property-rds.md)、[Server](server-property-rds.md) 和 [SQL](https://msdn.microsoft.com/library/jj248989\(v=office.15\)) 属性，然后才能将 **SubmitChanges** 方法用于 **RDS.DataControl** 对象。

如果在调用 [SubmitChanges](cancelupdate-method-rds.md) 后，针对同一 **Recordset** 对象又调用 **CancelUpdate** 方法，则由于更改已提交， **CancelUpdate** 调用将失败。

对于修改操作，只发送已更改的记录，并且所有更改要么都成功，要么都失败。

**SubmitChanges**仅使用*默认* **RDSServer.DataFactory**对象。 自定义业务对象不能使用此方法。

如果设置了 **URL** 属性，则 **SubmitChanges** 将更改提交到 URL 指定的位置。

