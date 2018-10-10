---
title: Groups 集合 (ADOX)
TOCTitle: Groups Collection (ADOX)
ms:assetid: 9aec57df-bc5c-f9b3-5aec-e7e7efa47ba8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249702(v=office.15)
ms:contentKeyID: 48546553
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6e7021d6dc485d4c0cfbeca4b9fe487817de715f
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467526"
---
# <a name="groups-collection-adox"></a>Groups 集合 (ADOX)


**适用于**： Access 2013 |Office 2013

包含目录或用户的所有存储的 [Group](group-object-adox.md) 对象。

## <a name="remarks"></a>说明

**Catalog** 的 [Groups](catalog-object-adox.md) 集合表示该目录的所有组帐户。 **User** 的 [Groups](user-object-adox.md) 集合仅表示该用户所属的组。

[Groups](append-method-adox-groups.md) 集合的 **Append** 方法对于 ADOX 来说是唯一的。您可以进行下列操作：

  - 使用 **Append** 方法向集合添加新的安全组。

其余属性和方法是 ADO 集合的标准属性和方法。您可以进行下列操作：

  - 使用 [Item](item-property-ado.md) 属性访问集合中的组。

  - 使用 [Count](count-property-ado.md) 属性返回集合中包含的组数。

  - 使用 [Delete](delete-method-adox-collections.md) 方法从集合中删除组。

  - 使用 [Refresh](refresh-method-ado.md) 方法更新集合中的对象以反映当前数据库的架构。


> [!NOTE]
> <P>[!注释] 在将 <STRONG>Group</STRONG> 对象追加到 <STRONG>User</STRONG> 对象的 <STRONG>Groups</STRONG> 集合之前， <STRONG>Catalog</STRONG> 的 <A href="name-property-adox.md">Groups</A> 集合中必须存在具有与要追加的 <STRONG>Group</STRONG> 对象相同 <STRONG>Name</STRONG> 的 Group 对象。</P>


