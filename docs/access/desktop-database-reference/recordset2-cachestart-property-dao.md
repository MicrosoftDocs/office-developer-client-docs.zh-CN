---
title: CacheStart 属性 (DAO) Recordset2
TOCTitle: CacheStart Property
ms:assetid: 2e9c2b0d-b382-e4d6-9406-ace0e538a7b7
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192239(v=office.15)
ms:contentKeyID: 48543989
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e6f68cc9704d7dafe7a1d779b338294c9d5fc1c8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307418"
---
# <a name="recordset2cachestart-property-dao"></a>CacheStart 属性 (DAO) Recordset2


**适用于**：Access 2013、Office 2013

设置或返回一个值，该值指定动态集类型 Recordset 对象（包含从 ODBC 数据源本地缓存的数据）中的第一条记录的书签（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式*。CacheStart

*表达式*一个代表**Recordset2**对象的变量。

## <a name="remarks"></a>注解

如果使用 **Recordset** 对象从远程服务器检索数据，数据缓存可以提高性能。缓存是内存中的一个位置，用于保存最近从服务器检索的数据；如果用户在应用程序正在运行时再次请求数据，缓存将发挥作用。用户请求数据时，Microsoft Access 数据库引擎将首先检查所请求数据的缓存，而不是从服务器检索此数据（从服务器检索会花费较长时间）。缓存只保存来自 ODBC 数据源的数据。

任何 Microsoft Access 数据库引擎连接的 ODBC 数据源（例如链接表）都可以有一个本地缓存。若要创建缓存，请从远程数据源打开 **Recordset** 对象，设置 **CacheSize** 和 **[CacheStart](recordset2-cachestart-property-dao.md)** 属性，然后使用 **[FillCache](recordset2-fillcache-method-dao.md)** 方法，或者使用 **Move** 方法遍历记录。

**CacheStart** 属性设置是要缓存的 **Recordset** 对象中的第一条记录的书签。可以使用任何记录的书签来设置 **CacheStart** 属性。将您要启动缓存的记录作为当前记录，并将 **CacheStart** 属性设置为等同于 **[Bookmark](recordset2-bookmark-property-dao.md)** 属性。

Microsoft Access 数据库引擎从缓存中请求位于缓存范围内的记录，同时从服务器中请求位于缓存范围以外的记录。

从缓存中检索的记录并不能反映其他用户对源数据所做的并发更改。

若要强制更新所有缓存的数据，请将 **Recordset** 对象的 **CacheSize** 属性设置为 0，再将它重置为最初请求的缓存的大小，然后使用 **FillCache** 方法。

