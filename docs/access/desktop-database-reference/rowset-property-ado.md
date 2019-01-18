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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28706140"
---
# <a name="rowset-property-ado"></a>Rowset 属性 (ADO)

**适用于**： Access 2013、 Office 2013

通过 **ADORecordsetConstruction** 对象获取或设置一个 OLE DB **Rowset** 对象。 当您使用 put\_行集，行集转换为 ADO **Recordset**对象。

读/写。

## <a name="syntax"></a>语法

HRESULT get\_行集 (\[out，retval\] IUnknown\* \* ppRowset);

HRESULT 放置\_行集 (\[的\]IUnknown\* pRowset);

## <a name="parameters"></a>Parameters

|参数|说明|
|:--------|:----------|
|*ppRowset* |指向 OLE DB **Rowset** 对象的指针。|
|*PRowset* |一个 OLE DB **Rowset** 对象。|

## <a name="return-values"></a>返回值

此属性方法返回标准 HRESULT 值，包括 S\_确定和 E\_失败。

## <a name="applies-to"></a>适用于

[ADORecordsetConstruction](adorecordsetconstruction-interface-ado.md)

