---
title: GetObjectOwner 方法 (ADOX)
TOCTitle: GetObjectOwner method (ADOX)
ms:assetid: 716dd49a-8663-3f7a-32a3-0be353aea506
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249451(v=office.15)
ms:contentKeyID: 48545585
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b1a37b0f341c849358b649c2222df2955fd88f5d
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25927808"
---
# <a name="getobjectowner-method-adox"></a>GetObjectOwner 方法 (ADOX)


**适用于**： Access 2013、 Office 2013


返回 [Catalog](catalog-object-adox.md) 中某个对象的所有者。

## <a name="syntax"></a>语法

*所有者* = *目录*。GetObjectOwner (*ObjectName*、 *ObjectType* \[，*ObjectTypeId*\])

## <a name="return-value"></a>返回值

返回一个 **String** 值，该值指定拥有该对象的 [User](name-property-adox.md) 或 [Group](user-object-adox.md) 的 [Name](group-object-adox.md)。

## <a name="parameters"></a>参数

  - *ObjectName*

  - **String** 值，指定返回所有者的对象的名称。

  - *ObjectType*

  - 一个可设为某一 **ObjectTypeEnum** 常量的 [Long](objecttypeenum.md) 值，指定获得其所有者的对象的类型。

  - *ObjectTypeId*

  - 可选。 **Variant** 值，指定 OLE DB 规范未定义的提供程序对象类型的 GUID。 此参数是必需的如果将*ObjectType*设置为**adPermObjProviderSpecific**;否则，它将不使用。

## <a name="remarks"></a>备注

如果提供程序不支持返回对象所有者，则会发生错误。

