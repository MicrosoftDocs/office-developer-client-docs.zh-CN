---
title: 章节属性 (ADO)
TOCTitle: Chapter property (ADO)
ms:assetid: d7c9478e-487f-7023-1dd8-5313433dbc5e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250085(v=office.15)
ms:contentKeyID: 48548014
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b4f4efc2ffab9f7996b2d805658b985badbaf87e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296393"
---
# <a name="chapter-property-ado"></a>章节属性 (ADO)

**适用于**：Access 2013、Office 2013
 
从 **ADORecordsetConstruction** 对象获取（或对它设置）OLE DB **Chapter** 对象。 当您使用 **"\_放置章节**" 设置**章节**对象时, 会将行的子集转换为 ADO **Recordset**对象。 这将设置**行集**对象的当前章节。 读/写。

## <a name="syntax"></a>语法

HRESULT get\_章节 (\[out, retval\] long\* plChapter);

HRESULT put\_章 (\[\] long lChapter);

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*plChapter* |指向子集的句柄的指针。|
|*LChapter* |子集的句柄。|

## <a name="return-values"></a>返回值

此属性方法返回标准的 HRESULT 值, 包括 S\_OK 和 E\_FAIL。

## <a name="applies-to"></a>应用于

[ADORecordsetConstruction](adorecordsetconstruction-interface-ado.md)

