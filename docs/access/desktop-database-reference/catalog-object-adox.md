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
# <a name="catalog-object-adox"></a><span data-ttu-id="9bd70-102">Catalog 对象 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="9bd70-102">Catalog Object (ADOX)</span></span>


<span data-ttu-id="9bd70-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="9bd70-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="9bd70-104">包含描述数据源的架构目录的集合（[Tables](tables-collection-adox.md)、[Views](views-collection-adox.md)、[Users](users-collection-adox.md)、[Groups](groups-collection-adox.md) 和 [Procedures](procedures-collection-adox.md)）。</span><span class="sxs-lookup"><span data-stu-id="9bd70-104">Contains collections ([Tables](tables-collection-adox.md), [Views](views-collection-adox.md), [Users](users-collection-adox.md), [Groups](groups-collection-adox.md), and [Procedures](procedures-collection-adox.md)) that describe the schema catalog of a data source.</span></span>

## <a name="remarks"></a><span data-ttu-id="9bd70-105">说明</span><span class="sxs-lookup"><span data-stu-id="9bd70-105">Remarks</span></span>

<span data-ttu-id="9bd70-p101">可以通过添加/删除对象或通过修改现有对象来修改 **Catalog** 对象。某些提供程序可能并不支持所有 **Catalog** 对象，或者仅支持查看架构信息。</span><span class="sxs-lookup"><span data-stu-id="9bd70-p101">You can modify the **Catalog** object by adding or removing objects or by modifying existing objects. Some providers may not support all of the **Catalog** objects or may support only viewing schema information.</span></span>

<span data-ttu-id="9bd70-108">使用 **Catalog** 对象的属性和方法，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="9bd70-108">With the properties and methods of a **Catalog** object, you can:</span></span>

  - <span data-ttu-id="9bd70-109">通过将 [ActiveConnection](activeconnection-property-adox.md) 属性设置为 ADO [Connection](connection-object-ado.md) 对象或有效的连接字符串来打开目录。</span><span class="sxs-lookup"><span data-stu-id="9bd70-109">Open the catalog by setting the [ActiveConnection](activeconnection-property-adox.md) property to an ADO [Connection](connection-object-ado.md) object or a valid connection string.</span></span>

  - <span data-ttu-id="9bd70-110">使用 [Create](create-method-adox.md) 方法创建新目录。</span><span class="sxs-lookup"><span data-stu-id="9bd70-110">Create a new catalog with the [Create](create-method-adox.md) method.</span></span>

  - <span data-ttu-id="9bd70-111">使用 **GetObjectOwner** 和 [SetObjectOwner](getobjectowner-method-adox.md) 方法确定 [Catalog](https://msdn.microsoft.com/library/jj249006\(v=office.15\)) 中的对象的所有者。</span><span class="sxs-lookup"><span data-stu-id="9bd70-111">Determine the owners of the objects in a **Catalog** with the [GetObjectOwner](getobjectowner-method-adox.md) and [SetObjectOwner](https://msdn.microsoft.com/library/jj249006\(v=office.15\)) methods.</span></span>

