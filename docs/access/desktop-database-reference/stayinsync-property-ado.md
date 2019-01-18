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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28703228"
---
# <a name="stayinsync-property-ado"></a>StayInSync 属性 (ADO)


**适用于**： Access 2013、 Office 2013

指示在分层 [Recordset](recordset-object-ado.md) 对象中，当父行位置更改时，对基础子记录（即*章节*）的引用是否发生了更改。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个**布尔**值。 默认值为 **True**。 如果 **，则返回 True**，章将更新的父**Recordset**对象更改的行位置; 如果如果**False**，章将继续即使父**Recordset**对象已更改行位置，请参阅上一章中的数据。

## <a name="remarks"></a>备注

此属性应用于分级 Recordset，例如由 [Microsoft Data Shaping Service for OLE DB](microsoft-data-shaping-service-for-ole-db-ado-service-provider.md) 提供的记录集，而且必须先在父 **Recordset** 上设置才能检索子 **Recordset** 。此属性简化了分级记录集的导航操作。

