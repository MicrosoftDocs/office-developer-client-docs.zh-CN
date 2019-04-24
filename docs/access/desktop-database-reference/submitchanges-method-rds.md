---
title: SubmitChanges 方法 (RDS)
TOCTitle: SubmitChanges method (RDS)
ms:assetid: ecaea12d-7e1a-095d-17e7-d631ef230b90
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250201(v=office.15)
ms:contentKeyID: 48548521
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ea7f3e27a75b4483cb8cf46e27d4492f831cff33
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314397"
---
# <a name="submitchanges-method-rds"></a>SubmitChanges 方法 (RDS)

**适用于**：Access 2013、Office 2013

可向在 [Connect](connect-property-rds.md) 属性或 [URL](url-property-rds.md) 属性中指定的数据源提交在本地缓存且可更新的 [Recordset](recordset-object-ado.md) 的挂起更改。

## <a name="syntax"></a>语法

*rds.datacontrol*。SubmitChanges

*DataFactory*。SubmitChanges*连接*、 *Recordset*

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*DataControl* |一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。|
|*DataFactory* |一个代表 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 对象的对象变量。|
|*Connection* |**字符串型** 值，表示用 **RDS.DataControl** 对象的 **Connect** 属性创建的连接。|
|*Recordset* |一个代表 **Recordset** 对象的对象变量。|

## <a name="remarks"></a>注解

必须先设置 [Connect](connect-property-rds.md)、[Server](server-property-rds.md) 和 [SQL](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/sql-property-ado) 属性，然后才能将 **SubmitChanges** 方法用于 **RDS.DataControl** 对象。

如果在调用 **SubmitChanges** 后，针对同一 **Recordset** 对象又调用 [CancelUpdate](cancelupdate-method-rds.md) 方法，则由于更改已提交，**CancelUpdate** 调用将失败。

对于修改操作，只发送已更改的记录，并且所有更改要么都成功，要么都失败。

只能将**SubmitChanges**用于*默认*的**rdsserver.datafactory DataFactory**对象。 自定义业务对象不能使用此方法。

如果设置了 **URL** 属性，则 **SubmitChanges** 将更改提交到 URL 指定的位置。

