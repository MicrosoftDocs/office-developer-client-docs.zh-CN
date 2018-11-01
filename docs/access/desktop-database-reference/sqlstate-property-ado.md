---
title: SQLState 属性 (ADO)
TOCTitle: SQLState property (ADO)
ms:assetid: cf3b078a-849e-1ad2-cba4-a26160080868
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250029(v=office.15)
ms:contentKeyID: 48547806
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f6fb45342a56a003856192a353270778b44654de
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25872177"
---
# <a name="sqlstate-property-ado"></a>SQLState 属性 (ADO)


**适用于**： Access 2013、 Office 2013

指示给定 [Error](error-object-ado.md) 对象的 SQL 状态。

## <a name="return-value"></a>返回值

返回一个符合 ANSI SQL 标准并指示错误代码的五字符 **String** 值。

## <a name="remarks"></a>备注

使用 **SQLState** 属性可读取在处理 SQL 语句的过程中发生错误时提供程序返回的五字符错误代码。例如，在将 Microsoft OLE DB Provider for ODBC 和 Microsoft SQL Server 数据库一起使用时，SQL 状态错误代码将从 ODBC 产生（基于特定于 ODBC 的错误或源于 Microsoft SQL Server 的错误），然后映射为 ODBC 错误。这些错误代码记录在 ANSI SQL 标准中，但不同数据源的实现方式可能会不同。

