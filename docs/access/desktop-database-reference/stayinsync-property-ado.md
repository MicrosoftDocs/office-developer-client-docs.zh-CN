---
title: StayInSync 属性 (ADO)
TOCTitle: StayInSync Property (ADO)
ms:assetid: 02c95c10-4032-14e1-e506-f334a8787142
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248792(v=office.15)
ms:contentKeyID: 48542966
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f492b2c3f58084be55eca4787cde486dab29ca67
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467468"
---
# <a name="stayinsync-property-ado"></a>StayInSync 属性 (ADO)


**适用于**： Access 2013 |Office 2013

指示在分层[Recordset](recordset-object-ado.md)对象是否父行位置更改时，更改对基础子记录 （即*章节*） 的引用。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个**布尔**值。 默认值为 **True** 。 如果 **，则返回 True**，章将更新的父**Recordset**对象更改的行位置; 如果如果**False**，章将继续即使父**Recordset**对象已更改行位置，请参阅上一章中的数据。

## <a name="remarks"></a>备注

此属性应用于分级 Recordset，例如由 [Microsoft Data Shaping Service for OLE DB](microsoft-data-shaping-service-for-ole-db-ado-service-provider.md) 提供的记录集，而且必须先在父 **Recordset** 上设置才能检索子 **Recordset** 。此属性简化了分级记录集的导航操作。

