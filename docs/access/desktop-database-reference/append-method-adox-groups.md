---
title: Append 方法（ADOX 组）
TOCTitle: Append method (ADOX Groups)
ms:assetid: c3245a24-55b8-3f3f-1c4a-43a119d84dc8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249954(v=office.15)
ms:contentKeyID: 48547567
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9f0e7731777e3d82e3746c3886bdbddb3e43db66
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28709024"
---
# <a name="append-method-adox-groups"></a>Append 方法（ADOX 组）

**适用于**： Access 2013、 Office 2013

将新的 [Group](group-object-adox.md) 对象添加到 [Groups](groups-collection-adox.md) 集合。

## <a name="syntax"></a>语法

*组*。追加*组*

## <a name="parameters"></a>Parameters

|参数|说明|
|:--------|:----------|
|*Group* |要追加的 **Group** 对象，或者要创建并追加的组的名称。|

## <a name="remarks"></a>备注

**Catalog** 的 [Groups](catalog-object-adox.md) 集合表示该目录的所有组帐户。 **User** 的 [Groups](user-object-adox.md) 集合仅表示该用户所属的组。

如果提供程序不支持创建组，则会发生错误。

> [!NOTE]
> [!注释] 在将 **Group** 对象追加到 **User** 对象的 **Groups** 集合之前， **Catalog** 的 [Groups](name-property-adox.md) 集合中必须存在具有与要追加的 **Group** 对象相同 **Name** 的 Group 对象。


