---
title: Catalog 对象 (ADOX)
TOCTitle: Catalog Object (ADOX)
ms:assetid: d9e8d94b-9161-3eb6-abaf-00d1244d1f2d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250097(v=office.15)
ms:contentKeyID: 48548068
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 8d1be720b8c3791830a4258d6241466ba596d85e
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25887654"
---
# <a name="catalog-object-adox"></a>Catalog 对象 (ADOX)


**适用于**： Access 2013、 Office 2013

包含描述数据源的架构目录的集合（[Tables](tables-collection-adox.md)、[Views](views-collection-adox.md)、[Users](users-collection-adox.md)、[Groups](groups-collection-adox.md) 和 [Procedures](procedures-collection-adox.md)）。

## <a name="remarks"></a>说明

可以通过添加/删除对象或通过修改现有对象来修改 **Catalog** 对象。某些提供程序可能并不支持所有 **Catalog** 对象，或者仅支持查看架构信息。

使用 **Catalog** 对象的属性和方法，可以执行下列操作：

  - 通过将 [ActiveConnection](activeconnection-property-adox.md) 属性设置为 ADO [Connection](connection-object-ado.md) 对象或有效的连接字符串来打开目录。

  - 使用 [Create](create-method-adox.md) 方法创建新目录。

  - 使用 **GetObjectOwner** 和 [SetObjectOwner](getobjectowner-method-adox.md) 方法确定 [Catalog](https://msdn.microsoft.com/library/jj249006\(v=office.15\)) 中的对象的所有者。

