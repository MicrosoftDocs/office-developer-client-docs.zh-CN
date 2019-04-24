---
title: RowPosition 属性 (ADO)
TOCTitle: RowPosition property (ADO)
ms:assetid: b87f14b0-136b-0564-3e12-f9d5ecc4f7c8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249887(v=office.15)
ms:contentKeyID: 48547325
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 84d3ad7cc5b3d43b15ac1113f6fa00932678ebc3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306858"
---
# <a name="rowposition-property-ado"></a>RowPosition 属性 (ADO)

**适用于**：Access 2013、Office 2013

通过 **ADORecordsetConstruction** 对象获取或设置一个 OLE DB **RowPosition** 对象。 当您使用**put\_RowPosition**设置**RowPosition**对象时, 生成的**Recordset**对象将使用**RowPosition**对象来确定当前行。

读/写。

## <a name="syntax"></a>语法

HRESULT get\_RowPosition (\[out, retval\] IUnknown\* \* ppRowPos);

HRESULT put\_RowPosition (\[在\] IUnknown\* pRowPos 中);

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*ppRowPos* |指向 OLE DB **RowPosition** 对象的指针。|
|*PRowPos* |一个 OLE DB **RowPosition** 对象。|

## <a name="return-values"></a>返回值

此属性方法返回标准的 HRESULT 值, 包括 S\_OK 和 E\_FAIL。

## <a name="remarks"></a>注解

设置此属性时，如果 **RowPosition** 对象上的 **Rowset** 对象与 **Recordset** 对象上的 **Rowset** 对象不同，则前者将覆盖后者。**RowPosition** 的当前 **Chapter** 也是如此。

## <a name="applies-to"></a>适用于

[ADORecordsetConstruction](adorecordsetconstruction-interface-ado.md)

