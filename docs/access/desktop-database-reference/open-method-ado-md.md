---
title: Open 方法 (ADO MD)
TOCTitle: Open method (ADO MD)
ms:assetid: 12395ff6-fe07-325a-2b69-007aa0b11ee6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248894(v=office.15)
ms:contentKeyID: 48543335
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 54f7ce4d5d588e644707cd7b466c29f619850824
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288397"
---
# <a name="open-method-ado-md"></a>Open 方法 (ADO MD)

**适用于**：Access 2013、Office 2013

检索多维查询的结果并将结果返回到单元格集。

## <a name="syntax"></a>语法

*单元格集*。开放*源代码*, *ActiveConnection*

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*Source* |可选。一个 **Variant** 值，计算后得到有效的多维查询（如多维表达式 (MDX) 查询）。*Source* 参数对应于 [Source](source-property-ado-md.md) 属性。有关 MDX 的更多信息，请参阅 Microsoft Data Access Components SDK 中的 OLE DB for OLAP 文档。|
|*ActiveConnection* |可选。一个 **Variant** 值，计算后得到字符串，该字符串指定一个有效的 ADO [Connection](connection-object-ado.md) 对象变量名或一个连接定义。*ActiveConnection* 参数指定在其中打开 [Cellset](cellset-object-ado-md.md) 对象的连接。如果为此参数传入连接定义，则 ADO 将使用指定的参数打开新连接。*ActiveConnection* 参数对应于 [ActiveConnection](activeconnection-property-ado-md.md) 属性。|

## <a name="remarks"></a>注解

如果省略 **Open** 方法的任一参数，并且在尝试打开 **Cellset** 之前不设置其对应的属性值，则该方法将生成错误。

