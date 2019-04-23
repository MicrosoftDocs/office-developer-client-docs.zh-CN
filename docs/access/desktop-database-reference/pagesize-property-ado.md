---
title: PageSize 属性 (ADO)
TOCTitle: PageSize property (ADO)
ms:assetid: da56edd8-8947-aeff-2ef5-a8535c66575b
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250099(v=office.15)
ms:contentKeyID: 48548079
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9365acb13820f898c053d4c90fc252bfd3b228c4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288131"
---
# <a name="pagesize-property-ado"></a>PageSize 属性 (ADO)


**适用于**：Access 2013、Office 2013

指示由多少记录构成 [Recordset](recordset-object-ado.md) 中的一页。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 **Long** 值，指示页上的记录数。 默认值为 10。

## <a name="remarks"></a>注解

使用 **PageSize** 属性可确定组成数据逻辑页的记录数。 建立页大小后就可以使用 [AbsolutePage](absolutepage-property-ado.md) 属性移至特定页的首条记录。 当您希望允许用户逐页浏览数据, 并一次查看特定数量的记录时, 这在 web 服务器方案中非常有用。

可随时设置此属性，并将其值用于计算特定页的首条记录的位置。

