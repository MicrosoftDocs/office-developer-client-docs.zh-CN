---
title: RecordCount 属性 (ADO)
TOCTitle: RecordCount property (ADO)
ms:assetid: e3072d10-5bf7-02a8-027e-a9d9a34e3f27
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250155(v=office.15)
ms:contentKeyID: 48548304
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 41fb9d8bdcb626fefe2e98fe4c1849554a73a6c3
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25876160"
---
# <a name="recordcount-property-ado"></a>RecordCount 属性 (ADO)


**适用于**： Access 2013、 Office 2013

指示 [Recordset](recordset-object-ado.md) 对象中的记录数。

## <a name="return-value"></a>返回值

返回一个 **Long** 值，指示 **Recordset** 中的记录数。

## <a name="remarks"></a>备注

使用 **RecordCount** 属性可了解 **Recordset** 对象中的记录数。如果提供程序或游标类型不支持 **RecordCount** ，而导致 ADO 无法确定记录数，则该属性返回 -1。读取已关闭的 **Recordset** 的 **RecordCount** 属性将导致错误。

如果 **Recordset** 对象支持近似定位或书签  即，分别为 **Supports (adApproxPosition)** 或 **Supports (adBookmark)** ，则返回 **True**  该值将是 **Recordset** 中的准确记录数，而不管是否已完全填充该记录集。如果 **Recordset** 对象不支持近似定位，由于不得不检索和计算所有记录以返回精确的 **RecordCount** 值，该属性将极大地耗费资源。

**Recordset** 对象的游标类型决定是否能确定记录数。对于只进游标， **RecordCount** 属性将返回 -1 ；对于静态游标或键集游标，则返回实际记录数；而对于动态游标，则返回 -1 或实际记录数，具体情况视数据源而定。

