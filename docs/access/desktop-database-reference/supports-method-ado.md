---
title: Supports 方法 (ADO)
TOCTitle: Supports method (ADO)
ms:assetid: 2b4062ce-44df-4e84-1ce9-d6618c10c2af
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249059(v=office.15)
ms:contentKeyID: 48543924
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4aa04cf3d04b71e0a84279bfc5340e7ee326de48
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949622"
---
# <a name="supports-method-ado"></a>Supports 方法 (ADO)

**适用于**： Access 2013、 Office 2013

用于确定指定的 [Recordset](recordset-object-ado.md) 对象是否支持特定类型的功能。

## <a name="syntax"></a>语法

*boolean* = *recordset*。支持 (*CursorOptions*)

## <a name="return-value"></a>返回值

返回一个**Boolean**值，指示是否*CursorOptions*参数标识的功能的所有支持的提供程序。

## <a name="parameters"></a>参数

|参数|说明|
|:--------|:----------|
|*CursorOptions* |**长整型** 表达式，由一个或多个 [CursorOptionEnum](cursoroptionenum.md) 值组成。|

## <a name="remarks"></a>备注

使用 **Supports** 方法可确定 **Recordset** 对象所支持的功能类型。如果 **Recordset** 对象支持与 *CursorOptions* 中的常量相对应的功能，则 **Supports** 方法会返回 **True**，否则返回 **False**。


> [!NOTE]
> [!注释] 尽管针对给定功能 **Supports** 方法可能返回 **True** ，但这并不保证提供程序在所有情况下都支持该功能。 **Supports** 方法只是返回一个值来说明在特定条件满足时提供程序是否可以支持指定的功能。例如，即使游标基于多个表联接，其中某些列无法更新， **Supports** 方法也可能指示 **Recordset** 对象支持更新。


