---
title: Groups 集合 (ADOX)
TOCTitle: Groups collection (ADOX)
ms:assetid: 9aec57df-bc5c-f9b3-5aec-e7e7efa47ba8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249702(v=office.15)
ms:contentKeyID: 48546553
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 21f1880a9effca6e51bc1e8b52a58dce22ce1ea9
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28712517"
---
# <a name="groups-collection-adox"></a><span data-ttu-id="13d1c-102">Groups 集合 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="13d1c-102">Groups collection (ADOX)</span></span>

<span data-ttu-id="13d1c-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="13d1c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="13d1c-104">包含目录或用户的所有存储的 [Group](group-object-adox.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="13d1c-104">Contains all stored [Group](group-object-adox.md) objects of a catalog or user.</span></span>

## <a name="remarks"></a><span data-ttu-id="13d1c-105">说明</span><span class="sxs-lookup"><span data-stu-id="13d1c-105">Remarks</span></span>

<span data-ttu-id="13d1c-p101">**Catalog** 的 [Groups](catalog-object-adox.md) 集合表示该目录的所有组帐户。 **User** 的 [Groups](user-object-adox.md) 集合仅表示该用户所属的组。</span><span class="sxs-lookup"><span data-stu-id="13d1c-p101">The **Groups** collection of a [Catalog](catalog-object-adox.md) represents all of the catalog's group accounts. The **Groups** collection for a [User](user-object-adox.md) represents only the group to which the user belongs.</span></span>

<span data-ttu-id="13d1c-p102">[Groups](append-method-adox-groups.md) 集合的 **Append** 方法对于 ADOX 来说是唯一的。您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="13d1c-p102">The [Append](append-method-adox-groups.md) method for a **Groups** collection is unique for ADOX. You can:</span></span>

- <span data-ttu-id="13d1c-110">使用 **Append** 方法向集合添加新的安全组。</span><span class="sxs-lookup"><span data-stu-id="13d1c-110">Add a new security group to the collection with the **Append** method.</span></span>

<span data-ttu-id="13d1c-p103">其余属性和方法是 ADO 集合的标准属性和方法。您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="13d1c-p103">The remaining properties and methods are standard to ADO collections. You can:</span></span>

- <span data-ttu-id="13d1c-113">使用 [Item](item-property-ado.md) 属性访问集合中的组。</span><span class="sxs-lookup"><span data-stu-id="13d1c-113">Access a group in the collection with the [Item](item-property-ado.md) property.</span></span>

- <span data-ttu-id="13d1c-114">使用 [Count](count-property-ado.md) 属性返回集合中包含的组数。</span><span class="sxs-lookup"><span data-stu-id="13d1c-114">Return the number of groups contained in the collection with the [Count](count-property-ado.md) property.</span></span>

- <span data-ttu-id="13d1c-115">使用 [Delete](delete-method-adox-collections.md) 方法从集合中删除组。</span><span class="sxs-lookup"><span data-stu-id="13d1c-115">Remove a group from the collection with the [Delete](delete-method-adox-collections.md) method.</span></span>

- <span data-ttu-id="13d1c-116">使用 [Refresh](refresh-method-ado.md) 方法更新集合中的对象以反映当前数据库的架构。</span><span class="sxs-lookup"><span data-stu-id="13d1c-116">Update the objects in the collection to reflect the current database's schema with the [Refresh](refresh-method-ado.md) method.</span></span>

> [!NOTE]
> <span data-ttu-id="13d1c-117">[!注释] 在将 **Group** 对象追加到 **User** 对象的 **Groups** 集合之前， **Catalog** 的 [Groups](name-property-adox.md) 集合中必须存在具有与要追加的 **Group** 对象相同 **Name** 的 Group 对象。</span><span class="sxs-lookup"><span data-stu-id="13d1c-117">Before appending a **Group** object to the **Groups** collection of a **User** object, a **Group** object with the same [Name](name-property-adox.md) as the one to be appended must already exist in the **Groups** collection of the **Catalog**.</span></span>


