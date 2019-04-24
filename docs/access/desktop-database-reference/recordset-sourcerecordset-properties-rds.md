---
title: Recordset、SourceRecordset 属性 (RDS)
TOCTitle: Recordset, SourceRecordset properties (RDS)
ms:assetid: 5f4bb72d-ddfa-41c0-c353-b3a6632b4a91
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249345(v=office.15)
ms:contentKeyID: 48545160
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: f83ab385b1fab511ab71ea9ff3456fe466efa17c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307586"
---
# <a name="recordset-sourcerecordset-properties-rds"></a>Recordset、SourceRecordset 属性 (RDS)

**适用于**：Access 2013、Office 2013

指示从自定义业务对象返回的 **Recordset** 对象。

## <a name="syntax"></a>语法

*rds.datacontrol*。SourceRecordset = *Recordset*

*Recordset* = *rds.datacontrol*。集

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*DataControl* |一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。|
|*Recordset* |一个代表 **Recordset** 对象的对象变量。|

## <a name="remarks"></a>注解

可以将 **SourceRecordset** 属性设置为从自定义业务对象返回的 [Recordset](recordset-object-ado.md)。

这些属性允许应用程序通过自定义进程处理绑定进程。这些属性接收的行集包装在 **Recordset** 中，因此可以直接与 **Recordset** 进行交互，同时可执行设置属性或遍历 **Recordset** 等操作。

可以设置 **SourceRecordset** 属性，也可以在运行时在脚本代码中读取 **Recordset** 属性。

**SourceRecordset** 为只写属性，与 **Recordset** 属性恰恰相反，后者为只读属性。

