---
title: SetPermissions 方法 (ADOX)
TOCTitle: SetPermissions method (ADOX)
ms:assetid: 63d1053d-fb32-456b-ae67-3a4e45aa01af
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249382(v=office.15)
ms:contentKeyID: 48545274
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4f9b393e90d579c131865b112263efd0aef3216b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314579"
---
# <a name="setpermissions-method-adox"></a>SetPermissions 方法 (ADOX)

**适用于**：Access 2013、Office 2013

指定组或用户对某个对象的权限。

## <a name="syntax"></a>语法

*GroupOrUser*。SetPermissions*Name*、 *ObjectType*、 *Action*、 *Rights* \[、*Inherit* \] \[、*ObjectTypeId*\]

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*Name* |**String** 值，指定设置权限所针对的对象的名称。|
|*ObjectType* |一个类型为 **Long** 的值，可以是 [ObjectTypeEnum](objecttypeenum.md) 常量中的一个，用于指定要为其获取权限的对象的类型。|
|*Action* |一个可设为 **ActionEnum** 常量之一的 [Long](actionenum.md) 值，指定设置权限时要执行的操作的类型。|
|*Rights* |**Long** 值，可以是一个或多个 [RightsEnum](rightsenum.md) 常量的位掩码，该值表示要设置的权限。|
|*Inherit* |可选。一个可设为 **InheritTypeEnum** 常量之一的 [Long](inherittypeenum.md) 值，指定对象如何继承这些权限。默认值为 **adInheritNone** 。|
|*ObjectTypeId* |可选。**Variant** 值，指定 OLE DB 规范未定义的提供程序对象类型的 GUID。如果 *ObjectType* 设置为 **adPermObjProviderSpecific**，则必须使用此参数；否则不使用它。|

## <a name="remarks"></a>注解

如果提供程序不支持为组或用户设置访问权限，则会发生错误。

> [!NOTE]
> 调用 **SetPermissions** 时，将 Actions 设置为 **adAccessRevoke** 会导致忽略 *Rights* 参数的任何设置。如果想让 *Rights* 参数指定的权限生效，请不要将 *Actions* 设置为 **adAccessRevoke**。


