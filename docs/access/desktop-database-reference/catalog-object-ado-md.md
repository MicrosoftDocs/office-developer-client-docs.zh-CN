---
title: Catalog 对象 (ADO MD)
TOCTitle: Catalog object (ADO MD)
ms:assetid: 708c4082-3589-7f3b-5ea3-f3705f3d3ff1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249445(v=office.15)
ms:contentKeyID: 48545559
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0ee7d2e68df90c8eee4227f949f93ea074b7df97
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28713084"
---
# <a name="catalog-object-ado-md"></a>Catalog 对象 (ADO MD)


**适用于**： Access 2013、 Office 2013

包含特定于多维数据提供程序 (MDP) 的多维架构信息（即，多维数据集和基础维、层次结构、级别和成员）。

## <a name="remarks"></a>说明

使用 **Catalog** 对象的集合和属性，可以执行下列操作：

- 通过将 [ActiveConnection](activeconnection-property-ado-md.md) 属性设置为标准 ADO [Connection](connection-object-ado.md) 对象或有效的连接字符串来打开目录。

- 使用 **Name** 属性标识 [Catalog](name-property-ado-md.md) 。

- 使用 [CubeDefs](cubedefs-collection-ado-md.md) 集合遍历目录中的多维数据集。

