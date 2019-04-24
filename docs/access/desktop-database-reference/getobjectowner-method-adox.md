---
title: GetObjectOwner 方法 (ADOX)
TOCTitle: GetObjectOwner method (ADOX)
ms:assetid: 716dd49a-8663-3f7a-32a3-0be353aea506
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249451(v=office.15)
ms:contentKeyID: 48545585
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 948464534f9bbfbea50c8eba2c926dea9cb9bcac
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292256"
---
# <a name="getobjectowner-method-adox"></a>GetObjectOwner 方法 (ADOX)

**适用于**：Access 2013、Office 2013

返回 [Catalog](catalog-object-adox.md) 中某个对象的所有者。

## <a name="syntax"></a>语法

*所有者* = *目录*。GetObjectOwner (*ObjectName*、 *ObjectType* \[、*ObjectTypeId*\])

## <a name="return-value"></a>返回值

返回一个 **String** 值，该值指定拥有该对象的 [User](user-object-adox.md) 或 [Group](group-object-adox.md) 的 [Name](name-property-adox.md)。

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*ObjectName* |**String** 值，指定返回所有者的对象的名称。|
|*ObjectType* |一个可设为某一 **ObjectTypeEnum** 常量的 [Long](objecttypeenum.md) 值，指定获得其所有者的对象的类型。|
|*ObjectTypeId* |可选。**Variant** 值，指定 OLE DB 规范未定义的提供程序对象类型的 GUID。如果 *ObjectType* 设置为 **adPermObjProviderSpecific**，则必须使用此参数；否则不使用它。|

## <a name="remarks"></a>注解

如果提供程序不支持返回对象所有者，则会发生错误。

