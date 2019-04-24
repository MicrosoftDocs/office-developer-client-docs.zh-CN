---
title: 行属性-ActiveX 数据对象 (ADO)
TOCTitle: Row property (ADO)
ms:assetid: 1c2b0e27-7232-4b1c-826c-9dc15d758851
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248959(v=office.15)
ms:contentKeyID: 48543562
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9b4beaa742bfc46ecd32fc04733c3e6ddaf12aa2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306480"
---
# <a name="row-property-ado"></a>Row 属性 (ADO)

**适用于**：Access 2013、Office 2013

获取或设置 **ADORecordConstruction** 对象的 OLE DB **Row** 对象。 当您使用 **"\_放置行**" 设置**row**对象时, 会将行转换为 ADO **Record**对象。 读/写。

## <a name="syntax"></a>语法

HRESULT get\_行 (\[out、retval\] IUnknown\* \* ppRow);

HRESULT put\_行 (\[在\] IUnknown\* pRow 中);

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*ppRow* |指向 OLE DB **Row** 对象的指针。|
|*PRow* |一个 OLE DB **Row** 对象。|

## <a name="return-values"></a>返回值

此属性方法返回标准的 HRESULT 值, 包括 S\_OK 和 E\_FAIL。

## <a name="applies-to"></a>适用于

[ADORecordConstruction](adorecordconstruction-interface-ado.md)

