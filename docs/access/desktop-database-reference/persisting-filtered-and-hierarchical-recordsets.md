---
title: 持久化筛选和分层记录集
TOCTitle: Persisting filtered and hierarchical Recordsets
ms:assetid: 3648a997-dac7-d8a3-3cca-a6827f26a4f0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249120(v=office.15)
ms:contentKeyID: 48544162
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 13255bcd5cd40745a767b8aff9f49449b0127294
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25946116"
---
# <a name="persisting-filtered-and-hierarchical-recordsets"></a>持久化筛选和分层记录集


**适用于**： Access 2013、 Office 2013

如果 [Filter](filter-property-ado.md) 属性对 **Recordset** 有效，则只保存在该筛选器下可访问的行。如果 **Recordset** 是分层的，则保存当前子 **Recordset** 及其子记录集，包括父 **Recordset** 。如果调用子 **Recordset** 的 **Save** 方法，则保存该子记录集及其所有子记录集，但不保存父记录集。有关分层 **Recordset** 的详细信息，请参阅 [第 9 章：数据定形](chapter-9-data-shaping.md)。


> [!NOTE]
> [!注释] 以 XML 格式保存分层 **Recordset** （数据定形）时，有某些限制。有关详细信息，请参阅 [ XML 中的分层记录集 ](hierarchical-recordsets-in-xml.md)。


