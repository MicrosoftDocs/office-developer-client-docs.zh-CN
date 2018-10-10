---
title: Append 方法 (ADOX Users)
TOCTitle: Append Method (ADOX Users)
ms:assetid: b7a1128b-c6e7-2071-c914-913b6bd245ae
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249884(v=office.15)
ms:contentKeyID: 48547302
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b8bce151e800b58e9c99c6dd6591114c53208a5c
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466325"
---
# <a name="append-method-adox-users"></a>Append 方法 (ADOX Users)


**适用于**： Access 2013 |Office 2013


将新的 [User](user-object-adox.md) 对象添加到 [Users](users-collection-adox.md) 集合。

## <a name="syntax"></a>语法

*用户*。追加*用户*\[，*密码*\]

## <a name="parameters"></a>参数

  - *User*

  - 一个 **Variant** 值，包含对要追加的 **User** 对象的引用，或者是要创建并追加的用户的名称。

  - *Password*

  - 可选。 包含该用户的密码的 **String** 值。 *Password*参数对应于指定的**用户**对象的[ChangePassword](changepassword-method-adox.md)方法的值。

## <a name="remarks"></a>说明

**Catalog** 的 [Users](catalog-object-adox.md) 集合表示该目录的所有用户。 **Group** 的 [Users](group-object-adox.md) 集合仅表示在该特定组中有成员资格的用户。

如果提供程序不支持创建用户，则会发生错误。


> [!NOTE]
> <P>[!注释] 在将 <STRONG>User</STRONG> 对象追加到 <STRONG>Group</STRONG> 对象的 <STRONG>Users</STRONG> 集合之前， <STRONG>Catalog</STRONG> 的 <A href="name-property-adox.md">Users</A> 集合中必须存在具有与要追加的 <STRONG>User</STRONG> 对象相同 <STRONG>Name</STRONG> 的 User 对象。</P>


