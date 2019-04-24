---
title: User 对象 (ADOX-Access 桌面数据库参考)
TOCTitle: User object (ADOX)
ms:assetid: e88b9a8a-e70f-c7ca-cb8c-bd274ff24948
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250178(v=office.15)
ms:contentKeyID: 48548426
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 3299a6c0742e7fcbbd26532f3522fdc96b7956b2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32313158"
---
# <a name="user-object-adox"></a><span data-ttu-id="bfdf1-102">User 对象 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="bfdf1-102">User object (ADOX)</span></span>


<span data-ttu-id="bfdf1-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="bfdf1-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="bfdf1-104">代表在受保护的数据库中有访问权限的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="bfdf1-104">Represents a user account that has access permissions within a secured database.</span></span>

## <a name="remarks"></a><span data-ttu-id="bfdf1-105">注解</span><span class="sxs-lookup"><span data-stu-id="bfdf1-105">Remarks</span></span>

<span data-ttu-id="bfdf1-p101">[Catalog](catalog-object-adox.md) 的 [Users](users-collection-adox.md) 集合表示该目录的所有用户。[Group](group-object-adox.md) 的 **Users** 集合仅表示特定组的用户。</span><span class="sxs-lookup"><span data-stu-id="bfdf1-p101">The [Users](users-collection-adox.md) collection of a [Catalog](catalog-object-adox.md) represents all the catalog's users. The **Users** collection for a [Group](group-object-adox.md) represents only the users of the specific group.</span></span>

<span data-ttu-id="bfdf1-108">使用 **User** 对象的属性、集合和方法，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="bfdf1-108">With the properties, collections, and methods of a **User** object, you can:</span></span>

  - <span data-ttu-id="bfdf1-109">使用 [Name](name-property-adox.md) 属性标识用户。</span><span class="sxs-lookup"><span data-stu-id="bfdf1-109">Identify the user with the [Name](name-property-adox.md) property.</span></span>

  - <span data-ttu-id="bfdf1-110">使用 [ChangePassword](changepassword-method-adox.md) 方法更改用户的密码。</span><span class="sxs-lookup"><span data-stu-id="bfdf1-110">Change the password for a user with the [ChangePassword](changepassword-method-adox.md) method.</span></span>

  - <span data-ttu-id="bfdf1-111">使用 [GetPermissions](getpermissions-method-adox.md) 和 [SetPermissions](setpermissions-method-adox.md) 方法确定用户是否具有读取、写入或删除权限。</span><span class="sxs-lookup"><span data-stu-id="bfdf1-111">Determine whether a user has read, write, or delete permissions with the [GetPermissions](getpermissions-method-adox.md) and [SetPermissions](setpermissions-method-adox.md) methods.</span></span>

  - <span data-ttu-id="bfdf1-112">使用 [Groups](groups-collection-adox.md) 集合访问用户所属的组。</span><span class="sxs-lookup"><span data-stu-id="bfdf1-112">Access the groups to which a user belongs with the [Groups](groups-collection-adox.md) collection.</span></span>

  - <span data-ttu-id="bfdf1-113">使用 [Properties](properties-collection-ado.md) 集合访问提供程序特定的属性。</span><span class="sxs-lookup"><span data-stu-id="bfdf1-113">Access provider-specific properties with the [Properties](properties-collection-ado.md) collection.</span></span>

