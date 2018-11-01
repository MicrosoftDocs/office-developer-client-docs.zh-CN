---
title: Rowset 属性 (ADO)
TOCTitle: Rowset property (ADO)
ms:assetid: 1a1cb3ef-8f3c-30c1-3eb0-8618fdcacd53
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248946(v=office.15)
ms:contentKeyID: 48543515
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7be8abbce6828dd202e0c64eec342de9198f7a9b
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25878533"
---
# <a name="rowset-property-ado"></a>Rowset 属性 (ADO)


**适用于**： Access 2013、 Office 2013



通过 **ADORecordsetConstruction** 对象获取或设置一个 OLE DB **Rowset** 对象。 当您使用 put\_行集，行集转换为 ADO **Recordset**对象。

为可读/写属性。

## <a name="syntax"></a>语法

HRESULT get\_行集 (\[out，retval\] IUnknown\* \* ppRowset);

HRESULT 放置\_行集 (\[的\]IUnknown\* pRowset);

## <a name="parameters"></a>参数

  - *ppRowset*

  - 指向 OLE DB **Rowset** 对象的指针。

  - *PRowset*

  - 一个 OLE DB **Rowset** 对象。

## <a name="return-values"></a>返回值

此属性方法返回标准 HRESULT 值，包括 S\_确定和 E\_失败。

## <a name="applies-to"></a>应用于

[ADORecordsetConstruction](adorecordsetconstruction-interface-ado.md)

