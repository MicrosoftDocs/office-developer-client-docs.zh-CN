---
title: Key 对象 (ADOX-访问桌面数据库引用)
TOCTitle: Key object (ADOX)
ms:assetid: 727198ec-57d2-7766-790c-370beb931de6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249461(v=office.15)
ms:contentKeyID: 48545608
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7722130c76516eaa7dcaf0598a5e1c040e21ba25
ms.sourcegitcommit: 45feafb3b55de0402dddf5548c0c1c43a0eabafd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26025943"
---
# <a name="key-object-adox"></a><span data-ttu-id="15b24-102">Key 对象 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="15b24-102">Key object (ADOX)</span></span>


<span data-ttu-id="15b24-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="15b24-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="15b24-104">表示数据库表中的主键、外键或唯一键字段。</span><span class="sxs-lookup"><span data-stu-id="15b24-104">Represents a primary, foreign, or unique key field from a database table.</span></span>

## <a name="remarks"></a><span data-ttu-id="15b24-105">说明</span><span class="sxs-lookup"><span data-stu-id="15b24-105">Remarks</span></span>

<span data-ttu-id="15b24-106">以下代码创建一个新的 **Key** ：</span><span class="sxs-lookup"><span data-stu-id="15b24-106">The following code creates a new **Key**:</span></span>

`Dim obj As New Key`

<span data-ttu-id="15b24-107">使用 **Key** 对象的属性和集合，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="15b24-107">With the properties and collections of a **Key** object, you can:</span></span>

- <span data-ttu-id="15b24-108">使用 [Name](name-property-adox.md) 属性标识键。</span><span class="sxs-lookup"><span data-stu-id="15b24-108">Identify the key with the [Name](name-property-adox.md) property.</span></span>

- <span data-ttu-id="15b24-109">使用 [Type](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/type-property-keyadox) 属性确定键是主键、外键还是唯一键。</span><span class="sxs-lookup"><span data-stu-id="15b24-109">Determine whether the key is primary, foreign, or unique with the [Type](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/type-property-keyadox) property.</span></span>

- <span data-ttu-id="15b24-110">使用 [Columns](columns-collection-adox.md) 集合访问键的数据库列。</span><span class="sxs-lookup"><span data-stu-id="15b24-110">Access the database columns of the key with the [Columns](columns-collection-adox.md) collection.</span></span>

- <span data-ttu-id="15b24-111">使用 [RelatedTable](relatedtable-property-adox.md) 属性指定相关表的名称。</span><span class="sxs-lookup"><span data-stu-id="15b24-111">Specify the name of the related table with the [RelatedTable](relatedtable-property-adox.md) property.</span></span>

- <span data-ttu-id="15b24-112">使用 [DeleteRule](deleterule-property-adox.md) 和 [UpdateRule](updaterule-property-adox.md) 属性确定在删除或更新主键时执行的操作。</span><span class="sxs-lookup"><span data-stu-id="15b24-112">Determine the action performed on deletion or update of a primary key with the [DeleteRule](deleterule-property-adox.md) and [UpdateRule](updaterule-property-adox.md) properties.</span></span>

