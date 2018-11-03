---
title: Seek 方法-ActiveX 数据对象 (ADO)
TOCTitle: Seek method (ADO)
ms:assetid: cf0f133b-31f2-a2df-6cf3-1b5fa73b516c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250027(v=office.15)
ms:contentKeyID: 48547802
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: be8127ea3f298a8f137012615b1f4de656a6ea1f
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949710"
---
# <a name="seek-method-ado"></a>Seek 方法 (ADO)

**适用于**： Access 2013、 Office 2013

可搜索 [Recordset](recordset-object-ado.md) 的索引，以快速找到与指定值匹配的行，并将当前行位置更改为该行。

## <a name="syntax"></a>语法

*记录集*。Seek*KeyValues*， *SeekOption*

## <a name="parameters"></a>参数

|参数|说明|
|:--------|:----------|
|*KeyValues* |**变量型** 值的数组。索引由一列或多列组成，而数组包含一个用于与每个相应列进行比较的值。|
|*SeekOption* |[SeekEnum](seekenum.md) 值，用于指定在索引列与相应 *KeyValues* 之间进行比较的类型。|

## <a name="remarks"></a>备注

**Seek**方法结合使用的[索引](index-property-ado.md)属性，如果基础提供程序支持对**Recordset**对象的索引。 使用[支持](supports-method-ado.md)**(adSeek)** 方法以确定基础提供程序是否支持**Seek**和**Supports(adIndex)** 方法以确定提供程序是否支持索引。 （例如， [OLE DB Provider for Microsoft Jet](microsoft-ole-db-provider-for-microsoft-jet.md)支持**Seek**和**Index**。）

如果 **Seek** 找不到所需的行，不会发生错误，只是将该行置于 **Recordset** 的末尾。将 **Index** 属性设置为所需索引，然后执行此方法。

只有服务器端游标才支持此方法。当 **Recordset** 对象的 [CursorLocation](cursorlocation-property-ado.md) 属性值为 **adUseClient** 时，不支持 Seek。

仅当事先使用 **adCmdTableDirect** 的 [CommandTypeEnum](commandtypeenum.md) 值打开 **Recordset** 对象时，才能使用此方法。

