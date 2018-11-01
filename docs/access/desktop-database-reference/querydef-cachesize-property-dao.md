---
title: QueryDef.CacheSize Property (DAO)
TOCTitle: CacheSize Property
ms:assetid: a84d990e-8180-daa3-7640-47d2be8fd28b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821397(v=office.15)
ms:contentKeyID: 48546899
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 827e0c751101ca68246278c04a408731b77c36a7
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25885120"
---
# <a name="querydefcachesize-property-dao"></a>QueryDef.CacheSize Property (DAO)


**适用于**： Access 2013、 Office 2013

设置或返回从 ODBC 数据源中检索的、需要本地缓存的记录数。可读/写 **Long** 类型。

## <a name="syntax"></a>语法

*表达式*。CacheSize

*表达式*一个代表**QueryDef**对象的变量。

## <a name="remarks"></a>注解

**CacheSize** 属性值必须介于 5 和 1200 之间，但不得超过可用内存允许的大小。典型值为 100。设置为 0 时将关闭缓存。

Microsoft Access 数据库引擎从缓存中请求位于缓存范围内的记录，同时从服务器中请求位于缓存范围以外的记录。

从缓存中检索的记录并不能反映其他用户对源数据所做的并发更改。

