---
title: Key 对象 (ADOX-Access 桌面数据库参考)
TOCTitle: Key object (ADOX)
ms:assetid: 727198ec-57d2-7766-790c-370beb931de6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249461(v=office.15)
ms:contentKeyID: 48545608
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: f56a90b7accd1b64c9a52e0a7cf5385f83fd10d5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290750"
---
# <a name="key-object-adox"></a><span data-ttu-id="e6bb4-102">Key 对象 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="e6bb4-102">Key object (ADOX)</span></span>


<span data-ttu-id="e6bb4-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="e6bb4-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e6bb4-104">表示数据库表中的主键、外键或唯一键字段。</span><span class="sxs-lookup"><span data-stu-id="e6bb4-104">Represents a primary, foreign, or unique key field from a database table.</span></span>

## <a name="remarks"></a><span data-ttu-id="e6bb4-105">注解</span><span class="sxs-lookup"><span data-stu-id="e6bb4-105">Remarks</span></span>

<span data-ttu-id="e6bb4-106">以下代码创建一个新的 **Key**：</span><span class="sxs-lookup"><span data-stu-id="e6bb4-106">The following code creates a new **Key**:</span></span>

`Dim obj As New Key`

<span data-ttu-id="e6bb4-107">使用 **Key** 对象的属性和集合，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e6bb4-107">With the properties and collections of a **Key** object, you can:</span></span>

- <span data-ttu-id="e6bb4-108">使用 [Name](name-property-adox.md) 属性标识键。</span><span class="sxs-lookup"><span data-stu-id="e6bb4-108">Identify the key with the [Name](name-property-adox.md) property.</span></span>

- <span data-ttu-id="e6bb4-109">使用 [Type](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/type-property-keyadox) 属性确定键是主键、外键还是唯一键。</span><span class="sxs-lookup"><span data-stu-id="e6bb4-109">Determine whether the key is primary, foreign, or unique with the [Type](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/type-property-keyadox) property.</span></span>

- <span data-ttu-id="e6bb4-110">使用 [Columns](columns-collection-adox.md) 集合访问键的数据库列。</span><span class="sxs-lookup"><span data-stu-id="e6bb4-110">Access the database columns of the key with the [Columns](columns-collection-adox.md) collection.</span></span>

- <span data-ttu-id="e6bb4-111">使用 [RelatedTable](relatedtable-property-adox.md) 属性指定相关表的名称。</span><span class="sxs-lookup"><span data-stu-id="e6bb4-111">Specify the name of the related table with the [RelatedTable](relatedtable-property-adox.md) property.</span></span>

- <span data-ttu-id="e6bb4-112">使用 [DeleteRule](deleterule-property-adox.md) 和 [UpdateRule](updaterule-property-adox.md) 属性确定在删除或更新主键时执行的操作。</span><span class="sxs-lookup"><span data-stu-id="e6bb4-112">Determine the action performed on deletion or update of a primary key with the [DeleteRule](deleterule-property-adox.md) and [UpdateRule](updaterule-property-adox.md) properties.</span></span>

