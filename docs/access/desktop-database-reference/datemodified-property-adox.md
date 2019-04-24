---
title: DateModified 属性 (ADOX)
TOCTitle: DateModified property (ADOX)
ms:assetid: aebe8818-82e7-84a4-24d7-d97afa32e193
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249827(v=office.15)
ms:contentKeyID: 48547078
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: daf72804d51c18b5875e607ce5fdb0dfe20f406c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294405"
---
# <a name="datemodified-property-adox"></a>DateModified 属性 (ADOX)


**适用于**：Access 2013、Office 2013

指示上次修改对象的日期。

## <a name="return-values"></a>返回值

返回一个指定修改日期的 **Variant** 值。 如果提供程序不支持 **DateModified**，则该值为 null。

## <a name="remarks"></a>注解

对于新追加的对象，**DateModified** 属性为 null。追加新的 [View](view-object-adox.md) 或 [Procedure](procedure-object-adox.md) 之后，必须调用 [Views](views-collection-adox.md) 或 [Procedures](procedures-collection-adox.md) 集合的 [Refresh](refresh-method-ado.md) 方法，以获取 **DateModified** 属性的值。

