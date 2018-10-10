---
title: PageSize 属性 (ADO)
TOCTitle: PageSize Property (ADO)
ms:assetid: da56edd8-8947-aeff-2ef5-a8535c66575b
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250099(v=office.15)
ms:contentKeyID: 48548079
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 89b28e382f1597ff6466aa323565eaf2ff068605
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465923"
---
# <a name="pagesize-property-ado"></a>PageSize 属性 (ADO)


**适用于**： Access 2013 |Office 2013

指示由多少记录构成 [Recordset](recordset-object-ado.md) 中的一页。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 **Long** 值，指示页上的记录数。默认值为 10。

## <a name="remarks"></a>备注

使用 **PageSize** 属性可确定组成数据逻辑页的记录数。建立页大小后就可以使用 [AbsolutePage](absolutepage-property-ado.md) 属性移至特定页的首条记录。在 Web 服务器方案中，若要允许用户分页浏览数据，每次查看特定数量的记录，该属性将非常有用。

可随时设置此属性，并将其值用于计算特定页的首条记录的位置。

