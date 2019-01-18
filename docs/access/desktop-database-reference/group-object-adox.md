---
title: Group 对象 (ADOX)
TOCTitle: Group object (ADOX)
ms:assetid: 91cf1b87-c928-1d89-2731-138f6299cc60
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249642(v=office.15)
ms:contentKeyID: 48546359
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e010ac58ff0b573d42c562ce3be7a99acab5abea
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28718166"
---
# <a name="group-object-adox"></a><span data-ttu-id="99c3f-102">Group 对象 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="99c3f-102">Group object (ADOX)</span></span>


<span data-ttu-id="99c3f-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="99c3f-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="99c3f-104">代表在受保护的数据库中有访问权限的组帐户。</span><span class="sxs-lookup"><span data-stu-id="99c3f-104">Represents a group account that has access permissions within a secured database.</span></span>

## <a name="remarks"></a><span data-ttu-id="99c3f-105">说明</span><span class="sxs-lookup"><span data-stu-id="99c3f-105">Remarks</span></span>

<span data-ttu-id="99c3f-p101">[Catalog](groups-collection-adox.md) 的 [Groups](catalog-object-adox.md) 集合表示该目录的所有组帐户。 **User** 的 [Groups](user-object-adox.md) 集合仅表示该用户所属的组。</span><span class="sxs-lookup"><span data-stu-id="99c3f-p101">The [Groups](groups-collection-adox.md) collection of a [Catalog](catalog-object-adox.md) represents all the catalog's group accounts. The **Groups** collection for a [User](user-object-adox.md) represents only the group to which the user belongs.</span></span>

<span data-ttu-id="99c3f-108">使用 **Group** 对象的属性、集合和方法，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="99c3f-108">With the properties, collections, and methods of a **Group** object, you can:</span></span>

  - <span data-ttu-id="99c3f-109">使用 [Name](name-property-adox.md) 属性标识组。</span><span class="sxs-lookup"><span data-stu-id="99c3f-109">Identify the group with the [Name](name-property-adox.md) property.</span></span>

  - <span data-ttu-id="99c3f-110">使用 [GetPermissions](getpermissions-method-adox.md) 和 [SetPermissions](setpermissions-method-adox.md) 方法确定组是否具有读取、写入或删除权限。</span><span class="sxs-lookup"><span data-stu-id="99c3f-110">Determine whether a group has read, write, or delete permissions with the [GetPermissions](getpermissions-method-adox.md) and [SetPermissions](setpermissions-method-adox.md) methods.</span></span>

  - <span data-ttu-id="99c3f-111">使用 [Users](users-collection-adox.md) 集合访问在组中具有成员资格的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="99c3f-111">Access the user accounts that have memberships in the group with the [Users](users-collection-adox.md) collection.</span></span>

  - <span data-ttu-id="99c3f-112">使用 [Properties](properties-collection-ado.md) 集合访问提供程序特定的属性。</span><span class="sxs-lookup"><span data-stu-id="99c3f-112">Access provider-specific properties with the [Properties](properties-collection-ado.md) collection.</span></span>

