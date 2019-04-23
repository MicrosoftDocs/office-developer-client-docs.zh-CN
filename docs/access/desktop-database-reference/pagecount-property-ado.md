---
title: PageCount 属性 (ADO)
TOCTitle: PageCount property (ADO)
ms:assetid: 9cd8bf5c-b1e7-a453-4629-9cba7e408f53
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249712(v=office.15)
ms:contentKeyID: 48546609
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b37ccc0c9a61e00b3c2e8f5eb3367831e5ddea43
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288117"
---
# <a name="pagecount-property-ado"></a>PageCount 属性 (ADO)


**适用于**：Access 2013、Office 2013

指示 [Recordset](recordset-object-ado.md) 对象包含的数据页数。

## <a name="return-value"></a>返回值

返回一个 **Long** 值，指示 **Recordset** 中的页数。

## <a name="remarks"></a>注解

使用 **PageCount** 属性可确定 **Recordset** 对象中的数据页数。*Pages* 是若干组记录，其大小与 [PageSize](pagesize-property-ado.md) 属性设置相等。即使最后一页由于记录数小于 **PageSize** 值而无法组成完整的一页，也仍将其算作 **PageCount** 值中的附加页。如果 **Recordset** 对象不支持此属性，则该值为 -1，指示 **PageCount** 不可确定。

有关页功能的详细信息，请参阅 **PageSize** 和 [AbsolutePage](absolutepage-property-ado.md) 属性。

