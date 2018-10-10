---
title: CancelUpdate 方法 (RDS)
TOCTitle: CancelUpdate Method (RDS)
ms:assetid: 373a3feb-125d-915a-fd56-d4b04b20db54
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249130(v=office.15)
ms:contentKeyID: 48544188
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ea646f2412ec078f3a45334ec2b1cdbe449285b6
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466794"
---
# <a name="cancelupdate-method-rds"></a>CancelUpdate 方法 (RDS)


**适用于**： Access 2013 |Office 2013



用于取消对 [Recordset](recordset-object-ado.md) 对象的当前行或新行所做的任何更改。

## <a name="syntax"></a>语法

*DataControl*。CancelUpdate

## <a name="parameters"></a>参数

  - *DataControl*

  - 一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。

## <a name="remarks"></a>备注

Cursor Service for OLE DB 同时保留原始值的副本和所做更改的缓存。在调用 **CancelUpdate** 时，所做更改的缓存会重置为空，且任何绑定控件都用原始数据进行刷新。

