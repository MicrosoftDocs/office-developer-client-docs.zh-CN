---
title: 行属性-ActiveX 数据对象 (ADO)
TOCTitle: Row Property (ADO)
ms:assetid: 1c2b0e27-7232-4b1c-826c-9dc15d758851
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248959(v=office.15)
ms:contentKeyID: 48543562
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 05d97bb411c4199677f512d9412653ca5a4b4fe1
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466955"
---
# <a name="row-property-ado"></a>Row 属性 (ADO)


**适用于**： Access 2013 |Office 2013



获取或设置 **ADORecordConstruction** 对象的 OLE DB **Row** 对象。 当您使用**放置\_行**设置**Row**对象，行转换为 ADO **Record**对象。 为可读/写属性。

## <a name="syntax"></a>语法

HRESULT get\_行 (\[out，retval\] IUnknown\* \* ppRow);

HRESULT 放置\_行 (\[的\]IUnknown\* pRow);

## <a name="parameters"></a>参数

  - *ppRow*

  - 指向 OLE DB **Row** 对象的指针。

  - *PRow*

  - 一个 OLE DB **Row** 对象。

## <a name="return-values"></a>返回值

此属性方法返回标准 HRESULT 值，包括 S\_确定和 E\_失败。

## <a name="applies-to"></a>应用于

[ADORecordConstruction](adorecordconstruction-interface-ado.md)

