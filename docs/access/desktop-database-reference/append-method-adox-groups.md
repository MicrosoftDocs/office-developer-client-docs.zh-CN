---
title: Append 方法 (ADOX Groups)
TOCTitle: Append Method (ADOX Groups)
ms:assetid: c3245a24-55b8-3f3f-1c4a-43a119d84dc8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249954(v=office.15)
ms:contentKeyID: 48547567
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 76c602896a629881d06a3f3cf80326e02340186e
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468572"
---
# <a name="append-method-adox-groups"></a>Append 方法 (ADOX Groups)


**适用于**： Access 2013 |Office 2013



将新的 [Group](group-object-adox.md) 对象添加到 [Groups](groups-collection-adox.md) 集合。

## <a name="syntax"></a>语法

*组*。追加*组*

## <a name="parameters"></a>参数

  - *Group*

  - 要追加的 **Group** 对象，或者要创建并追加的组的名称。

## <a name="remarks"></a>备注

**Catalog** 的 [Groups](catalog-object-adox.md) 集合表示该目录的所有组帐户。 **User** 的 [Groups](user-object-adox.md) 集合仅表示该用户所属的组。

如果提供程序不支持创建组，则会发生错误。


> [!NOTE]
> <P>[!注释] 在将 <STRONG>Group</STRONG> 对象追加到 <STRONG>User</STRONG> 对象的 <STRONG>Groups</STRONG> 集合之前， <STRONG>Catalog</STRONG> 的 <A href="name-property-adox.md">Groups</A> 集合中必须存在具有与要追加的 <STRONG>Group</STRONG> 对象相同 <STRONG>Name</STRONG> 的 Group 对象。</P>


