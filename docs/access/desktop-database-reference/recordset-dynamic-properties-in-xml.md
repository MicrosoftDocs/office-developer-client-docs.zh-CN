---
title: XML 中的记录集动态属性
TOCTitle: Recordset Dynamic Properties in XML
ms:assetid: 6ee1f176-9986-4ade-fc97-e3dad8e6bc6b
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249439(v=office.15)
ms:contentKeyID: 48545522
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4193220e450c59e7293ed6befa37d8da23801f27
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465860"
---
# <a name="recordset-dynamic-properties-in-xml"></a>XML 中的记录集动态属性


**适用于**： Access 2013 |Office 2013

## <a name="recordset-dynamic-properties-in-xml"></a>XML 中的记录集动态属性

以下特定于提供程序的 **Recordset** 属性（从客户端游标引擎）目前会持久化到 XML 格式中：

  - **Update Resync**

  - **Unique Table**

  - **Unique Schema**

  - **Unique Catalog**

  - **Resync Command**

  - **IRowsetChange**

  - **IRowsetUpdate**

  - **CommandTimeout**

  - **BatchSize**

  - **UpdateCriteria**

  - **Reshape Name**

  - **AutoRecalc**

这些属性将作为正在持久化的 **Recordset** 的元素定义的属性保存在架构节中。这些属性是在行集架构命名空间中定义的，并且必须有前缀"rs:"。

