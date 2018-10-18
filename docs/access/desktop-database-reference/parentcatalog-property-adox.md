---
title: ParentCatalog 属性 (ADOX)
TOCTitle: ParentCatalog Property (ADOX)
ms:assetid: 7eef4ef5-1fa4-73ea-a710-fc8767c9ea21
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249535(v=office.15)
ms:contentKeyID: 48545891
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d9fdd4b41578b4f185d199a47204faabd0af3ff8
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25603411"
---
# <a name="parentcatalog-property-adox"></a>ParentCatalog 属性 (ADOX)


**适用于**： Access 2013 |Office 2013

指定表或列的父目录，以提供对特定于提供程序的属性的访问。

<<<<<<< 标头
## <a name="settings-and-return-values"></a>设置和返回值
=======
## <a name="settings-and-return-values"></a>设置和返回值
>>>>>>> master

设置和返回一个 [Catalog](catalog-object-adox.md) 对象。将 **ParentCatalog** 设置为打开的 **Catalog** 可允许在将表或列追加到 **Catalog** 集合之前访问特定于提供程序的属性。

## <a name="remarks"></a>说明

某些数据提供程序只允许在创建时（将表或列追加到其 **Catalog** 集合时）写入特定于提供程序的属性值。若要在将这些对象追加到 **Catalog** 之前访问这些属性，应先在 **ParentCatalog** 属性中指定 **Catalog** 。

将表或列追加到不同于 **ParentCatalog** 的 **Catalog** 中时，将发生错误。

