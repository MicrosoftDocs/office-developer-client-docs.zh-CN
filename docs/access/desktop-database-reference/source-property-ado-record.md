---
title: Source 属性（ADO 记录）
TOCTitle: Source property (ADO Record)
ms:assetid: f36f0f5f-4493-d8c5-db4b-c72f5031bcb3
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250235(v=office.15)
ms:contentKeyID: 48548670
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b41521ac3b4ba0f07eac188a7103025be2800e4d
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25946501"
---
# <a name="source-property-ado-record"></a>Source 属性（ADO 记录）


**适用于**： Access 2013、 Office 2013

指示由 [Record](record-object-ado.md) 表示的数据源或对象。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 **Variant** 值，指示 **Record** 表示的实体。

## <a name="remarks"></a>备注

**Source**属性返回**Record**对象的[Open](open-method-ado-record.md)方法的*Source*参数。 该属性可包含一个绝对或相对 URL 字符串。 使用绝对 URL 可直接打开 [Record](activeconnection-property-ado.md) 对象，而无需设置 **ActiveConnection** 属性。 此时将创建一个隐式 **Connection** 对象。

**Source** 属性还可包含对已打开的 **Recordset** 的引用，这将打开一个表示该 **Recordset** 中当前行的 **Record** 对象。

**Source** 属性还可包含对从提供程序返回单行数据的 [Command](command-object-ado.md) 对象的引用。

如果也设置了 **ActiveConnection** 属性，则 **Source** 属性必须指向该连接范围内的某个对象。例如，在树状命名空间中，如果 **Source** 属性包含绝对 URL，则必须指向由连接字符串中的 URL 标识的节点范围之内的节点。如果 **Source** 属性包含相对 URL，则将在由 **ActiveConnection** 属性设置的上下文中对其进行验证。

**Record** 对象关闭时， **Source** 属性为可读/写属性， **Record** 对象打开时为只读属性。

> [!NOTE]
> [!注释] 使用 http 方案的 URL 将自动调用 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。 有关详细信息，请参阅[绝对和相对 Url](absolute-and-relative-urls.md)。


