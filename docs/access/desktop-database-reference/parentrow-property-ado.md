---
title: ParentRow 属性 (ADO)
TOCTitle: ParentRow property (ADO)
ms:assetid: c7520353-9428-9c8f-9d21-ff42e30e1193
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249971(v=office.15)
ms:contentKeyID: 48547638
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 2844f7c93164c4b384a895cd32a13bd682154ce3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287736"
---
# <a name="parentrow-property-ado"></a>ParentRow 属性 (ADO)

**适用于**：Access 2013、Office 2013

在 **ADORecordConstruction** 对象上设置 OLE DB **Row** 对象的容器，以便将行的父项转换为 ADO **Record** 对象。

为只写属性。

## <a name="syntax"></a>语法

HRESULT put\_ParentRow (\[在\] IUnknown\* pParent 中);

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*pParent* |行的容器。|

## <a name="return-values"></a>返回值

此属性方法返回标准的 HRESULT 值, 包括 S\_OK 和 E\_FAIL。

## <a name="applies-to"></a>适用于

[ADORecordConstruction](adorecordconstruction-interface-ado.md)

