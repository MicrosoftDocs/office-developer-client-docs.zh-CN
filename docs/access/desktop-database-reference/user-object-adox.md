---
title: 用户对象 (ADOX-访问桌面数据库引用)
TOCTitle: User object (ADOX)
ms:assetid: e88b9a8a-e70f-c7ca-cb8c-bd274ff24948
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250178(v=office.15)
ms:contentKeyID: 48548426
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 845697f54ea5e37e051836896b84d8a3ff061237
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25919876"
---
# <a name="user-object-adox"></a><span data-ttu-id="e77c6-102">User 对象 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="e77c6-102">User object (ADOX)</span></span>


<span data-ttu-id="e77c6-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="e77c6-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e77c6-104">代表在受保护的数据库中有访问权限的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e77c6-104">Represents a user account that has access permissions within a secured database.</span></span>

## <a name="remarks"></a><span data-ttu-id="e77c6-105">说明</span><span class="sxs-lookup"><span data-stu-id="e77c6-105">Remarks</span></span>

<span data-ttu-id="e77c6-p101">[Catalog](users-collection-adox.md) 的 [Users](catalog-object-adox.md) 集合表示该目录的所有用户。 **Group** 的 [Users](group-object-adox.md) 集合仅表示特定组的用户。</span><span class="sxs-lookup"><span data-stu-id="e77c6-p101">The [Users](users-collection-adox.md) collection of a [Catalog](catalog-object-adox.md) represents all the catalog's users. The **Users** collection for a [Group](group-object-adox.md) represents only the users of the specific group.</span></span>

<span data-ttu-id="e77c6-108">使用 **User** 对象的属性、集合和方法，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e77c6-108">With the properties, collections, and methods of a **User** object, you can:</span></span>

  - <span data-ttu-id="e77c6-109">使用 [Name](name-property-adox.md) 属性标识用户。</span><span class="sxs-lookup"><span data-stu-id="e77c6-109">Identify the user with the [Name](name-property-adox.md) property.</span></span>

  - <span data-ttu-id="e77c6-110">使用 [ChangePassword](changepassword-method-adox.md) 方法更改用户的密码。</span><span class="sxs-lookup"><span data-stu-id="e77c6-110">Change the password for a user with the [ChangePassword](changepassword-method-adox.md) method.</span></span>

  - <span data-ttu-id="e77c6-111">使用 [GetPermissions](getpermissions-method-adox.md) 和 [SetPermissions](setpermissions-method-adox.md) 方法确定用户是否具有读取、写入或删除权限。</span><span class="sxs-lookup"><span data-stu-id="e77c6-111">Determine whether a user has read, write, or delete permissions with the [GetPermissions](getpermissions-method-adox.md) and [SetPermissions](setpermissions-method-adox.md) methods.</span></span>

  - <span data-ttu-id="e77c6-112">使用 [Groups](groups-collection-adox.md) 集合访问用户所属的组。</span><span class="sxs-lookup"><span data-stu-id="e77c6-112">Access the groups to which a user belongs with the [Groups](groups-collection-adox.md) collection.</span></span>

  - <span data-ttu-id="e77c6-113">使用 [Properties](properties-collection-ado.md) 集合访问提供程序特定的属性。</span><span class="sxs-lookup"><span data-stu-id="e77c6-113">Access provider-specific properties with the [Properties](properties-collection-ado.md) collection.</span></span>

