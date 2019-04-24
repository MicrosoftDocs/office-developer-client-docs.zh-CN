---
title: CancelUpdate 方法 (RDS)
TOCTitle: CancelUpdate method (RDS)
ms:assetid: 373a3feb-125d-915a-fd56-d4b04b20db54
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249130(v=office.15)
ms:contentKeyID: 48544188
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b0c02a9ca72add763e1d3ccf62d5ede8adaecc6b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296666"
---
# <a name="cancelupdate-method-rds"></a>CancelUpdate 方法 (RDS)

**适用于**：Access 2013、Office 2013

用于取消对 [Recordset](recordset-object-ado.md) 对象的当前行或新行所做的任何更改。

## <a name="syntax"></a>语法

*rds.datacontrol*。CancelUpdate

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*DataControl* |一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。|

## <a name="remarks"></a>注解

Cursor Service for OLE DB 同时保留原始值的副本和所做更改的缓存。在调用 **CancelUpdate** 时，所做更改的缓存会重置为空，且任何绑定控件都用原始数据进行刷新。

