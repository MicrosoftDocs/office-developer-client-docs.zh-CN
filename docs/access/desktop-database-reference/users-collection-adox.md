---
title: Users 集合 (ADOX)
TOCTitle: Users collection (ADOX)
ms:assetid: bc61c862-1637-02e7-4b56-5ad984bdbcb0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249905(v=office.15)
ms:contentKeyID: 48547413
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 24d7a5cab3260dac80b39e5134938c5f55175851
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28720406"
---
# <a name="users-collection-adox"></a><span data-ttu-id="dca03-102">Users 集合 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="dca03-102">Users collection (ADOX)</span></span>

<span data-ttu-id="dca03-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="dca03-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="dca03-104">包含目录或组的所有存储的 [User](user-object-adox.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="dca03-104">Contains all stored [User](user-object-adox.md) objects of a catalog or group.</span></span>

## <a name="remarks"></a><span data-ttu-id="dca03-105">说明</span><span class="sxs-lookup"><span data-stu-id="dca03-105">Remarks</span></span>

<span data-ttu-id="dca03-p101">**Catalog** 的 [Users](catalog-object-adox.md) 集合表示该目录的所有用户。 **Group** 的 [Users](group-object-adox.md) 集合仅表示在该特定组中有成员资格的用户。</span><span class="sxs-lookup"><span data-stu-id="dca03-p101">The **Users** collection of a [Catalog](catalog-object-adox.md) represents all the catalog's users. The **Users** collection for a [Group](group-object-adox.md) represents only the users that have a membership in the specific group.</span></span>

<span data-ttu-id="dca03-p102">[Users](append-method-adox-users.md) 集合的 **Append** 方法对于 ADOX 来说是唯一的。您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="dca03-p102">The [Append](append-method-adox-users.md) method for a **Users** collection is unique for ADOX. You can:</span></span>

- <span data-ttu-id="dca03-110">使用 **Append** 方法向集合添加新用户。</span><span class="sxs-lookup"><span data-stu-id="dca03-110">Add a new user to the collection with the **Append** method.</span></span>

<span data-ttu-id="dca03-p103">其余属性和方法是 ADO 集合的标准属性和方法。您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="dca03-p103">The remaining properties and methods are standard to ADO collections. You can:</span></span>

- <span data-ttu-id="dca03-113">使用 [Item](item-property-ado.md) 属性访问集合中的用户。</span><span class="sxs-lookup"><span data-stu-id="dca03-113">Access a user in the collection with the [Item](item-property-ado.md) property.</span></span>

- <span data-ttu-id="dca03-114">使用 [Count](count-property-ado.md) 属性返回集合中包含的用户数。</span><span class="sxs-lookup"><span data-stu-id="dca03-114">Return the number of users contained in the collection with the [Count](count-property-ado.md) property.</span></span>

- <span data-ttu-id="dca03-115">使用 [Delete](delete-method-adox-collections.md) 方法从集合中删除用户。</span><span class="sxs-lookup"><span data-stu-id="dca03-115">Remove a user from the collection with the [Delete](delete-method-adox-collections.md) method.</span></span>

- <span data-ttu-id="dca03-116">使用 [Refresh](refresh-method-ado.md) 方法更新集合中的对象以反映当前数据库的架构。</span><span class="sxs-lookup"><span data-stu-id="dca03-116">Update the objects in the collection to reflect the current database's schema with the [Refresh](refresh-method-ado.md) method.</span></span>

> [!NOTE]
> <span data-ttu-id="dca03-117">[!注释] 在将 **User** 对象追加到 **Group** 对象的 **Users** 集合之前， **Catalog** 的 [Users](name-property-adox.md) 集合中必须存在具有与要追加的 **User** 对象相同 **Name** 的 User 对象。</span><span class="sxs-lookup"><span data-stu-id="dca03-117">Before appending a **User** object to the **Users** collection of a **Group** object, a **User** object with the same [Name](name-property-adox.md) as the one to be appended must already exist in the **Users** collection of the **Catalog**.</span></span>

