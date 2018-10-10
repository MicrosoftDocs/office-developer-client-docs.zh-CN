---
title: Users 集合 (ADOX)
TOCTitle: Users Collection (ADOX)
ms:assetid: bc61c862-1637-02e7-4b56-5ad984bdbcb0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249905(v=office.15)
ms:contentKeyID: 48547413
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d68dc2dd368523e8ca3dd04a06008cea9bef337e
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465989"
---
# <a name="users-collection-adox"></a>Users 集合 (ADOX)


**适用于**： Access 2013 |Office 2013

包含目录或组的所有存储的 [User](user-object-adox.md) 对象。

## <a name="remarks"></a>说明

**Catalog** 的 [Users](catalog-object-adox.md) 集合表示该目录的所有用户。 **Group** 的 [Users](group-object-adox.md) 集合仅表示在该特定组中有成员资格的用户。

[Users](append-method-adox-users.md) 集合的 **Append** 方法对于 ADOX 来说是唯一的。您可以进行下列操作：

  - 使用 **Append** 方法向集合添加新用户。

其余属性和方法是 ADO 集合的标准属性和方法。您可以进行下列操作：

  - 使用 [Item](item-property-ado.md) 属性访问集合中的用户。

  - 使用 [Count](count-property-ado.md) 属性返回集合中包含的用户数。

  - 使用 [Delete](delete-method-adox-collections.md) 方法从集合中删除用户。

  - 使用 [Refresh](refresh-method-ado.md) 方法更新集合中的对象以反映当前数据库的架构。


> [!NOTE]
> <P>[!注释] 在将 <STRONG>User</STRONG> 对象追加到 <STRONG>Group</STRONG> 对象的 <STRONG>Users</STRONG> 集合之前， <STRONG>Catalog</STRONG> 的 <A href="name-property-adox.md">Users</A> 集合中必须存在具有与要追加的 <STRONG>User</STRONG> 对象相同 <STRONG>Name</STRONG> 的 User 对象。</P>


