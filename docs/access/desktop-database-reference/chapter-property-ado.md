---
title: Chapter 属性 (ADO)
TOCTitle: Chapter property (ADO)
ms:assetid: d7c9478e-487f-7023-1dd8-5313433dbc5e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250085(v=office.15)
ms:contentKeyID: 48548014
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b4f4efc2ffab9f7996b2d805658b985badbaf87e
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28717935"
---
# <a name="chapter-property-ado"></a>Chapter 属性 (ADO)

**适用于**： Access 2013、 Office 2013
 
从 **ADORecordsetConstruction** 对象获取（或对它设置）OLE DB **Chapter** 对象。 当您使用**放置\_章**设置**Chapter**对象，行的子集处于到 ADO **Recordset**对象。 这将设置**Rowset**对象的当前一章。 读/写。

## <a name="syntax"></a>语法

HRESULT get\_章 (\[out，retval\]长\*plChapter);

HRESULT 放置\_章 (\[的\]长 lChapter);

## <a name="parameters"></a>Parameters

|参数|说明|
|:--------|:----------|
|*plChapter* |指向子集的句柄的指针。|
|*LChapter* |子集的句柄。|

## <a name="return-values"></a>返回值

此属性方法返回标准 HRESULT 值，包括 S\_确定和 E\_失败。

## <a name="applies-to"></a>应用于

[ADORecordsetConstruction](adorecordsetconstruction-interface-ado.md)

