---
title: DateModified 属性 (ADOX)
TOCTitle: DateModified property (ADOX)
ms:assetid: aebe8818-82e7-84a4-24d7-d97afa32e193
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249827(v=office.15)
ms:contentKeyID: 48547078
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 447b7c609dd122d825d97a7430349eb88f8f7b0b
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25923950"
---
# <a name="datemodified-property-adox"></a>DateModified 属性 (ADOX)


**适用于**： Access 2013、 Office 2013

指示上次修改对象的日期。

## <a name="return-values"></a>返回值

返回一个指定修改日期的 **Variant** 值。如果提供程序不支持 **DateModified** ，则该值为 null。

## <a name="remarks"></a>说明

对于新追加的对象， **DateModified** 属性为 null。追加新的 [View](view-object-adox.md) 或 [Procedure](procedure-object-adox.md) 之后，必须调用 [Views](refresh-method-ado.md) 或 [Procedures](views-collection-adox.md) 集合的 [Refresh](procedures-collection-adox.md) 方法，以获取 **DateModified** 属性的值。

