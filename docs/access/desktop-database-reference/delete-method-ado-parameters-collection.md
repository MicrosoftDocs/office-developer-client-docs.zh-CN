---
title: Delete 方法 (ADO Parameters 集合)
TOCTitle: Delete method (ADO Parameters Collection)
ms:assetid: 03ffc24d-fea2-30fa-c8e9-43eb524fd51f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248804(v=office.15)
ms:contentKeyID: 48542998
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e075e176f1c007a258f6277147442223ae108b47
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294090"
---
# <a name="delete-method-ado-parameters-collection"></a>Delete 方法 (ADO Parameters 集合)

**适用于**：Access 2013、Office 2013

用于从 [Parameters](parameters-collection-ado.md) 集合中删除对象。

## <a name="syntax"></a>语法

*参数*。删除*索引*

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*Index* |**字符串** 值，包含要删除的对象的名称，或对象在集合中的序号位置（索引）。|

## <a name="remarks"></a>注解

通过对集合使用 **Delete** 方法，可以删除集合中的对象之一。此方法仅适用于 [Command](command-object-ado.md) 对象的 **Parameters** 集合。在调用 **Delete** 方法时，必须使用 [Parameter](parameter-object-ado.md) 对象的 [Name](name-property-ado.md) 属性或其集合索引，对象变量不是有效的参数。

