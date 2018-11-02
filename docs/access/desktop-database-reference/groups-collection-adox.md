---
title: Groups 集合 (ADOX)
TOCTitle: Groups collection (ADOX)
ms:assetid: 9aec57df-bc5c-f9b3-5aec-e7e7efa47ba8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249702(v=office.15)
ms:contentKeyID: 48546553
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b75f6277695c00c251352e0ae2bdcc44f2c86d34
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25929151"
---
# <a name="groups-collection-adox"></a><span data-ttu-id="d57af-102">Groups 集合 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="d57af-102">Groups collection (ADOX)</span></span>


<span data-ttu-id="d57af-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="d57af-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="d57af-104">包含目录或用户的所有存储的 [Group](group-object-adox.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="d57af-104">Contains all stored [Group](group-object-adox.md) objects of a catalog or user.</span></span>

## <a name="remarks"></a><span data-ttu-id="d57af-105">说明</span><span class="sxs-lookup"><span data-stu-id="d57af-105">Remarks</span></span>

<span data-ttu-id="d57af-p101">**Catalog** 的 [Groups](catalog-object-adox.md) 集合表示该目录的所有组帐户。 **User** 的 [Groups](user-object-adox.md) 集合仅表示该用户所属的组。</span><span class="sxs-lookup"><span data-stu-id="d57af-p101">The **Groups** collection of a [Catalog](catalog-object-adox.md) represents all of the catalog's group accounts. The **Groups** collection for a [User](user-object-adox.md) represents only the group to which the user belongs.</span></span>

<span data-ttu-id="d57af-p102">[Groups](append-method-adox-groups.md) 集合的 **Append** 方法对于 ADOX 来说是唯一的。您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="d57af-p102">The [Append](append-method-adox-groups.md) method for a **Groups** collection is unique for ADOX. You can:</span></span>

  - <span data-ttu-id="d57af-110">使用 **Append** 方法向集合添加新的安全组。</span><span class="sxs-lookup"><span data-stu-id="d57af-110">Add a new security group to the collection with the **Append** method.</span></span>

<span data-ttu-id="d57af-p103">其余属性和方法是 ADO 集合的标准属性和方法。您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="d57af-p103">The remaining properties and methods are standard to ADO collections. You can:</span></span>

  - <span data-ttu-id="d57af-113">使用 [Item](item-property-ado.md) 属性访问集合中的组。</span><span class="sxs-lookup"><span data-stu-id="d57af-113">Access a group in the collection with the [Item](item-property-ado.md) property.</span></span>

  - <span data-ttu-id="d57af-114">使用 [Count](count-property-ado.md) 属性返回集合中包含的组数。</span><span class="sxs-lookup"><span data-stu-id="d57af-114">Return the number of groups contained in the collection with the [Count](count-property-ado.md) property.</span></span>

  - <span data-ttu-id="d57af-115">使用 [Delete](delete-method-adox-collections.md) 方法从集合中删除组。</span><span class="sxs-lookup"><span data-stu-id="d57af-115">Remove a group from the collection with the [Delete](delete-method-adox-collections.md) method.</span></span>

  - <span data-ttu-id="d57af-116">使用 [Refresh](refresh-method-ado.md) 方法更新集合中的对象以反映当前数据库的架构。</span><span class="sxs-lookup"><span data-stu-id="d57af-116">Update the objects in the collection to reflect the current database's schema with the [Refresh](refresh-method-ado.md) method.</span></span>


> [!NOTE]
> <P><span data-ttu-id="d57af-117">[!注释] 在将 <STRONG>Group</STRONG> 对象追加到 <STRONG>User</STRONG> 对象的 <STRONG>Groups</STRONG> 集合之前， <STRONG>Catalog</STRONG> 的 <A href="name-property-adox.md">Groups</A> 集合中必须存在具有与要追加的 <STRONG>Group</STRONG> 对象相同 <STRONG>Name</STRONG> 的 Group 对象。</span><span class="sxs-lookup"><span data-stu-id="d57af-117">Before appending a <STRONG>Group</STRONG> object to the <STRONG>Groups</STRONG> collection of a <STRONG>User</STRONG> object, a <STRONG>Group</STRONG> object with the same <A href="name-property-adox.md">Name</A> as the one to be appended must already exist in the <STRONG>Groups</STRONG> collection of the <STRONG>Catalog</STRONG>.</span></span></P>


