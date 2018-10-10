---
title: Chapter 属性 (ADO)
TOCTitle: Chapter Property (ADO)
ms:assetid: d7c9478e-487f-7023-1dd8-5313433dbc5e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250085(v=office.15)
ms:contentKeyID: 48548014
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f02b20aef2b76ff00ce23b8597132dc22b414993
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468099"
---
# <a name="chapter-property-ado"></a>Chapter 属性 (ADO)


**适用于**： Access 2013 |Office 2013
 

从 **ADORecordsetConstruction** 对象获取（或对它设置）OLE DB **Chapter** 对象。 当您使用**放置\_章**设置**Chapter**对象，行的子集处于到 ADO **Recordset**对象。 这将设置**Rowset**对象的当前一章。 为可读/写属性。

## <a name="syntax"></a>语法

HRESULT get\_章 (\[out，retval\]长\*plChapter);

HRESULT 放置\_章 (\[的\]长 lChapter);

## <a name="parameters"></a>参数

  - *plChapter*

  - 指向子集的句柄的指针。

  - *LChapter*

  - 子集的句柄。

## <a name="return-values"></a>返回值

此属性方法返回标准 HRESULT 值，包括 S\_确定和 E\_失败。

## <a name="applies-to"></a>应用于

[ADORecordsetConstruction](adorecordsetconstruction-interface-ado.md)

