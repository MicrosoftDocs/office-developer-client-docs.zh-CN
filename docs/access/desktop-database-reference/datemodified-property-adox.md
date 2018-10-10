---
title: DateModified 属性 (ADOX)
TOCTitle: DateModified Property (ADOX)
ms:assetid: aebe8818-82e7-84a4-24d7-d97afa32e193
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249827(v=office.15)
ms:contentKeyID: 48547078
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 8465f97565d8519196b8221089121670ceedb275
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465858"
---
# <a name="datemodified-property-adox"></a>DateModified 属性 (ADOX)


**适用于**： Access 2013 |Office 2013

指示上次修改对象的日期。

## <a name="return-values"></a>返回值

返回一个指定修改日期的 **Variant** 值。如果提供程序不支持 **DateModified** ，则该值为 null。

## <a name="remarks"></a>说明

对于新追加的对象， **DateModified** 属性为 null。追加新的 [View](view-object-adox.md) 或 [Procedure](procedure-object-adox.md) 之后，必须调用 [Views](refresh-method-ado.md) 或 [Procedures](views-collection-adox.md) 集合的 [Refresh](procedures-collection-adox.md) 方法，以获取 **DateModified** 属性的值。

