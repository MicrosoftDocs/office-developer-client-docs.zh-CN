---
title: Key 对象 (ADOX-访问桌面数据库引用)
TOCTitle: Key object (ADOX)
ms:assetid: 727198ec-57d2-7766-790c-370beb931de6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249461(v=office.15)
ms:contentKeyID: 48545608
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 11bd05c4959ba1f3e1819e482ce311fc798bf0e6
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25929830"
---
# <a name="key-object-adox"></a><span data-ttu-id="1b7ec-102">Key 对象 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="1b7ec-102">Key object (ADOX)</span></span>


<span data-ttu-id="1b7ec-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="1b7ec-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="1b7ec-104">表示数据库表中的主键、外键或唯一键字段。</span><span class="sxs-lookup"><span data-stu-id="1b7ec-104">Represents a primary, foreign, or unique key field from a database table.</span></span>

## <a name="remarks"></a><span data-ttu-id="1b7ec-105">说明</span><span class="sxs-lookup"><span data-stu-id="1b7ec-105">Remarks</span></span>

<span data-ttu-id="1b7ec-106">以下代码创建一个新的 **Key** ：</span><span class="sxs-lookup"><span data-stu-id="1b7ec-106">The following code creates a new **Key**:</span></span>

`Dim obj As New Key`

<span data-ttu-id="1b7ec-107">使用 **Key** 对象的属性和集合，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1b7ec-107">With the properties and collections of a **Key** object, you can:</span></span>

- <span data-ttu-id="1b7ec-108">使用 [Name](name-property-adox.md) 属性标识键。</span><span class="sxs-lookup"><span data-stu-id="1b7ec-108">Identify the key with the [Name](name-property-adox.md) property.</span></span>

- <span data-ttu-id="1b7ec-109">使用 [Type](https://msdn.microsoft.com/library/jj248879\(v=office.15\)) 属性确定键是主键、外键还是唯一键。</span><span class="sxs-lookup"><span data-stu-id="1b7ec-109">Determine whether the key is primary, foreign, or unique with the [Type](https://msdn.microsoft.com/library/jj248879\(v=office.15\)) property.</span></span>

- <span data-ttu-id="1b7ec-110">使用 [Columns](columns-collection-adox.md) 集合访问键的数据库列。</span><span class="sxs-lookup"><span data-stu-id="1b7ec-110">Access the database columns of the key with the [Columns](columns-collection-adox.md) collection.</span></span>

- <span data-ttu-id="1b7ec-111">使用 [RelatedTable](relatedtable-property-adox.md) 属性指定相关表的名称。</span><span class="sxs-lookup"><span data-stu-id="1b7ec-111">Specify the name of the related table with the [RelatedTable](relatedtable-property-adox.md) property.</span></span>

- <span data-ttu-id="1b7ec-112">使用 [DeleteRule](deleterule-property-adox.md) 和 [UpdateRule](updaterule-property-adox.md) 属性确定在删除或更新主键时执行的操作。</span><span class="sxs-lookup"><span data-stu-id="1b7ec-112">Determine the action performed on deletion or update of a primary key with the [DeleteRule](deleterule-property-adox.md) and [UpdateRule](updaterule-property-adox.md) properties.</span></span>

