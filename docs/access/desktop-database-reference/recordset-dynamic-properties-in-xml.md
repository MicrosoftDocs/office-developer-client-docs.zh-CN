---
title: XML 中的记录集动态属性
TOCTitle: Recordset dynamic properties in XML
ms:assetid: 6ee1f176-9986-4ade-fc97-e3dad8e6bc6b
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249439(v=office.15)
ms:contentKeyID: 48545522
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 36069ec0e8e9020bc70ef1ea72ce25f4461c6487
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25946956"
---
# <a name="recordset-dynamic-properties-in-xml"></a>XML 中的记录集动态属性

**适用于**： Access 2013、 Office 2013

以下特定于提供程序的 **Recordset** 属性（从客户端游标引擎）目前会持久化到 XML 格式中：

- **AutoRecalc**
- **BatchSize**
- **CommandTimeout**
- **IRowsetChange**
- **IRowsetUpdate**
- **Reshape Name**
- **Resync Command**
- **Unique Catalog**
- **Unique Schema**
- **Unique Table**
- **Update Resync**
- **UpdateCriteria**


这些属性将作为正在持久化的 **Recordset** 的元素定义的属性保存在架构节中。这些属性是在行集架构命名空间中定义的，并且必须有前缀"rs:"。

## <a name="see-also"></a>另请参阅

- [ADO 动态属性](ado-dynamic-properties.md)