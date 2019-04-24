---
title: Delete 方法 (ADO Fields 集合)
TOCTitle: Delete method (ADO Fields Collection)
ms:assetid: adc66365-703f-4491-fc5b-dbc9bca2ac53
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249817(v=office.15)
ms:contentKeyID: 48547047
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e5d97cec041d69ddbbfe61600ca6b03cb09bc466
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294104"
---
# <a name="delete-method-ado-fields-collection"></a>Delete 方法 (ADO Fields 集合)

**适用于**：Access 2013、Office 2013


用于从 [Fields](fields-collection-ado.md) 集合中删除对象。

## <a name="syntax"></a>语法

*字段*。删除*字段*

## <a name="parameters"></a>参数

|参数|说明|
|:--------|:----------|
|*Field* |**变量型** ，指定要删除的 [Field](field-object-ado.md) 对象。此参数可以是 **Field** 对象的名称，或 **Field** 对象自身的序号位置。|

## <a name="remarks"></a>注解

对打开的 [Recordset](recordset-object-ado.md) 调用 **Fields.Delete** 方法会引发运行时错误。

