---
title: StayInSync 属性 (ADO)
TOCTitle: StayInSync property (ADO)
ms:assetid: 02c95c10-4032-14e1-e506-f334a8787142
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248792(v=office.15)
ms:contentKeyID: 48542966
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: bfc9ef5229fe230ad0c83ebde7a887e0fac0c233
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308489"
---
# <a name="stayinsync-property-ado"></a>StayInSync 属性 (ADO)


**适用于**：Access 2013、Office 2013

指示在分层 [Recordset](recordset-object-ado.md) 对象中，当父行位置更改时，对基础子记录（即*章节*）的引用是否发生了更改。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 **Boolean** 值。默认值为“True”****。如果为“True”****，则父 **Recordset** 对象更改行位置时子集将更新；如果为“False”****，即使父 **Recordset** 对象已更改行位置，子集也将继续引用前一子集中的数据。

## <a name="remarks"></a>注解

此属性应用于分级 Recordset，例如由 [Microsoft Data Shaping Service for OLE DB](microsoft-data-shaping-service-for-ole-db-ado-service-provider.md) 提供的记录集，而且必须先在父 **Recordset** 上设置才能检索子 **Recordset**。此属性简化了分级记录集的导航操作。

