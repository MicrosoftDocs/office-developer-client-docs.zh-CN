---
title: Delete 方法 （ADO Fields 集合）
TOCTitle: Delete method (ADO Fields Collection)
ms:assetid: adc66365-703f-4491-fc5b-dbc9bca2ac53
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249817(v=office.15)
ms:contentKeyID: 48547047
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b33c15adf1d079e2da12590891d950aa35e5414f
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25950172"
---
# <a name="delete-method-ado-fields-collection"></a>Delete 方法 （ADO Fields 集合）

**适用于**： Access 2013、 Office 2013


用于从 [Fields](fields-collection-ado.md) 集合中删除对象。

## <a name="syntax"></a>语法

*字段*。删除*字段*

## <a name="parameters"></a>参数

|参数|说明|
|:--------|:----------|
|*Field* |**变量型** ，指定要删除的 [Field](field-object-ado.md) 对象。此参数可以是 **Field** 对象的名称，或 **Field** 对象自身的序号位置。|

## <a name="remarks"></a>备注

对打开的 **Recordset** 调用 [Fields.Delete](recordset-object-ado.md) 方法会引发运行时错误。

