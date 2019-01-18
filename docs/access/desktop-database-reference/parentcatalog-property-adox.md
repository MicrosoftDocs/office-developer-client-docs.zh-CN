---
title: ParentCatalog 属性 (ADOX)
TOCTitle: ParentCatalog property (ADOX)
ms:assetid: 7eef4ef5-1fa4-73ea-a710-fc8767c9ea21
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249535(v=office.15)
ms:contentKeyID: 48545891
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d7a10bac3c02a771518038351bc4d0b780c0e774
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28707456"
---
# <a name="parentcatalog-property-adox"></a>ParentCatalog 属性 (ADOX)


**适用于**： Access 2013、 Office 2013

指定表或列的父目录，以提供对特定于提供程序的属性的访问。

## <a name="settings-and-return-values"></a>设置和返回值

设置和返回一个 [Catalog](catalog-object-adox.md) 对象。将 **ParentCatalog** 设置为打开的 **Catalog** 可允许在将表或列追加到 **Catalog** 集合之前访问特定于提供程序的属性。

## <a name="remarks"></a>说明

某些数据提供程序只允许在创建时（将表或列追加到其 **Catalog** 集合时）写入特定于提供程序的属性值。若要在将这些对象追加到 **Catalog** 之前访问这些属性，应先在 **ParentCatalog** 属性中指定 **Catalog** 。

将表或列追加到不同于 **ParentCatalog** 的 **Catalog** 中时，将发生错误。

