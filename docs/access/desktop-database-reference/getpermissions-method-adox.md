---
title: GetPermissions 方法 (ADOX)
TOCTitle: GetPermissions Method (ADOX)
ms:assetid: 98a2b2b6-a8af-15ee-b052-622a6f0661b9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249683(v=office.15)
ms:contentKeyID: 48546496
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f53298d56f09b3df94c1b9e20158b3549317af6b
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25886534"
---
# <a name="getpermissions-method-adox"></a>GetPermissions 方法 (ADOX)


**适用于**： Access 2013、 Office 2013


返回组或用户对某个对象或对象容器的权限。

## <a name="syntax"></a>语法

*ReturnValue* = *GroupOrUser*。GetPermissions (*名称*、 *ObjectType* \[，*ObjectTypeId*\])

## <a name="return-value"></a>返回值

返回一个指定位掩码的 **Long** 值，该位掩码包含组或用户对该对象所拥有的权限。此值可为一个或多个 [RightsEnum](rightsenum.md) 常量。

## <a name="parameters"></a>参数

  - *Name*

  - **Variant** 值，指定设置权限所针对的对象的名称。 如果您想要获取的对象容器的权限，请将*名称*设置为 null 值。

  - *ObjectType*

  - 一个类型为 **Long** 的值，可以是 [ObjectTypeEnum](objecttypeenum.md) 常量中的一个，用于指定要为其获取权限的对象的类型。

  - *ObjectTypeId*

  - 可选。 **Variant** 值，指定 OLE DB 规范未定义的提供程序对象类型的 GUID。 此参数是必需的如果将*ObjectType*设置为**adPermObjProviderSpecific**;否则，它将不使用。

