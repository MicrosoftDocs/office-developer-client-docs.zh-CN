---
title: Index.Clustered 属性 (DAO)
TOCTitle: Clustered Property
ms:assetid: dd0876a9-b7fe-c8c8-e675-5ed758ce5bd3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835375(v=office.15)
ms:contentKeyID: 48548149
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052930
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 060963dc47c933fee903cd9b220adb45c7f63df6
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28706696"
---
# <a name="indexclustered-property-dao"></a>Index.Clustered 属性 (DAO)

**适用于**： Access 2013、 Office 2013

设置或返回一个值，该值指示某个 **Index** 对象是否代表某个表的聚簇索引（仅适用于 Microsoft Access 工作区）。可读写 **Boolean**。

## <a name="syntax"></a>语法

*表达式*。群集

*表达式*返回一个**Index**对象的表达式。

## <a name="remarks"></a>注解

如果 **Index** 对象代表聚簇索引，则设置或返回值为 Boolean 数据类型 **True**。

某些 IISAM 桌面数据库格式使用聚簇索引。聚簇索引包含一个或多个组合在一起的非键字段，这些字段可以按预定义的顺序排列表中的所有记录。聚簇索引可以对索引值可能不唯一的表中的记录提供高效访问。

**Clustered** 属性对于尚未追加到集合的新 **Index** 对象是可读写的，而对于 **Indexes** 集合中的现有 **Index** 对象是只读的。

> [!NOTE]
> - Microsoft Access 数据库引擎数据库将忽略 **Clustered** 属性，这是因为 Microsoft Access 数据库引擎不支持聚簇索引。
> - 对于 ODBC 数据源， **Clustered**属性始终返回**False**;它不检测 ODBC 数据源具有聚簇的索引。


