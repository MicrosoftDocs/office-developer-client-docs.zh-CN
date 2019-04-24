---
title: Rowset 属性 (ADO)
TOCTitle: Rowset property (ADO)
ms:assetid: 1a1cb3ef-8f3c-30c1-3eb0-8618fdcacd53
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248946(v=office.15)
ms:contentKeyID: 48543515
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: be2a4855b3411a11ddd5a76225acaa52344877a4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306739"
---
# <a name="rowset-property-ado"></a>Rowset 属性 (ADO)

**适用于**：Access 2013、Office 2013

通过 **ADORecordsetConstruction** 对象获取或设置一个 OLE DB **Rowset** 对象。 使用 put\_行集时, 行集将转换为 ADO **Recordset**对象。

读/写。

## <a name="syntax"></a>语法

HRESULT get\_Rowset (\[out, retval\] IUnknown\* \* ppRowset);

HRESULT put\_行集\[(\]在\* IUnknown pRowset 中);

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*ppRowset* |指向 OLE DB **Rowset** 对象的指针。|
|*PRowset* |一个 OLE DB **Rowset** 对象。|

## <a name="return-values"></a>返回值

此属性方法返回标准的 HRESULT 值, 包括 S\_OK 和 E\_FAIL。

## <a name="applies-to"></a>适用于

[ADORecordsetConstruction](adorecordsetconstruction-interface-ado.md)

