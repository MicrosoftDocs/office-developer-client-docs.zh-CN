---
title: Provider 属性 (ADO)
TOCTitle: Provider property (ADO)
ms:assetid: 1b795f51-93d7-431c-b1fe-0db95f69a56a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248953(v=office.15)
ms:contentKeyID: 48543543
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: df764aca267cab9b38760c432cd19154d6c6827f
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25881564"
---
# <a name="provider-property-ado"></a>Provider 属性 (ADO)


**适用于**： Access 2013、 Office 2013

指示 [Connection](connection-object-ado.md) 对象的提供程序的名称。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 **String** 值，指示提供程序的名称。

## <a name="remarks"></a>备注

使用 **Provider** 属性可设置或返回连接的提供程序的名称。还可以通过 [ConnectionString](connectionstring-property-ado.md) 属性或 [Open](open-method-ado-connection.md) 方法的 *ConnectionString* 参数的内容设置此属性；但是，如果在多处指定提供程序，调用 **Open** 方法会导致不可预知的结果。如果未指定提供程序，则该属性将默认为 MSDASQL ([Microsoft OLE DB Provider for ODBC](microsoft-ole-db-provider-for-odbc.md))。

关闭连接时 **Provider** 属性为可读/写属性，打开连接时为只读属性。只有在打开 **Connection** 对象或访问 [Connection](properties-collection-ado.md) 对象的 **Properties** 集合时该设置才会生效。如果该设置无效，则将发生错误。

